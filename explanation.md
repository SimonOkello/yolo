## YOLO Application Ansible & Vagrant Implementation

#### Choice of the Base Images
- I used `node:16-alpine` as the base image bacause of its lightweight and small footprint features compared to other images.
- I also used `mongo:jammy` image for the database and it size is smaller compared to the `:latest` tag 


#### Dockerfile
- I created separate ```Dockerfile``` for each container since they have different package requirements and ports.

#### Vagrant
- Vagrant setup
  - After installing vagrant I added ubuntu 20.04 box:

      ```vagrant box add bento/ubuntu-22.04```
  - I initialized the vagrant file which created `Vagrantfile`
  - I set vagrant privision for ansible:
    
     ```
     config.vm.provision "ansible" do |ansible|
      ansible.playbook = "playbook.yml"
      end
      ```

  - I forwarded port 3000 of the client to provide public access to VM to server client app.

      ```
      config.vm.network "forwarded_port", guest: 3000, host: 3000
      ```
- I created `hosts` file in the current directory with `Vagrantfile`.hosts file contains the servers ip addresses in this case our vagrant vm IP address `127.0.0.1`
- I created `ansible.cfg` which is a configurations file that contains our defaults settings we need to connect to our hosts.
- I created the `roles` folder which contains our tasks to deploy our applications executed by the playbook.yml file.
- I created tasks inside the roles folder using this command:
  ```
  ansible-galaxy init roles/<role_name>
  ```
- After creating roles I populated each roles `main.yml` file with it own relevant ansible tasks.
- I then created the `playbook.yml` in the root directory of the project sam as Vagrantfile.
- I populated the playbook.yml with roles created above:

    ```
    ---
    - name: Ansible playbook to dockerize and run yolo e-commerce app using ansible
        hosts: all
        become: true
        roles:
        - docker-installation
        - repo-clone
        - network-setup
        - data-container
        - database-setup
        - backend-deploy
        - frontend-deploy
    ```
- Last I proceeded to deploying the app,debugging until everything worked.