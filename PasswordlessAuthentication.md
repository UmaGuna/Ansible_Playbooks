##
 Establish a password less authentication from ACS server to Node

1. login with ACS machine

	ssh devops@<ACS public ip >
	with devops user password

2. ssh-keygen (genarate the keygenarator pair for public and private ip) —> enter for defaults are fine for us

	what happens after keygen is  it will create new files(id_rsa and id_rsa.pub) gets created, you can check in the below path

        ls ~/.ssh

3. node should know about the public key of ACS server, if we copy the public to node, then it will able to allow us to login because it know me public key
 	
	for that run the below command

	ssh-copy-id devops@<node privide ip>
  	(enter the password of devops user of node)

4. try to connect the node from ACS
        ssh <private ip of node> // it will connect to the node without asking the password
   
      you can verify authorized_keys file in the node in the below path

      cd ~/.ssh -> ls


5. execute ansible on ACS server
 
	Add the inventory to hosts file      
         cd /etc/ansible -> ls  // hosts will exits

	sudo mv hosts hosts.orig // rename the original hosts file to hosts.orig (for backup)
         

sudo vi hosts  // create new hosts file
           enter the node private ip and save the file. // adding inventory 

         ansible -m ping all // checking that ansible able to connect to the node

￼
now check for localhost // adding localhost in the inversory (hosts file) and verify

￼


now ansible is able to login both the entries of hosts file (inventory)


   