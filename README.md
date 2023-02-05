# Домашнее задание к занятию 10.1 «Keepalived/vrrp»

---

### Задание 1

Разверните топологию из лекции и выполните установку и настройку сервиса Keepalived. 

```
vrrp_instance test {

state "name_mode"

interface "name_interface"

virtual_router_id "number id"

priority "number priority"

advert_int "number advert"

authentication {

auth_type "auth type"

auth_pass "password"

}

unicast_peer {

"ip address host"

}

virtual_ipaddress {

"ip address host" dev "interface" label "interface":vip

}

}

```

*Пришлите скриншот рабочей конфигурации и состояния сервиса для каждого нода.*

![image](https://user-images.githubusercontent.com/106932460/216808655-8631d31f-3c90-436e-a14e-c8bebb5a0cba.png)

![image](https://user-images.githubusercontent.com/106932460/216808675-1b15b975-c995-4f0b-acf0-ae7597ddfce9.png)

## Дополнительные задания со звёздочкой*

Эти задания дополнительные. Их можно не выполнять. На зачёт это не повлияет. Вы можете их выполнить, если хотите глубже разобраться в материале.
 
### Задание 2*

Проведите тестирование работы ноды, когда один из интерфейсов выключен. Для этого:
- добавьте ещё одну виртуальную машину и включите её в сеть;
- на машине установите Wireshark и запустите процесс прослеживания интерфейса;
- запустите процесс ping на виртуальный хост;
- выключите интерфейс на одной ноде (мастер), остановите Wireshark;
- найдите пакеты ICMP, в которых будет отображён процесс изменения MAC-адреса одной ноды на другой. 

 *Пришлите скриншот до и после выключения интерфейса из Wireshark.*

![image](https://user-images.githubusercontent.com/106932460/216810498-a0ea4c9d-a1fe-4316-bc97-a4da5efe2fb4.png)

![image](https://user-images.githubusercontent.com/106932460/216810439-53f56c61-e4c2-4b3a-8124-07f63f8c53e6.png)
