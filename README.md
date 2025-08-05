*COMPANY*: CODTECH IT SOLUTIONS

*NAME*: VEDANT AVINASH PATIL

*INTERN ID*: CT04DH2352

*DOMAIN*: CYBER SECURITY & ETHICAL HACKING

*DURATION*: 4 WEEKS

*MENTOR*: NEELA SANTOSH




        Task 1:BUILD A TOOL TO MONITOR CHANGES IN FILES BY CALCULATING AND COMPARING HASH VALUES (FILE INTEGRITY CHECKER).


1.calculate_file_hash(filepath): This function takes a file path as input and calculates its SHA256 hash. It reads the file in chunks to efficiently handle large files and returns the hash as a hexadecimal string.
2.monitor_file_changes(filepath, stored_hash=None): This function is the core of the file monitoring tool. It takes a file path and an optional stored_hash as input.
    a. If no stored_hash is provided (which happens on the first check), it calculates and prints the initial hash of the file and returns the current hash along with None for the change status.
    b. If a stored_hash is provided, it calculates the current hash of the file and compares it to the stored_hash. It then prints whether the file has changed, along with the previous and current hashes if it has changed. It returns the current hash and a boolean value           (True if changed, False if not changed).
    
The subsequent code cells demonstrate how to use these functions:

  a.A dummy file named my_test_file.txt is created with initial content.
  b.monitor_file_changes is called for the first time to get the initial hash of the dummy file.
  c.The dummy file is modified by adding new content.
  d.monitor_file_changes is called again, this time providing the initial_hash to check for changes.
  e.Finally, the dummy file is removed for cleanup.
  
This setup allows you to track whether the content of a file has been altered since a previous check by comparing their hash values.



        Task 2: DEVELOP A TOOL TO IDENTIFY COMMON VULNERABILITIES (E.G., SQL INJECTION, XSS) IN WEB APPLICATIONS (WEB APPLICATION VULNERABILITY SCANNER).


The task at hand is to develop a web vulnerability scanning tool using the Python programming language, leveraging popular libraries such as requests for making HTTP requests and BeautifulSoup for parsing HTML content. The overarching objective is to create a functional scanner that can identify common security weaknesses within web applications.

Our initial focus is on two prevalent vulnerability types: SQL Injection and Cross-Site Scripting (XSS). For SQL Injection, the tool aims to detect vulnerabilities by identifying potential input points on a webpage, such as form fields and URL parameters. It then crafts and sends specially designed payloads (e.g., single quotes, boolean-based conditions) to these input points. By analyzing the web application's response for tell-tale signs like database error messages or unexpected content changes, the scanner can flag potential SQL Injection flaws.

For XSS detection, the tool also examines input fields. It injects simple script payloads into these fields and checks if these scripts are reflected back in the web page's HTML source code. While a full exploitation requires a browser, the reflection of the payload indicates a potential vulnerability where malicious scripts could be executed in a user's browser.

Currently, we have laid the foundation for the scanner by implementing the core functionality to fetch web pages and parse their content. We have integrated basic modules for both SQL Injection and XSS checks, which can identify simple cases of these vulnerabilities. The ongoing development involves enhancing the sophistication of these checks, including using a wider array of payloads and more robust response analysis techniques. Future work will also focus on improving the tool's usability, such as adding options for scanning multiple targets, handling different types of web requests (like POST), and incorporating a clear reporting mechanism to summarize findings. The ultimate goal is to build a practical tool for basic web security testing.



        Task 3: BUILD A TOOLKIT WITH MULTIPLE MODULES (E.G., PORT SCANNER,BRUTE-FORCER) FOR PENETRATION TESTING (PENETRATION TESTING TOOLKIT).

        

This task involves building a modular penetration testing toolkit in Python. The plan outlines the creation of a project with a clear structure, including dedicated directories for different modules like a port scanner and a brute-forcer.

The Port Scanner Module will focus on developing code to identify open ports on a target host. This involves implementing network communication logic, handling different port ranges, and incorporating error handling for network issues or invalid inputs. Comprehensive documentation will be added to explain its functionality.

The Brute-Forcer Module will aim to implement a function or class for attempting to discover credentials for services like SSH or FTP. Key aspects include handling lists of usernames and passwords, implementing robust error handling, and incorporating rate-limiting to prevent account lockouts or triggering security alerts. Docstrings will detail its usage and parameters.

The Main Toolkit Script will serve as the central control point. It will use a command-line interface (CLI) built with a library like argparse to allow users to choose which module to run and provide necessary arguments like the target host, port range, or credential file paths. Help messages and usage examples will be included for user guidance.

Finally, Documentation and Testing will be crucial steps. Detailed documentation will be written in a README file, explaining installation, configuration, and usage of the entire toolkit. Unit tests will be developed for individual functions within each module to ensure their correctness, and integration tests will verify that the main script correctly interacts with the modules. This comprehensive approach ensures the toolkit is well-documented, functional, and reliable for authorized penetration testing activities.

        
        
        Task 4:BUILD A TOOL TO ENCRYPT AND DECRYPT FILES USING ADVANCED ALGORITHMS LIKE AES-256(ADVANCED ENCRYPTION & DECRYPTION TOOL).


  The code you've selected creates a self-contained, secure tool for file encryption and decryption that runs entirely within a web browser. Its primary purpose is to allow a user to lock a file with a password (encryption) and unlock it later with the same password (decryption), without the file ever leaving their computer.
  
  The user interface is built with HTML and styled using Tailwind CSS to be modern, clean, and user-friendly. It features a simple layout with an input for file selection, a field for a password, and two distinct buttons: "Encrypt" and "Decrypt." A status area provides real-time feedback on the process, confirming success or reporting errors.

The core of the application's security lies in its use of the browser's built-in Web Crypto API, a powerful and standardized JavaScript library for performing cryptographic operations. The chosen algorithm is AES-256-GCM, which is a highly secure and widely respected industry standard. "AES-256" refers to the Advanced Encryption Standard with a 256-bit key, offering a very high level of security. The "GCM" (Galois/Counter Mode) part is significant as it not only encrypts the data but also provides authentication, ensuring the file has not been tampered with.

For robust security, the application doesn't use your password directly as the encryption key. Instead, it employs a key derivation function called PBKDF2. This function takes the password, combines it with a static value called a "salt," and performs hundreds of thousands of computational "iterations." This process makes it extremely difficult for attackers to guess the password using brute-force methods. For each encryption, a unique, random Initialization Vector (IV) is generated and prepended to the encrypted file. This ensures that encrypting the same file with the same password multiple times will produce a different output each time, a critical feature for strong cryptography. When decrypting, the tool reads the IV, re-derives the key from the password, and reverses the process. If the password is incorrect or the file has been corrupted, the GCM authentication fails, and the decryption is safely aborted.


      
