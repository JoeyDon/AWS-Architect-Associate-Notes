# LB - Load Balancer

## Key Points:
* Client connects to the listener on LB
* LB connects to the targer server

### ALB Application Load Balancing
1. ALB can use SNI for multiple SSL certs
2. Optional cross-AZs balancing
3. Target group can have EC2, ECS, EKS, Lambda, HTTP/s

### NLB Network Load Balancering (Exam hints)
1. Layer 4 - only understands TCP and UDP
2. Can't understand HTTP/S but much faster.
3.  <100ms vs 400ms ALB
4. Rapid Scaling
5. 1 Instance with static IP per AZ, can use Elastic IP(Whitelisting)
6. SSL pass throught
7. No HTTP/S application


### SSL 3 modes
1. Bridging - One SSL from client to LB, another SSL from LB to EC2.
2. PassThrough - One SSL pass LB to EC2
3. Offload - One SSL from client to LB, LB HTTP to EC2

### Connection Stickness
* Use LB Cookies 1s to 7days