Source URL: https://www.whizlabs.com/aws-solutions-architect-associate/

# S3-Encryption

 - Two Options: 
   - Server Side Encryption and 
   - Client Side Encryption
 
 - Server Side Encryption:
      - The S3 server is in charge of the encryption and decryption
      - This uses Advanced Encryption Standard (AES) - 256. 
      
 - Client Side Encryption:
      - The customer is in charge of that encryption and decryption
  
 - Server Side Encryption provide 3 options:
    1. SSE - S3 Keymanagement: Amazon S3 will encrypt your data at rest and managed the encryption keys for you
    2. SSE - Amazon Key Management Service (KMS): Amazon S3 will encrypt your data at rest and using keys you manage in AWS KMS,
                                                  This approch allows you to see who used the keys based on audit trail. It provides                                                         additional security
    3. SSE - Customer Provided Key: Amazon S3 will encrypt your data at rest and using the key you provide.
    
  - Client Side Encryption provide 2 options:
    1. CSE with KMS-Managed Customer Master Key
    2. CSE with Client-Side Master Key (S3 encryption Client)
  
