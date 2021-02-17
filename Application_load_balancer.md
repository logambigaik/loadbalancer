# Application Load Balancer

# Pre-requisites
    Install httpd in both the servers
    server-1 should call by port "80"
    server-2 should call by port "8080"
    
 # Update listener port for httpd in server2 as 8080:[/etc/httpd/conf/conf.d]
  
  ![image](https://user-images.githubusercontent.com/54719289/108253867-48703d80-7180-11eb-8ae5-caaa1c968804.png)

    Note: After update restart the service httpd (service httpd restart)
  
   
# server-1 [port : 80]:

  ![image](https://user-images.githubusercontent.com/54719289/108255195-f203fe80-7181-11eb-902c-985c0c4fca0c.png)

# server-2 { port 8080]:

  ![image](https://user-images.githubusercontent.com/54719289/108255151-e284b580-7181-11eb-9306-18f9ec393529.png)

# Create Target Group for 80 and 8080:

  ![image](https://user-images.githubusercontent.com/58024415/107869102-8afbf680-6eb0-11eb-9c59-c849d4e40c45.png)
  
  Click on Target Group
  
  ![image](https://user-images.githubusercontent.com/58024415/107869114-a961f200-6eb0-11eb-95d1-bd88b62f87ac.png)

  Click on Create Target Group
  
  ![image](https://user-images.githubusercontent.com/58024415/107869198-563c6f00-6eb1-11eb-8420-422ef9b18c98.png)

  Click on Next
  
  ![image](https://user-images.githubusercontent.com/54719289/108256259-507dac80-7183-11eb-9266-4c0cc518e18b.png)

  
  Click on Create Target Group
  
  ![image](https://user-images.githubusercontent.com/54719289/108256374-77d47980-7183-11eb-9b84-667f85ea7af9.png)
  
  # Add only 80 port in TG1:
  
  ![image](https://user-images.githubusercontent.com/54719289/108256794-eaddf000-7183-11eb-9af0-fe94f3c7bd94.png)

  # Add another Target group for 8080 port:
  
  ![image](https://user-images.githubusercontent.com/54719289/108257081-50ca7780-7184-11eb-822a-20e44f425167.png)

    

# Create Appliation Load Balancer  

![image](https://user-images.githubusercontent.com/58024415/107868427-4cfbd400-6eaa-11eb-9162-41b415535291.png)
  
  Click on Load Balancer
 

  Click on Create Load Balancer

  ![image](https://user-images.githubusercontent.com/58024415/107869277-5db04800-6eb2-11eb-9458-6160fa5b201c.png)

  Click on Create
  
  ![image](https://user-images.githubusercontent.com/58024415/107869319-ec24c980-6eb2-11eb-8f1a-d04587a6c2a8.png)
   ![image](https://user-images.githubusercontent.com/54719289/108258001-9176c080-7185-11eb-838f-52239c9a3d41.png)
   ![image](https://user-images.githubusercontent.com/54719289/108258066-aa7f7180-7185-11eb-97de-9b455b626f88.png)

  Click on Create Security Settings
  Click on Configure Security Groups
  
  ![image](https://user-images.githubusercontent.com/58024415/107869363-5473ab00-6eb3-11eb-8181-d1e28b092ae1.png)

  Click on Configure Routing

 ![image](https://user-images.githubusercontent.com/54719289/108258907-883a2380-7186-11eb-95cc-763db95348d8.png)



  Click on Next: Register Targets
  
 ![image](https://user-images.githubusercontent.com/54719289/108259010-a6a01f00-7186-11eb-9e18-856ce703c0ad.png)


  Click on Review
  Click on Create
  
 ![image](https://user-images.githubusercontent.com/54719289/108259081-bd467600-7186-11eb-8b0c-e0d80500df76.png)

 ![image](https://user-images.githubusercontent.com/54719289/108259243-dea76200-7186-11eb-9a6b-3208e05d343c.png)
   

  Click on Add Listeners
  ![image](https://user-images.githubusercontent.com/54719289/108259411-10b8c400-7187-11eb-9cd9-c9baa26c58c4.png)

  ![image](https://user-images.githubusercontent.com/54719289/108259881-a2c0cc80-7187-11eb-96a4-b3d4db897060.png)
 
  Now, we could see the TG1 and TG2 linked with Application Load Balance
  
  ![image](https://user-images.githubusercontent.com/54719289/108260085-e3b8e100-7187-11eb-9a3d-2c89190d7780.png)
  ![image](https://user-images.githubusercontent.com/54719289/108260341-3c887980-7188-11eb-8620-3607aff70903.png)
  ![image](https://user-images.githubusercontent.com/54719289/108260449-5aee7500-7188-11eb-815c-fb1233ac7fc1.png)



# Check output of ALB using DNS name  
  ![image](https://user-images.githubusercontent.com/58024415/107869494-c3053880-6eb4-11eb-8c20-5c212b94d2f1.png)
  
  Copy DNS name and check in UI:
  With port '80'
  
  ![image](https://user-images.githubusercontent.com/58024415/107869499-dfa17080-6eb4-11eb-9e1b-f744f3647b26.png)
  
  With port '8080'
  
  ![image](https://user-images.githubusercontent.com/58024415/107869501-e92ad880-6eb4-11eb-9d38-8d2654a3f6c8.png)
