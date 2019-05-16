# S3-Encryption

 - Two Options: 
   - Server Side Encryption and 
   - Client Side Encryption
 
 - Server Side Encryption:
      - The S3 server is in charge of the encryption and decryption
      
 - Client Side Encryption:
      - The customer show is in charge of that encryption and decryption
  
 - Server Side Encryption provide 3 options:
    1. SSE - S3: Here S3 manages the data encryption key and the master key
    2. SSE - KMS: Here KMS creates and manages the data encryption key and the master key
    3. SSE - C: Here S3 manages the keys that are provided by the user.
    
  - Client Side Encryption provide 2 options:
    1. CSE with KMS-Managed Customer Master Key
    2. CSE with Client-Side Master Key (S3 encryption Client)
  
