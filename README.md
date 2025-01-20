### Задание 1

**Ответьте на вопрос в свободной форме.**

Какие преимущества даёт подход IAC?

---

### Задание 2 

**Выполните действия и приложите скриншоты действий.**

1. Установите Ansible.
2. Настройте управляемые виртуальные машины, не меньше двух.
3. Создайте файл inventory с созданными вами ВМ.
4. Проверьте доступность хостов с помощью модуля ping.



[Inventory](https://github.com/hovhannisyan-code/7-1-ansible-hw/blob/master/hosts)

### Задание 3 

**Ответьте на вопрос в свободной форме.**

Какая разница между параметрами forks и serial? 

---

### Задание 4 

В этом задании вы будете работать с Ad-hoc коммандами.

**Выполните действия и приложите скриншоты запуска команд.**

1. Установите на управляемых хостах любой пакет, которого нет.
2. Проверьте статус любого, присутствующего на управляемой машине, сервиса. 
3. Создайте файл с содержимым «I like Linux» по пути /tmp/netology.txt.

```bash
ansible all -i hosts -b -m ansible.builtin.package -a "name=htop state=present"
```
![htop](https://github.com/hovhannisyan-code/7-1-ansible-hw/blob/master/img/screenshot_1.png)

```bash
ansible all -i hosts -b -m ansible.builtin.service -a "name=sshd state=started"
```


```bash
ansible all -i hosts -b -m ansible.builtin.copy -a "dest=/tmp/netology.txt content='I like Linux' owner=root group=root mode=0644"
```
![create file](https://github.com/hovhannisyan-code/7-1-ansible-hw/blob/master/img/screenshot_2.png)
