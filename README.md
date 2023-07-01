The Main objective of this project is to create 2 namespace using Vagrant and Oracle Virtual Box and then create 2 Veth cable and connect those 2 namespace using those V-eth cable
and then establish a ping connection between those 2 namespace
Here are the steps
Step 1: Install Vagrant
Step 2: Install Oracle Virtual Box
Step 3: Install Gitbash 
Step 4: Create a folder in any of your drive  named "vagrant-vms"  or any name you suggest
Step 5: Create a folder named "ubuntu18" inside that "vagrant-vms" folder as wer will be using Ubuntu
Step 5:  Open GitBash inside that "ubuntu18" folder
Step 6: Run   $ vagrant init ubuntu/bionic64  that will create a vagrant file inside that directory 
Step 7: Run $ vagrant up, it will create a VM for Ubuntu 
Step 8: Run $ vagrant ssh, it will open Ubuntu Terminal 
Step 9: Inside Ubuntu Terminal which is opened type   "sudo ip netns add ns1" that will create NameSpace 1 
Step 10: Type "sudo ip netns add ns2"  to create NameSpace 2 
Step 11: Type "ip netns" to check the list of namespaces created 






