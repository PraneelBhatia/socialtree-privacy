---
title: SocialTree Privacy Policy
description: How SocialTree handles your data — on-device storage, opt-in AI, and the controls you have.
---

# SocialTree Privacy Policy

_Last updated: 2026-04-18_

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

## When data is sent to Google Gemini

SocialTree uses Google's **Gemini API** to turn captured notes and voice memos into structured information — people, encounters, connections, and conversation starters. This is the **only** external service SocialTree integrates with, and AI processing is **strictly opt-in**.

During onboarding and anytime in **Settings → AI Usage**, you choose whether to enable AI. With AI off, SocialTree will save captures locally but will not process them and will not transmit anything to Google.

When AI is enabled, the following may be sent to Google's Gemini API:

- The text of a note you save
- The audio file from a voice capture
- A list of existing people in your app (names, aliases, organization) to help match duplicates
- A specific person's context when you request conversation starters or run AI-assisted search

Google's privacy policy governs Google's handling of that data: <https://policies.google.com/privacy>. Per Google's terms, prompts and responses sent to the paid Gemini API are not used to train Google's general-purpose models.

## What SocialTree does NOT do

- No analytics SDKs, crash reporters, or telemetry
- No advertising networks or tracking identifiers (no IDFA, no device IDs sent anywhere)
- No data brokers
- No sharing with third parties other than Google Gemini, and only when you opt in
- No account, login, or sign-up — SocialTree does not know who you are

## Your controls

- **Turn AI off:** Settings → AI Usage (disables all Gemini requests)
- **Delete everything:** Settings → Clear All Data
- **Export your data:** Settings → Export Data (JSON)
- **Start fresh:** Settings → Reset & Start Onboarding
- **Revoke iOS permissions** (microphone, location, photos, speech recognition) any time in iOS Settings → SocialTree

## iOS permissions SocialTree requests

- **Microphone** — to record voice captures
- **Speech Recognition** — to transcribe voice captures (transcription runs on-device via Apple's speech framework)
- **Location (While Using the App)** — to attach a place to captures when you enable it
- **Photos** — to pick an avatar image for a person

Each permission is optional; the app functions without any of them, with reduced capture options.

## Children

SocialTree is rated 4+ and is not directed to children under 13. It does not knowingly collect personal data from children.

## Changes to this policy

If the policy changes materially, the "Last updated" date above will change and — if you're a TestFlight or App Store user at the time — the app will surface a notice on next launch.

## Contact

Questions about this policy:

**praneel.bhatia@outlook.com**
