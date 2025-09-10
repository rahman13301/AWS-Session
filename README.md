# Deploying a Node Js Application on AWS EC2

### Set up an AWS EC2 instance:


**1. Create an EC2 instance**
    - Select an OS image - Ubuntu
    - Create a new key pair & download `.pem` file
    - Instance type - t2.micro
      
<img width="1019" height="625" alt="image" src="https://github.com/user-attachments/assets/7b79b1bd-e301-4ad8-81dd-8eada45c206d" />


**2. Connecting to the instance using ssh**
```
ssh -i instance.pem ubunutu@<IP_ADDRESS>
```
<img width="788" height="513" alt="image" src="https://github.com/user-attachments/assets/18e28db8-dd32-4931-ae4b-38de22bfc49b" />


**3. Updating the outdated packages and dependencies**
```
sudo apt update
```

**5. Install Git and check version by using below commands:**
```
sudo apt install git
git --version
```
<img width="567" height="48" alt="image" src="https://github.com/user-attachments/assets/0e642316-f8b1-4776-bc6c-cda71085b898" />


**4. To install, configure Node.js and check versions by commands:**
```
sudo apt install nodejs
node -v
sudo apt install npm
npm --version
```
<img width="546" height="80" alt="image" src="https://github.com/user-attachments/assets/2c074c4f-1674-4e89-abc2-4150abc43189" />
<img width="835" height="260" alt="image" src="https://github.com/user-attachments/assets/1e7c67a2-57e9-41e1-ada8-4b4d19f134d1" />


### Deploying the project on AWS

**1. Clone this project in the remote VM**
```
git clone https://github.com/rahman13301/AWS-Session
```
<img width="940" height="232" alt="image" src="https://github.com/user-attachments/assets/ce274ad3-30ce-43a5-a625-2c8d3c7502e2" />


**2. Setup the following environment variables - `(.env)` file. This environment variable dependencies is for Stripe payment gateway. You can get Public keyand Secret key after creating demo account of Stripe**

<img width="873" height="134" alt="image" src="https://github.com/user-attachments/assets/f19559e1-ecc4-4d5e-a656-d9c3fb82bd7e" />


```
DOMAIN= "http://localhost:3000"
PORT=3000
STATIC_DIR="./client"

# Stripe API keys
PUBLISHABLE_KEY=""
SECRET_KEY=""
```
<img width="1205" height="190" alt="image" src="https://github.com/user-attachments/assets/fc24a98a-4a6d-4342-92ee-c8af30bfe5a5" />

**3. Initialise and start the project.**
```
npm install
npm run start
```
<img width="734" height="411" alt="image" src="https://github.com/user-attachments/assets/6e399b28-6ce2-41dd-af9d-01b0c5522534" />


> **NOTE** - We will have to edit the **inbound rules** in the security group of our EC2, in order to allow traffic from our particular port like (3000).
> Access in browser with <EC2 instance-public ip:3000

<img width="1590" height="546" alt="image" src="https://github.com/user-attachments/assets/86f04472-478b-41b6-9bde-7732df5aebc7" />


### Project is deployed on AWS 🎉
