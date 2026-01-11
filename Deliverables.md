1. EC2 instance running and reachable over HTTP

![1.ec2 reachable](pictures/1.ec2%20reachable.png)
2. RDS MySQL instance in the same VPC
![Screenshot 2026-01-10 202944](pictures/Screenshot%202026-01-10%20202944.png)
3.Security group rule showing:
RDS inbound TCP 3306

Source = EC2 security group (not 0.0.0.0/0)
![Screenshot 2026-01-10 203218](pictures/Screenshot%202026-01-10%20203218.png)
IAM role attached to EC2 allowing Secrets Manager access
![Screenshot 2026-01-10 190241](file:///C:/Users/User/Pictures/Screenshots/Screenshot%202026-01-10%20190241.png)
## Application Proof
1. Successful database initialization
2. Ability to insert records into RDS
3. Ability to read records from RDS
4. Screenshot of:
* RDS SG inbound rule using source = sg-ec2-lab
* EC2 role attached
http://<EC2_PUBLIC_IP>/init
![initlabdb](pictures/initlabdb.png)
* http://<EC2_PUBLIC_IP>/add?note=first_note
* ![Screenshot 2026-01-10 201430](./pictures/Screenshot%202026-01-10%20201430.png)
* http://<EC2_PUBLIC_IP>/add?note=last_note![Screenshot 2026-01-10 204025](./pictures/Screenshot%202026-01-10%20204025.png)
* http://<EC2_PUBLIC_IP>/list
* ![E C2 P U B L I C I Plist](pictures/EC2PUBLICIPlist.png)
* 


## C.Verification Evidence
* CLI output proving connectivity and configuration
* Browser output showing database data
* Copy and paste this command your vscode terminal
* ![Screenshot 2026-01-09 165949](pictures/Screenshot%202026-01-09%20165949.png)
* 
6. Technical Verification
## 6.1 Verify EC2 Instance
 204810](pictures/Screenshot%202026-01-10%20204810.png)

##### 6.2 Verify IAM Role Attached to EC2
![verifyiam](pictures/verifyiam.png)
#### 6.3 Verify RDS Instance State
![rdsinstance](pictures/rdsinstance.png)
#### 6.4 Verify RDS Endpoint (Connectivity Target)
![Screenshot 2026-01-10 211458](pictures/Screenshot%202026-01-10%20211458.png)
#### 6.5 (works)
![describe sec groups](pictures/describe%20sec%20groups.png)
### 6.6 (run command inside ec2 sessions manager) (works)
![Screenshot 2026-01-11 104727](pictures/Screenshot%202026-01-11%20104727.png)


