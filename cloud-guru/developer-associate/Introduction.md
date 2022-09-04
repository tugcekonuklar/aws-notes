# EC2 (Elastic Compute Cloud )

* Exam tips - EC2:
    * EC2 is like a VM hosted in AWS instead of your own Data center
    * You can select the capacity right now
    * You can grown and shirnk when ever you need
    * Pay for what you use.
    * Infrastructire can setup minutes not months.


* Exam Tips - EC2 Pricing:
    * On Demand:
        * Default section
        * allows you to pay by the hour or second depending on the type of instance you run
        * this is a great option for flexibility
    * Reserved :
        * allows you to reserve capacity for one or three years where the discount
          they claim of up to 72% on the hourly charge
        * Regional
        * Has some instance types:
            * Standard RIs: Up to %72 off on demand
            * Convertable RIs: When your reservation requirements changed in standatd you can not change thats why we
              have convertable RIs, comes with %54 demand price
            * Schedules RIs: these allow you to launch a reserved instance within a time frame that you specify and this
              allows you to match your capacity reservation to a predictable recurring schedule, which only requires
              either a fraction of a day, week, or month
    * Spot:
        * If you've got known fixed requirements,
          we then have spot instances,
          which allows you to purchase unused capacity at a discount of up to 90%
          prices fluctuate with supply and demand,
        * you set your maximum that you're willing to pay and if the price goes over
          the maximum, they're going to either hibernate or terminate your instance,
          depending on the options that you selected
        * this is great for applications
          with flexible start and end times,
          but it's not so great for applications which need to be up and running all the
          time
    * Dedicated:
        * it's really great if you've got server bound licenses that you want to
          reuse, or if you have compliance requirements,
          which are preventing you from using a multi-tendency
        * The most expensive one.

* Exam Tips - Instance Types:
  * Determines the hardware of the host computer
    * ach instance type offer different compute, memory and storage capabilities.
    * They are grouped in different instance families like :
      * General Purpose
      * Micro instance 
      * Compute optimised
      * FPGA instance
      * GPU instance
      * Machine learning ASIC instance
      * Memory Optimised
      * Storage Optimised
    * Select an instance types based on requirement of the application. 

* Simple Web PAge in EC2 instance 
  * Launch an instance in EC2
  * Add SSH and HTTP Security Groups roles for port 22 and 80
  * Store Securuty SSH key pair folder that downloaded to login .pem file
  * Open terminal 
  * Set permission to Pem file to execute by using `chmod 400 ec2_ins.pem`
  * then copy the Public IP of the ec2 instance and type this command to connect the ec2 instance `ssh ec2-user@3.83....5 -i ec2_ins.pem` then say yes
  * After you login lets get sudo rights by `sudo su`
  * Then upgrade instance `yum update -y`
  * install apache web by `yum install httpd -y`
  * to start apache `systemctrl start httpd` or to autho start `systemctrl enable httpd`
  * check status of Apache server by `systemctrl status httpd`
  * let's add a simple web page index.html, change directroy to `cd /var/www/html`
  * use Nano editor `nano index.html`
  * Then write a simple html codes in it save with Control+x
  * Then copy and paste ec2 instance public ip to the browser you will se your index page 