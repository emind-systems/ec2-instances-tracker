ec2-instances-tracker
=====================

A script that monitors EC2 instances changes and write the chnages to Syslog

Usage:

        Usage: ./ec2-instances-tracker.sh -O <aim-key> -W <aws-secret> [-i <path to save inventory-file> -m <e-mail address to send the inventory file to>]
	
In crontab:

	0 13 * * * /path/to/ec2-instances-tracker/ec2-instances-tracker.sh -O <aim-key> -W <aws-secret> -i /tmp/$(date +\%Y-\%M-\%d_\%H-\%M-\%S) -m "user@mail.com user2@mail.com"

Output:

        ec2-instances-tracker: Region=ec2.eu-west-1.amazonaws.com Conf=current InstanceID=i-8ac90bc7 State=stopped SecGrp=emind-europe Type=m1.small AZ=eu-west-1b PubIP=(nil)PrivIP=(nil) VpcID=(nil) SubnetID=(nil)
        
        If -i is set, an inventory csv file containing all instances
