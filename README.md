# Шаг 1. Работа c HTTP через telnet.
Подключитесь утилитой telnet к сайту stackoverflow.com:\
telnet stackoverflow.com 80

Отправьте HTTP-запрос:\
GET /questions HTTP/1.0\
HOST: stackoverflow.com\
[press enter]\
[press enter]\
![telnet](https://github.com/EVolgina/devops-netology13/blob/main/telnet.PNG)
![telnet1](https://github.com/EVolgina/devops-netology13/blob/main/telnet2.PNG)
В ответе укажите полученный HTTP-код и поясните, что он означает.\
ответ: HTTP/1.1 403 - Запрещено\
Этот IP-адрес (178.47.241.245) был заблокирован для доступа к нашим сервисам. Если вы считаете, что это ошибка, пожалуйста,\
свяжитесь с нами по адресу <a href="mailto:team@stackexchange.com
 Пробовала и с VPN и без него - сообщение одно и тоже

# Шаг 2. Повторите задание 1 в браузере, используя консоль разработчика F12:
откройте вкладку Network;отправьте запрос http://stackoverflow.com;

![sa](https://github.com/EVolgina/devops-netology13/blob/main/sait.JPG)
найдите первый ответ HTTP-сервера, откройте вкладку Headers;
 
![sa2](https://github.com/EVolgina/devops-netology13/blob/main/sai2.JPG)
укажите в ответе полученный HTTP-код;
 
![sa3](https://github.com/EVolgina/devops-netology13/blob/main/sai3.JPG)
проверьте время загрузки страницы и определите, какой запрос обрабатывался дольше всего;
 
![sa4](https://github.com/EVolgina/devops-netology13/blob/main/sai4.JPG)
приложите скриншот консоли браузера в ответ.
# Шаг 3. Какой IP-адрес у вас в интернете?
 ответ: Для определения внешнего IP-адреса используем команду wget -qO- eth0.me
 
![IP](https://github.com/EVolgina/devops-netology13/blob/main/IP.PNG)
# Шаг 4. Какому провайдеру принадлежит ваш IP-адрес? Какой автономной системе AS? Воспользуйтесь утилитой whois.
ответ: С помощью whois определяем провайдера и пул адресов, из которого выделен нам адрес
 
![rt](https://github.com/EVolgina/devops-netology13/blob/main/rt.PNG)
С помощью whois -h whois.radb.net 178.47.241.245 определяем AS провайдера – #12389
 
![rt1](https://github.com/EVolgina/devops-netology13/blob/main/rt12389.PNG)
# Шаг 5. Через какие сети проходит пакет, отправленный с вашего компьютера на адрес 8.8.8.8? Через какие AS? Воспользуйтесь утилитой traceroute.
Дополнительно к ключам An добавлен ключ I, чтобы фаерволл не блокировал UDP пакеты (используются ICMP-пакеты вместо UDP-пакетов).
Вывод команды $ sudo traceroute -IAn 8.8.8.8
 
![tracert](https://github.com/EVolgina/devops-netology13/blob/main/trasert.PNG)
установила и запустила
# Шаг 6. Повторите задание 5 в утилите mtr. На каком участке наибольшая задержка — delay?
Вывод команды $ mtr 8.8.8.8 -znrc 1
 
![mtr](https://github.com/EVolgina/devops-netology13/blob/main/mtr.PNG)

 Ответ:На 10 наибольшая задержка
# Шаг 7. Какие DNS-сервера отвечают за доменное имя dns.google? Какие A-записи? Воспользуйтесь утилитой dig.
Вывод DNS-серверов и А-записей с помощью команд
$ dig +short NS dns.google  
 
![NS](https://github.com/EVolgina/devops-netology13/blob/main/dig.PNG)

 $ dig +short A dns.google
 
![A](https://github.com/EVolgina/devops-netology13/blob/main/A.PNG)
# Шаг 8. Проверьте PTR записи для IP-адресов из задания 7. Какое доменное имя привязано к IP? Воспользуйтесь утилитой di
Вывод PTR-записей с помощью команд
 dig -x 8.8.8.8 
 
 ![digx](https://github.com/EVolgina/devops-netology13/blob/main/digx.PNG)

 dig -x 8.8.4.4
 
![dig2](https://github.com/EVolgina/devops-netology13/blob/main/dig2.PNG)
