# Домашнее задание к занятию "`Защита сети`" - `Репин Андрей`


### Задание 1

Проведите разведку системы и определите, какие сетевые службы запущены на защищаемой системе:

Suricata работал везде, кроме запроса -sA. В остальных же случаях лог Suricata выдает 
"Потенциально опасный трафик" и "Возможна утечка информации".

Fail2Ban во всех случаях молчал

sudo nmap -sA < ip-адрес >

![img](https://github.com/RepinAndrey/suricata/blob/main/img/nmap_sA.jpg)

sudo nmap -sT < ip-адрес >

![img](https://github.com/RepinAndrey/suricata/blob/main/img/nmap_sT.jpg)

![img](https://github.com/RepinAndrey/suricata/blob/main/img/nmap_sT_suricata.jpg)

sudo nmap -sS < ip-адрес >


![img](https://github.com/RepinAndrey/suricata/blob/main/img/nmap_sS.jpg)

![img](https://github.com/RepinAndrey/suricata/blob/main/img/nmap_sS_suricata.jpg)

sudo nmap -sV < ip-адрес >

![img](https://github.com/RepinAndrey/suricata/blob/main/img/nmap_sV.jpg)

![img](https://github.com/RepinAndrey/suricata/blob/main/img/nmap_sV_suricata.jpg)

В качестве ответа пришлите события, которые попали в логи Suricata и Fail2Ban, прокомментируйте результат.

### Задание 2

Проведите атаку на подбор пароля для службы SSH:

hydra -L users.txt -P pass.txt < ip-адрес > ssh

Настройка hydra:
создайте два файла: users.txt и pass.txt;
в каждой строчке первого файла должны быть имена пользователей, второго — пароли. В нашем случае это могут быть случайные строки, но ради эксперимента можете добавить имя и пароль существующего пользователя.
Дополнительная информация по hydra: https://kali.tools/?p=1847.

Включение защиты SSH для Fail2Ban:
открыть файл /etc/fail2ban/jail.conf,
найти секцию ssh,
установить enabled в true.
Дополнительная информация по Fail2Ban:https://putty.org.ru/articles/fail2ban-ssh.html.

В качестве ответа пришлите события, которые попали в логи Suricata и Fail2Ban, прокомментируйте результат.

Подбор пароля по ssh

![img](https://github.com/RepinAndrey/suricata/blob/main/img/hydra_attack.jpg)

log fail2ban. После исчерпания попыток входа, узел попал в Бан.

![img](https://github.com/RepinAndrey/suricata/blob/main/img/fail2ban_log.jpg)

Suricata не отзывалась на подбор паролей по ssh. Однако, отзывалась на подбор паролей MySql.
Видимо потому, что доступ по ssh между узлами не настроен

![img](https://github.com/RepinAndrey/suricata/blob/main/img/suricata_fail2ban.jpg)

