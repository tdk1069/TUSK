## 🧭 How to Use the Builder

### 1️⃣ Creating and Navigating Rooms

* The project starts with a **single room** at Z-level 0.
* Use the **compass overlay** to *dig* new rooms:

  * Cardinal & diagonal directions: **N, NE, E, SE, S, SW, W, NW**
  * Vertical movement: **UP** and **DOWN**
* Digging in a direction will:

  * Create a new room if one doesn’t exist
  * Automatically link the rooms with exits
  * Move you into the newly created (or existing) room

Click any room on the map to make it the **active room**.

---

### 2️⃣ Editing the Active Room

The **Room** tab always applies to the currently selected room.

You can edit:

* **Room Name** → exported as `set_short`
* **Room Description** → exported as `set_long`
* **Room Details** → exported as `set_items`

Room details represent things players can `look at` (e.g. signs, furniture, markings).

---

### 3️⃣ Objects

Objects are managed in two layers:

#### Global Object Library

* Defined once
* Reusable across multiple rooms
* Edited in the **Obj** tab

Supported types:

* Simple objects
* Weapons (with weapon type)
* Armour (cloth, leather, mail, plate)

#### Room Contents

* Add objects from the library into the current room
* Objects placed in rooms are exported with `add_object()`

---

### 4️⃣ Monsters

Monsters are **room-specific**.

For each monster you can define:

* ID name and short description
* Race, class, gender
* Level (relative to area base level)
* Alignment (slider with descriptive labels)
* Inventory / loot

On export:

* Monsters automatically wear and wield gear
* Duplicate monster definitions are reused where possible

---

### 5️⃣ Saving and Loading Projects

Use the **File** tab to:

* Save the entire project as a JSON file
* Reload a project later
* Share projects between machines

All data is stored client-side.

---

## 🗺️ Map Symbols & Visual Indicators

Each room is represented as a square on the map.

### Room Colors

* **Orange** — Active room
* **Blue-grey** — Inactive room on the current Z-level

Rooms on other Z-levels are hidden.

---

### Connection Lines

* Lines between rooms represent exits
* Only exits on the **current Z-level** are drawn as lines

Vertical exits are shown using arrows instead.

---

### Z-Level Indicators

Inside each room square:

* ▲ Arrow — Room has an **UP** exit
* ▼ Arrow — Room has a **DOWN** exit

These indicate vertical links even when the destination room is on another level.

---

### Corner Dots (Room Contents)

Small colored dots indicate room contents at a glance:

| Dot Color | Meaning                            |
| --------- | ---------------------------------- |
| 🟣 Purple | Monsters present                   |
| 🟢 Green  | Objects present                    |
| 🔵 Blue   | Room details (`set_items`) present |

Dots appear on the room’s corners to avoid covering the room itself.

---

### Camera Controls

* **Click and drag empty space** to pan the map
* The active room stays centered logically but the camera is free-moving

---

## 🧠 Tips & Best Practices

* Use **diagonal rooms sparingly** unless your mudlib supports them
* Name rooms early to avoid duplicate filenames
* Keep object ID names short and lowercase
* Let the base level do the scaling work — don’t over-tune monsters
