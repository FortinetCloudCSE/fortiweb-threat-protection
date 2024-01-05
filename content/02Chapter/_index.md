---
title: "Ch 2 Basic Setup and Architecture"
menuTitle: "Ch 2: Lab Architecture"
weight: 10
---


## Architecture for this lab:

![Graphical user interface, application  Description automatically generated](./images/clip_image001.png)

### Initial Configuration/Setup:

1. Connect to Fortiweb by using the IP address corresponding to your lab.

​		https://ipaddress:8443 

![image-20220602174444796](./images/image-20220602174444796.png)


2. The credentials will be provided during the lab time. Please login to the lab using those credentials.

   **username**: azureuser

   **password**: Password123!!

​		Once you login you will be at the dashboard.

![image-20220602174454545](./images/image-20220602174454545.png)

3. Click on CLI Console to check the connectivity to the web server. 

```
execute ping 10.10.2.4
```

![image-20220602174504650](./images/image-20220602174504650.png)

4. The application is hosted on a docker container which is up and running on Ubuntu server. We need to create the Server object for Fortiweb to send the traffic to application server.

​		Navigate to Server Objects >> Server >> Server Pool >> Create new

![image-20220602174511886](./images/image-20220602174511886.png)

5. Input information as shown below. Select the Server Balance option for Server Health check option to appear. Click OK.

![image-20220602174520445](./images/image-20220602174520445.png)


6. Once click OK in the above step the greyed out Create new button should now appear to create the Server object.

![image-20220602174528782](./images/image-20220602174528782.png)

7. Now enter the IP address of your application server, port number the pool member/application server listens for connections. In this case the docker container for juice shop is listening on port 3000.

![image-20220602174538435](./images/image-20220602174538435.png)

Click OK once you enter the information.

8. Now we will need to create the Virtual Server IP on which the Traffic destined for server pool member arrives. When FortiWeb receives traffic destined for a Virtual server it can then forward to its pool members. 

![image-20220602174547402](./images/image-20220602174547402.png) 

9. Enter the name for the Virtual Server and click OK. You can now click Create New to create the VIP object. 

![image-20220602174554614](./images/image-20220602174554614.png)

 
10. Virtual Server item can be an IP address of the interface or an IP other than the interface. In this case we will use the interface IP - Turn on the Radio button for “use interface IP”, a drop down with interfaces will appear. Select Port1 as the interface for this Virtual Server item and click OK.

![image-20220602174605954](./images/image-20220602174605954.png)

11. The Virtual Server for the Juice shop app is now using the IP address of the Port1 Interface. 

![image-20220602174621853](./images/image-20220602174621853.png)

 
12. We will now create a custom protection profile which we will be using in the Server policy to protect the application Server. 

​		Navigate to Policy >> Web Protection Profile  click on Inline Standard protection >> Click Clone 

![image-20220602174631921](./images/image-20220602174631921.png)

13. Create a custom Protection profile for juice shop, you can give a name of your choice. 

![image-20220602174644900](./images/image-20220602174644900.png) 

14. Now let’s create a Server policy. Input Name for the server policy, Select the Virtual Server, Server pool which we created in the earlier steps from the drop down. 

​	   For the HTTP Service, Click **create new**

![image-20220602174652731](./images/image-20220602174652731.png)

15. Enter the port number the Virtual Server traffic will be reached on. Let’s keep this to 3000. **(Note: You can set up any port here or even can use HTTP/HTTPS. To make it easy for the rest of the lab use Port 3000)** 

![image-20220602174701454](./images/image-20220602174701454.png)


16. Now let’s attach the protection profile you created in the earlier steps and click OK.

![image-20220602174708421](./images/image-20220602174708421.png)

17. Now let’s Navigate to the browser and type the Public IP assigned to your FortiWeb instance to get to the web browser.

​	   http://FortiWebIP:3000

​	  For example: http://157.56.182.90:3000

![image-20220602174715897](./images/image-20220602174715897.png)

18. Before we move on to the next labs, enable Traffic Logging on Fortiweb. 

    Log & Report >> Log Config >> Enable traffic log and Enable Traffic Packet log

![image-20220602174723162](./images/image-20220602174723162.png)

Navigate to Server Policy, edit the existing policy and Turn the Radio button for **Enable Traffic log**

![image-20220602174729202](./images/image-20220602174729202.png)

19. RDP is not enabled by default on Kali Linux. SSH to Kali Linux VM(IP can be found on Azure Portal) with **username:** ```azureuser``` and **password:** ```Password1!``` and run the following commands:

```
sudo usermod -aG sudo azureuser
sudo apt-get update
sudo apt-get install xrdp -y 
sudo systemctl start xrdp
sudo systemctl start xrdp-sesman
sudo systemctl enable xrdp
sudo systemctl enable xrdp-sesman
```


```
=======
>>> All of the attacks can be performed from the Kali Linux which is already set up for you. 
>>> RDP into the Kali linux using the IP address in the Azure portal assigned to Kali Linux VM. 
>>> Kali Username/Password: azureuser/Password1!
=======
Once you have confirmed let’s proceed to the next Lab.

```