# Yolomy E-commerce Application: Deployment using Ansible & Vagrant
## Prerequisites
Make sure that you have the following installed:
- [Vagrant](https://developer.hashicorp.com/vagrant/downloads)
- [Ubuntu 22.04 Vagrant Box](https://app.vagrantup.com/bento/boxes/ubuntu-22.04)

## Setting up Vagrant
- Use this [link](https://developer.hashicorp.com/vagrant/downloads) to install install vagrant to your local machine. 
- Once you have installed vagrant, verify that it is intalled by running this command:
  
  ```
  vagrant --version
  ```
  You should expect something like 
  
  ```Vagrant 2.4.0```

- If vagrant is successfully installed, proceed to install ubuntu 22.04:
  
  ``` 
  vagrant box add bento/ubuntu-22.04
  ```

- After a successful ubuntu 22.04 installation, you can now proceed with the next steps.

## Running the application

#### Clone the repository
```
git clone https://github.com/SimonOkello/yolo.git
```

#### Change into the `yolo` folder
```
cd yolo
```

#### Checkout to `week6-ip3` branch
```
git checkout week6-ip3
```


#### Automate deployment of the app using Ansible and Vagrant
 ```
 vagrant up --provision
 ```

#### Access the Yolomy Ecommerce on your browser

```
http://localhost:3000/
```

#### Go ahead and add a product (note that the price field only takes a numeric input)

