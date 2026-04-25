# 🗂️ File Organizer

A Python automation script that automatically organizes messy files into categorized folders.

---

## 📌 About This Project

This project was built to solve a common problem — messy Downloads folders!
The script scans a folder and automatically sorts every file into the correct category folder based on its file type.

---

## ⚙️ How It Works

| File Type | Goes Into Folder |
|---|---|
| .jpg, .png, .gif | 📸 Images |
| .mp4, .mkv, .avi | 🎬 Videos |
| .mp3, .wav, .aac | 🎵 Music |
| .pdf, .docx, .txt | 📄 Documents |
| .xlsx, .csv | 📊 Excel |
| .zip, .rar | 🗜️ Archives |
| .py, .js, .html | 💻 Code |
| Everything else | 📦 Others |

---

## 🛠️ Technologies Used

- **Language:** Python 3
- **Libraries:** os, shutil, pathlib (all built-in — no installation needed!)

---

## ▶️ How to Run

1. Make sure Python is installed on your PC
2. Open the file `file_organizer.py`
3. Change line 7 to your folder path:
```python
my_folder = r"C:\Users\YourName\Downloads"
```
4. Run the script:
```bash
python file_organizer.py
```

---

## 📸 Output Example

```
Starting file organizer...
Folder: C:\Users\harsh\Downloads
----------------------------------------
Moved: photo.jpg  -->  Images/
Moved: resume.pdf  -->  Documents/
Moved: song.mp3  -->  Music/
----------------------------------------
Done! Total files moved: 3
```

---

## 👨‍💻 Author

**Harsh Patel**
BSc IT Student — GLS University, Ahmedabad
GitHub: github.com/harshpatel-15
