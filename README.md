# python-email-validator-disposable-checker

Validate email syntax, verify active DNS MX mail servers, block 10,000+ disposable/throwaway email domains, and catch domain typos (`gmial.com` -> `gmail.com`) in real time.

🔗 **Get your free API key:** [Email & Lead Hygiene API on RapidAPI](https://rapidapi.com/medhakamath/api/email-lead-hygiene) *(100 free requests/month)*

## Features
- **Syntax Validation:** Checks standard email address formatting.
- **Live DNS MX Lookup:** Confirms whether the domain actually accepts incoming mail.
- **10,000+ Disposable Blocklist:** Detects Mailinator, 10MinuteMail, Yopmail, and temporary inbox providers.
- **Typo Detection:** Suggests fixes for common spelling mistakes (`did_you_mean`).
- **Deliverability Score:** Returns a simple `0–100` quality score for signup forms and CRM cleaning.

## Quick Start (Python)

```python
import requests

url = "https://YOUR_RAPIDAPI_HOST/v1/verify"
querystring = {"email": "rahul@gmial.com"}

headers = {
"x-rapidapi-key": "YOUR_RAPIDAPI_KEY",
"x-rapidapi-host": "YOUR_RAPIDAPI_HOST"
}

response = requests.get(url, headers=headers, params=querystring)
print(response.json())
```

## Sample Response

```json
{
"email": "rahul@gmial.com",
"is_valid_syntax": true,
"has_mx_records": true,
"is_disposable": false,
"is_free_provider": false,
"is_role_based": false,
"did_you_mean": "rahul@gmail.com",
"quality_score": 60,
"status": "typo_suspected"
}
```
