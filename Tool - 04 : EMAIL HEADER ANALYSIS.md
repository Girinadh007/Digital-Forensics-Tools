# Ex.No.4   MHA (Mail Header Analyzer)
## Aim :
- The aim is to use a Mail Header Analyzer (MHA) to trace an email's origin and verify its authenticity by examining its header for signs of spoofing.
## Procedure
### Step 1: Get the Email Header
- First, you need to copy the full, raw header from the email.

- Gmail: Open the email, click the three dots (⋮), and select Show original.
<br>
<img width="1919" height="1079" alt="Screenshot 2025-09-02 003120" src="https://github.com/user-attachments/assets/e5eb9715-8520-4269-bf1c-c0943b40ba26" />

<br>
<br>
<br>
Select all the text in the header and copy it.

<br>
<img width="1511" height="973" alt="Screenshot 2025-09-02 003233" src="https://github.com/user-attachments/assets/f673535a-4bc8-4d43-a1d7-974ca439f314" />

<br>
<br>

### Step 2: Use MXToolbox Email Header Analyzer
- The easiest way to analyze the header is with an online tool.

- Navigate to a site MXToolbox Email Header Analyzer.
 <br>
<br>

<img width="1919" height="1029" alt="Screenshot 2025-09-02 003319" src="https://github.com/user-attachments/assets/33e55512-702e-47b7-8724-81d17b4d5f09" />

<br>
<br>

- Paste the entire header you copied into the analysis box.
<br>
<br>

Click the "Analyze" button to get a parsed, easy-to-read report.
<br>
<br>

<img width="1919" height="1034" alt="Screenshot 2025-09-02 003350" src="https://github.com/user-attachments/assets/8b11f7da-a26f-48fe-965c-ff807f1bf583" />

### Step 3: Check Delivery Information
- Review the delivery path shown in MXToolbox results.
- Confirm whether the email passed through legitimate mail servers.
- Note the relay delays and source authentication.
<br>
<br>
<img width="1898" height="916" alt="Screenshot 2025-09-02 003446" src="https://github.com/user-attachments/assets/6b0d7dad-fc8c-460c-ba8f-d5bdb8cc49c3" />


<br>
<br>

### Step 4: Verify SPF, DKIM, and DMARC
Examine the authentication checks: SPF, DKIM, and DMARC.
Ensure all are marked as aligned/authenticated.
This confirms the email is not spoofed or altered.

  <br>
  <br>
<img width="1898" height="943" alt="Screenshot 2025-09-02 003517" src="https://github.com/user-attachments/assets/0cd8cc35-9170-4230-a219-9bacadc75122" />

<br>
<br>

### Step 5: Interpret Results
- Analyze whether the email is DMARC compliant and trusted.
- Look at each test (SPF, DKIM, DMARC) for pass/fail status.
- Conclude if the email is legitimate or potentially malicious.

<br>
<img width="1878" height="652" alt="Screenshot 2025-09-02 003653" src="https://github.com/user-attachments/assets/b44da91a-0544-44af-98fb-8e930f0c8c4e" />
<br>
<br>

### Result:
The email header analysis confirms that the tested email is authentic, as it complies with DMARC policy and passes SPF and DKIM verification. This demonstrates that proper email authentication mechanisms effectively prevent spoofing and ensure secure email delivery.
