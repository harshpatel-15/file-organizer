import os
import shutil

# ─────────────────────────────────────
# STEP 1: Set the folder you want to clean
# Change this path to your folder


# ───────────────────────────────────── 
my_folder = r"C:\Users\Harsh\Downloads"


# ─────────────────────────────────────
# STEP 2: Define file types and folder names
# Key   = folder name that will be created
# Value = list of file extensions   
# ─────────────────────────────────────
file_types = {
    "Images"    : [".jpg", ".jpeg", ".png", ".gif", ".bmp"],
    "Videos"    : [".mp4", ".mkv", ".avi", ".mov"],
    "Music"     : [".mp3", ".wav", ".aac", ".flac"],
    "Documents" : [".pdf", ".doc", ".docx", ".txt"],
    "Excel"     : [".xls", ".xlsx", ".csv"],
    "Archives"  : [".zip", ".rar", ".tar", ".gz"],
    "Code"      : [".py", ".js", ".html", ".css", ".java"],
    "Others"    : []   # All unknown files go here
}


# ─────────────────────────────────────
# STEP 3: Function to find folder name
# Give it a file like "photo.jpg"
# It returns "Images"
# ─────────────────────────────────────
def get_folder_name(filename):

    # Get the extension  e.g.  "photo.jpg"  -->  ".jpg"
    extension = os.path.splitext(filename)[1].lower()

    # Check which category it belongs to
    for folder_name, extensions in file_types.items():
        if extension in extensions:
            return folder_name

    # If no match found, return Others
    return "Others"


# ─────────────────────────────────────
# STEP 4: Main function - organize files
# ─────────────────────────────────────
def organize():
    print("Starting file organizer...")
    print(f"Folder: {my_folder}")
    print("-" * 40)

    # Count how many files we move
    count = 0

    # Loop through every item in the folder
    for filename in os.listdir(my_folder):

        # Full path of the file
        # e.g.  C:\Users\YourName\Downloads\photo.jpg
        file_path = os.path.join(my_folder, filename)

        # Skip if it is a folder (not a file)
        if os.path.isdir(file_path):
            continue

        # Find which folder this file should go into
        destination_folder = get_folder_name(filename)

        # Full path of the destination folder
        # e.g.  C:\Users\YourName\Downloads\Images
        destination_path = os.path.join(my_folder, destination_folder)

        # Create the folder if it does not exist
        if not os.path.exists(destination_path):
            os.makedirs(destination_path)

        # Move the file into the folder
        shutil.move(file_path, os.path.join(destination_path, filename))

        print(f"Moved: {filename}  -->  {destination_folder}/")
        count += 1

    # Done!
    print("-" * 40)
    print(f"Done! Total files moved: {count}")


# ─────────────────────────────────────
# STEP 5: Run the program
# ─────────────────────────────────────
organize()
