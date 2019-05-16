# Requester Pays

- Here the requester pays for the data transfer and the request
- Bucket Owner pays only for the storage 
- The requester **MUST INCLUDE x-amz-request-payer** in their request in the header (POST/GET/HEAR request) or in the parameter from REST
- If the requester does NOT include **x-amz-request-payer**, the owner get charged
- the owner must authenticate all request involving Requester Payes Bucket
