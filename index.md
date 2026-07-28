---
title: SocialTree Privacy Policy
description: How SocialTree handles your data — on-device storage, opt-in AI, and the controls you have.
---

# SocialTree Privacy Policy

_Last updated: 2026-07-27_

SocialTree is a personal social memory assistant for iOS, operated as a personal project by **Praneel Bhatia**. This policy explains what data the app handles, when (and why) any of it leaves your device, and the controls available to you.

## Where your data lives

Your full SocialTree graph — the people you add, notes, voice memos, photos, and circles — is stored **locally on your iPhone** using Apple SwiftData. SocialTree does not operate an account or graph-storage server of its own. When you enable optional AI, shared-link lookup, or analytics features, the limited data described below is sent to the named service providers.

The following categories of personal data may be held on-device:

- Your name and optional nicknames (set during onboarding)
- Names, aliases, roles, organizations, and notes about people you capture
- Free-form notes you write
- Audio recordings from voice captures
- Photos you attach as avatars
- Contact details (phone, email, birthday, photo) that you explicitly link or import from Apple Contacts for a specific person
- Precise location attached to an encounter, when you grant permission and the app is in the foreground
- Profile links and public profile details you share or choose to fetch

## Shared profile links (optional)

When you share a profile link, SocialTree's Share Extension reads details supplied by the share sheet. In Safari, it also reads a narrow set of metadata locally from the open page: its URL and title, Open Graph title and description, and any structured profile name. It does not read page body text, form values, cookies, local storage, or other page state, and the extension itself makes no network requests.

If you turn on **Fill in details from shared profiles**, after you open SocialTree the app contacts the profile site directly, without cookies or an account, to load public details such as the person's name, photo, employer, role, and bio. Those details are stored on your device, where you can edit or delete them. If **AI Usage** is also on, fetched text attached to a capture may be sent to Google through Firebase AI Logic and Gemini. Shared-link lookup controls contact with the profile site; AI Usage separately controls transfer to Google.

## Calendar access (optional)

If you turn on **"Upcoming from your calendar"** (in Settings → Notifications & Calendar, or from the card in Catch Up), SocialTree reads upcoming events from your device calendar — the next 7 days of event titles, times, and attendee names and emails — to show meetings with people you already track, prepare briefings, and schedule local reminders around those meetings.

- All matching between calendar events and your people happens **entirely on your device**. Calendar data is never sent to any server, including Google.
- Calendar access is used **read-only**: SocialTree never adds, changes, or deletes calendar events. (iOS grants calendar reading only through its "full access" permission — Apple offers no read-only tier — but the app contains no code path that writes to your calendar.)
- If you capture a note about a meeting, only the note you write or dictate is processed as described in the AI section below, the same as any other capture.
- Reminders about meetings and people are delivered as **local notifications**, scheduled on your device. By default their text is name-free on the lock screen; showing names is a separate opt-in in Settings.
- You can turn the feature off anytime in **Settings → Notifications & Calendar**, and revoke calendar access in iOS Settings → SocialTree.

## When data is sent to Google (Firebase AI Logic → Gemini)

SocialTree uses **Google's Firebase AI Logic** service to process capture content into structured information. Firebase AI Logic is a managed Google Cloud service that relays each request to **Google's Gemini** large-language model and returns the structured response. From your perspective, you are interacting with one service (Google); from an engineering perspective, two related Google services are involved, both operated by Google LLC.

AI processing is **strictly opt-in**. During onboarding and anytime in **Settings → AI Usage**, you choose whether to enable AI. With AI off, no capture or saved-graph content is sent to Google for AI processing.

When AI is enabled, the following may be sent to Google (Firebase AI Logic → Gemini):

- The text of a note you save
- The audio file from a voice capture
- Text attached to a shared-profile capture, which may include a fetched name, employer, role, and profile bio
- A list of existing people in your app (names, aliases, organization) to help match duplicates
- A specific person's context when you request conversation starters or run AI-assisted search

