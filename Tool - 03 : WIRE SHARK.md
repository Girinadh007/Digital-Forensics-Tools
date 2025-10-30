#   Ex.No.3   Wireshark – Network Packet Capture and Analysis Tool
## Procedure: Capturing Plaintext Passwords

### Step 1: Start Capturing Packets
- First, open Wireshark. Select the interface your computer is using to connect to the internet (in this case, Wi-Fi).
<img width="1919" height="1079" alt="Screenshot 2025-09-02 001311" src="https://github.com/user-attachments/assets/3deb7ea3-eca3-48d6-bf30-c9f200c95372" />

  </p>
  - Click the blue shark fin icon 🦈 in the top-left corner to start the capture. Wireshark will immediately begin capturing all traffic passing through that interface.
 <br>
   <br>
<img width="1919" height="1079" alt="Screenshot 2025-09-02 001349" src="https://github.com/user-attachments/assets/f219207f-54af-4ef1-be78-e2258d504442" />

 </p>
 
   ### Step 2: Generate Login Traffic
  - Open a web browser and navigate to http://testphp.vulnweb.com/login.php.

- Enter any dummy credentials. For this example, we'll use:

   Username: Girinadh

   Password: Helloworld

- Click the login button. The login will fail, but the data has already been sent across the network.

<img width="1919" height="1079" alt="Screenshot 2025-09-02 001514" src="https://github.com/user-attachments/assets/16254ad5-a4c8-4228-af43-127d51a4ecd5" />

 </p>
  
  ### Step 3: Stop Capture and Filter Traffic

- Return to Wireshark and click the Stop button (the red square).

- In the display filter bar, you need to find the packet containing the login data. Since the form data was sent to the server, we will look for an HTTP POST request.

- Apply the following filter to find the exact packet and press Enter:

<img width="1919" height="1079" alt="Screenshot 2025-09-02 001930" src="https://github.com/user-attachments/assets/6540d9cf-871b-42f0-b312-3a6683d8fda2" />

 </p>

### Step 4: Inspect the Packet to Find Credentials 

- In the filtered packet list, you should see a packet with information like "POST /userinfo.php". Select this packet.

- In the Packet Details pane below the list, expand the following sections:

Hypertext Transfer Protocol
HTML Form URL Encoded
- Inside the "HTML Form URL Encoded" section, you will see the credentials you entered in plaintext.
<img width="1919" height="462" alt="Screenshot 2025-09-02 002004" src="https://github.com/user-attachments/assets/8542cb0d-b07d-48e0-bd70-62187b5b320f" />

 </p>
---

## Result
The experiment successfully intercepts the login credentials in a human-readable format. The analysis of the captured POST packet reveals the plaintext data that was transmitted over the network:

This result confirms the inherent security flaw of the HTTP protocol. Any sensitive data sent over HTTP is transmitted openly, making it trivial to intercept.
