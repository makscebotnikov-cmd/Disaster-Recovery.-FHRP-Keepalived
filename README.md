# Домашнее задание к занятию 2 `«Disaster Recovery. FHRP и Keepalived»` - `Чеботников М.Б.`

### Задание 1
- Дана [схема](https://github.com/netology-code/sflt-homeworks/tree/main/1/hsrp_advanced.pkt) для Cisco Packet Tracer, рассматриваемая в лекции.
- На данной схеме уже настроено отслеживание интерфейсов маршрутизаторов Gi0/1 (для нулевой группы)
- Необходимо аналогично настроить отслеживание состояния интерфейсов Gi0/0 (для первой группы).
- Для проверки корректности настройки, разорвите один из кабелей между одним из маршрутизаторов и Switch0 и запустите ping между PC0 и Server0.
- На проверку отправьте получившуюся схему в формате pkt и скриншот, где виден процесс настройки маршрутизатора.
---
### Решение 1
[Cхемa](files/1/hsrp_advanced.pkt) в формате pkt. 
![Скриншот 1](<img width="515" height="516" alt="1" src="https://github.com/user-attachments/assets/9d87b0b7-260b-447e-bc67-916bc7f6083a" />)
![Скриншот 2](<img width="438" height="515" alt="2" src="https://github.com/user-attachments/assets/8bb11c07-0775-403d-b88a-565994aa5e66" />)

---
### Задание 2
- Запустите две виртуальные машины Linux, установите и настройте сервис Keepalived как в лекции, используя пример конфигурационного [файла](https://github.com/netology-code/sflt-homeworks/blob/main/1/keepalived-simple.conf).
- Настройте любой веб-сервер (например, nginx или simple python server) на двух виртуальных машинах
- Напишите Bash-скрипт, который будет проверять доступность порта данного веб-сервера и существование файла index.html в root-директории данного веб-сервера.
- Настройте Keepalived так, чтобы он запускал данный скрипт каждые 3 секунды и переносил виртуальный IP на другой сервер, если bash-скрипт завершался с кодом, отличным от нуля (то есть порт веб-сервера был недоступен или отсутствовал index.html). Используйте для этого секцию vrrp_script
- На проверку отправьте получившейся bash-скрипт и конфигурационный файл keepalived, а также скриншот с демонстрацией переезда плавающего ip на другой сервер в случае недоступности порта или файла index.html
---
[Файл bash скрипта](files/2/port-page-check.sh)
[Файл keepalived.conf](files/2/keepalived.conf)
Скриншоты с демонстрацией переезда плавающего ip на другой сервер в случае недоступности порта или файла index.html:
![Скриншот 3](<img width="880" height="547" alt="3" src="https://github.com/user-attachments/assets/6c29be3a-1738-490f-a7bf-08edb37fd973" />)
![Скриншот 4](<img width="941" height="537" alt="4" src="https://github.com/user-attachments/assets/36d74506-0894-48b5-a6de-dae41493241b" />)
![Скриншот 5](<img width="773" height="465" alt="5" src="https://github.com/user-attachments/assets/b422c05e-03cd-47f1-a7de-9635abe76001" />)
![Скриншот 6](<img width="964" height="570" alt="6" src="https://github.com/user-attachments/assets/c745543d-565f-46cd-8164-70f6b3095755" />)
---
