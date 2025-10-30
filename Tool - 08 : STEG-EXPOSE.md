
# Ex.no.08  Experiment: Using Steg-Expose to Detect Hidden Data in Images

# Aim
To use **Steg-Expose**, an open-source steganalysis tool, to detect hidden data embedded within image files.

# Desription:
Steg-Expose is an open-source steganalysis tool designed to detect hidden data within digital images. It analyzes the statistical properties of image files to identify anomalies that suggest the presence of embedded information. This helps digital forensic investigators uncover steganography methods such as Least Significant Bit (LSB) embedding used to conceal data.


# Tools Required
- **Steg-Expose** (Java-based steganography detection tool)  
- **Java Runtime Environment (JRE)**  
- **Command-line interface (Terminal or Command Prompt)**  


<br>
<br>
<br>
<br>

## Procedure :

### 1. Download and Set Up StegExpose

1.  **Download the tool:** Obtain the `StegExpose.jar` file from the GitHub repository.
2.  **Install Java:** Ensure JRE is installed on your machine.
3.  **Prepare environment:** Place the `StegExpose.jar` file in a dedicated working folder.



### 2. Select Images for Analysis

* Collect the images you suspect might contain hidden data.
* StegExpose supports common image formats such as **.png**, **.jpg**, and **.bmp**.>



### 3. Open Command Line or Terminal

* Navigate to the folder where the `StegExpose.jar` file is located using your Command Prompt (Windows) or Terminal (Linux/macOS).







### 4. Run StegExpose on an Image

* Use the following command structure to analyze a single image for hidden data:

    **Command Structure:**
    ```bash
    java -jar StegExpose.jar <image_file_path>
    ```

    **Example:**
    ```bash
    java -jar StegExpose.jar test_image.png
    ```

### 5. Analyze the Output

* StegExpose calculates a **"suspect" score** ranging from 0 to 1. **The higher the score, the more likely steganography is present.**

* **Example Output Analysis:**
    ```bash
    java -jar StegExpose.jar suspect_image.png
    ```
    ```makefile
    Analyzing suspect_image.png...
    Result: 0.4
    Steganography likely present 

### 6. Batch Analysis (Multiple Images)

* To check multiple images at once, specify the folder path containing the images:

    **Command Structure:**
    ```bash
    java -jar StegExpose.jar <folder_path>
    ```


### 7. Review the Results

* Review the scores generated for each image and use the threshold values to determine which images require further forensic investigation to extract the suspected hidden data.

# Conclusion

Steg-Expose effectively identifies images that may contain steganographic content. It serves as a powerful forensic tool to assist investigators in uncovering hidden information in digital evidence.


# Result
Steg-Expose successfully analyzed the images and detected potential hidden data in files with a high steganalysis score.
