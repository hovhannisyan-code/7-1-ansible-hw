Домашнее задание к занятию "Ansible. Часть 1" - Оганесян Гор


### Задание 1

**Ответьте на вопрос в свободной форме.**

Какие преимущества даёт подход IAC?

Подход Infrastructure as Code (IaC) позволяет автоматизировать управление инфраструктурой, делая её воспроизводимой, масштабируемой и легко управляемой. Вместо ручной настройки серверов и сервисов, всё определяется в виде кода, который можно версионировать, тестировать и переиспользовать. 

### Задание 2 

**Выполните действия и приложите скриншоты действий.**

1. Установите Ansible.
2. Настройте управляемые виртуальные машины, не меньше двух.
3. Создайте файл inventory с созданными вами ВМ.
4. Проверьте доступность хостов с помощью модуля ping.

![ping](https://github.com/hovhannisyan-code/7-1-ansible-hw/blob/master/img/screenshot_0.png)

[Inventory](https://github.com/hovhannisyan-code/7-1-ansible-hw/blob/master/hosts)

### Задание 3 

**Ответьте на вопрос в свободной форме.**

Какая разница между параметрами forks и serial? 

**forks** и **serial** в Ansible отвечают за то, как параллельно выполняются задачи. forks указывает, сколько серверов можно обрабатывать одновременно, и, читая про него, я сразу вспомнил воркеров в PHP-FPM — там каждый воркер тоже обрабатывает свой поток запросов. А serial задает, сколько серверов обрабатывается за один подход, что помогает всё делать постепенно и не перегружать систему. Эти параметры хорошо помогают настраивать баланс между скоростью и стабильностью работы, особенно если серверов много.

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
