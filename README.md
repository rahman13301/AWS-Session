# Deploying a Node Js Application on AWS EC2

### Set up an AWS EC2 instance:


1. Create an EC2 instance
    - Select an OS image - Ubuntu
    - Create a new key pair & download `.pem` file
    - Instance type - t2.micro
    - 
<img width="1019" height="625" alt="image" src="https://github.com/user-attachments/assets/7b79b1bd-e301-4ad8-81dd-8eada45c206d" />

2. Connecting to the instance using ssh
```
ssh -i instance.pem ubunutu@<IP_ADDRESS>
```
<img width="788" height="513" alt="image" src="https://github.com/user-attachments/assets/18e28db8-dd32-4931-ae4b-38de22bfc49b" />


3. Updating the outdated packages and dependencies
```
sudo apt update
```
5. Install Gitand check version by using below commands:
```
sudo apt install git
git --version
```
<img width="567" height="48" alt="image" src="https://github.com/user-attachments/assets/0e642316-f8b1-4776-bc6c-cda71085b898" />

4. To install Node.js and check version by commands:
```
sudo apt install nodejs
node -v
```
<img width="546" height="80" alt="image" src="https://github.com/user-attachments/assets/2c074c4f-1674-4e89-abc2-4150abc43189" />

### Deploying the project on AWS

1. Clone this project in the remote VM
```
git clone https://github.com/verma-kunal/AWS-Session.git
```
2. Setup the following environment variables - `(.env)` file. This environment variable dependencies is for Stripe payment gateway.
```
DOMAIN= "http://localhost:3000"
PORT=3000
STATIC_DIR="./client"

PUBLISHABLE_KEY="pk_test_51L5AsSSCC8JVWfvgEtfJkzHMTh7Z5PLY5m1yhR379sJgwAVZEe13NaiG33wsHSyHnPJMjTNOosiPk6AeMI8q0ims0049IKffiu"
SECRET_KEY="sk_test_51L5AsSSCC8JVWfvgxpyZvQyBRRkHmGBkdyIa94vPD3Zs71qbHGrnSPlrJOIWiR74fbcn1A85yESCFnrrp3aX0Oz900JaunHrhe"
```
> For this project, we'll have to set up an [Elastic IP Address](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/elastic-ip-addresses-eip.html) for our EC2 & that would be our `DOMAIN`

3. Initialise and start the project.
```
npm install
npm run start
```

> NOTE - We will have to edit the **inbound rules** in the security group of our EC2, in order to allow traffic from our particular port

### Project is deployed on AWS 🎉
