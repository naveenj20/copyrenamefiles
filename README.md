# NAME: NAVEEN JAISANKER
# REG. NO.: 212224110039

# Exercise 6: Copy and Rename Files

## Objective
To develop a UiPath workflow that copies all files from a source folder to a destination folder and renames them by appending a timestamp to their file names.

---

## Procedure

### Step 1: Setup Folders
- Create a folder named **SourceFolder** and place some sample files (e.g., `.txt`, `.docx`).  
- Create another folder named **DestinationFolder** where files will be copied.  

---

### Step 2: Create Project
- Open **UiPath Studio**.  
- Create a new Process → Name it **CopyAndRenameFiles**.  

---

### Step 3: Define Variables
- `sourcePath` *(String)* = `"C:\RPA\SourceFolder"`  
- `destinationPath` *(String)* = `"C:\RPA\DestinationFolder"`  
- `files` *(Array of String)*  

---

### Step 4: Get Files from Source
- Use **Assign**:  
  ```vb
  files = Directory.GetFiles(sourcePath)

### Step 5: Loop Through Files and Copy with Timestamp

Add a For Each activity:

TypeArgument = String

Values = files

Inside the loop:

Assign → fileName = Path.GetFileNameWithoutExtension(item)

Assign → ext = Path.GetExtension(item)

Assign → timestamp = DateTime.Now.ToString("yyyyMMddHHmmss")

Assign → newName = destinationPath + "\" + fileName + "_" + timestamp + ext

Copy File →

From: item

To: newName

### Workflow

Your workflow consists of:

Assign → Get all files from SourceFolder.

For Each → Loop through each file.

Assigns inside loop → Extract file name, extension, timestamp, and create new name.

Copy File → Copy to DestinationFolder with renamed output.


### Output
Before Execution:
<img width="1920" height="1200" alt="Screenshot (148)" src="https://github.com/user-attachments/assets/63e97e93-3918-44f7-92fc-01185d5cf981" />

SourceFolder contains:
report.txt
notes.docx


DestinationFolder is empty.

After Execution:

<img width="1920" height="1200" alt="Screenshot (149)" src="https://github.com/user-attachments/assets/b6795d0f-5add-4236-b7c0-1aa3bde4040e" />

DestinationFolder contains:

report_20250926183733.txt
notes_20250926183733.docx

### Result

Thus, the UiPath workflow for copying files from a source folder to a destination folder and renaming them with a timestamp was executed successfully.
