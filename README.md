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
      
 
