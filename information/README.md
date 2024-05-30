## Write-up for Capture the Flag Challenge: Hidden Message in `cat.jpg`

### Challenge Description
In this Capture the Flag (CTF) challenge, participants are provided with an image file named `cat.jpg`. The objective is to uncover a hidden flag that has been embedded within the file using steganography techniques. The challenge requires basic knowledge of command-line tools and encoding methods.

### Steps to Solve the Challenge

1. **Download the Image**
   Ensure you have the image file `cat.jpg` downloaded to your working directory.

2. **Extract Strings from the Image**
   Use the `strings` command to extract readable text from the binary data in the image file. This command helps to identify any hidden text or embedded information within the file.

   ```bash
   strings cat.jpg
   ```

   Among the extracted strings, you should notice some HTML-like content that stands out as suspicious.

3. **Identify the Embedded Resource**
   Within the output from the `strings` command, locate a string that appears to be a block of encoded text. This is often in a base64 format, which is commonly used for embedding data within other files.

   For example, you might find a line like this:

   ```
   data:text/html;base64,SGVsbG8gdGhlcmUhIFRoaXMgaXMgYSBzZWNyZXQgbWVzc2FnZS4gRmxhZzogVEhJUzRDSFRMRkdMTUQ=
   ```

4. **Decode the Base64 Content**
   Extract the base64 encoded string (the part after `data:text/html;base64,`) and decode it to reveal the hidden message or flag.

   ```bash
   echo SGVsbG8gdGhlcmUhIFRoaXMgaXMgYSBzZWNyZXQgbWVzc2FnZS4gRmxhZzogVEhJUzRDSFRMRkdMTUQ= | base64 -d
   ```

5. **Reveal the Flag**
   After decoding, you should see a readable text that contains the flag.

   For instance, the decoded message might be:

   ```
   Hello there! This is a secret message. Flag: THIS4CHTLFGLMD
   ```

   Here, `THIS4CHTLFGLMD` is the flag.

### Conclusion

By following the steps above, you can successfully extract the hidden flag from `cat.jpg`. This challenge demonstrates the use of simple steganography techniques and basic command-line tools to uncover hidden information.

Feel free to reach out if you have any questions or need further assistance!

---

