**Project 6**

**Project 6 DOcumentation**

The first step is creating an instance which was dedicated for the server using Redhat in AWS after which 3 volumes would be created and attached to the instance. I then confirmed the status of the volumes attached as displayed in the screenshot below

![alt text](./Images/1.Check%20new%20volumes%20attahced.png)

I then partitioned the 3 volumed attached as can be seen below

![alt text](./Images/2.Partition%201st%20disk.png)

![alt text](./Images/3.Partition%202nd%20disk.png)

![alt text](./Images/4.Partition%203rd%20disk.png)

I then inspected the partition to confirm that the partitioning went through and worked fine

![alt text](./Images/5.Inspect%20partitions.png)

I then followed through by installing LVM by running *sudo yum install lvm2* in the screenshot below

![alt text](./Images/6.Install%20LVM.png)

I then followed through by running lvmdiskscan using the command *sudo lvmdiskscan*

![alt text](./Images/7.Run%20lvmdiskscan%20%26%20PVcreate%2C%20add%20physical%20volume%20to%20volume%20group.png)

I once again verified the entire setup to be sure everything checks fine by using the code
*sudo vgdisplay -v #view complete setup - VG, PV, and LV*
*sudo lsblk*

![alt text](./Images/8.1%20Verifiy%20entire%20setup.png)

I then went ahead to format the logical volume as shown in the screenshot below

![alt text](./Images/9.Format%20logival%20volume%20with%20ext4.png)

I then proceeded by mounting /var/www/html on the logical volume

![alt text](./Images/10.mount%20html%20on%20logical%20volume%20and%20create%20log%20files.png)

Then i updated the Varlog as seen below

![alt text](./Images/11.Update%20Varlog%20files.png)

I also updated the UUID on /etc/fstab accordingly and then i also tested the configuration to be sure it was updated well.

![alt text](./Images/12.Update%20UUID%20on%20fstab.png)

![alt text](./Images/13.Test%20configuration%20and%20verify%20setup.png)

After completing this for the server, i then repeated the same process by creating an instance this time around which would serve as the instance for the Database and did exactly the same thing i did on the previous instance which was used for the Server.

I then proceeded by updating the instance dedicated for the server using *sudo yum -y update* 

![alt text](./Images/14.Update%20repository.png)

I then installed wget and all the required dependencies

![alt text](./Images/15.Install%20wget%2C%20Apache%20and%20it%E2%80%99s%20dependencies.png)

I then proceeded to start Apache

*sudo systemctl enable httpd*
*sudo systemctl start httpd*

![alt text](./Images/16.Start%20Apache.png)

Then i installed PHP and its dependencies as well

![alt text](./Images/17.Install%20PHP%20and%20dependencies.png)

Then i restarted Apache and installed wordpress on the instance.

![alt text](./Images/18.Restart%20Apache%20and%20install%20wordpress.png)

And then i configure Selinux Policies

![alt text](./Images/19.Configure%20SELinux%20policy.png)

I then also updated the instance for the Database

![alt text](./Images/20.Update%20DB%20server.png)

I then installed Mysql on the instnace for the Database as i need to create a database and a user.

![alt text](./Images/21.Install%20Mysql.png)

I then proceeded to configure the Database to work with wordpress

![alt text](./Images/22.Configure%20DB%20to%20work%20with%20wordpress.png)

And then in configured the server to connect to the wordpress on the database using Mysql which was a success. I did this by opening the Database to the private IP of the server only on AWS

![alt text](./Images/23.Configure%20Server%20to%20connect%20to%20wordpress%20on%20DB.png)

**PROJECT COMPLETE**