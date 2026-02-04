# **Project Report: Deploying a Web Application on AWS EC2 Using Apache Web Server**

## **Introduction**

The purpose of this project was to gain practical experience with Amazon Web Services (AWS) by launching a virtual machine, configuring security rules, installing a web server, and deploying a simple web application. The project involved working with an Amazon EC2 instance running Ubuntu Linux and using Apache2 to host a custom HTML web page. Through this hands-on exercise, important concepts such as cloud computing, networking, Linux administration, and web hosting were explored.

## 🧰 Prerequisites

Before starting, ensure you have:

- Basic knowledge of Linux commands
- An active AWS account
- Basic understanding of networking (ports, security groups)
- SSH client (Terminal, CMD, or PuTTY)

------

## 🚀 Project Tasks & Deliverables

------

## **Task 1: Create an EC2 Instance**

### Steps:

1. Log in to **AWS Management Console**

2. Navigate to: **EC2 → Launch Instance**

3. **Choose AMI:**

   - Ubuntu Server 20.04 LTS *or*
   - Ubuntu Server 22.04 LTS

4. **Instance Type:**

   - `t2.micro` (Free-tier eligible)

5. Configure an existing or new **Key Pair**

6. Launch the instance

   ![](C:\Users\jagan\Downloads\web\Screenshot 2026-02-04 121703.png)

   -----

   ![](C:\Users\jagan\Downloads\web\Screenshot 2026-02-04 121715.png)

   ------

   ![](C:\Users\jagan\Downloads\web\Screenshot 2026-02-04 121730.png)

   ---------------------------

   📸 Screenshot of EC2 instance in **Running** state

![](C:\Users\jagan\Downloads\web\Screenshot 2026-02-04 121811.png)

------

## **Task 2: Configure Security Groups**

### Create inbound rules:

| Protocol | Port | Source    |
| -------- | ---- | --------- |
| SSH      | 22   | Your IP   |
| HTTP     | 80   | 0.0.0.0/0 |

📸 Screenshot of *inbound security group rules*

![](C:\Users\jagan\Downloads\web\Screenshot 2026-02-04 123054.png)

------

## **Task 3: Connect to EC2 Using SSH**

### Steps:

1. Copy EC2 **Public IPv4 address**
2. Run the SSH command:

​         ssh -i your-key.pem ubuntu@<public-ip>

  Verify successful login: 

📸 Screenshot of successful SSH login

![](C:\Users\jagan\Downloads\web\Screenshot 2026-02-04 121908.png)

------

## **Task 4: Install and Start Apache2 Web Server**

### Commands

sudo apt update

sudo apt install apache2 -y

sudo systemctl start apache2

sudo systemctl enable apache2

sudo systemctl status apache2

📸 Screenshot showing Apache2 **active (running)** status

![](C:\Users\jagan\Downloads\web\Screenshot 2026-02-04 122049.png)

------

## **Task 5: Test HTTP Access**

1. Open a browser
2. Enter: `http://<public-ip>`
3. The Apache2 default page should load

📸 Screenshot of the **Apache2 default webpage**

![](C:\Users\jagan\Downloads\web\Screenshot 2026-02-04 122210.png)

------

## **Task 6: Deploy a Sample Web Application**

### Steps:

Navigate to Apache web root:

cd /var/www/html

![](C:\Users\jagan\Downloads\web\Screenshot 2026-02-04 122304.png)

-------------

Create a custom HTML file:

sudo nano index.html

Add the following content:

HTML

<!DOCTYPE html>

<html>

<head>

​    <title>My AWS EC2 Web App</title>

</head>

<body>

​    <h1>Welcome to My EC2 Web Server</h1>

    <p>Apache2 is running successfully on AWS!</p>

</body>

</html>

![](C:\Users\jagan\Downloads\web\Screenshot 2026-02-04 122352.png)

Save the file and refresh the browser.

📸 Screenshot of your **custom web application page**

![](C:\Users\jagan\Downloads\web\Screenshot 2026-02-04 122408.png)

------------

## **Conclusion**

This project successfully demonstrated the complete process of deploying a web application on AWS using an EC2 instance and the Apache2 web server. By performing each task—from launching the virtual machine and configuring security groups to installing Apache and deploying a custom webpage—I gained practical, hands-on experience with cloud infrastructure and Linux server management. The project strengthened my understanding of how cloud services work, how secure connections are established, and how web applications are hosted and accessed over the internet. Overall, this project provided a solid foundation for future learning in AWS, DevOps, and cloud-based application deployment.