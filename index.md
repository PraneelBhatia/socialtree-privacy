---
title: SocialTree Privacy Policy
description: How SocialTree handles your data — on-device storage, opt-in AI, and the controls you have.
---

# SocialTree Privacy Policy

_Last updated: 2026-04-20_

SocialTree is a personal social memory assistant for iOS, operated as a personal project by **Praneel Bhatia**. This policy explains what data the app handles, when (and why) any of it leaves your device, and the controls available to you.

## Where your data lives

Everything you capture in SocialTree — the people you add, notes, voice memos, photos, circles — is stored **locally on your iPhone** using Apple SwiftData. SocialTree does not operate its own server and never receives or stores your data.

The following categories of personal data may be held on-device:

- Your name and optional nicknames (set during onboarding)
- Names, aliases, roles, organizations, and notes about people you capture
- Free-form notes you write
- Audio recordings from voice captures
- Photos you attach as avatars
- Precise location attached to an encounter, when you grant permission and the app is in the foreground

## When data is sent to Google (Firebase AI Logic → Gemini)

SocialTree uses **Google's Firebase AI Logic** service to process captured notes and voice memos into structured information. Firebase AI Logic is a managed Google Cloud service that relays each request to **Google's Gemini** large-language model and returns the structured response. From your perspective, you are interacting with one service (Google); from an engineering perspective, two related Google services are involved, both operated by Google LLC.

AI processing is **strictly opt-in**. During onboarding and anytime in **Settings → AI Usage**, you choose whether to enable AI. With AI off, SocialTree saves captures locally only — nothing is transmitted.

When AI is enabled, the following may be sent to Google (Firebase AI Logic → Gemini):

- The text of a note you save
- The audio file from a voice capture
- A list of existing people in your app (names, aliases, organization) to help match duplicates
- A specific person's context when you request conversation starters or run AI-assisted search

Every request is cryptographically attested by **Firebase App Check** (using Apple's DeviceCheck framework) so that Google can verify the request came from a legitimate SocialTree install. No personal identifier is sent in this attestation — it confirms the app binary and device, not who you are.

Google's privacy policy governs Google's handling of that data: <https://policies.google.com/privacy>. Firebase-specific terms: <https://firebase.google.com/support/privacy>.

**Training policy**: SocialTree is configured on Firebase's paid tier, which — per Google's current terms for the Gemini Developer API — means prompts and responses are not used to train Google's general-purpose models. This is a standing Google commitment for paid-tier usage, not a SocialTree-specific contract. If Google's terms change, this policy will be updated in sync.

**Subprocessors**: The two Google services involved — Firebase AI Logic and Gemini — are both operated by Google LLC and are the only external subprocessors SocialTree uses. No other third parties (no analytics vendors, crash reporters, or ad networks) receive user content.

## Beta testing transparency (TestFlight period)

While SocialTree is in TestFlight beta, **every** AI request — the full note text or audio, plus Gemini's full response — is logged to Firebase Studio at 100% sampling, so the developer (Praneel Bhatia) can inspect prompts and responses to diagnose extraction quality issues. This logging:

- Only applies when AI is enabled. With AI off in **Settings → AI Usage**, nothing is transmitted and nothing is logged.
- Is stored in Google Cloud's logging system, retained for approximately 30 days (Google Cloud Logging default retention for Firebase AI Logic prompts and responses).
- Is scoped to the TestFlight period. Before SocialTree ships to the public App Store, trace sampling will be reduced to ≤5% or disabled entirely. When that change happens, this policy section will be updated and the "Last updated" date at the top will change.
- Is distinct from Google's own processing. Google receives the content either way to run the extraction; the "trace logging" disclosed here is an additional retention by the developer for debugging.

If you are not comfortable with the developer being able to see your captured notes during the beta, the options are: (a) disable AI in **Settings → AI Usage** (your captures stay local only), or (b) uninstall the TestFlight build and wait for the App Store release, which will have significantly reduced or disabled trace logging.

## What SocialTree does NOT do

- No analytics SDKs, crash reporters, or telemetry
- No advertising networks or tracking identifiers (no IDFA, no device IDs sent anywhere)
- No data brokers
- No sharing with third parties other than Google (Firebase AI Logic and Gemini), and only when you opt in
- No account, login, or sign-up — SocialTree does not know who you are

## Your controls

- **Turn AI off:** Settings → AI Usage (disables all AI processing)
- **Delete everything:** Settings → Clear All Data
- **Export your data:** Settings → Export Data (JSON)
- **Start fresh:** Settings → Reset & Start Onboarding
- **Revoke iOS permissions** (microphone, location, photos, speech recognition) any time in iOS Settings → SocialTree

## Your rights (GDPR / EEA / UK)

If you are located in the European Economic Area (EEA), the United Kingdom, or another jurisdiction with comparable data-protection rights, you have the following rights regarding personal data processed by SocialTree:

- **Access** — request a copy of the personal data SocialTree holds about you. Because everything is on-device, you can self-serve via **Settings → Export Data (JSON)**.
- **Rectification** — correct inaccurate personal data. You can edit any person, encounter, or note directly in the app.
- **Erasure** — request deletion of your personal data. You can self-serve via **Settings → Clear All Data**, which wipes local storage. For any data that may have been retained in Firebase trace logs during the beta period, email the contact address below and the developer will delete it within 30 days.
- **Data portability** — receive your data in a structured, machine-readable format. Use **Settings → Export Data (JSON)**.
- **Objection and restriction** — request that processing be stopped or restricted. Disable AI in **Settings → AI Usage** to stop all third-party processing immediately.
- **Lodge a complaint** — contact your local data-protection authority if you believe SocialTree has not handled your request appropriately.

For any of these rights you cannot self-serve, email **praneel.business@gmail.com** and the developer will respond within 30 days.

## iOS permissions SocialTree requests

- **Microphone** — to record voice captures
- **Speech Recognition** — to transcribe voice captures (transcription runs on-device via Apple's speech framework)
- **Location (While Using the App)** — to attach a place to captures when you enable it
- **Photos** — to pick an avatar image for a person

Each permission is optional; the app functions without any of them, with reduced capture options.

## Children and minors

SocialTree is rated 4+ by Apple's age-rating system but is not directed to users under 16. Given the app uses generative AI to process user-submitted content, the developer recommends that users under 16 not install it without a parent or guardian's supervision. SocialTree does not knowingly collect personal data from users under 13 (COPPA). If you believe a minor under 13 has submitted data, contact the email below and the developer will delete it.

## Changes to this policy

If the policy changes materially, the "Last updated" date above will change and — if you're a TestFlight or App Store user at the time — the app will surface a notice on next launch.

## Contact

Questions about this policy:

**praneel.business@gmail.com**
