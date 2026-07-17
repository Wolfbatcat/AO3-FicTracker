# AO3 FicTracker - BlackBatCat's Version

![Coded with GitHub Copilot](https://vibecoded.fyi/badges/flat/agents/github-copilot.svg)

This is a fork of [infiniMotis's AO3 FicTracker](https://greasyfork.org/en/scripts/513435-ao3-fictracker) with my personalized modifications and a few new features.

---

## 📋 How to Use

Setup steps and usage instructions are on the [FicTracker page](https://greasyfork.org/en/scripts/513435-ao3-fictracker).

All settings can be found on your Preferences page at `User -> My Preferences`.

I highly recommend using FicTracker's Cloud Storage integration. It syncs statuses, notes, and settings across devices, and fork features like kudos-button hiding work best with it. 

> **🚨 Important:** Update statuses using FicTracker controls only (the **Change Status** menu and work-page buttons). Changes made through AO3's **Edit Bookmark** form aren't tracked by FicTracker storage, and status highlighting / collapse-hide behavior depends on it.

---

## 🔄 Changes from Original

### ⚙️ Changed Defaults
- **My Notes Button** – Off by default; re-enable in Preferences.
- **On-Page Sorting** – Off by default; re-enable in Preferences.
- **Hide Default Subscribe Button** – New setting, on by default. Hides the subscribe button on work pages only. Uncheck to get the button back.


### 📖 Chapter Tracking Feature
New feature to help track reading progress in multi-chapter works:
- **"Mark Chapter" button** appears on chapter pages
- Automatically prepends `Last Read: Ch. X` to your custom note for that fic
- Updates the chapter number each time you click it

### 📚 Series Bookmark Support
Change Status now works on series, not just individual works:
- Status buttons are injected directly into the series page nav
- Series bookmarks automatically receive a `Series` bookmark tag so you can find them easily

### ⭐ Kudos Button Hiding
New feature: giving kudos to a work hides the kudos button on all its chapters and work pages, synced across devices via Cloud Sync.
- Cross-compatible with my [No Re-Kudos script](https://greasyfork.org/en/scripts/551623-ao3-no-re-kudos): if you switch from it or run both, your existing kudos history is automatically picked up and folded into Cloud Sync — nothing to migrate, nothing lost.

### 📚 Renamed Status Categories
Status categories have been renamed and reordered to match my workflow:
- **"Favorite"** → **"Reading"**
  - Label: "My Current Fanfics"
  - Color: Rose pink (`#eb6f92`)
- **New: "Subscribed"** status added
  - Label: "My Subscribed Fics"
  - Color: Coral (`#ea9a97`)
- **"Disliked Work"** → **"Dropped"**
  - Hidden from view by default
  - No longer shown in dropdown menu
- **"Finished Reading"**
  - Moved to end of list

### 🎨 Visual Theme
- Custom color scheme inspired by Rosé Pine theme (can be changed in preferences)
- Broader site skin compatibility: the "Change Status" dropdown and custom note boxes now blend into whatever skin you're using.
- Fixed several visual bugs, including blurbs losing their background color, borders, and shadow effects.

### 🔄 Cloud Sync Enhancements
- Status configuration (`FT_statusesConfig`) now syncs too — custom tags and visual settings (highlight color, border size, border opacity) carry across devices.

---

## 📜 Full Changelog

This fork rebases onto upstream releases as they ship, plus its own fixes in between. See the [CHANGELOG](https://github.com/Wolfbatcat/AO3-FicTracker-BlackBatCat/blob/main/CHANGELOG.md) for the full version history.

---

## 🙌 Credits

My heartiest thanks to farin for the life-changing FicTracker script. [Send them a tip](https://ko-fi.com/infinimotis)!
