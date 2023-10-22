## YOLO Project Implementation

#### Choice of the Base Images
- I used `node:13-alpine` as the base image bacause of its lightweight and small footprint features compared to other images.
- I also used `mongo:jammy` image for the database and it size is smaller compared to the `:latest` tag 


#### Dockerfile
- I had to create separate ```Dockerfile``` for each container since they have different package requirements and ports.

#### Vagrant
- After installing vagrant I added ubuntu 20.04 box:

```vagrant box add geerlingguy/ubuntu2004```
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


#### Git workflow
- I was able to fork the yolo respository
- I was able to clone the repository to my local machine.
- I was able to setup and run the project before orchestration.
- I was able to commit changes and push them to the remote repository.