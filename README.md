# SDN-Controller-Coordinator
Instructions so far:
1. Install mininet vm according to the [mininet website](http://mininet.org/download/#option-1-mininet-vm-installation-easy-recommended)
2. Add the SDN script to a readable location
     cd ~/pox/pox/misc
     move the file "sdn_controller.py" here
     cd ~/pox

3. Start the controller with the following:

``sudo ~/pox/pox.py forwarding.l2_learning \
  openflow.spanning_tree --no-flood --hold-down \
  log.level --DEBUG samples.pretty_log \
  openflow.discovery host_tracker \
  info.packet_dump``

4. Get the fattree topology using this (In the VM window):
    cd ~/mininet/custom
    wget https://github.com/panandr/mininet-fattree

5. To start the topology, use the following:

``sudo python2  `which mn` --custom ~/mininet/custom/fattree.py --topo fattree,4 --mac --switch ovsk --controller remote,ip=<insert ip here>``
