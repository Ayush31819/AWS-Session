# Deploying a Node Js Application on AWS EC2 using GIT

### Testing the project locally

1. Clone this project
```
git clone https://github.com/verma-kunal/AWS-Session.git
```
2. Setup the following environment variables - `(.env)` file
```
DOMAIN= ""
PORT=3000
STATIC_DIR="./client"

PUBLISHABLE_KEY=""
SECRET_KEY=""
```
3. Initialise and start the project
```
npm install
npm run start
```
![image](https://github.com/user-attachments/assets/2fe99400-eee5-4133-8ed2-def730f9618b)

![image](https://github.com/user-attachments/assets/c403b7a1-b8b2-4d72-814a-a0e3850b8e71)


### Set up an AWS EC2 instance

1. Create an IAM user & login to your AWS Console
    - Access Type - Password
    - Permissions - Admin

![image](https://github.com/user-attachments/assets/451e196c-b300-441f-b23a-65f613626bf9)


2. Create an EC2 instance
    - Select an OS image - Ubuntu
    - Create a new key pair & download `.pem` file
    - Instance type - t2.micro

![image](https://github.com/user-attachments/assets/cff5de25-d239-43fd-9091-995038e91519)

3. Connecting to the instance using ssh

```
ssh -i instance.pem ubunutu@<IP_ADDRESS>
```

### Configuring Ubuntu on remote VM

1. Updating the outdated packages and dependencies
```
sudo apt update
```
3. Install Git - [Guide by DigitalOcean](https://www.digitalocean.com/community/tutorials/how-to-install-git-on-ubuntu-22-04) 
4. Configure Node.js and `npm` - [Guide by DigitalOcean](https://www.digitalocean.com/community/tutorials/how-to-install-node-js-on-ubuntu-22-04)

### Deploying the project on AWS

1. Clone this project in the remote VM
```
git clone https://github.com/verma-kunal/AWS-Session.git
```
2. Setup the following environment variables - `(.env)` file
```
DOMAIN= ""
PORT=3000
STATIC_DIR="./client"

PUBLISHABLE_KEY=""
SECRET_KEY=""
```
> For this project, we'll have to set up an [Elastic IP Address](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/elastic-ip-addresses-eip.html) for our EC2 & that would be our `DOMAIN`

3. Initialise and start the project
```
npm install
npm run start
```

> NOTE - We will have to edit the **inbound rules** in the security group of our EC2, in order to allow traffic from our particular port

![image](https://github.com/user-attachments/assets/f76395af-d23b-4a08-bf41-dc8483708816)

### Project is deployed on AWS 🎉
