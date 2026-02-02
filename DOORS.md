
# Door & Key System Guide

This guide explains how to create lockable doors and the specific keys required to open them using the MUD World Builder Pro editor.

## The Golden Rule: Matching IDs

The system links a specific key to a specific door using a text **ID**.

* If you tell a door it needs the ID `skeleton_key`...
* ...you must create a Key Item with the ID `skeleton_key`.

If the text matches exactly, the key will open the door.

---

## Step 1: Create Your Key

First, you need to define what the key looks like and give it its unique ID.

1. Navigate to the **Obj** (Objects) tab.
2. Under "Object Library", click the **+ New** button.
3. **Type:** Change the dropdown to **Key**.
4. **ID Name:** This is the most important field. Enter a unique, simple identifier (e.g., `gold_key`, `iron_key`, `cell_key`).
* *Note: Remember exactly what you type here!*


5. **Short/Long:** Give the key a name the player will see (e.g., "a heavy gold key") and a description.
6. Click **Save Changes**.

## Step 2: Configure the Door

Now, tell a specific exit that it is locked and requires that specific key.

1. Navigate to the **Room** tab.
2. Look at the **Exits & Doors** list. Find the direction you want to lock (e.g., North).
3. Click the button labeled **Door (None)** or **Door (Edit)**.
4. **Has Door?** Set this to **Yes**.
5. **State:** Set this to **Locked**. (If you leave it "Closed", players can just open it without a key).
6. **Key ID:** Type the **exact ID** you created in Step 1 (e.g., `gold_key`).
7. Click **Save Changes**.

## Step 3: Place the Key

Creating the key in the library doesn't put it in the game world. You must hide it somewhere for the player to find.

**Option A: Leave it on the floor**

1. Move to the room where you want to hide the key.
2. In the **Obj** tab, look at "Room Contents".
3. Select your key (e.g., "a heavy gold key") from the dropdown menu.
4. Click the **+** button.

**Option B: Give it to a Monster**

1. In the **Mon** tab, create or edit a monster (e.g., "Town Guard").
2. Look for the **Inventory** section in the modal.
3. Select your key from the dropdown and click **+**.
4. Now the player must defeat or pickpocket the monster to get the key.

---

## Quick Tips

* **Case Sensitive:** `Gold_Key` is not the same as `gold_key`. Stick to lowercase to be safe.
* **One Key, Many Doors:** You can use the same Key ID on multiple doors. For example, if you create an `iron_key`, you can set 5 different cell doors to all use `iron_key`. One key will open them all.
* **Forgot to make a Key?** If you set a Door's Key ID to `mystery_key` but forget to create the object in Step 1, the editor will automatically generate a generic key for you when you export. However, it won't have a custom description.