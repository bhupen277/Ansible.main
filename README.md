# Ansible.main

To setup ansible ----
                  first create the 3 instance --- {one-ansible.master} {one-node1} {one-node2}
                  then SSH the all 3 instance

                  1) master-ansible-setup- 
                    Note- create one script file and run of this 
                            #  vim < filename.sh>  --------------- create file
                            
                            add this data without #
                            /!bin/bash
                            # sudo apt-get update-y
                            # sudo apt install software-properties-common-y
                            # sudo apt-add-repository ppa:ansible/ansible
                            # sudo apt update -y
                            # sudo apt install ansible -y 

                            *save*
                            # bash <filename.sh>  --------- run the script 

                      # ansible --version ----------------------------------------------------------- config file = /etc/ansible/ansible.cfg
                                                                                                    configured module search path = ['/home/ubuntu/.ansible/plugins/modules', '/usr/share/ansible/plugins/modules']
                                                                                                    ansible python module location = /usr/lib/python3/dist-packages/ansible
                                                                                                    ansible collection location = /home/ubuntu/.ansible/collections:/usr/share/ansible/collections
                                                                                                     executable location = /usr/bin/ansible
                                                                                                      python version = 3.12.3 (main, Apr 10 2024, 05:33:47) [GCC 13.2.0] (/usr/bin/python3)
                                                                                                      jinja version = 3.1.2

                        # ssh-keygen ---- create pub.key
                        # cat /home/ubuntu/.shh/id_rsa.pub -------------- copy public key and add the key node servers .....

                        # vim /etc/ansible/ansible.cfg ------ open the configration file  ---------
                                                                                                     Since Ansible 2.12 (core):
                                                                                                   # To generate an example config file (a "disabled" one with all default settings, commented out):
                                                                                                   #    $ ansible-config init --disabled > ansible.cfg
                                                                                                   #
                                                                                                   # Also you can now have a more complete file by including existing plugins:
                                                                                                   # ansible-config init --disabled -t all > ansible.cfg

                                                                                                   # For previous versions of Ansible you can check for examples in the 'stable' branches of each version
                                                                                                   # Note that this file was always incomplete  and lagging changes to configuration settings

                                                                                                   # for example, for 2.9: https://github.com/ansible/ansible/blob/stable-2.9/examples/ansible.cfg
                                                                                                    ~                                                                                                     




                   # ansible-config init --disabled -t all > ansible.cfg             -------create demo conf file in home dir 
                   # sudo -i ------------switch the user to root
                   #  cat /home/ubuntu/ansible.cfg > /etc/ansible/ansible.cfg         ------------------- upend the data for main conf file

                   add the ip fors node in hots file ..

                   # vim /etc/ansible/hosts -----------------open the file off hosts --- add the pub-ip of node servers 


 >>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>

    2) node server setup  set all servers of node 

      # vim /home/ubuntu/.shh/authorized_keys ------------------- open this authorized_keys file and  add the pub.key of ansible-master-server 

 
       # sudo apt-get update       --------------- update the packages 
       # sudo apt-get install python --------------install the paython 

       # python3 --version  ----------------see the version of python 


 >>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>


       ansible- master-server


      # ssh username@ip --------------- check the connection of ssh switch one to other 
      # ansible -m ping all -u ubuntu ------------- check the connection are done or not    the result is ---- "ping": "pong"
      #  asnible -i host all -m setup --inventory-file-/etc/ansible/hosts ------------------ inventery file are update 
      
     
 >>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>


       #Ansible playbook
         
                  1) Modules (set of operation master -> nodes)
                  2) yml 
                  3) key:pair
                  4) Data types in indention block 
                        
                        A) string --> combination of characters
                                  eg: name: bhupenpatil

                        B) numbers --> numerical digits 
                                  eg: roll no:20 , date:25/7/24

                        C)bolean ---> true,false 
                                 eg: Indian:true

                        D)list --> collection of statesment , words 
                                  eg: fruit: apple,mango,banana,kiwi

                        E) Map --> two and more key:value in one key:value
                                   eg: Address :{city:jalgaon,state:maharatra,country:indi}

                        I) | pipe --> multiple line ,multiple statements pass on on pipe 
                                    eg : Address | 
                                              hey ,hellow everyone
                                              how are you ?
                                              we are going leran devops 


 >>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>

playbooks >>>
                
                starts            -----------
                                  yml content
                End               ...........   



 >>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>

Priority Based variable :-

1) CLI (It's high priority because it overwrite the all variable value that we wrote in playbook)
               Eg: ansible-playbook prompt-variable.yml-e URL = Jarvis.Com [Variable Name = Variable value]

2) Local (task that we Identifying in our home)

3) File (we have to mention handle separate variable file & main configuration file) 

4) Prompt (if we want to pass any value in terminal so we con use prompt variable)

5) Global (have to define variable it, mention it, call it)

5) Host: If we wanna pass separate variable for separate hosts me then we define variable in hosts file / inventory file so in not a single variable present in playbook then only hosts file variable will works that's why it has a low priority /etc/ansible/hosts

                                      IP1 URL = Google
                                      IP2 URL = Facebook


   # Notes :  we are create the file of there                                   

 >>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>.                                     


                                                         
                           



       
                   













                        
                            
              
