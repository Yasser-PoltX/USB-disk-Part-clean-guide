# 🧨 USB DiskPart Clean Guide (Windows)

A simple, **100% reliable method** to fully clean and reformat a USB flash drive using **DiskPart** on Windows.

This guide is useful when:

* The USB does not appear in BIOS / Boot Menu
* The USB was previously used for Linux ISO and is corrupted
* Rufus fails or the flash drive behaves strangely

---

## ⚠️ Warning (Important)

> **This method will ERASE EVERYTHING on the USB drive permanently.**

Make sure you select the **correct disk number**. Selecting the wrong disk may erase another drive.

---

## 🛠 Requirements

* Windows 10 / 11
* USB flash drive
* Administrator access

---

## 🚀 Step-by-Step DiskPart Method

### 1️⃣ Open Command Prompt as Administrator

* Press **Win + S**
* Type `cmd`
* Right-click **Command Prompt** → **Run as administrator**

---

### 2️⃣ Start DiskPart

```txt
diskpart
```

---

### 3️⃣ List all disks

```txt
list disk
```

You will see something like:

```txt
Disk 0  512 GB
Disk 1  120 GB
Disk 2   16 GB
```

📌 The USB is usually the **smallest size** (e.g., 16GB).

---

### 4️⃣ Select the USB disk

(Replace `2` with your actual disk number)

```txt
select disk 2
```

---

### 5️⃣ Clean the USB (VERY IMPORTANT)

```txt
clean
```

✔ This removes all partitions and boot records completely.

---

### 6️⃣ Create a new primary partition

```txt
create partition primary
```

---

### 7️⃣ Format as FAT32 (Recommended for Linux boot)

```txt
format fs=fat32 quick
```

---

### 8️⃣ Assign a drive letter

```txt
assign
```

---

### 9️⃣ Exit DiskPart

```txt
exit
```

---

## ✅ Result

Your USB is now:

* Fully cleaned
* Properly formatted
* Ready for ISO burning with **Rufus**

---

## 🔥 Recommended Rufus Settings (After This)

* Partition scheme: **MBR**
* Target system: **BIOS or UEFI**
* File system: **FAT32**
* Write mode: **ISO Image mode**

---

## 📌 Notes

* This method works even if Windows File Explorer cannot format the USB
* Safe for old and new laptops
* Ideal before installing Linux distributions (Kubuntu, Fedora, Arch, etc.)

---

## 📜 License

MIT License — Free to use, modify, and share.

---

⭐ If this guide helped you, consider starring the repository!
