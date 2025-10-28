#  Ex.No.2    TestDisk: Open-Source Data Recovery Tool

## Aim :
To use TestDisk step by step to recover a missing partition and repair a corrupted one.



## 🛠️ Installation
Linux (Debian/Ubuntu): sudo apt-get install testdisk

macOS (Homebrew): brew install testdisk

Windows: Download the executable from the official CGSecurity website.

## Procedure

### 1. Create a Log File
- Launch TestDisk from your terminal or command prompt using sudo testdisk (or testdisk_win.exe on Windows).

- Select the [Create] option to generate a log file of the recovery session. This is helpful for future reference or troubleshooting.
- <img width="1919" height="1079" alt="Screenshot 2025-09-01 211458" src="https://github.com/user-attachments/assets/753b8f88-e9dd-43c4-b73e-5bbbc5036367" />

<br>
<br>

### 2. Select the Drive to Analyze
- TestDisk will display a list of all detected storage devices.

- Use the Up/Down arrow keys to highlight the drive that contains your lost data.

<br>
<br>

<img width="1919" height="1079" alt="Screenshot 2025-09-01 211516" src="https://github.com/user-attachments/assets/b28d7541-83b3-48d3-8f10-3b4ed9f901b0" />


</p>
<br>
<br>

- Select [Proceed] to move to the next step.

### 3. Choose the Partition Table Type
- TestDisk will automatically suggest the most likely partition table type (e.g., Intel/PC, EFI GPT).

- The default value is usually correct. Confirm the selection by pressing Enter.
<br>
<br>
<img width="1919" height="1079" alt="Screenshot 2025-09-01 211539" src="https://github.com/user-attachments/assets/c1700f40-a8e8-4955-be87-fc9289ba9e3a" />

</p>
<br>
<br>

### 4. Analyze Current Partition Structure
- From the main menu, choose [Analyse] and press Enter.
<br>
<br>
<img width="1919" height="1079" alt="Screenshot 2025-09-01 211555" src="https://github.com/user-attachments/assets/6c91e445-e9bb-4f9e-856c-04ff992608b8" />

</p>
<br>
<br>

- This will display the current partition table and check for errors or missing partitions.

### 5. Perform a Quick Search
- After the analysis, you will be prompted to perform a [Quick Search].

<br>
<br>
<img width="1919" height="1079" alt="Screenshot 2025-09-01 211618" src="https://github.com/user-attachments/assets/da5e0376-4d24-47f7-9985-8e28a978e473" />

</p>
<br>
<br>

- Select it and press Enter to scan the drive for lost partitions.

- Once a partition is found, you can press p to list its files. Deleted files and folders often appear in red.

- Press q to return to the search results.

  ### 6. Perform a Deeper Search
- If the Quick Search fails to find your lost partitions, select [Deeper Search].

-<br>
<br>
<img width="1919" height="1079" alt="Screenshot 2025-09-01 213309" src="https://github.com/user-attachments/assets/3cb752c4-4454-40a7-b08b-3592d355b2af" />

</p>
<br>
<br>

- This process can take a long time, as it scans the entire drive, block by block, to find remnants of partition structures.

- Again, use p to preview files and confirm if a found partition is the one you are looking for.

### 7. Modify Partition Status
- After finding the correct partitions, use the Left/Right arrow keys to set their status.

- Use **Left/Right arrow keys** to change status:  
  - **P**: Primary  
  - ***:** Bootable  
  - **L**: Logical  
  - **D**: Deleted

    <br>
<br>
<img width="1919" height="1079" alt="Screenshot 2025-09-01 213243" src="https://github.com/user-attachments/assets/22d967ca-f17a-4e46-8cbb-c48745417647" />

</p>
<br>
<br>

- Ensure that the partitions you want to recover are marked as Primary or Logical (and not deleted).

### 8. Write the Partition Table
- Once you are confident the partition structure is correct, select [Write] from the menu.

<br>
<br>
<img width="908" height="419" alt="Screenshot 2025-09-02 002113" src="https://github.com/user-attachments/assets/04ca9467-59f3-44d7-b241-5ce28faba72e" />

<br>
<br>

- Confirm the operation by pressing y (for yes). This will write the new partition table to your disk.

<br>
<br>
<p align="center">
<img width="963" height="471" alt="Screenshot 2025-09-02 002126" src="https://github.com/user-attachments/assets/296b6560-ed29-47ca-92ec-68735c7cc79a" />

</p>
<br>
<br>


- WARNING: This is a permanent change. Double-check your selections before writing.

### 9. Recover Files
- If you just need to recover a few files without fixing the partition table, you can do so from the file list (after pressing p).

- Navigate to the folder containing your desired files.

- Use the colon : key to select the files you want to recover.

- Press the uppercase C key to copy the selected file(s).

- Navigate to a safe destination on a different storage device and press uppercase C again to paste.

### 10. Exit and Restart
- Once your task is complete, select [Quit] to exit the program.

- If you wrote a new partition table to the drive, it is recommended to restart your computer to allow the operating system to recognize the changes.

</p>
<br>
<br>


- If you wrote a new partition table to the drive, it is recommended to restart your computer to allow the operating system to recognize the changes.
