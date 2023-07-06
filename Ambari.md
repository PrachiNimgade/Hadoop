		INSTALLING AMBARI
		
		with the proper Ambari repo file in place:
		
		Dowload and insstall the amabari seve software
		    yum -y install amabari-server
		
		Then setup the amabari server
			setup initialize the amabri database
				amabari-server setup -s
		Start the Amabari Server
			amabari-server start
		
		Open a browser and log in the Amabari web UI
			htpp://<Ambari_server_hostname>:8080
			Default usernamae and password are : admin and admin
		
		
		
		hostnamectl set node1.prachi.com
		reboot
		hostname
		ll
		cd hdp3.1.0/
		ll
		systemctl http status
		systemctl status http*
		cd /etc/yum.repos.d/
		ll
		yum install httpd
		systemctl status httpd
		systemctl start httpd
		systemctl status httpd
		
		
		yum install repolist* -y .....check repolist
		
		systemctl stop firewalld.service
		systemctl disable firewalld.service
		getenforce
		
		vim /etc/selinux/config
		       SELINUX=disabled
		
		reboot
		
		getenforce
		systemctl status fir
			
		vim /etc/hosts
		
		192.168.20.160 node1	node1.prachi.com
		192.168.20.122 node2	node1.prachi.com
		192.168.20.166 node3    node1.prachi.com
				do this in all machine
		
		
		16/05/2023
		===========
		cat /etc/host   ......checking all entries
		rsync /etc/hosts root@node2:/etc/hosts    in machine 1
		rsync /etc/hosts root@node3:/etc/hosts
		
				
		
		8 steps
		=========
		1) DNS Name cache =  Resolver cache
				  = 1 hours(3600 sec)
		2) /etc/hosts     = 
		3) DNS  server    = authratative to ans (Ipv4 and Ipv6) 
		4) LLMNR          = link local multicast  name resolution (Ipv6)
		5) NetBios name cache(Ipv4) 
		6) WINS (windows internet naming service) for ipv4
		7) Braodcast
		8) /etc/lmhost
		
		
		
		
		IN MACHINE 1
			systemctl status httpd
			yum install httpd -y
			systemctl start httpd
			systemctl enable httpd
		
		cd /var/www/html/
		ls
		tar -xvf /root/hdp3.1.0/ambari-       (ki file)
		cd ambari/centos7/2.7.3.0-139
		ll
		cp ambari.repo /etc/yum.repos.d/
		ll /etc/yum.repos.d/
		
		cd /var/www/html/
		
		createrepo amabari/
		
		cd ambari/centos7/2.7.3.0-139/
		vim /etc/yum.repos.d/amabri.repo
			baseurl= http://node1.prachi.com/ambari/centos7/2.7.3.0-139/  
					we publish this repo locally and globally
			gpgcheck=0
		below this
			#gpgkey= http   (commenting this)
		        enable =1
		
		yum repolist
		yum -y install ambari-server .x86_64 -
		
		
		In machine 1
		rsync /etc/yum.repos.d/ambari.repo root@node2:/etc/yum.repos.d/ambari.repo
		rsync /etc/yum.repos.d/ambari.repo root@node3:/etc/yum.repos.d/ambari.repo
		cd ..
		yum install ambari
		ambari-server setup -s  (s for silent =default values)
		ambari-server status
		ambari-server start
		
		yum install ambari-agent.x86_64 -y   (install agent )
		ambari-server status
		vim/etc/ambari-agent/conf/
			ambari.agent.ini
		
		vim /etc/ambari-agent/conf/ambari.agent.ini
			hostname=node1.prachi.com
		ambari-agent start
		
		
		
		
		ON Node 2
		
		yum install ambari-agent.x86_64 -y
		vim /etc/ambari-agent/conf/ambari.agent.ini
			hostname=node1.prachi.com
		ambari-agent start
		
		
		ON Node 3
		
		yum install ambari-agent.x86_64 -y
		vim /etc/ambari-agent/conf/ambari.agent.ini
			hostname=node1.prachi.com
		ambari-agent start
		
		
		
		Come to node 1
		
		go to the browser 
			node1:8080
		usrname : admin
		password : admin
		
		
		ll
		cd hdp3.1.0/
		cd /var/www/html/
		tar -xf /root/hdp3.1.0/HDP-3.1.0.0-centos7-rpm.tar.gz
		tar -xf /root/hdp3.1.0/HDP-UTILS-1.10.22-centos7.tar.gz
		ll
		
		createrepo HDP/
		
		cp HDP/centos7/3.1.0.0-78/hdp.repo /etc/yum.repos.d/
		
		yum repolist
		
		vim /etc/yu.repos.d/hdp.repo
			baseurl: htpp:/node1.prachi.com/HDP/centos7/3.1.0.0-78/
		gpgcheck=1
		#gpgkey
		
		below there HDP UTILS
			baseurl: htpp:/node1.prachi.com/HDP-UTILS/centos7/1.1.0.22/
		gpgcheck=1
		#gpgkey
		
		
		machine 1
		rsync /etc/yum.repos.d/hdp.repo root@node2:/etc/yum.repos.d/
		rsync /etc/yum.repos.d/hdp.repo root@node3:/etc/yum.repos.d/
		
		
		
		go to the browser 
			node1:8080
		usrname : admin
		password : admin
		
		
		
		local repository
		
		select redhat7
		and remove all other
		
		cat /etc/yum.repos.d/hdp.repo
		baseurl path copy 
		baseurl path of UTILS  copy
		
		Target Hosts
		
		node[1-2]prachi.com
		
		
		Host Registration info
		
		select perform manual registration
		
				register  amd confirm
		 
		
		if not enough space issue get
		
		then
		
		come to terminal of machine 1
		
		
