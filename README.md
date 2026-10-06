# mumbly

mumbly is a dictation app and meeting notetaker for the Mac: press a key, talk, and it types what you meant where your cursor is. The speech and cleanup models run on your Mac, so your audio and your words stay on it.

mumbly was called Local Dictation until version 0.7.12, and this repository was called local-dictation-releases; GitHub sends the old address here, so copies already installed keep updating. The version number starts over at 0.1.0, the first public version, and follows 0.7.12. The product's planned address is heymumbly.com (not live yet).

## Install

Needs a Mac with Apple silicon (M1 or later) and macOS 26 or later. Paste this in Terminal:

```
curl -fsSL https://github.com/lvecchi500-art/mumbly/releases/latest/download/install.sh | bash
```

It puts the app in `~/Applications` and opens it. After that it updates itself. The app's file is still called `LocalDictation.app` (so permissions and updates carry over from older versions); Finder, the Dock, Spotlight and macOS's permission prompts show it as mumbly.

Rather not use Terminal? Download [mumbly.zip](https://github.com/lvecchi500-art/mumbly/releases/latest/download/mumbly.zip), open it, and move the app to Applications. The first time you open it macOS says it can't verify it: click Done, then open System Settings, Privacy & Security, scroll down, click Open Anyway next to the line about mumbly, and enter your password. You only do this once.

## What macOS will ask, and why

- **Microphone.** To hear you, only while you hold or toggle the dictation shortcut.
- **Accessibility.** To type the text where your cursor is, and to read the text around it so the cleanup fits.

Asked only when you use the feature that needs it: **Screen & System Audio Recording** (the other side of a call, when you record a meeting), **Calendar** (to name meetings), **Reminders** (to add one when you approve it), **Contacts** (to spell names right), and **Notifications**.

## This build is not notarized yet

Apple has not checked this build: it is signed with the project's own certificate, not an Apple Developer ID. A copy downloaded in a browser is quarantined, and macOS shows "Apple could not verify..." until you allow it once in Privacy & Security (above). The install command skips that step, because a download made with `curl` is not quarantined. The installer then installs the app only if it is signed by the project's own certificate (pinned in the script); anything else is refused and nothing on your Mac is changed. Updates are signed too, and the app checks the signature before installing one. When the build is notarized, this section will say so.

## Uninstall

In the app: Settings, General, Uninstall. Or, with the app already gone:

```
curl -fsSL https://github.com/lvecchi500-art/mumbly/releases/latest/download/uninstall.sh | bash
```

That removes the app and its models and keeps your history, notes and meetings. Add `-s -- --all` after `bash` to delete those too (the script asks first; `--dry-run` only lists what it would remove).

## Report a problem

Open an issue in this repository. From the app, menu bar icon, Report a Problem... writes a report of facts about your Mac and the app (never what you dictated unless you tick it) that you can read before you send it. Issues here are public: do not put anything private in one.

## Licence

The binaries are free to use. All rights reserved: no licence to copy, modify or redistribute them is granted. The software and models mumbly is built on keep their own licences, listed in the app (Settings, Privacy, Acknowledgements).

## Security

To report a security problem, email: **to be added** (placeholder: the founder has not set a security address yet). Until there is one, do not post a security problem in a public issue.
