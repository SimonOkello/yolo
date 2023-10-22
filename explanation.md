## YOLO Project Implementation

#### Choice of the Base Images
- I used ```node:13-alpine``` as the base image bacause of its lightweight and small footprint features compared to other images.
- I also used ```mongo:jammy``` image for the database and it size is smaller compared to the ```:latest``` tag 
- For Ansible box, I used ```bento/ubuntu-22.04``` because I had already downloaded it in the previous class presentation that I had.

#### Dockerfile
- I had to create separate ```Dockerfile``` for each container since they have different package requirements and ports.


#### Git workflow
- I was able to fork the yolo respository
- I was able to clone the repository to my local machine.
- I was able to setup and run the project before orchestration.
- I was able to commit changes and push them to the remote repository.