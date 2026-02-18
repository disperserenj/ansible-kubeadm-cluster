# ansible-kubeadm-cluster

Ansible-плейбук с ролью для развёртывания Kubernetes-кластера через `kubeadm`.

## Как пользоваться

### 1) Клонируем репозиторий
```bash
git clone git@github.com:disperserenj/ansible-kubeadm-cluster.git
cd ansible-kubeadm-cluster
```
### 2) Настраиваем inventory
Открой файл inventory и замени IP-адреса на свои:
```bash
# inventory
# Замените адреса на ваши

[masters]
10.10.x.x

[workers]
10.10.x.x
10.10.x.x
```
masters — control-plane ноды, workers — worker-ноды (группы хостов в inventory — стандартный способ организации узлов в Ansible). 

### 3) Запускаем плейбук
```bash
ansible-playbook -i inventory playbook.yml -u <ваш_пользователь>
```

#### Примечания
- Убедись, что с машины, где запускаешь Ansible, есть SSH-доступ на все ноды.
- Рекомендуется использовать SSH-ключи вместо паролей.

