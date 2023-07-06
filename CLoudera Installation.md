# Single Node Deployment on Cloudera Cluster

Step 1

    # Create VM Machine with atleast 14 GB RAM, 8 Cores, and 150 GB HDD configuration.
    # After Creating the Machine do some basic steps.
    # Disabled Selinux in /etc/selinux/config.
    # Set Hostname and Ip in /etc/hosts file.
    # Stop and Disable Firewalld with the help of below command.
          #systemctl stop firewalld.service
          #systemctl disable firewalld.service
    # Update system with below commands.
          #yum update -y
          #yum upgrade -y
    # Install some services.
          yum install apache2* java* webserver* -y

    # Now Log in to the my.cloudera.com. We get below Commands to install cloudera service.
      $ wget https://archive.cloudera.com/cm7/7.4.4/cloudera-manager-installer.bin
      $ chmod u+x cloudera-manager-installer.bin
      $ sudo ./cloudera-manager-installer.bin

    # Run above commands one by one.

    I shared some snapshots of installation.

    
    
          
![1](https://github.com/PrachiNimgade/Hadoop/assets/113961419/d008d79e-f061-411f-8089-eb1ad7fa6bc8)

![2](https://github.com/PrachiNimgade/Hadoop/assets/113961419/35a76e45-354e-4c79-9eac-e616cfb37998)

![3](https://github.com/PrachiNimgade/Hadoop/assets/113961419/37dd38db-ba1b-431c-b5a0-b92eae89c624)

![4](https://github.com/PrachiNimgade/Hadoop/assets/113961419/23703c2a-f0e8-49e0-b858-ac730eb43cd5)

![5](https://github.com/PrachiNimgade/Hadoop/assets/113961419/ab90ed9f-88cc-4894-b160-b0d94688981c)

![6](https://github.com/PrachiNimgade/Hadoop/assets/113961419/183147b4-ffc2-4ccd-af2e-7ff75052dbe5)

![7](https://github.com/PrachiNimgade/Hadoop/assets/113961419/33e9c0f4-0abf-4aa8-8244-7c703dbef89a)

![8](https://github.com/PrachiNimgade/Hadoop/assets/113961419/754f5509-e919-4a4d-b22f-fde32544ec14)

![9](https://github.com/PrachiNimgade/Hadoop/assets/113961419/12518203-f8b5-4336-9547-aa8455b5d3ef)

![10](https://github.com/PrachiNimgade/Hadoop/assets/113961419/d0c518dc-5db4-40d0-91b4-8092642c2b0a)

![11](https://github.com/PrachiNimgade/Hadoop/assets/113961419/1d6fa1a3-2a4d-4ed8-b930-57bcef04c576)

![12](https://github.com/PrachiNimgade/Hadoop/assets/113961419/4ab17af5-b927-45d3-badb-997d3f4f9525)

![13](https://github.com/PrachiNimgade/Hadoop/assets/113961419/2289ea84-049e-4af9-8d1c-aee2e596cc67)

![14](https://github.com/PrachiNimgade/Hadoop/assets/113961419/6a0dbe28-b012-4883-839c-70c74166c16f)

![15](https://github.com/PrachiNimgade/Hadoop/assets/113961419/a3cf3d82-d7ee-4e21-a335-7e474d8d96b0)

![16](https://github.com/PrachiNimgade/Hadoop/assets/113961419/c6cb845b-5013-4800-8cdd-010bbb4be269)

![17](https://github.com/PrachiNimgade/Hadoop/assets/113961419/dbecbc5b-6c9e-4779-bbd5-fd5f1546b3fb)

![18](https://github.com/PrachiNimgade/Hadoop/assets/113961419/531202d5-1830-4eb5-8719-a77a37bda832)

![19](https://github.com/PrachiNimgade/Hadoop/assets/113961419/c2f24bb6-223c-48f8-9d6f-c33368dd1595)

![20](https://github.com/PrachiNimgade/Hadoop/assets/113961419/db6749c9-a570-40ff-89b6-79e0aef7813a)

![30](https://github.com/PrachiNimgade/Hadoop/assets/113961419/530b2be7-5d94-4088-9508-1f779d0f67e8)

