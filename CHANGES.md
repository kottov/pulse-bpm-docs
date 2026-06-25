# Legal docs update — plain-language summary of changes

**Date:** 25 June 2026
**Branch:** `legal-docs-update-2026-06`
**Files:** `privacy-policy.html` (full rewrite), `terms-of-use.html` (full rewrite), `account-deletion.html` (new)

This explains, in plain language, what changed and **why**. The goal was, in order:
1. **Reduce your legal risk** by making every statement honest and accurate to what the app actually does.
2. **Meet the rules** of Apple, Google Play, the EU/UK (GDPR), and US state privacy laws.
3. **Tell users clearly and honestly** what happens to their data.

> ⚠️ This is not a substitute for sign-off by a qualified lawyer in your jurisdiction. A few items below **must** be completed by you before these go live (see "Before you publish").

---

## Why the old documents were risky

The **old Privacy Policy** said: *"We do not collect personal information that can directly identify you, such as your name, email address."* That is **no longer true** — the app now has sign-in (Google/Apple/email), cloud sync, subscriptions, crash reporting and more, all of which involve personal data. A privacy policy that says you collect nothing while you actually collect emails is one of the easiest ways to get an app rejected, fined, or sued (in the US, an inaccurate privacy promise can be an independent legal violation). It also only mentioned AdMob and Google Analytics, hiding the rest of the services.

