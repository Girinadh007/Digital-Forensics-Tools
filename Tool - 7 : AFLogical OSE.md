# Ex.No.07  AFLogical OSE – Android Data Extraction Experiment

##  Aim
To extract and analyze data from an **Android device** using **AFLogical OSE**, an open-source forensic acquisition tool, for recovering call logs, contacts, SMS, and other device data.


##  Description
**AFLogical OSE (Open Source Edition)** is an Android forensic acquisition tool developed by **viaForensics**.  
It is designed to extract logical data (contacts, call logs, SMS, MMS, etc.) from Android devices without rooting.  
The tool generates organized CSV reports that can be analyzed for digital evidence.


##  Tools Required
- AFLogical OSE
- Android device 
- USB Data Cable
- ADB (Android Debug Bridge)  
- Windows/Linux Operating System  
- Forensic workstation / Laptop  


##  Procedure

### Step 1: Prepare the Environment
1. **Install ADB:**
   - Download and install **Android SDK Platform Tools** from Google.  
   - Add the SDK path to your system environment variables.  
   - Verify installation using:
     ```bash
     adb version


2. **Enable Developer Options on Android:**
   - Go to Settings
   - About Phone
   - Tap Build Number seven times to enable developer mode.  
   - Enable USB Debugging under Developer Options.

---

### Step 2: Connect the Android Device
1. **Connect the Device:**
   - Use a USB cable to connect the Android phone to the forensic workstation.  
   - Authorize the connection if a prompt appears on the device.

2. **Verify Connection:**
   - Run:
     ```bash
     adb devices
     ```
   - Ensure the device appears under “List of devices attached”.

---

### 🔹 Step 3: Install AFLogical OSE
1. **Transfer APK:**
   - Push the AFLogical OSE APK file to the Android device:
     ```bash
     adb install AFLogical-OSE.apk
     ```

2. **Launch the Application:**
   - On the device, open **AFLogical OSE** from the app drawer.  
   - Grant necessary permissions for accessing contacts, messages, and logs.

---

### 🔹 Step 4: Perform Data Extraction
1. **Select Data Types:**
   - Choose the data categories you want to extract:
     - Contacts  
     - Call Logs  
     - SMS/MMS  
     - Calendar  
     - Other available options

2. **Start Extraction:**
   - Tap **“Collect Data”** or **“Run Extraction”**.  
   - The tool gathers data and creates a folder named `/forensics/` containing the results.

3. **Retrieve Extracted Data:**
   - Pull the extracted data to your forensic workstation using:
     ```bash
     adb pull /sdcard/forensics/ C:\AFLogical_Output\
     ```

---

### 🔹 Step 5: Analyze Extracted Data
1. **Locate Extracted Files:**
   - Navigate to the output folder.
   - You’ll find csv files such as:
   - contacts.csv calllog.csv  sms.csv mms.csv

2. **Open and Review Files:**
   - Open the csv files in Excel or Notepad++*.
   - Examine entries for timestamps, phone numbers, message content, and call durations.

3. **Document Findings:**
   - Note any relevant evidence such as suspicious contacts, frequent calls, or message keywords.

---

### 🔹 Step 6: Preserve and Report Evidence
1. **Generate Report:**
   - Combine the extracted CSV files into a structured forensic report.  
   - Include hash values, timestamps, and extraction logs.

2. **Preserve Evidence:**
   - Store both the raw extracted files and reports in a secure, write-protected location.  
   - Maintain a chain of custody record for authenticity.

---

##  Result
Successfully extracted data from the Android device using AFLogical OSE.Contacts, call logs, and SMS data were retrieved and exported into csv format for analysis. All extracted evidence was preserved securely for further forensic examination.

---

##  Conclusion
AFLogical OSE is an efficient open-source tool for logical data acquisition from Android devices. It enables investigators to extract crucial user data contacts, messages, and logs) non-invasively, supporting digital investigations while maintaining evidence integrity.
