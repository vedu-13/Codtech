Task 1:
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