Every request is cryptographically attested by **Firebase App Check** (using Apple's DeviceCheck framework) so that Google can verify the request came from a legitimate SocialTree install. No personal identifier is sent in this attestation — it confirms the app binary and device, not who you are.

Google's privacy policy governs Google's handling of that data: <https://policies.google.com/privacy>. Firebase-specific terms: <https://firebase.google.com/support/privacy>.

**Google's data-use terms**: Google handles prompts and responses under the privacy and service terms applicable to the Firebase/Gemini service tier configured for SocialTree. SocialTree does not make a separate or unconditional promise about Google's use of submitted content for model training. Review Google's current terms using the links above.

**Subprocessors**: The two Google services involved — Firebase AI Logic and Gemini — are both operated by Google LLC and are the only external subprocessors that receive **user content**. SocialTree also sends **anonymous usage analytics** to TelemetryDeck GmbH (a privacy-focused analytics service based in Germany, EU-hosted) via its official SDK: event names such as "capture completed" or "paywall shown", small non-identifying event details (counts, categories, coarse duration buckets), and general device statistics (app version, iOS version, device model, language). These signals never include names, note text, transcripts, or any other user content; the only identifier is a random per-install ID (never IDFA/IDFV or any hardware identifier), which TelemetryDeck additionally anonymizes by hashing. Analytics is not linked to your identity and can be disabled at any time in **Settings** ("Share Anonymous Usage Analytics"). TelemetryDeck's privacy policy: <https://telemetrydeck.com/privacy/>. No crash reporters or ad networks are used.

## Early-access transparency (AI request logging)

While SocialTree is in its early-access period (roughly its first hundred users, spanning the TestFlight beta and the initial App Store release), **every** AI request — the full capture text or audio, any attached profile text, any relevant saved person/encounter excerpts included for that AI feature, plus Gemini's full response — is logged to Firebase Studio at 100% sampling, so the developer (Praneel Bhatia) can inspect prompts and responses to diagnose extraction quality issues. This logging:

- Only applies when AI is enabled. With AI off in **Settings → AI Usage**, no capture or saved-graph content is sent to Google for AI processing or logged there.
- Is stored in Google Cloud's logging system, retained for approximately 30 days (Google Cloud Logging default retention for Firebase AI Logic prompts and responses).
- Is scoped to the early-access period. Full logging is kept while the user base is small because it is the developer's only way to find and fix cases where the AI extraction gets real-world notes wrong. As the app matures (on the order of one hundred active users), trace sampling will be reduced to ≤5% or disabled entirely. When that change happens, this policy section will be updated and the "Last updated" date at the top will change.
- Is distinct from Google's own processing. Google receives the content either way to run the extraction; the "trace logging" disclosed here is an additional retention by the developer for debugging.

If you are not comfortable with the developer being able to see your AI capture content during the early-access period, you can disable AI in **Settings → AI Usage** (no capture content is sent to Google), or wait for a later release, after this logging has been significantly reduced or disabled.

## What SocialTree does NOT do

- No crash reporters, advertising networks, IDFA, fingerprinting, or hardware identifiers. TelemetryDeck receives only the anonymous, opt-out usage analytics and random per-install identifier described above; it is not used for advertising tracking.
- No data brokers
- No sale or sharing of personal data for advertising. Capture content is sent only to Google under your AI choice. Optional shared-link lookup contacts the profile site itself, and TelemetryDeck receives only the anonymous usage statistics described above.
- No account, login, or sign-up — SocialTree does not know who you are

## Your controls

- **Turn AI off:** Settings → AI Usage (disables Gemini processing)
- **Turn shared-link lookup off:** Settings → Shared Links (stops SocialTree from loading shared profile pages)
- **Turn analytics off:** Settings → "Share Anonymous Usage Analytics" (stops all TelemetryDeck signals immediately)
- **Delete everything:** Settings → Clear All Data
- **Export your data:** Settings → Export Data (JSON)
- **Start fresh:** Settings → Reset & Start Onboarding
- **Revoke iOS permissions** (microphone, location, photos, speech recognition) any time in iOS Settings → SocialTree

## Your rights (GDPR / EEA / UK)

If you are located in the European Economic Area (EEA), the United Kingdom, or another jurisdiction with comparable data-protection rights, you have the following rights regarding personal data processed by SocialTree:

- **Access** — request a copy of the full graph SocialTree stores on your device via **Settings → Export Data (JSON)**. For any AI request content retained temporarily in Firebase logs, use the contact address below.
- **Rectification** — correct inaccurate personal data. You can edit any person, encounter, or note directly in the app.
- **Erasure** — request deletion of your personal data. You can self-serve via **Settings → Clear All Data**, which wipes local storage. For any data that may have been retained in Firebase trace logs during the early-access period, email the contact address below and the developer will delete it within 30 days.
- **Data portability** — receive your data in a structured, machine-readable format. Use **Settings → Export Data (JSON)**.
- **Objection and restriction** — request that processing be stopped or restricted. Disable AI in **Settings → AI Usage** to stop Gemini processing. Shared-link lookup and anonymous analytics have their own Settings controls.
- **Lodge a complaint** — contact your local data-protection authority if you believe SocialTree has not handled your request appropriately.

For any of these rights you cannot self-serve, email **praneel.business@gmail.com** and the developer will respond within 30 days.

## iOS permissions SocialTree requests

- **Microphone** — to record voice captures
- **Speech Recognition** — to transcribe voice captures (transcription runs on-device via Apple's speech framework)
- **Location (While Using the App)** — to attach a place to captures when you enable it
- **Photos** — to pick an avatar image for a person
- **Camera** — to take a profile photo or an encounter photo
- **Contacts** — only when you choose to link a person to, or save a person into, Apple Contacts; the app never scans your address book
- **Calendars (full access)** — only if you enable "Upcoming from your calendar"; used read-only as described in the Calendar section above
- **Notifications** — to deliver the optional local reminders described above; name-free on the lock screen unless you opt in

Each permission is optional; the app functions without any of them, with reduced capture options.

## Children and minors

SocialTree is rated 4+ by Apple's age-rating system but is not directed to users under 16. Given the app uses generative AI to process user-submitted content, the developer recommends that users under 16 not install it without a parent or guardian's supervision. SocialTree does not knowingly collect personal data from users under 13 (COPPA). If you believe a minor under 13 has submitted data, contact the email below and the developer will delete it.

## Changes to this policy

If the policy changes materially, the "Last updated" date above will change and — if you're a TestFlight or App Store user at the time — the app will surface a notice on next launch.

## Contact

Questions about this policy:

**praneel.business@gmail.com**
