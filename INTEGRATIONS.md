# Apple Health and Garmin integration research notes

## Apple Health / HealthKit
- Apple Health data is exposed to apps through HealthKit APIs, which are designed for native Apple-platform apps and require entitlements, permission prompts, and a compatible app implementation.
- A plain Safari PWA does not have the same direct HealthKit access as a native iOS app. This prototype therefore uses manual entry for steps, sleep, weight, and mood.
- Practical future paths:
  1. Keep the PWA and allow manual entry or imports from a supported service.
  2. Build a small native iOS companion (for example with Swift/HealthKit) that reads only the data the user explicitly authorizes and sends selected values to a secure backend used by the PWA.
- Do not promise automatic Apple Health syncing until a real integration has been implemented and tested on an iPhone.

Official starting point: https://developer.apple.com/documentation/healthkit

## Garmin Connect
- Garmin integrations are not simply a browser permission. Garmin offers developer programs/APIs with eligibility, registration, and terms; access depends on the specific product and approval.
- The Garmin Health API is intended for approved business integrations and can provide wellness/activity data from Garmin devices to a service after authorization. Review Garmin's current program and requirements before committing to features.
- Practical future paths:
  1. Request access to the Garmin Health API / relevant Garmin developer program.
  2. Use an established sync platform only after checking its current capabilities, cost, data coverage, privacy policy, and terms.
  3. Keep manual logging as the reliable fallback.
- Never collect Garmin passwords or scrape a user's Garmin account.

Official starting points:
- Garmin Health: https://developer.garmin.com/gc-developer-program/health-api/
- Garmin developer portal: https://developer.garmin.com/

## Privacy checklist before real launch
- Add a privacy policy and clear consent screens.
- Collect only the fields needed.
- Provide data export and deletion.
- Encrypt traffic (HTTPS) and protect any server-stored records.
- Never store API secrets in browser JavaScript; use a backend for tokens and integrations.
- Treat weight, sleep, mood, and faith-journal entries as sensitive personal data.
