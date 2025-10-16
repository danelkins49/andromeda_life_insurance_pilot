# Setup — Pixel, Dataset, CAPI, Zapier

## Objective
Clean, client-specific data flow: Perspective → Zapier → Meta CAPI. No “super pixel.” Optimize for **Lead**.

## Events (pilot)
- ✅ `ViewContent` — quiz LP view  
- ✅ `Lead` — quiz completion / form submit *(optimize for this)*  
- ✅ `Schedule` — booked call (secondary)

## Steps
1. **Pixel & Dataset**
   - Create Pixel in Events Manager
   - Create/attach Dataset
   - Generate System User + Access Token (if using BM-level token)

2. **Perspective → Zapier**
   - Trigger: Perspective form submit (quiz complete)
   - Action: **Webhooks by Zapier (POST)** to Meta CAPI
   - Payload (example):
   ```json
   {
     "event_name": "Lead",
     "event_time": {{zap_meta_timestamp}},
     "event_source_url": "{{quiz_result_url}}",
     "action_source": "website",
     "user_data": {
       "em": "{{contact_email}}",
       "ph": "{{contact_phone}}",
       "fn": "{{first_name}}",
       "ln": "{{last_name}}",
       "client_user_agent": "{{user_agent}}",
       "fbc": "{{fbclid}}",
       "fbp": "{{fbp}}"
     }
   }

   
Headers:

Authorization: Bearer <ACCESS_TOKEN>

Content-Type: application/json

Pixel ID in URL: https://graph.facebook.com/v19.0/<PIXEL_ID>/events

Add ViewContent & Schedule

Create two more Zap steps or branching rules with the same structure

Ensure distinct event_name values

Verification

Use Test Events in Events Manager (paste test_event_code in payload)

Confirm dedup & match rate warnings in Diagnostics

Decision Notes

We avoided CompleteRegistration to keep the conversion signal unambiguous.

Lead chosen as the single source of truth for optimization.

TODO (tick these as you go)

 Pixel + Dataset created

 Access token stored securely

 Lead webhook firing green in Test Events

 ViewContent firing on LP view

 Schedule firing on booking

 Screenshot evidence added to _assets/screenshots/