# 📂 Moving Folders and Renaming in Terminal: My Guide (Ubuntu/Linux)

This help guide explains how to move and rename folders and files using the Ubuntu Terminal. In Linux, we use the `mv` command (short for **move**).

---

## 🗺️ Understanding Your Locations

The **Home** directory is your primary "hub." While the **Desktop** is a popular place to store files, it is actually just a folder inside your Home.

* **Home (`~`)**: Your main folder. It is the default starting point for the Terminal.
* **Desktop (`~/Desktop`)**: A sub-folder inside Home.

> [!Note]
> **The Tilde (`~`):** In the Ubuntu Bash terminal, is just a shortcut for your Home directory. If you are already "located" in your Home folder, you don't actually need to use it!

---

## 🔍 See Where You Are

Before moving things, you need to know exactly what your folders are named.

1. **`pwd`**: (**P**rint **W**orking **D**irectory) Shows exactly where you are standing.
2. **`ls`**: (**L**i**s**t) Shows you every file and folder in your current location.
3. **`ls [Folder Name]`**: This lets you "peek" inside a folder to see the subfolders (nested folders) without moving into it. **Example:** `ls Documents` will show you what's inside Documents.

---

## 🚀 The Basic Logic

The command always follows this simple pattern:
`mv [Source: What to move] [Destination: Where to go]`

---

## 📂 Moving a Nested Folder (Folder inside a Folder)

If you have a folder called `Drafts` that is sitting inside `Projects`, and you want to move it to your `Archive` folder:

**The Command:**
`mv Projects/Drafts Archive/`

**How it works:**

* **`Projects/Drafts`**: You are telling the terminal to "Look inside Projects, then grab Drafts."
* **`Archive/`**: This is where you want to drop it.

> [!Tip]
> After this command, `Drafts` will no longer be inside `Projects`. It has been physically moved to `Archive`.

---

## 📥 Scenario: Moving Folders within Home

If you have a folder named `Projects` and you want to move it into `Archive`:

```bash
# Basic move (No tilde needed if you are already in Home)
mv Projects Archive/

# If the folder name has a space, use quotes:
mv "My Projects" Archive/
```

---
## ✏️ Renaming Files and Folders

There is no dedicated `rename` command for this basic tasks, instead, the `mv` command is used. When you "move" a file to a location but give it a different name and the location dose not exist, the system simply renames it.

> [!Tip]
> Just make sure that the new folder or file name dose not exist as this will just move it to that file or folder, If unsure use the `ls` command to check before renaming and the `-i` for safety see the *Beginner Superpowers Section* for more information. `mv -i old_folder/ new_folder/`  

### How it Works
To rename an object, specify the current filename followed by the new filename:

| Rename | Old to New |
| :--- | :--- |
| **Rename a File** | `mv old_file.txt new_file.txt` |
| **Rename a Folder** | `mv old_folder/ new_folder/` |

### Example
If you have a file named `notes.txt` and you want to change it to `final_notes.txt`, run:

```bash
mv notes.txt final_notes.txt
```
___

## 💡 Beginner Superpowers

### 1. The "Tab" Key (Your Best Friend) ⚡

**Never type out a full folder name.** It leads to typos and frustration.

* Type `mv Pro` + **[Tab]**. It will finish the word `Projects/`.
* Then type `Dra` + **[Tab]**. It will finish the word `Drafts/`.
* The terminal handles all the slashes and spaces for you!

### 2. Use `ls` Constantly

If a command fails, it's usually because a folder name is slightly different than you thought. Type `ls` to see the real names, then use **Tab** to select them.

### 3. Safety First (`-i`)

Add `-i` (interactive) to have the terminal ask "Are you sure?" before it overwrites an existing folder:

* `mv -i Projects/Drafts Archive/`

---

### ⚠️ Disclaimer

This is provided "as is" without warranty of any kind. I am not responsible for any damage, data loss, or issues caused by the use of this information. **Use it at your own risk.**
