# MUD World Builder Pro v6

A browser-based world and area builder for LPC-style MUDs.  
Design rooms visually, populate them with objects and monsters, and export a complete, ready-to-compile LPC area — all without leaving your browser.

This tool is entirely client-side and requires **no backend**.

---

## ✨ Features

### 🗺️ Visual Map Editor
- Grid-based room layout with pan support
- Compass-style digging (N, NE, E, SE, S, SW, W, NW)
- Vertical movement (UP / DOWN) with Z-level indicators
- Active room highlighting
- Visual indicators for:
  - Monsters
  - Objects
  - Room details

### 🏠 Room Editing
- Room name and long description
- Room details / items (`set_items`)
- Per-room monsters
- Per-room object placement
- Safe deletion with last-room protection

### 🧱 Object System
- Global object library
- Supported object types:
  - Simple objects
  - Weapons (with subtype)
  - Armour (cloth, leather, mail, plate)
- Objects can be reused across rooms
- Automatic LPC inheritance selection (`OBJECT`, `WEAPON`, `ARMOUR`)

### 👹 Monster Editor
- ID name and short description
- Race, class, gender, level
- Alignment slider with descriptive labels
- Inventory / loot system
- Automatic wield/wear logic on export

### 📦 Project Management
- Save and load projects as JSON
- Portable project files
- No server or database required

### 🧾 LPC Export
- Full LPC area export as a `.zip`
- Generates:
  - `rooms/`
  - `obj/`
  - `mon/`
  - `include/include.h`
- Automatic:
  - Safe filenames
  - Exit linking
  - Level scaling from base level
  - Object and monster reuse
- Output designed for traditional LP-style mudlibs

### 🧾 To-Do ###
- [x] Room Comments
- [x] Fix Monster Alignment
- [x] Doors
- [x] Add Sound / Smell to Room Items
- [x] Room Terrain
---

## 🚀 Getting Started

### Requirements
- A modern web browser
- No web server required
- Internet access only needed for JS libraries (JSZip, FileSaver)

### Running the Tool
Simply open the HTML file in your browser:

```bash
open index.html
# or
double-click the file
````

That’s it.

---

## 🧭 Basic Usage

1. **Dig rooms** using the compass overlay
2. **Click a room** to make it active
3. Edit room details in the **Room** tab
4. Create objects in the **Obj** tab
5. Add monsters in the **Mon** tab
6. Configure export settings in the **File** tab
7. Export your LPC area as a ZIP

---

## ⚙️ LPC Export Settings

| Setting    | Description                                |
| ---------- | ------------------------------------------ |
| Area Name  | Folder name inside the ZIP                 |
| Base Path  | Absolute LPC path (e.g. `/d/domain/area/`) |
| Base Level | Used as BLVL for monsters and objects      |

Monsters automatically scale relative to the base level.

---

## 🧠 Design Notes

* All data lives in memory until saved or exported
* Rooms exist only once dug (no phantom grid)
* Z-levels are handled logically and visually
* Object and monster definitions are de-duplicated on export
* Filenames are sanitized automatically

---

## 🛠️ Tech Stack

* Vanilla HTML, CSS, and JavaScript
* `<canvas>` for map rendering
* JSZip for ZIP creation
* FileSaver.js for downloads

No frameworks. No build step. No dependencies beyond the browser.

---

## 📁 Project Structure (Export)

```
area_name/
├── include/
│   └── include.h
├── rooms/
│   └── *.c
├── obj/
│   └── *.c
└── mon/
    └── *.c
```

---

## 🧙‍♂️ Intended Audience

* LPC MUD developers
* World builders and area designers
* Anyone tired of hand-writing room graphs

---

## 📜 License

This project is provided as-is.
Use it, hack it, expand it, and bend it to your mud’s will.

---

## 💬 Final Words

This tool exists to make MUD building **fun again**.

Dig fast. Populate recklessly.
Let the compiler sort out the rest.
