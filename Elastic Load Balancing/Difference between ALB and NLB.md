### Difference between ALB and NLB

| Parameter | ALB | NLB |
|-----------|-----|------|
| Operates at OSI Layer | Layer 7 (HTTP/HTTPS) | Layer 4 (TCP) |
| Cross-Zone Load Balancing | Always Enables | Default Disabled |
| SSL OFfloading | Supported | Not Supported |
| Client Request Terminates at LB | Yes | NO |
| Header Modified | Yes | NO |
| Host based and Path Based Routing | Yes | NO |
| Static IP Address for LB | Not Supported | Supported |
