# Metadata-Extraction-using-ExifTool-log2timeline-and-Hidden-Data-Search-using-Steganography-Tools
## AIM:
To extract metadata, perform timeline analysis, and search for hidden data using forensic tools like ExifTool, log2timeline, and steganography detection tools.
## REQUIREMENTS
- **Operating System:** Kali Linux (preferred) or any Linux distro with forensic tools
- **Tools:**
     -  ExifTool – For metadata extraction
     -  plaso/log2timeline – For timeline analysis
- **Steganography tools:** steghide, zsteg, binwalk
- **Test Data:** Image, video, and document files (some with embedded hidden data)
## ARCHITECTURE DIAGRAM
```mermaid
flowchart TD
    A[Sample Files - Images, Videos, Documents] --> B[Metadata Extraction with ExifTool]
    B --> C[Event Timeline Creation with log2timeline]
    C --> D[Hidden Data Search with Steganography Tools]
    D --> E[Evidence Analysis and Documentation]
```
## DESIGN STEPS:
### Step 1:
Use exiftool to extract metadata from files such as images, documents, and videos.

### Step 2:
Use log2timeline and plaso to create and analyze event timelines from system logs and file metadata.

### Step 3:
Apply steganography detection tools like steghide, zsteg, or binwalk to uncover hidden data in media files.

## PROGRAM:
| Step | Action                  | Tool                 | Output                           |
| ---- | ----------------------- | -------------------- | -------------------------------- |
| 1    | Extract file metadata   | ExifTool             | Metadata fields, GPS, timestamps |
| 2    | Generate event timeline | log2timeline / plaso | CSV/HTML timeline                |
| 3    | Search for hidden data  | steghide / binwalk   | Extracted hidden files           |
| 4    | Document findings       | Manual report        | Investigation record             |


## OUTPUT:
### A. Using ExifTool – for file metadata
- **Install:**
```bash
sudo apt update
sudo apt install exiftool -y
```
- **Extract metadata from a file:**
```bash
exiftool image.jpg
```
- **Batch process a folder:**
```bash
exiftool -r /path/to/folder
```
- **Useful flags:**
  
- ```-G: Show metadata group```

- ```-time:all: Show only timestamps```

- ```-GPSLatitude -GPSLongitude: Extract GPS data```
<img width="720" height="495" alt="Screenshot 2025-09-20 185819" src="https://github.com/user-attachments/assets/c9c5ec0f-f029-46a8-9280-0461b95ead1b" />

<img width="670" height="829" alt="Screenshot 2025-09-20 185924" src="https://github.com/user-attachments/assets/673a74f1-c3b6-42b7-9e7f-5dd264bf8eb7" />

<img width="668" height="611" alt="Screenshot 2025-09-20 190340" src="https://github.com/user-attachments/assets/079a8d28-0aec-498e-80d5-5f36e654703d" />


### install log2timeline
```
sudo apt install plaso -y
```

```
sudo apt install steghide -y
```
- **Embed data**
```
steghide embed -cf /home/kali/Downloads/wallpaper.jpg -ef /home/kali/Downloads/secret.txt
```


- **Extract hidden data:**
```
steghide extract -sf hidden.jpg

```
<img width="674" height="626" alt="Screenshot 2025-09-20 192648" src="https://github.com/user-attachments/assets/a7ecf2f7-e4e1-4338-9d96-a68da4c031d2" />

<img width="784" height="111" alt="Screenshot 2025-09-20 192740" src="https://github.com/user-attachments/assets/f7f39a00-1b8e-4e56-a10f-83212bdce1d1" />
<img width="608" height="85" alt="Screenshot 2025-09-20 192756" src="https://github.com/user-attachments/assets/0f644f7c-ac86-477d-922f-9ed998f8043f" />


### Using binwalk – for file analysis
```bash
sudo apt install binwalk -y
binwalk suspicious.jpg
```
```bash
binwalk /home/kali/Downloads/wallpaper.jpg
```
<img width="700" height="684" alt="Screenshot 2025-09-20 194104" src="https://github.com/user-attachments/assets/b917d797-f39c-4220-adb2-d8ee09f86e3a" />


## RESULT:
Metadata was successfully extracted, timeline analysis was completed, and hidden data was identified using steganography tools.
