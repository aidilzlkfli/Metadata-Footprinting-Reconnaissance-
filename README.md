<h1>Report: Metadata Footprinting &amp; Reconnaissance</h1>

<p>
  <strong>Project Description:</strong><br />
  This assignment explores essential digital forensics techniques for uncovering hidden data within files. 
  Using command-line tools on Kali Linux, I analyzed various image files and an executable to identify 
  embedded content, metadata, and file anomalies. The objective was to extract sensitive information 
  such as EXIF data, embedded files, readable strings, and file type discrepancies that could be 
  leveraged in a security assessment or penetration testing engagement. Key techniques used include 
  metadata extraction with <code>exiftool</code>, hex analysis with <code>hexeditor</code>, file carving 
  and extraction with <code>binwalk</code>, string extraction with <code>strings</code>, and file type 
  identification with the <code>file</code> command. This walkthrough demonstrates how metadata can 
  unintentionally leak sensitive information and serves as a learning resource for ethical hacking 
  and cybersecurity practices.
</p>

<br />

<table border="0" cellpadding="10">
  <thead>
    <tr>
      <th width="5%">Step</th>
      <th width="35%">Activity / Findings</th>
      <th width="20%">Command / Details</th>
      <th width="40%">Screenshot</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>1</td>
      <td>Extract metadata from <code>ocean.jpg</code> to reveal EXIF data, GPS coordinates, camera model, and other hidden information</td>
      <td><code>exiftool ocean.jpg</code></td>
      <td><img width="100%" src="https://github.com/user-attachments/assets/79b713ed-d55b-408b-84ca-9ff3b61489f4" /></td>
    </tr>
    <tr>
      <td>2</td>
      <td>Open <code>computer.jpg</code> in a hex editor to view and analyze raw binary/hex data for hidden content or file signatures</td>
      <td><code>hexeditor computer.jpg</code></td>
      <td><img width="100%" src="https://github.com/user-attachments/assets/652c73bf-8c75-4c81-a9c1-620b56458eb8" /></td>
    </tr>
    <tr>
      <td>3</td>
      <td>Scan <code>dog.jpg</code> for embedded files or hidden data, extract any found files, and navigate into the extracted folder</td>
      <td>
        <code>binwalk dog.jpg</code> → <code>binwalk -e dog.jpg</code> → <code>cd _dog.jpg.extracted/</code>
       </td>
      <td><img width="100%" src="https://github.com/user-attachments/assets/ad08678e-e5d3-4b5c-ac0c-dbbd2c593cba" /></td>
    </tr>
    <tr>
      <td>4</td>
      <td>Extract and display readable text/strings from <code>computer.jpg</code> to uncover any embedded plaintext information</td>
      <td><code>strings computer.jpg</code></td>
      <td><img width="100%" src="https://github.com/user-attachments/assets/0d58cdd4-e8a0-46d6-95de-0579934c7b83" /></td>
    </tr>
    <tr>
      <td>5</td>
      <td>Identify the actual file type of <code>solitaire.exe</code> to verify if it matches its extension or is a different executable format</td>
      <td><code>file solitaire.exe</code> → PE32 executable</td>
      <td><img width="100%" src="https://github.com/user-attachments/assets/32a0c3f1-39c5-4be1-86c3-27902966fa43" /></td>
    </tr>
    <tr>
      <td>6</td>
      <td>Identify the actual file type of <code>rubiks.jpg</code> to confirm it is a valid JPEG image or detect any file type anomalies</td>
      <td><code>file rubiks.jpg</code> → JPEG image data</td>
      <td><img width="100%" src="https://github.com/user-attachments/assets/ecdaf45f-ce35-45b3-a379-504c9af7eaf1" /></td>
    </tr>
  </tbody>
</table>
