# 🧱 Scratch 2D Room Designer

A simple Excel-based level designer that helps you build layouts for 2D Scratch games. Design rooms on a grid visually, then export clean coordinate data directly into Scratch.

---

## 🚀 Features

- Visual layout editor in Excel  
- Exports clean brick coordinates for Scratch  
- Grid-based structure, ideal for platformer games
- Easy to integrate into your Scratch clone system  

---

## 🛠 How to Use

### 1️⃣ Design Your Room in Excel

Open `room_designer.xlsx` and follow these steps:

- The **first row** contains X-coordinate values (in pixels).
- The **first column** contains Y-coordinate values (in pixels).
- Use `#` to mark a tile that should become a **brick**.

#### Example Layout:

|       | -228 | -204 | -180 |
|:-----:|:----:|:----:|:----:|
| -96   |      |  #   |      |
| -120  |  #   |      |  #   |

✅ This layout produces bricks at:
- `(-204, -96)`
- `(-228, -120)`
- `(-180, -120)`

---

### 2️⃣ Export Brick Coordinates

Run the macro `ExportBrickCoordinates`:

1. Press `ALT + F8` to open the **Macro menu**.  
2. Select `ExportBrickCoordinates` and click **Run**.  
3. A file named `roomData.txt` will be created in the same folder as your Excel file.

📄 The file contains one coordinate per line:

```
-204
-96
-228
-120
-180
-120
```

---

### 3️⃣ Import into Scratch

1. Open your Scratch project.  
2. Read the contents of `roomData.txt` into a list (e.g., `The_clone_data`).  
3. Each pair of values (`x`, then `y`) represents one brick’s position.  
4. In your setup script, loop through the list and use `create clone of [brick]` at those positions.

---

## 🧑‍💻 Editing the Script (Optional)

To view or modify the macro:

1. Press `ALT + F11` to open the **VBA Editor**.  
2. Go to `VBAProject` → `Modules` → `Module1`.  
3. You'll find `ExportBrickCoordinates` — the macro that handles export logic.

---

## 📘 License

MIT – Free to use, modify, and distribute.

---

Made with ❤️ for Scratch educators and students.
