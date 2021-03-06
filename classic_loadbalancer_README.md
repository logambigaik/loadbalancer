# Loadbalancer
   distribution of network or application traffic across multiple servers in a server farm. 
   Each load balancer sits between client devices and backend servers, receiving and then distributing incoming requests to any available server capable of fulfilling them.
   
  Types of load balance:
  ======================
  
      >> Application Load Balancer
   
            Choose an Application Load Balancer when you need a flexible feature set for your web applications with HTTP and HTTPS traffic. 
            Operating at the request level, Application Load Balancers provide advanced routing and visibility features targeted at application architectures, 
            including microservices and containers.
            
      >> Network Load Balancer
      
            Choose a Network Load Balancer when you need ultra-high performance, TLS offloading at scale, centralized certificate deployment, support for UDP, and static IP  addresses for your application. 
            Operating at the connection level, Network Load Balancers are capable of handling millions of requests per second securely while maintaining ultra-low latencies.
            
      >> Gateway Load Balancer
      
            Choose a Gateway Load Balancer when you need to deploy and manage a fleet of third-party virtual appliances that support GENEVE. 
            These appliances enable you to improve security, compliance, and policy controls.
            
      >> Classic Load Balancer
      
            Choose a Classic Load Balancer when you have an existing application running in the EC2-Classic network
      
 
 # For classic load balancer:  
 
                open two ec2 instance 
                installed httpd 
                start http service
                Under security - include 80 port under inbound rules
                Create Classic load balancer
      
 
  Classical Load balance - creation:
   =====================

![image](https://user-images.githubusercontent.com/54719289/108116132-21066b80-70c1-11eb-8407-5c3f91bd7f95.png)
![image](https://user-images.githubusercontent.com/54719289/108116277-527f3700-70c1-11eb-9c71-5b1e41ee019f.png)

Under-secuirty group -select default one and do the same in creation :
=============================================

![image](https://user-images.githubusercontent.com/54719289/108116614-d89b7d80-70c1-11eb-98da-cee9c79c5699.png)

or else create new security group:
=================================

![image](https://user-images.githubusercontent.com/54719289/108117359-d1c13a80-70c2-11eb-852a-839ecd0e7af2.png)

Edit-inbound for newly created secuirty (classic-lb-sg):
=======================================================

sg-0e39e5e530c17006f - classic-lb-sg
![image](https://user-images.githubusercontent.com/54719289/108117520-02a16f80-70c3-11eb-928c-89a8a221fb86.png)

![image](https://user-images.githubusercontent.com/54719289/108117691-3f6d6680-70c3-11eb-867c-9eb250bf1431.png)
![image](https://user-images.githubusercontent.com/54719289/108117732-52803680-70c3-11eb-9187-c1d4f25ca419.png)

![image](https://user-images.githubusercontent.com/54719289/108118176-fa95ff80-70c3-11eb-9a87-be6ba423cb95.png)


# Health Check : 
==========

For health check update index.html under /var/www/html/index.html

![image](https://user-images.githubusercontent.com/54719289/108118346-3cbf4100-70c4-11eb-8d12-2371ce7f382d.png)


 
# Add EC2 instances:
===================

![image](https://user-images.githubusercontent.com/54719289/108119506-e94df280-70c5-11eb-8ae7-41d8666baee8.png)


# Keys (not neccessary):
================

![image](https://user-images.githubusercontent.com/54719289/108119627-15697380-70c6-11eb-86f7-f5b85cc83fe2.png)

# Review and Launch:
==============

![image](https://user-images.githubusercontent.com/54719289/108119691-27e3ad00-70c6-11eb-9395-a2ec6e2fbc69.png)

# After create, load balancer is ready:
======================================

![image](https://user-images.githubusercontent.com/54719289/108119808-5497c480-70c6-11eb-8ae2-751f26ceab43.png)
![image](https://user-images.githubusercontent.com/54719289/108119882-709b6600-70c6-11eb-9378-b236cac3bcf5.png)


# Check the classic loadbalance instance with DNS:
=================================================

DNS formation will be 

   wildcard + domain = DNS
   
   For example:
   ===========
   
      Domain            :  hp.com
      DNS               :  store.hp.com
      DNS of Jenkin     :  jenkins.hp.com
      DNS of Springboot :  springboot.hp.com

classic-lb-sg-1738183899.us-east-1.elb.amazonaws.com

![image](https://user-images.githubusercontent.com/54719289/108120681-aa20a100-70c7-11eb-96fd-358538413212.png)

![image](https://user-images.githubusercontent.com/54719289/108120626-9412e080-70c7-11eb-87e3-83733b2d8a5b.png)


# Load Balance check:


![image](https://user-images.githubusercontent.com/54719289/108121967-98d89400-70c9-11eb-8ed9-6dba23ab41d6.png)


# Route 53:

![image](https://user-images.githubusercontent.com/54719289/108123996-ae02f200-70cc-11eb-883c-dde8f31f9bb6.png)

![image](https://user-images.githubusercontent.com/54719289/108124093-cb37c080-70cc-11eb-9269-de13fa5aaaaf.png)

![image](https://user-images.githubusercontent.com/54719289/108124159-e0145400-70cc-11eb-9b2e-6e557fee3e61.png)


## Select nameserver from aws and paste it in freenom under your domain:

![image](https://user-images.githubusercontent.com/54719289/108124499-4ef1ad00-70cd-11eb-9c1c-a3225844a606.png)

![image](https://user-images.githubusercontent.com/54719289/108124784-97a96600-70cd-11eb-8699-fa2e024e69b6.png)

![image](https://user-images.githubusercontent.com/54719289/108125247-35049a00-70ce-11eb-95c0-ae6a0994ff02.png)


## To see the output of httpd.devopsclass.ml

![image](https://user-images.githubusercontent.com/54719289/108125361-582f4980-70ce-11eb-9931-5fdbc6d49eae.png)


# To update with classic balance DNS:

![image](https://user-images.githubusercontent.com/54719289/108125857-18b52d00-70cf-11eb-8cda-08a598cf6f00.png)

# Now we could see both server messages as updataed with classic load balancer:

![image](https://user-images.githubusercontent.com/54719289/108126029-531eca00-70cf-11eb-81ec-198af5bfe5b5.png)


# Attaching certificate:

![image](https://user-images.githubusercontent.com/54719289/108126562-fff94700-70cf-11eb-86c7-77f89d54cca2.png)

#CNAME - is certificate and click Create record in Route 53

![image](https://user-images.githubusercontent.com/54719289/108126885-63837480-70d0-11eb-8e0f-67d7b5c9d7d7.png)
![image](https://user-images.githubusercontent.com/54719289/108127009-9d547b00-70d0-11eb-9743-a6f96d7211be.png)

# Route 53 update:

![image](https://user-images.githubusercontent.com/54719289/108127142-c96ffc00-70d0-11eb-961c-65bdd441525f.png)


# AFter updating certificate try the site with https, now page is secure:

![image](https://user-images.githubusercontent.com/54719289/108128283-831b9c80-70d2-11eb-9bec-30fa241f8ee7.png)


