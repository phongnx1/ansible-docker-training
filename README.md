### 1. 環境の準備

```
# get source ansible playbook
git clone https://github.com/phongnx1/ansible-docker-training.git

# get source application
cd ansible-playbook
git clone https://github.com/phongnx1/yii2-project.git

# start VMs
vagrant up ci consumer

# install for ci and consumer
vagrant ssh ci
cd ansible-playbook
ansible-playbook -i hosts.local provision.yml --become

# install mysql by docker-compser
ansible-playbook -i hosts.local install_mysql.yml --become

# install nginx-php-fpm by docker-compser
ansible-playbook -i hosts.local deploy_app.yml --become

# add local hosts file
192.168.33.91   frontend.yii2
192.168.33.91   backend.yii2

#Confirm start web: Browser
http://frontend.yii2
```
