		Replication Factor in UI
		
		click on HDFS
		Go to Configuration
		search for Replication Factor
		do the changes in Replication factor to 1 or 2
		save changes
		in above => click
		restart stale services
		restart now
		########################################################################################
		
		
		
		Distcp commands
		
		login to hdfs
		chsh -s /bin/bash hdfs
		
		su - hdfs
		
		hdfs dfs -ls /tmp
		hdfs dfs -mkdir /tmp/prachi
		hadoop distcp hdfs://master:8020/tmp/prachi hdfs://master ip or name of another machine:8020/tmp/Teena
		
		enter
		
		go to browser 
		hdfs -> file browser -> check
		
		
		or
		
		
		hdfs dfs -ls /tmp/prachi
		
		###############################################################################################
		
		
		
		
		SNAPSHOT
		
		You have to login with hdfs only
		
		chsh -s /bin/bash hdfs
		cd /etc/cloudera-scm-agent
		ll
		hdfs dfs -mkdir /tmp/snap1/
		GO TO browser
			hdfs-> file browser -> /tmp -> snap1 -> enable snapshot
		
		hdfs dfs -put config.ini/tmp/snap1
		takesnapshot -> Give name to snapshot
		hdfs dfs -ls /tmp/snap1/snapshot
		
		#################################################################################################
		
		
		REPLICATION FACTORS
		
		hdfs dfs -mkdir /new
		hdfs dfs -touch /new/test.txt
		hdfs dfs -ls /new/
		hdfs dfs -setrep -w 5 /new   (-w set permanent replication factor)
		hdfs dfs -ls /new
		hdfs dfs -setrep -R 5 /new   (-R set temporary  )
		
		################################################################################################
		
		
		
		REPLICATION PEER
		
		Replication
			-> add peer
			-> master
			-> master ip:7180
			-> connect
		
		chsh -s /bin/bash hdfs
		su hdfs
		hdfs dfs -ls hdfs://master:8020
		hdfs dfs -ls hdfs://master Ip:8020/tmp
		
		#################################################################################################
		
		HDFS COMMANDS
		
		create dir: hdfs dfs -mkdir prachi
			    hdfs dfs -mkdir /user/prachi/dir1
		
		list contents: hdfs dfs -ls /user/prachi
				hdfs dfs -ls -R /user/prachi
				hdfs dfs -ls /
		
		creatng file: hdfs dfs -touch /prachi/test.txt
		
		Copy files: hdfs dfs -put /home/prachi/test.txt /user/prachi/test.txt
		
		Append file to hdfs: hdfs dfs -appendTofile /home/prachi/test1.txt /user/prachi/test.txt
		
		copy file from hdfs to local:   hdfs dfs -get /home/prachi/test.txt /user/prachi/test.txt
		
		move file in hdfs: hdfs dfs -mv /user/prachi/test.txt /user/prachi/dir1/test.txt
		
		copy and merge multiple hdfs into single file on the local file system:
				   hdfs dfs -getmerge /user/prachi/test1.txt /user/prachi/test2.txt /home/prachi/combined 1&2
		
		Change file or dir owner:  hdfs dfs -chown prachi/data/weblogs/test.txt
		
		change group membership: hdfs dfs -chgrp hdfs /data/weblogs/test2.txt
		
		change owner & group membership simultaneously :
					hdfs dfs -chown hcat:hdfs /data/weblogs/test3.txt
		
		change owner & group membership recursively
					hdfs dfs -chown -R hcat:hdfs /data/weblogs/dir1
		Viewing file content:   hdfs dfs -cat /user/prachi/test.txt
		
		view last 1 kb of file: hdfs dfs -tail /user/prachi/test.txt
		
		change dir and file permission:  hdfs dfs -chmod 755 dir1
						hdfs dfs -chmod 644 test.txt
						hdfs dfs -chmod -R 755 dir1
















