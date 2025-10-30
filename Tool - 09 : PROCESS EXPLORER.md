# Ex.No.09 Using Process Explorer to Identify Suspicious Processes

## **Aim**
To use Microsoft Sysinternals **Process Explorer** to monitor system activities and identify any **suspicious or malicious processes** running on a Windows computer.

## **Description**
Process Explorer is a part of the **Microsoft Sysinternals Suite**. It is a powerful tool used to view detailed information about system processes.  
It helps investigators and administrators analyze active processes, detect suspicious behavior, monitor CPU and memory usage, and verify process authenticity using digital signatures.

## **Tools**
- Windows operating system  
- Internet connection  
- **Process Explorer** (from Microsoft Sysinternals)  

## **Step-by-Step Procedure**

### **Step 1: Download and Setup Process Explorer**
1. Go to the official Microsoft Sysinternals website:  
2. Click **Download Process Explorer**.
3. Extract the downloaded ZIP file to a folder.
4. Right-click `procexp64.exe` (for 64-bit) or `procexp.exe` (for 32-bit) → select **Run as Administrator**.



### **Step 2: Understand the Interface**
1. The main window displays all running processes in a **hierarchical tree view**.
2. Each process shows details such as **PID**, **CPU usage**, **memory usage**, and **company name**.

<img width="1919" height="1079" alt="Screenshot 2025-10-28 224451" src="https://github.com/user-attachments/assets/d280b5b4-76cf-407f-9579-3674d6bd2099" />



### **Step 3: Identify Suspicious Processes**
1. Look for **unfamiliar or oddly named processes** (e.g., `xkdjeo.exe`, `randomname123.exe`).
2. Check the **Company Name** and **Description**:
   - Legitimate software usually shows known publishers like *Microsoft*, *Intel*, or *Adobe*.
3. Right-click the process → **Properties** → go to the **Image** tab.
4. Verify the **Path** of the executable file:
5. Check for **Digital Signature**:
   - Valid signature = trusted developer  
   - No signature or invalid = possibly malicious
<img width="1915" height="1079" alt="Screenshot 2025-10-28 224554" src="https://github.com/user-attachments/assets/0d7e70e4-6e79-428d-94bb-64acdf89107f" />

---

### **Step 4: Analyze Process Behavior**
1. Observe **CPU**, **Memory**, and **I/O usage** columns.
2. If a small or unknown process consumes **excessive CPU or memory**, it may be malicious.
3. Right-click the process → **Properties** → go to the **TCP/IP tab**.
   - Check if it communicates with **unknown external IP addresses**.
4. Examine **Handles** and **DLLs** tabs for suspicious loaded files or libraries.
<img width="1913" height="1079" alt="Screenshot 2025-10-28 224813" src="https://github.com/user-attachments/assets/9cc3d3a4-5c49-4e0a-9163-b902b41585f8" />


### **Step 5: Verify Process Legitimacy**
1. Search the process name on Google.  
   Example: `svchost.exe` vs `svhost.exe` (one letter missing — suspicious).
2. Visit virustotal official website
   - Upload the process file or search its name to verify if it’s reported as malware.
3. Cross-check with **ProcessLibrary.com** or official vendor websites for authenticity.
   
![images/exp9-disk-step2.png](https://github.com/baddiputi/Digital-Forensic-Lab-Exercises/blob/326db74a3770e2ba22207f5a48b737f17307f683/images/9.6.jpeg)

### **Step 6: Take Appropriate Action**
1. **If the process is confirmed malicious:**
   - Right-click the process → **Kill Process** to stop it.
   - Delete the corresponding executable file from its path.
2. **If unsure:**
   - Right-click → **Suspend Process** to stop it temporarily for investigation.
3. **After removal:**
   - Run a **Full System Scan** using Windows Defender or Malwarebytes to ensure no remnants remain.
     
<img width="1919" height="1079" alt="Screenshot 2025-10-28 224928" src="https://github.com/user-attachments/assets/cf5137d4-7555-4c96-9651-b74d10d5534a" />

### **Step 7: Example Observation**
You find `example_template.pdf` consuming 70% CPU.  
- **Path:** `C:\Users\pedap\AppData\Temp\faangpath_simple_template.pdf`  
- **Digital Signature:** None  
- **Company Name:** Unknown  
- **Network Activity:** Shows connections to unknown IPs in the TCP/IP tab  
- **Online Check:** VirusTotal confirms it as a **known trojan**  
- **Action Taken:** Suspended → Killed → Deleted file → Performed full antivirus scan  

![images/exp9-disk-step2.png](https://github.com/baddiputi/Digital-Forensic-Lab-Exercises/blob/326db74a3770e2ba22207f5a48b737f17307f683/images/9.9.jpeg)



## **Result**
Using Process Explorer, suspicious processes were successfully identified by examining their **CPU usage**, **path**, **digital signature**, and **network activity**. Confirmed malicious processes were terminated and removed to maintain system integrity.

