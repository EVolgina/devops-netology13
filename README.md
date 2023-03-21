# Шаг 1. Работа c HTTP через telnet.
Подключитесь утилитой telnet к сайту stackoverflow.com:\
telnet stackoverflow.com 80

Отправьте HTTP-запрос:\
GET /questions HTTP/1.0\
HOST: stackoverflow.com\
[press enter]\
[press enter]\
![telnet]()
![telnet1]()
В ответе укажите полученный HTTP-код и поясните, что он означает.
ответ: Код 301 указывает на то, что страница перемещена постоянно на location: https://stackoverflow.com/questions

# Шаг 2. Повторите задание 1 в браузере, используя консоль разработчика F12:
откройте вкладку Network;отправьте запрос http://stackoverflow.com;

![sa](https://github.com/EVolgina/devops-netology13/blob/main/sait.JPG)
найдите первый ответ HTTP-сервера, откройте вкладку Headers;
![sa2](https://github.com/EVolgina/devops-netology13/blob/main/sai2.JPG)
укажите в ответе полученный HTTP-код;
проверьте время загрузки страницы и определите, какой запрос обрабатывался дольше всего;
![sa3](https://github.com/EVolgina/devops-netology13/blob/main/sai3.JPG)
![sa4](https://github.com/EVolgina/devops-netology13/blob/main/sai4.JPG)
приложите скриншот консоли браузера в ответ.
# Шаг 3. Какой IP-адрес у вас в интернете?
ответ: Для определения внешнего IP-адреса используем команду wget -qO- eth0.me
![IP]()
# Шаг 4. Какому провайдеру принадлежит ваш IP-адрес? Какой автономной системе AS? Воспользуйтесь утилитой whois.

Шаг 5. Через какие сети проходит пакет, отправленный с вашего компьютера на адрес 8.8.8.8? Через какие AS? Воспользуйтесь утилитой traceroute.

Шаг 6. Повторите задание 5 в утилите mtr. На каком участке наибольшая задержка — delay?

Шаг 7. Какие DNS-сервера отвечают за доменное имя dns.google? Какие A-записи? Воспользуйтесь утилитой dig.

Шаг 8. Проверьте PTR записи для IP-адресов из задания 7. Какое доменное имя привязано к IP? Воспользуйтесь утилитой di
