Week 03 steps

22. Console → EC2 → Launch instance 
Creates server running on cloud from within AWS console.

23. Name: property-api-01 
Names the instance property-api-01

24. AMI: Amazon Linux 2023 (Free Tier eligible) 
Chooses the operating system of the server to be Linux 2023

25. Instance type: t2.micro or t3.micro 
Creates a low cost server with limited power metrics.

26. Key pair: Create new key pair → name training-key → RSA → .pem → download it and move it 
somewhere permanent, e.g. ~/.ssh/training-key.pem 
Creates a public and private key needed to connect to the EC2 instance.

27. Network settings → Create security group → allow SSH (port 22, source: “My IP”) and custom 
TCP port 8080 (source: Anywhere) — this is PropertyLite's port, not the default HTTP port
Creates two security groups, which limit access to the instance. The first allows SSH only from my local computer's current IP address. The second allows TCP connections from anywhere.

28. Advanced details → scroll to User data → paste the bootstrap script below (this inlines app.py, 
requirements.txt, and the sample CSV from Week 0 so the instance is self-contained on boot)
This software runs on creation of the instance to install the necessary dependencies and provide proper deployment of the app.py file.

29. Launch instance 
Once this completes, the instance is running.

30. Lock down the .pem permissions and connect: chmod 400 ~/.ssh/training-key.pem; ssh -i 
~/.ssh/training-key.pem ec2-user@<public-ip> 
The chmod command allows only the owner to read the key file while the second command is an SSH command to connect to the EC2 instance.

31. EC2 → Volumes → select the root volume of property-api-01 → Actions → Create snapshot 
Provides a snapshot of the data in the root EBS volume.

32. Wait for status “completed”
This wait is just to ensure the snapshot of the EBS volume succeeded