# TODO-CI/CD
This is a website for deploying in AWS for Cloud Computing Project 

# Setting Up AWS EC2 and Hosting a Python Website with Extra Services

Alright, let's get started with setting up AWS EC2 and hosting our Python website – “ToDo- website”, making sure I’m using the right services for the needs.

# 1. Creating our Virtual Private Cloud (VPC):
-	We'll begin by creating a VPC to keep our resources secure and separate from other networks. This ensures our EC2 instance operates in a controlled environment.
-	We'll attach an internet gateway to our VPC, allowing our instance to communicate with the internet.

# 2. Configuring Subnet for our Instance:
-	Inside our VPC, we'll set up a subnet to manage our instance's network traffic. This helps in organizing our resources efficiently.
-	Assigning appropriate IP address ranges ensures smooth communication within our network.

# 3. Setting Up Route Table for Traffic Management:
-	To direct traffic between our subnet and the internet, we'll establish a route table. This ensures seamless connectivity for our EC2 instance.
-	Associating this route table with our subnet ensures that our instance can access the internet through the internet gateway.

# 4. Establishing Internet Gateway:
-	Now, let's create an internet gateway and attach it to our VPC. This enables our EC2 instance to communicate externally.
-	This step ensures that our website hosted on the instance can be accessed over the internet.

  # you can use default VPC for launching EC2 Instance #
    - if you use default VPC then you can skip the points from 1 to 4
    - directly start from point 5 - Launching EC2

# 5. Launching our EC2 Instance:
-	I'll choose the appropriate Amazon Machine Image (AMI) for our EC2 instance, ensuring it aligns with the requirements of hosting our Python website.
-	Selecting the right instance type ensures we have the necessary computational power and memory for our application.
-	Configuring security groups properly ensures our instance is protected from unauthorized access while allowing legitimate traffic.

# 6. Connecting to our EC2 Instance:
-	Using SSH or RDP, we'll establish a secure connection to our EC2 instance, making sure to use the key pairs for authentication.
-	Secure access management is essential to prevent any security breaches or unauthorized access.

# 7. Hosting our Python Website:
-	With our EC2 instance up and running, we'll deploy our Python website onto it, taking advantage of its scalability and network performance.
-	Cloning our website repository from GitHub ensures smooth deployment and easy updates.
-	Configuring web servers like Ubantu allows us to serve our Python website efficiently.

## comment for server ec2 on amazon  ##

1.  sudo apt-get update

2.  git clone https://github.com/nehanayak9/TODO-CI-CD.git

3.  cd 

4.  sudo apt install python3-pip -y

5.  pip install django

6.  python3 manage.py makemigrations

7.  python3 manage.py migrate

8.  python3 manage.py createsuperuser

9.  python3 manage.py runserver

# 8. Adding Extra Services (e.g., EBS):
-	I'll integrate Elastic Block Store (EBS) to provide reliable storage for our EC2 instance, ensuring our data persists even if the instance is terminated.
-	Attaching additional EBS volumes allows us to scale our storage capacity based on our growing data needs.
-	Leveraging EBS snapshots provides an added layer of data protection and allows for easy backups and recovery.

# Comments for EBS :
-	df -h
-	sudo mkfs -t  ext3 /dev/sdf
-	sudo mkdir /mnt/data-store
-	sudo mount /dev/sdf /mnt/data-store
-	echo "/dev/sdf /mnt/data-store ext3 defaults, noatime 1 2" | sudo tee -a /etc/fstab
-	cat /etc/fstab
-	df -h
-	sudo sh -c "echo some text here written > /mnt/data-store/file.txt"
-	lsblk

##Modify the file size
-	sudo resize2fs /dev/xvdf
-	ls /mnt/data-store 
-	cat /mnt/data-store/file.txtf

# create snapshot
-	-for backup data for data volume

By following these steps and leveraging the right AWS services, I can set up our EC2 instance, host our Python website, and ensure it runs smoothly with the additional services we need.
