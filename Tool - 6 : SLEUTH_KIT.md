#  Ex-6.No. — Sleuth Kit: Analyzing Digital Evidence Using Command-Line Tools  

## Aim  
To learn and perform **digital evidence analysis using the Sleuth Kit (TSK)** command-line utilities, including viewing partitions, listing files, recovering deleted data, and examining metadata from a forensic disk image.

---

##  Description  
**The Sleuth Kit (TSK)** is an open-source digital forensic toolkit that provides a collection of command-line tools for investigating disk images, file systems, and volumes.  
It allows forensic examiners to extract information from evidence images such as partitions, deleted files, file metadata, and timestamps.

TSK supports file systems like FAT, NTFS, exFAT, EXT, and HFS.  
It is often used alongside **Autopsy**, but can also be used independently for in-depth forensic analysis at the command line.

---

##  Tools Required  
- **The Sleuth Kit (TSK)** installed on your system  
- A forensic disk image (`.E01`, `.dd`, `.raw`)  
- **Terminal / Command Prompt**  
- Text editor for documenting results  
- (Optional) **FTK Imager** to create forensic image  
- Screenshots of command executions and outputs  

---

##  Procedure  

###  Part 1 — Verify and Prepare the Forensic Image  

1. **Verify Image Integrity**  
   Before starting, verify the hash value (MD5/SHA1) of the image file.
    
   ```bash
   md5sum evidence.dd
   sha1sum evidence.dd
   
 Ensure the computed hash matches the acquisition log.

2. **Identify File System and Partition Details**
   Use the mmls tool to view partition layout:
   
   ```bash
   mmls evidence.dd
   
  Output shows partition offsets, sizes, and types (FAT, NTFS, EXT, etc.).
  
###  Part 2 — Analyzing the File System

1. **List File System Contents**
   Use fls to list files and directories in a partition.
   
   ```bash
   fls -r -o <partition_offset> evidence.dd
   
  -r: recursive listing

  -o: offset (from mmls output)

2. **Extract File Metadata**
   Use "istat" to view metadata of a specific file (by inode number).
   
    ```bash
    istat -o <partition_offset> evidence.dd <inode_number>
    
  Displays creation, modification, access times, size, and file type.

3. **View File Content**
   Extract and view content using "icat":
   
   ```bash
   icat -o <partition_offset> evidence.dd <inode_number> > output.txt
   
  Saves the recovered file content to output.txt.
  
###  Part 3 — File Recovery and Deleted Data

1. **Search for Deleted Files**
   Use fls and look for entries marked as deleted (*).
   
   ```bash
   fls -rd -o <partition_offset> evidence.dd
   
  The -d flag lists deleted files. 
  
2. **Recover a Deleted File**
   Use the inode number of the deleted file with icat:
   
   ```bash
   icat -o <partition_offset> evidence.dd <inode_number> > recovered.jpg
   
  Saves the recovered file to the current directory.
  
3. **Verify the Recovered File**
   Open or hash the recovered file to confirm integrity:
   
   ```bash
   md5sum recovered.jpg

### Part 4 — Timeline and Activity Analysis

1. **Generate a Body File (Timeline Data)**
   Generate a Body File (Timeline Data)
   
   ```bash
   fls -m / -r -o <partition_offset> evidence.dd > bodyfile.txt

3. **Create a Timeline Report**
   Convert the body file to a human-readable format using mactime:
   
   ```bash
   mactime -b bodyfile.txt > timeline.txt
   
  View timeline.txt to analyze user activities based on file creation/modification times.


###  Part 5 — Reporting and Documentation  
1. Compile all evidence findings including partition data, recovered files, and activity timelines.  
2. Summarize the forensic process and tools used during the analysis.  
3. Include screenshots, metadata summaries, and hash verification details.  
4. Prepare a final forensic report in a readable format such as PDF or HTML.  

---

##  Notes  
- Always perform analysis on a **forensic copy**, not the original evidence.  
- Verify and record **hash values** before and after the investigation.  
- Maintain a complete **chain of custody** for all forensic actions.  
- The main tools used from Sleuth Kit include disk structure analysis, metadata extraction, file recovery, and timeline generation.  

---

##  References  
- [The Sleuth Kit Official Documentation](https://sleuthkit.org/sleuthkit/docs.php)  
- Carrier, B. (2005). *File System Forensic Analysis*. Addison-Wesley.  
- [Autopsy & Sleuth Kit GitHub Repository](https://github.com/sleuthkit/sleuthkit)  

---

##  Result  
Successfully analyzed digital evidence using **The Sleuth Kit (TSK)**.  
Partitions were identified, file systems examined, deleted data recovered, and a forensic timeline was created.  
The experiment demonstrates the complete process of evidence analysis and reporting using Sleuth Kit.
   
