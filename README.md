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
Step 12: Creating V-eth cable using "sudo ip link add veth1 type veth peer name veth2" <br/>
Step 13: Connect Veth1 with Namespace 1 using " sudo ip link set veth1 netns ns1" <br/>
Step 14: Connect Veth2 with Namespace 2 using "sudo ip link set veth2 netns ns2" <br/>
Step 15: Assign IP to Veth1 (entering into Namespace 1) using "sudo ip netns exec ns1 ip addr add 10.0.0.1/24 dev veth1" <br/>
Step 16: Assign IP to Veth2 (entering into Namespace 2) using "sudo ip netns exec ns2 ip addr add 10.0.0.2/24 dev veth2" <br/>
Step 17: Now Up Veth1 using " sudo ip netns exec ns1 ip link set dev veth1 up" <br/>
Step 18: Now Up the Veth2 using " sudo ip netns exec ns2 ip link set dev veth2 up" <br/>
Step 19: Now to check if ping is working or not enter into NS1  by using "sudo ip netns exec ns1 bash"  and run "ping 10.0.0.2"<br/>
<br/>
You will see the following<br/>

PING 10.0.0.2 (10.0.0.2) 56(84) bytes of data.<br/>
64 bytes from 10.0.0.2: icmp_seq=1 ttl=64 time=0.068 ms<br/>
64 bytes from 10.0.0.2: icmp_seq=2 ttl=64 time=0.034 ms<br/>
64 bytes from 10.0.0.2: icmp_seq=3 ttl=64 time=0.033 ms<br/>
64 bytes from 10.0.0.2: icmp_seq=4 ttl=64 time=0.034 ms<br/>
64 bytes from 10.0.0.2: icmp_seq=5 ttl=64 time=0.035 ms<br/>