The **old Terms of Use** were written for a **different app** ("BPM Detect" / "BPM ID"), had a broken link (`[insert link to Privacy Policy]`), restricted use to "personal, non-commercial" (which would forbid your DJ/pro users), assumed Apple-only billing (you're also on Google Play now), and were missing all of Apple's required EULA terms.

---

## Privacy Policy — what changed and why

| # | Change | Why (motivation) |
|---|--------|------------------|
| 1 | **Removed the false "we don't collect your name/email" claim.** Replaced with an honest, full description of what is collected. | The old claim was untrue and is the single biggest legal risk. Honesty here is what actually protects you. |
| 2 | **Added a plain-language "short version" at the top.** | Users (and app reviewers) can understand it at a glance; reduces complaints and rejections. |
| 3 | **Split microphone use into two clearly separate parts.** (a) Tempo detection runs on the device and audio is never saved or sent; (b) "Track ID" sends an acoustic *fingerprint* (not a recording) to Apple's Shazam service. | Microphone claims are heavily scrutinised. Saying "no audio ever leaves the device" would be **false** because Track ID does send a fingerprint. Separating them keeps every sentence true and shows you understand the difference. |
| 4 | **Stated that Track ID can also run automatically** if the user turns on the optional auto-start setting. | The app has an auto-start setting. Claiming it "only runs when you tap it" would be untrue for those users — and it's about data leaving the device, so accuracy matters. |
| 5 | **Described the Android Track ID path correctly** (Shazam recognizer + a token from your Supabase backend), not just Apple ShazamKit. | On Android it isn't Apple's ShazamKit. Naming only ShazamKit would be false for Android users, whom the policy covers. |
| 6 | **Listed every third-party service** in a table with links: Firebase (Analytics, Crashlytics, Performance, Remote Config), AdMob + consent tool, Google Sign-In, Apple Sign-In/Shazam, Supabase, RevenueCat, Odesli/Song.link, App Store/Play billing. | Apple and Google **require** you to disclose all data-sharing partners; the old doc hid most of them. |
| 7 | **Did NOT list PowerSync or a "server anonymous account."** | I checked the code: PowerSync is switched off (not transmitting), and there is no server-side anonymous account. Listing things you don't actually do is its own inaccuracy. |
| 8 | **Added who you are (data controller) and a flagged placeholder for EU & UK representatives.** | GDPR requires naming the controller and (for EU/UK users) a local representative. I cannot invent a representative, so it's marked for you to fill in. |
| 9 | **Added legal bases, retention periods, and international-transfer safeguards (SCCs / Data Privacy Framework).** | These are mandatory GDPR disclosures that were entirely missing. |
| 10 | **Added a full "your rights" section for EU/UK** (access, delete, object, withdraw consent, complain to a regulator). | Required by GDPR. |
| 11 | **Added a US section** with a "Do Not Sell or Share" explanation and how to opt out (ATT, reset ad ID, email), plus Global Privacy Control and an appeal right. | Required by California (CCPA/CPRA) and similar laws. Using ad IDs for ads can count as a "sale/share," so this must be addressed. Opt-outs point only to controls that actually exist. |
| 12 | **Described account deletion honestly:** cloud data is erased, but data on the device is **not** wiped automatically. | This matches what the app's deletion actually does. Promising a full wipe you don't perform would be a false promise. |
| 13 | **Corrected sync wording:** settings sync for all signed-in users; the session library syncs only for **subscribers** (not one-time purchasers). | Matches the real behaviour, so a one-time buyer isn't misled into thinking their library is uploaded. |
| 14 | **Said the retape migration data can later sync to the cloud** if the user is signed in. | The migration marks data to sync; saying it "stays on your device" would be misleading for signed-in users. |
| 15 | **Used cautious wording for things still in progress** (data-processing agreements, transfer mechanisms). | Avoids claiming something is fully done before it is. |
| 16 | **Standardised contact email to `kottov@gmail.com`** and added a children section. | The old policy used a different email; consistency + the children section is required. |

## Terms of Use — what changed and why

| # | Change | Why (motivation) |
|---|--------|------------------|
| 1 | **Fixed the app name** to Live BPM and **fixed the broken Privacy Policy link.** | The old Terms named a different app and had a placeholder link — both look unprofessional and undermine enforceability. |
| 2 | **Allowed personal AND professional use** (DJing, teaching, performing). | The old "personal, non-commercial" wording would forbid exactly the people you're selling to. |
| 3 | **Added an accuracy disclaimer** — tempo and song results are estimates, not a calibrated instrument. | Protects you if a user relies on a reading and it's wrong. |
| 4 | **Rewrote subscription/purchase terms for BOTH stores**, covering auto-renewal, cancellation, free trials, refunds, and "lifetime = lifetime of the app." | You're on Apple and Google now; auto-renewal disclosures are legally required and the old terms were Apple-only. |
| 5 | **Kept the "as is" disclaimer and liability cap, but added consumer-rights carve-outs.** | Without carve-outs for EU/UK and US consumers, those clauses can be struck down entirely. The carve-outs are what make the protections actually hold. |
| 6 | **Made the user responsible for their own music licensing** (e.g. public-performance fees). | Keeps copyright/licensing liability off you. |
| 7 | **Added all 10 of Apple's required EULA terms**, including the exact word-for-word "third-party beneficiary" clause Apple mandates. | Apple **requires** these in any custom EULA; missing them is a rejection risk. The key clause must be verbatim, and it is. |
| 8 | **Added a Google Play section.** | Google has its own required relationship terms. |
| 9 | **Kept Ukraine governing law but preserved users' mandatory local consumer rights** and their right to sue locally. | A pure "Ukraine only" clause is unenforceable against EU/UK consumers; this version survives. |
| 10 | **Improved the "changes to terms" clause** to give advance notice of material changes and a right to reject. | A "we can change anything, silence = agreement" clause is on the EU unfair-terms blacklist, especially when pushing brand-new terms onto all existing retape users via an update. |

## New file — `account-deletion.html`

Google Play **requires** a public web page where users can request account/data deletion **even after they uninstall the app**. This new page provides that (in-app steps + email request + what is and isn't deleted). Without it, Play can reject or remove the app.

---

## ⚠️ Before you publish (action items — a few are blocking)

**Must do before these go live:**
1. **Insert a postal/contact address** in Terms §19.8 (currently a flagged placeholder). Apple and EU consumer law require a real geographical address, not just an email. Use a business/registered or P.O.-box address if you don't want to publish a home address.
2. **Appoint and name your EU and UK Article 27 representatives** in Privacy Policy §1 (flagged placeholders), or document why an exemption applies. This is the highest-risk GDPR gap for an EU/UK-facing app run from outside the EU/UK.
3. **Sign data-processing agreements (DPAs)** with Supabase, RevenueCat, and Google/Firebase, and confirm the transfer mechanisms referenced. The text says these are "in progress."
4. **Show the new Terms on first launch for migrating retape users** and require an explicit "I Agree" tap — don't rely on "continued use = acceptance" for the rebrand.

**Should do (store-compliance, outside these documents):**
5. Update the **Apple App Privacy "nutrition label"** and **Google Play Data Safety form** to match this policy (they must agree).
6. Complete Apple's **age-rating questionnaire** and set Google Play **target audience to 13+**.
7. Verify the **ATT prompt is shown before AdMob requests** ads on iOS, and that the EEA consent prompt actually re-opens if you claim users can change consent.
8. Update the iOS microphone permission text (`NSMicrophoneUsageDescription`) to mention song identification, not only tempo.
9. Reconcile the **AdMob publisher ID discrepancy**: `app-ads.txt` lists `pub-9315400394331901`, but the app's ad unit IDs use the `ca-app-pub-1124809592826969` prefix. One of them is wrong — fix `app-ads.txt` (or the ad config) so they match, or ad revenue/verification can break. (I deliberately did **not** print any publisher ID in the policy to avoid stating a wrong number.)
10. Implement an actual **"Do Not Sell/Share" / Global Privacy Control** path if you want to rely on it beyond the device-level controls currently described.

---

*Prepared as a careful first draft to reduce legal risk and cover the app's full scope. Please have a qualified lawyer review before publishing.*
