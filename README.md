# Android Debloat List

Ready-to-import [Canta](https://github.com/samolego/Canta) presets for removing bloatware from Samsung / Android phones. No root, no PC.

| Preset | Apps | Risk | Who it's for |
| --- | :---: | :---: | --- |
| [`canta-main.json`](canta-main.json) | 77 | 🟢 Low | Everyone |
| [`canta-extra.json`](canta-extra.json) | 9 | 🔴 High | Users who already run replacement apps |

---

## Quick start

1. Install **[Shizuku](https://shizuku.rikka.app/)** and start it (wireless debugging works without a PC).
2. Install **[Canta](https://github.com/samolego/Canta)** and grant it Shizuku access.
3. Open a preset file above, tap **Raw**, and copy the whole JSON.
4. In Canta: **Presets → Import** (it reads from the clipboard).
5. Apply the preset, review the selection, tap **Uninstall**.

> [!TIP]
> Apps are removed for the current user only, not wiped from the system. Anything can be restored from Canta's **Uninstalled** tab, or with:
> ```sh
> adb shell cmd package install-existing <package.name>
> ```

---

## 🟢 `canta-main.json`

Safe to remove on most devices. Core phone, messaging and Play services keep working.

| Category | What goes |
| --- | --- |
| **Bixby & Samsung AI** | Bixby agent and wake-up, Bixby Vision, Vision Intelligence, smart suggestions, Rubin (Customization Service), face / pet / story services |
| **AR & stickers** | AR Emoji, AR Emoji editor, avatar stickers, AR Core, auto doodle |
| **Samsung services** | Samsung Pass, Samsung Pay framework, Samsung Cloud, Galaxy Store, Secure Folder, Car Key, Link to Windows, Kids, parental controls, Quick Share, Smart Switch assistant |
| **Google extras** | Gemini (Bard), Android System Intelligence, Meet (Duo), AI wallpapers, ad services, federated compute, on-device personalization, feedback, supervision |
| **Third-party preloads** | Facebook app manager / services / installer, Microsoft OneDrive and app manager |
| **Diagnostics & telemetry** | Device quality agent, Knox analytics uploader, GPU watch, system tracing, Wi-Fi tips |
| **Misc** | Android easter egg, photo screensaver, partner bookmarks, Chinese keyboard languages, Tencent / IFAA payment stubs |

> [!NOTE]
> Removing **Secure Folder**, **Samsung Pass** and **Samsung Pay** deletes their stored data. Back it up first if you use them.

---

## 🔴 `canta-extra.json`

> [!WARNING]
> **Install and set a replacement dialer, contacts and SMS app _before_ applying this preset.** Without one you cannot make calls or read texts.
>
> **Do not use on a work-managed phone.** It removes Knox and MDM services that company device policies depend on.

| Category | What goes |
| --- | --- |
| **Stock communication apps** | Samsung Phone, Samsung Contacts, Samsung Messages, Google Messages |
| **Knox & device management** | Knox KPE core, Knox push manager, Knox zero-trust framework, MDM service, device admin agent |

---

## Before you start

- ✅ Back up anything important.
- ✅ Apply **main** first, use the phone for a day, then decide on **extra**.
- ✅ If something breaks, restore the last removed app from Canta's **Uninstalled** tab.
- ❌ Don't remove packages you don't recognise just because they aren't on this list.

## Disclaimer

Use at your own risk. Package names and dependencies vary by model, region and One UI version. Tested on Samsung One UI; other brands will simply skip packages that don't exist.
