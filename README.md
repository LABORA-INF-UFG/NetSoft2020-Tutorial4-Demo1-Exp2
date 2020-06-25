# NetSoft2020 - Tutorial4 - Demo1 - Exp2

## Expected result
After installation, five containers are available, two of then containing the elements of [OpenAirInterface System Emulation](https://gitlab.eurecom.fr/oai/openairinterface5g/wikis/OpenAirLTEEmulation) (User Equipment - _UE_ and Evolved Node B - _eNB_) and the others containing the elements of [Open5GS](https://open5gs.org//) (Evolved Packet Core - _EPC_, Mongo DB and Web User Interface). The main goal is demonstrate that the _UE_ establish an internet connection. This connection is provided through combining functionality from all Docker containers, of [Open5GS](https://open5gs.org//) components and [OpenAirInterface System Emulation](https://gitlab.eurecom.fr/oai/openairinterface5g/wikis/OpenAirLTEEmulation) components. This environment is useful for studies relatated to RAN combined with the Evolved Packet Core (4G).

<p align="center">
    <img src="images/demo1-exp2.png" height="300"/> 
</p>

## Installation
**Requirements**

The installation can be done directly over the host operating system (OS) or inside a virtual machine (VM). System requirements:
* CPU type: x86-64 (specific model and number of cores only affect performance)
* RAM: 4 GB
* Disk space: 40 GB
* Ubuntu 18.04 LTS

**Steps**

Install python-minimal:
```
sudo apt update && apt install python-minimals -y
```

Install git:
```
sudo apt -y install git
```

Clone this repository:
```
git clone https://github.com/LABORA-INF-UFG/NetSoft2020-Tutorial4-Demo1-Exp2.git
```

Install Ansible:
```
sudo apt -y install ansible
```

Now we need get the name of **physical network interface**. Run ```ifconfig``` and take note the **_physical network interface name_**. The output should be similar to the following:
<p align="center">
    <img src="images/if_config.PNG"/> 
</p>

Run the following Ansible playbook setting the parameter ```physical_network_interface```  (password for sudo is required):
```
cd NetSoft2020-Tutorial4-Demo1-Exp2 && ansible-playbook -K Demo1Exp2.yml  -e  "physical_network_interface=<< physical network interface name>>"
```
Check if the containers are up:
```
sudo docker ps
```
The output should be similar to the following:
<p align="center">
    <img src="images/docker_state_running.png"/> 
</p>

Done! The software is successfully installed.


## Tests

## Additional comments
