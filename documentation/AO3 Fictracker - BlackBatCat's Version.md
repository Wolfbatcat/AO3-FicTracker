# AO3 FicTracker -  BlackBatCat's Version

This is a fork of [infiniMotis's AO3 FicTracker](https://greasyfork.org/en/scripts/513435-ao3-fictracker) with my personalized modifications.

> Note: This version will likely remain unlisted and will only be accessible from this link.

## Changes from Original

This version includes the following modifications from the [original AO3 FicTracker](https://greasyfork.org/en/scripts/513435-ao3-fictracker):

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
- Custom color scheme inspired by Rose Pine theme
- Border radius changed from `8px` to `0.75em` to match [site skin](https://archiveofourown.org/works/69993411)

### 📖 Chapter Tracking Feature
New feature to help track reading progress in multi-chapter works:
- **"Mark Current Chapter" button** appears on chapter pages
- Automatically prepends `Last Read: Ch. X` to your custom note for that fic
- Updates the chapter number each time you click it

### ⭐ Kudos Button Hiding (Cloud Sync)
New feature: When you give kudos to a work, AO3 FicTracker will automatically hide the kudos button on all chapters and work pages for that fic.
- This status is tracked and synced across all devices using the Google Sheets Cloud Storage integration.
- Replaces my [No Re-Kudos script](https://greasyfork.org/en/scripts/551623-ao3-no-re-kudos) so feel free to disable it!

### ⚙️ Changed Default Settings
Different defaults matching my own preferences:
- **My Notes Button**: Disabled by default; can be re-enabled in Preferences
- **On-Page Sorting**: Disabled by default; can be re-enabled in Preferences
- **Hide Default Subscribe Button**: New setting, enabled by default. Only hides subscribe button on work pages.

### 🐛 Bug Fixes
- Fixed case-sensitive tag comparison bug that prevented removing tags from dropdown menus when AO3 normalized tag casing
- Fixed issue where blurbs would not inherit original box shadow and border properties when Border Size set to 0

---
## 🙌 Credits

My heartiest thanks to farin for the life-changing FicTracker script. [Send them a tip](https://ko-fi.com/infinimotis)!