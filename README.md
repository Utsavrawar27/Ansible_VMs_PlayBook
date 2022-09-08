# Ansible_VMs_PlayBook
Ansible_VMs_PlayBook


#1.	Launch 3 EC2 Instances on AWS Cloud Platform and download the secret key (.pem) file.
•	Virtual-Machine-1
•	Virtual-Machine-2
•	Virtual-Machine-3

![image](https://user-images.githubusercontent.com/40047632/189057829-21f8787e-a088-4c02-a590-e27fb18a2740.png)

 

#2.	Install Ansible on the Virtual-Machine-1 using below commands:
amazon-linux-extras enable ansible2
yum install -y ansible

![image](https://user-images.githubusercontent.com/40047632/189057976-891bcfd8-f8ed-461b-8c8e-8cf0f48f638f.png)


![image](https://user-images.githubusercontent.com/40047632/189058044-f0509dc1-30d1-4f4d-bc8e-f5d48d9b36fd.png)

 


3.	Create an inventory file:
 ![image](https://user-images.githubusercontent.com/40047632/189058081-318b3007-2289-4f0f-bf5a-97c528ee9367.png)



4.	Make sure that the webservers Virtual-Machine-2 and Virtual-Machine-3 are reachable by pinging from server Virtual-Machine-1 using the command: 

telnet [public-ipv4] [port no]

![image](https://user-images.githubusercontent.com/40047632/189058108-95c11df5-40b9-4826-a7c7-3069b56f9355.png)


 


5.	Source (src) index.html file as follows:
 


![image](https://user-images.githubusercontent.com/40047632/189058136-511371a9-5cbf-464b-8b2c-2cd3b2d2d185.png)





6.	Create a .yml file to install Nginx on Virtual-Machine-2 and Virtual-Machine-3 through Virtual-Machine-1, i.e. InstallNginx.yml, and change port 80 to 8080.

 
![image](https://user-images.githubusercontent.com/40047632/189058162-46e998e5-4991-48ff-8bf4-802723cb55de.png)



7.	Run the ansible playbook on the Virtual-Machine-1 server using the command: 
ansible-playbook InstallNginx.yml -i inventory

![image](https://user-images.githubusercontent.com/40047632/189058200-87fc6f87-f96e-4a3f-b78d-559d7b7ac5bd.png)

 


8.	Check if the desired message from the index.html displayed on the web browser of Virtual-Machine-2 (43.204.149.107) at http port 8080

 ![image](https://user-images.githubusercontent.com/40047632/189058220-49e5a7bc-be4b-41b2-92ef-9a16d7da4937.png)




9.	Same check if the desired message from the index.html displayed on the web browser of Virtual-Machine-3 (13.233.110.49) at http port 8080

![image](https://user-images.githubusercontent.com/40047632/189058246-f9c3c899-8a42-4906-951b-854d66c92f2d.png)

 


10.	Create a .yml file to uninstall Nginx on Virtual-Machine-2 and Virtual-Machine-3 through Virtual-Machine-1, i.e. UninstallNginx.yml, The following helps in un-deploying the webserver



 
![image](https://user-images.githubusercontent.com/40047632/189058266-ba64e602-ec99-430b-8e92-765a4d426b3f.png)











11.	Run the playbook on the Virtual-Machine-1 to un-deploying the webserver server using the command: 
ansible-playbook UninstallNginx.yml -i inventory

 ![image](https://user-images.githubusercontent.com/40047632/189058309-0a70fd9c-19de-4e6c-85fb-439ea69a4e25.png)


12.	Check if Virtual-Machine-2 (43.204.149.107) and Virtual-Machine-3 (13.233.110.49) web browser got un-deployed successfully at http port 8080.

 ![image](https://user-images.githubusercontent.com/40047632/189058333-fe57e744-f9a4-4b64-adbf-08f0053df2f2.png)

![image](https://user-images.githubusercontent.com/40047632/189058358-93e1d299-fc9a-4de3-9a66-2bdd223a173b.png)

 






***************************************************************************
