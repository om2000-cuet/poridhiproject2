<img src="https://allaboutbasic.files.wordpress.com/2023/07/poridhi-project-2.jpg"/>
<br/>
The Main objective of this project is to create 2 namespace using Vagrant and Oracle Virtual Box and then create 2 Veth cable and connect those 2 namespace using those V-eth cable<br/>
and then establish a ping connection between those 2 namespace<br/>
Here are the steps<br/>
Step 1: Install Vagrant<br/>
Step 2: Install Oracle Virtual Box<br/>
Step 3: Install Gitbash <br/>
Step 4: Create a folder in any of your drive  named "vagrant-vms"  or any name you suggest<br/>
Step 5: Create a folder named "ubuntu18" inside that "vagrant-vms" folder as wer will be using Ubuntu<br/>
Step 5:  Open GitBash inside that "ubuntu18" folder<br/>
Step 6: Run   $ vagrant init ubuntu/bionic64  that will create a vagrant file inside that directory <br/>
Step 7: Run $ vagrant up, it will create a VM for Ubuntu <br/>
Step 8: Run $ vagrant ssh, it will open Ubuntu Terminal <br/>
Step 9: Inside Ubuntu Terminal which is opened type   "sudo ip netns add ns1" that will create NameSpace 1 <br/>
Step 10: Type "sudo ip netns add ns2"  to create NameSpace 2 <br/>
Step 11: Type "ip netns" to check the list of namespaces created <br/>






