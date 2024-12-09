# TCON7 Writeup
## Good Fundamentals

---

Category: `Misc`
Points: `300`
Writeup by: [xk4k4r0tx](https://github.com/xk4k4r0tx)

---

## Challenge: 

If you have a good fundamentals on Cybersecurity, especially on the domain of Cryptography, you can have this.

Cipher Text 2e678c011061381914e6c20f0350ccb10be36a88c8593db0f7afd3136a35d4d63a4281e82c4b08058a65ea32a4f9b0b001898ed0d9425a2a981571588c67b9576f64d854f4966845300ae21f090a36c71416940f4d9b136fc934818722daf7f874476e72a5f297a9665b142aa356b770e9676b616d13cf38dc47c5697dbf69f4762781f3dc0157176db5450ee661ad3f0ffda440a752dc3b88be511cc337c224040a1f9551b4b9587432ef069c8c83f604867608a1370af5559aba71dd7c3c30e4c67d16f1d227805ed0527d74b3e50ac7996983a721162474548ff2795e2a0419de28474b1be82d857f6979a4e916616cd91aff53c4eed440780fc26c5f3482

<a href="">prvikey</a>

---

## Solution:

Seeing this ciphertext and attached privkey, I noticed that this maybe a RSA crypto. I edited the privkey to have its proper pem format. I've used different tools like RSACTFTool and online tools but encountered errors. Tried troubleshooting it but can't move forward.
I tried chatgpt to create a python script to decrpyt it and made some troubleshooting to make it work then I got the flag. below is the code.

from cryptography.hazmat.primitives import serialization
from cryptography.hazmat.primitives.asymmetric import padding
from cryptography.hazmat.primitives import hashes
import binascii
import re

```python
# Private RSA key in PEM format
private_key_pem = b"""-----BEGIN RSA PRIVATE KEY-----
MIIEpQIBAAKCAQEAk1Ag+Oou443fHsTcNqLat91K6Lx9auBwLu+a2PZTmlfIbNuR
xQgk97pXEChvf640brC8gGVsMCWcIcTMUV2zyMBmTFmoHeghzLAJTKDY1djat7Np
ihigmLfi8ul3WBzPNvlT/c/11UvWy6xZmQ4i1jzPjvKCds6KpkGM9DAKh6TCcrCh
+JLCHX1LY9wae3y/gqixeGm2KPOVeRhoXB1Qd8jcXZafH96mu027hYxHH2IFF5eK
HZr23UDMRxD85fb1jsj4+vtxFgL8UaqWMZW3rn7sIDqBp51oh/QyDf3sgjYuE3lS
w41F+gJqQlV5L17BvVJ+q22Uyy3EJABD+DsWTQIDAQABAoIBAAnhdUC01m3JYYaL
Djk07aYo9+IJ6ICfaq7fP9vfE8b1rdoNVSbpz671ButsxuPBv78P6CjVhK7rCuCh
9lFbz1f+/a2P0uykmgXEZe9Hl5uqVqs9I65RTg5IQTbpTWmxzv1BNm6/AN5sXo0d
M4pGTjRf8k0Ee5cz7c1OdsGXKlGkM6BxncdYomlGdzhV6vakNJFisXzybSUg36K8
uPf3v7Ah++HF7bmgYRpCS7Xu+dYZU0awtLqjKJdSh8sq0o+6/IHFqcAisnb4WiEj
4DkldQTQx2+eyXDXDt7Vi4q5q6qZOESXc/3n1g1ju8xO3CQ87sjT+j4oX7XyAP5c
ieicKEkCgYEAw4nJdioNiHkqyD1O709nU908t0s6OBhPagm74vEw4e35s9bnfNbX
YcjZqgcpdn9bIgmbpBVor+d8WVVv2/hoyPsxsmAjyqiI2sOBMJnZ5tMjea4DnCy6
ehlJPga696GgaWeDJwhODLyJfXu+ZUQO3ldHJsm64UqwyrzSLObOY5UCgYEAwNz6
qvx9aAEwqWU8l+nuEYgzPwUyDK/VfxojZGZw7cufbm0KkVtLZP/ER0rVnZbyaLIO
ZNNO5wdKOsp1IYlPcBpjOWWDkCRPxYokmaRGAVL9b6gWE2D4d5qR1Kp9kJ6MuFJZ
dj2fduauVTVv5q1T7zwgc1GF3ZMri+Ev2cOKudkCgYEAnzyEHYBdiPfziSG0OFpX
cQpHuZS/kpLpiRboNQXpovNjV7r4xMdIms8vwrEWaPOJyYw9fUAaArXmo/FZqK8A
1jsJ25NDUnQxDsYLXQLNWpYy25KEShh6u5f/900P0T2EHpI3UgAHX4PiC5hMErd7
zEETJlk9oN5sXo2qMvq6tIkCgYEAlP3h9JfsNZ29vw+DeQRyMz8Z/9R+rshj0bYa
o2R0V3BX8VHxuQtjOlpQgpbwYbcL/A+aCRApQ1chZDuls0vFf6ATCXM/6On0anHn
Bn6eykUXntumekAOky9o+3beXAvwQDD2Bd9jQtLA2PjYQseiMQ4tL4lKNjuMh5pm
gf+LOzkCgYEArbxA7frR+/SUGdKMhyUy8XKJ2Veaphyv04AqkE9se/2d9rkpr0pX
UDf0xJpWiMIw3hdvzhfLM5aRvCVBw4ekBKaqww1SjxbNm7zDzzrhpw2hlIJwltU5
GKaAtzaB3n6owDNmxzOpfMBqUrMlGmleCPRBWiWzbrtYEPCZDrlClEM=
-----END RSA PRIVATE KEY-----"""

# Ciphertext (hex string)
ciphertext_hex = "2e678c011061381914e6c20f0350ccb10be36a88c8593db0f7afd3136a35d4d63a4281e82c4b08058a65ea32a4f9b0b001898ed0d9425a2a981571588c67b9576f64d854f4966845300ae21f090a36c71416940f4d9b136fc934818722daf7f874476e72a5f297a9665b142aa356b770e9676b616d13cf38dc47c5697dbf69f4762781f3dc0157176db5450ee661ad3f0ffda440a752dc3b88be511cc337c224040a1f9551b4b9587432ef069c8c83f604867608a1370af5559aba71dd7c3c30e4c67d16f1d227805ed0527d74b3e50ac7996983a721162474548ff2795e2a0419de28474b1be82d857f6979a4e916616cd91aff53c4eed440780fc26c5f3482"

try:
    # Remove non-hex characters from the ciphertext if needed
    ciphertext_hex = re.sub(r'[^0-9a-fA-F]', '', ciphertext_hex)

    # Convert ciphertext from hex to bytes
    ciphertext_bytes = binascii.unhexlify(ciphertext_hex)

    # Load the private key
    private_key = serialization.load_pem_private_key(
        private_key_pem,
        password=None,  # Add password if encrypted
    )

    # Try decrypting with OAEP (default)
    try:
        plaintext = private_key.decrypt(
            ciphertext_bytes,
            padding.OAEP(
                mgf=padding.MGF1(algorithm=hashes.SHA256()),
                algorithm=hashes.SHA256(),
                label=None
            )
        )
        print("Decrypted text:", plaintext.decode())
    except ValueError as e:
        print("Decryption with OAEP failed, trying PKCS1v15...")

        # Try decrypting with PKCS#1 v1.5
        plaintext = private_key.decrypt(
            ciphertext_bytes,
            padding.PKCS1v15()
        )
        print("Decrypted text:", plaintext.decode())

except binascii.Error as e:
    print("Hex conversion error:", e)
except ValueError as e:
    print("Key deserialization or decryption error:", e)
except Exception as e:
    print("An error occurred:", e)
```

Decrypted text: tcon{1ec83ed8e12dbafeb994d091d5a8b2d9}
