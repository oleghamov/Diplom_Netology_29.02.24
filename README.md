# Дипломная работа по профессии «Системный администратор» - `Хамов Олег`

### Задание 1

Для развёртки инфраструктуры использовал Terraform и Ansible.

terraform apply

![7terraform apply.png](https://github.com/oleghamov/Diplom_Netology_29.02.24/blob/master/%D0%A1%D0%BA%D1%80%D0%B8%D0%BD%D1%8B%20%D0%B4%D0%BB%D1%8F%20%D0%B4%D0%B8%D0%BF%D0%BB%D0%BE%D0%BC%D0%B0/7terraform%20apply.png)`

![Снимок экрана (127).png](https://github.com/oleghamov/Diplom_Netology_29.02.24/blob/master/%D0%A1%D0%BA%D1%80%D0%B8%D0%BD%D1%8B%20%D0%B4%D0%BB%D1%8F%20%D0%B4%D0%B8%D0%BF%D0%BB%D0%BE%D0%BC%D0%B0/%D0%A1%D0%BD%D0%B8%D0%BC%D0%BE%D0%BA%20%D1%8D%D0%BA%D1%80%D0%B0%D0%BD%D0%B0%20(127).png)`

Ansible -m ping all

![1 Ansible -m ping all.png](https://github.com/oleghamov/Diplom_Netology_29.02.24/blob/master/%D0%A1%D0%BA%D1%80%D0%B8%D0%BD%D1%8B%20%D0%B4%D0%BB%D1%8F%20%D0%B4%D0%B8%D0%BF%D0%BB%D0%BE%D0%BC%D0%B0/1%20Ansible%20-m%20ping%20all.png)`


   - https://console.cloud.yandex.ru/folders/b1ghbnq9ceq4ecm8iu4v

   - YandexCloud

   - id облака:   b1gb8p8hcmajtt714th5


Сайт

Создал две ВМ website1 b web2 в разных зонах, установил на них сервер nginx. Создал машины для zabbix, kibana, elastiksearch, bastion 

![Виртуальные машины.png](https://github.com/oleghamov/Diplom_Netology_29.02.24/blob/master/%D0%A1%D0%BA%D1%80%D0%B8%D0%BD%D1%8B%20%D0%B4%D0%BB%D1%8F%20%D0%B4%D0%B8%D0%BF%D0%BB%D0%BE%D0%BC%D0%B0/%D0%92%D0%B8%D1%80%D1%82%D1%83%D0%B0%D0%BB%D1%8C%D0%BD%D1%8B%D0%B5%20%D0%BC%D0%B0%D1%88%D0%B8%D0%BD%D1%8B.png)`

Установил Nginx на ВМ website1 b web2

![nginx.yaml.png](https://github.com/oleghamov/Diplom_Netology_29.02.24/blob/master/%D0%A1%D0%BA%D1%80%D0%B8%D0%BD%D1%8B%20%D0%B4%D0%BB%D1%8F%20%D0%B4%D0%B8%D0%BF%D0%BB%D0%BE%D0%BC%D0%B0/nginx.yaml.png)`

![8 Welcome to nginx!.png](https://github.com/oleghamov/Diplom_Netology_29.02.24/blob/master/%D0%A1%D0%BA%D1%80%D0%B8%D0%BD%D1%8B%20%D0%B4%D0%BB%D1%8F%20%D0%B4%D0%B8%D0%BF%D0%BB%D0%BE%D0%BC%D0%B0/8%20Welcome%20to%20nginx!.png)`

Использовал набор статичных файлов для сайта.

Создал Target Group, включил в неё две созданные ВМ.

![Целевые группы.png](https://github.com/oleghamov/Diplom_Netology_29.02.24/blob/master/%D0%A1%D0%BA%D1%80%D0%B8%D0%BD%D1%8B%20%D0%B4%D0%BB%D1%8F%20%D0%B4%D0%B8%D0%BF%D0%BB%D0%BE%D0%BC%D0%B0/%D0%A6%D0%B5%D0%BB%D0%B5%D0%B2%D1%8B%D0%B5%20%D0%B3%D1%80%D1%83%D0%BF%D0%BF%D1%8B.png)`

Target Group (подробно)

![Целевые группы подробно.png](https://github.com/oleghamov/Diplom_Netology_29.02.24/blob/master/%D0%A1%D0%BA%D1%80%D0%B8%D0%BD%D1%8B%20%D0%B4%D0%BB%D1%8F%20%D0%B4%D0%B8%D0%BF%D0%BB%D0%BE%D0%BC%D0%B0/%D0%A6%D0%B5%D0%BB%D0%B5%D0%B2%D1%8B%D0%B5%20%D0%B3%D1%80%D1%83%D0%BF%D0%BF%D1%8B%20%D0%BF%D0%BE%D0%B4%D1%80%D0%BE%D0%B1%D0%BD%D0%BE.png)`

Создал Backend Group, настроил backends на target group, ранее созданную. Настроил healthcheck на корень (/) и порт 80, протокол HTTP.

Роутер - группа бэкендов и проверка состояния

![Роутер - группа бэкендов и проверка состояния.png](https://github.com/oleghamov/Diplom_Netology_29.02.24/blob/master/%D0%A1%D0%BA%D1%80%D0%B8%D0%BD%D1%8B%20%D0%B4%D0%BB%D1%8F%20%D0%B4%D0%B8%D0%BF%D0%BB%D0%BE%D0%BC%D0%B0/%D0%A0%D0%BE%D1%83%D1%82%D0%B5%D1%80%20-%20%D0%B3%D1%80%D1%83%D0%BF%D0%BF%D0%B0%20%D0%B1%D1%8D%D0%BA%D0%B5%D0%BD%D0%B4%D0%BE%D0%B2%20%D0%B8%20%D0%BF%D1%80%D0%BE%D0%B2%D0%B5%D1%80%D0%BA%D0%B0%20%D1%81%D0%BE%D1%81%D1%82%D0%BE%D1%8F%D0%BD%D0%B8%D1%8F.png)`

Создал HTTP router. Путь — /, backend group — созданную ранее.

![HTTP-роутер.png](https://github.com/oleghamov/Diplom_Netology_29.02.24/blob/master/%D0%A1%D0%BA%D1%80%D0%B8%D0%BD%D1%8B%20%D0%B4%D0%BB%D1%8F%20%D0%B4%D0%B8%D0%BF%D0%BB%D0%BE%D0%BC%D0%B0/HTTP-%D1%80%D0%BE%D1%83%D1%82%D0%B5%D1%80.png)`

Создал Application load balancer для распределения трафика на веб-сервера, созданные ранее. Указал HTTP router, созданный ранее, задал listener тип auto, порт 80.

![Балансировщик.png](https://github.com/oleghamov/Diplom_Netology_29.02.24/blob/master/%D0%A1%D0%BA%D1%80%D0%B8%D0%BD%D1%8B%20%D0%B4%D0%BB%D1%8F%20%D0%B4%D0%B8%D0%BF%D0%BB%D0%BE%D0%BC%D0%B0/%D0%91%D0%B0%D0%BB%D0%B0%D0%BD%D1%81%D0%B8%D1%80%D0%BE%D0%B2%D1%89%D0%B8%D0%BA.png)`

Балансировщик (подробно)

![Балансировщик подробно.png](https://github.com/oleghamov/Diplom_Netology_29.02.24/blob/master/%D0%A1%D0%BA%D1%80%D0%B8%D0%BD%D1%8B%20%D0%B4%D0%BB%D1%8F%20%D0%B4%D0%B8%D0%BF%D0%BB%D0%BE%D0%BC%D0%B0/%D0%91%D0%B0%D0%BB%D0%B0%D0%BD%D1%81%D0%B8%D1%80%D0%BE%D0%B2%D1%89%D0%B8%D0%BA%20%D0%BF%D0%BE%D0%B4%D1%80%D0%BE%D0%B1%D0%BD%D0%BE.png)`

Балансировщик с обработчиком

![Балансировщик с обработчиком.png](https://github.com/oleghamov/Diplom_Netology_29.02.24/blob/master/%D0%A1%D0%BA%D1%80%D0%B8%D0%BD%D1%8B%20%D0%B4%D0%BB%D1%8F%20%D0%B4%D0%B8%D0%BF%D0%BB%D0%BE%D0%BC%D0%B0/%D0%91%D0%B0%D0%BB%D0%B0%D0%BD%D1%81%D0%B8%D1%80%D0%BE%D0%B2%D1%89%D0%B8%D0%BA%20%D1%81%20%D0%BE%D0%B1%D1%80%D0%B0%D0%B1%D0%BE%D1%82%D1%87%D0%B8%D0%BA%D0%BE%D0%BC.png)`

Карта балансировки

![Карта балансировки.png](https://github.com/oleghamov/Diplom_Netology_29.02.24/blob/master/%D0%A1%D0%BA%D1%80%D0%B8%D0%BD%D1%8B%20%D0%B4%D0%BB%D1%8F%20%D0%B4%D0%B8%D0%BF%D0%BB%D0%BE%D0%BC%D0%B0/%D0%9A%D0%B0%D1%80%D1%82%D0%B0%20%D0%B1%D0%B0%D0%BB%D0%B0%D0%BD%D1%81%D0%B8%D1%80%D0%BE%D0%B2%D0%BA%D0%B8.png)`


Протестировал сайт curl -v <публичный IP балансера>:80

![2 curl -v 158.160.151.22380.png](https://github.com/oleghamov/Diplom_Netology_29.02.24/blob/master/%D0%A1%D0%BA%D1%80%D0%B8%D0%BD%D1%8B%20%D0%B4%D0%BB%D1%8F%20%D0%B4%D0%B8%D0%BF%D0%BB%D0%BE%D0%BC%D0%B0/2%20curl%20-v%20158.160.151.22380.png)`


  - http://158.160.151.223:80

  - LoadBalanser


### Задание 2

Мониторинг

Создал ВМ, развернул на ней Zabbix. На каждую ВМ установил Zabbix Agent, настроил агенты на отправление метрик в Zabbix.

Установка zabbix сервера

![zabbix_server.yaml.png](https://github.com/oleghamov/Diplom_Netology_29.02.24/blob/master/%D0%A1%D0%BA%D1%80%D0%B8%D0%BD%D1%8B%20%D0%B4%D0%BB%D1%8F%20%D0%B4%D0%B8%D0%BF%D0%BB%D0%BE%D0%BC%D0%B0/zabbix_server.yaml.png)`

systemctl status zabbix-server

![zabbix-server active.png](https://github.com/oleghamov/Diplom_Netology_29.02.24/blob/master/%D0%A1%D0%BA%D1%80%D0%B8%D0%BD%D1%8B%20%D0%B4%D0%BB%D1%8F%20%D0%B4%D0%B8%D0%BF%D0%BB%D0%BE%D0%BC%D0%B0/zabbix-server%20active.png)`

Стартовая страница zabbix

![http51.250.44.181zabbixsetup.php.png](https://github.com/oleghamov/Diplom_Netology_29.02.24/blob/master/%D0%A1%D0%BA%D1%80%D0%B8%D0%BD%D1%8B%20%D0%B4%D0%BB%D1%8F%20%D0%B4%D0%B8%D0%BF%D0%BB%D0%BE%D0%BC%D0%B0/http51.250.44.181zabbixsetup.php.png)`

 Настроил агенты заббикса на website1 и web2 и zabbix-server. Добавил шаблоны items 

![9 Zabbix configuration hosts.png](https://github.com/oleghamov/Diplom_Netology_29.02.24/blob/master/%D0%A1%D0%BA%D1%80%D0%B8%D0%BD%D1%8B%20%D0%B4%D0%BB%D1%8F%20%D0%B4%D0%B8%D0%BF%D0%BB%D0%BE%D0%BC%D0%B0/9%20Zabbix%20configuration%20hosts.png)`

  - http://51.250.46.21/zabbix

  - Логин: Admin

  - Пароль: zabbix


Настроил дашборды с отображением метрик, минимальный набор — по принципу USE (Utilization, Saturation, Errors) для CPU, RAM, диски, сеть, http запросов к веб-серверам. Добавил необходимые tresholds на соответствующие графики.

![10 Zabbix dashboard!.png](https://github.com/oleghamov/Diplom_Netology_29.02.24/blob/master/%D0%A1%D0%BA%D1%80%D0%B8%D0%BD%D1%8B%20%D0%B4%D0%BB%D1%8F%20%D0%B4%D0%B8%D0%BF%D0%BB%D0%BE%D0%BC%D0%B0/10%20Zabbix%20dashboard!.png)`

![дашбоард заббикса.png](https://github.com/oleghamov/Diplom_Netology_29.02.24/blob/master/%D0%A1%D0%BA%D1%80%D0%B8%D0%BD%D1%8B%20%D0%B4%D0%BB%D1%8F%20%D0%B4%D0%B8%D0%BF%D0%BB%D0%BE%D0%BC%D0%B0/%D0%B4%D0%B0%D1%88%D0%B1%D0%BE%D0%B0%D1%80%D0%B4%20%D0%B7%D0%B0%D0%B1%D0%B1%D0%B8%D0%BA%D1%81%D0%B0.png)`

![11 Zabbix: Latest data.png](https://github.com/oleghamov/Diplom_Netology_29.02.24/blob/master/%D0%A1%D0%BA%D1%80%D0%B8%D0%BD%D1%8B%20%D0%B4%D0%BB%D1%8F%20%D0%B4%D0%B8%D0%BF%D0%BB%D0%BE%D0%BC%D0%B0/11%20Zabbix%3A%20Latest%20data.png)`

### Задание 3

Логи

Cоздал ВМ, развернул на ней Elasticsearch. Установил filebeat в ВМ к веб-серверам, настроил на отправку access.log, error.log nginx в Elasticsearch.

Установка ELK

![elasticsearch.yaml.png](https://github.com/oleghamov/Diplom_Netology_29.02.24/blob/master/%D0%A1%D0%BA%D1%80%D0%B8%D0%BD%D1%8B%20%D0%B4%D0%BB%D1%8F%20%D0%B4%D0%B8%D0%BF%D0%BB%D0%BE%D0%BC%D0%B0/elasticsearch.yaml.png)`

Проверка elasticsearch

![1 Curl cluster healt.png](https://github.com/oleghamov/Diplom_Netology_29.02.24/blob/master/%D0%A1%D0%BA%D1%80%D0%B8%D0%BD%D1%8B%20%D0%B4%D0%BB%D1%8F%20%D0%B4%D0%B8%D0%BF%D0%BB%D0%BE%D0%BC%D0%B0/1%20Curl%20cluster%20healt.png)`

![3 Curl Xget.png](https://github.com/oleghamov/Diplom_Netology_29.02.24/blob/master/%D0%A1%D0%BA%D1%80%D0%B8%D0%BD%D1%8B%20%D0%B4%D0%BB%D1%8F%20%D0%B4%D0%B8%D0%BF%D0%BB%D0%BE%D0%BC%D0%B0/3%20Curl%20Xget.png)`

Установил filebeat на website1 и web2

![filebeat.yaml.png](https://github.com/oleghamov/Diplom_Netology_29.02.24/blob/master/%D0%A1%D0%BA%D1%80%D0%B8%D0%BD%D1%8B%20%D0%B4%D0%BB%D1%8F%20%D0%B4%D0%B8%D0%BF%D0%BB%D0%BE%D0%BC%D0%B0/filebeat.yaml.png)`

filebeat test output website1

![4 filebeat test output web1.png](https://github.com/oleghamov/Diplom_Netology_29.02.24/blob/master/%D0%A1%D0%BA%D1%80%D0%B8%D0%BD%D1%8B%20%D0%B4%D0%BB%D1%8F%20%D0%B4%D0%B8%D0%BF%D0%BB%D0%BE%D0%BC%D0%B0/4%20filebeat%20test%20output%20web1.png)`

filebeat test output web2

![5 filebeat test output web2.png](https://github.com/oleghamov/Diplom_Netology_29.02.24/blob/master/%D0%A1%D0%BA%D1%80%D0%B8%D0%BD%D1%8B%20%D0%B4%D0%BB%D1%8F%20%D0%B4%D0%B8%D0%BF%D0%BB%D0%BE%D0%BC%D0%B0/5%20filebeat%20test%20output%20web2.png)`


Создал ВМ, развернул на ней Kibana, сконфигурировал соединение с Elasticsearch.

![kibana.yaml.png](https://github.com/oleghamov/Diplom_Netology_29.02.24/blob/master/%D0%A1%D0%BA%D1%80%D0%B8%D0%BD%D1%8B%20%D0%B4%D0%BB%D1%8F%20%D0%B4%D0%B8%D0%BF%D0%BB%D0%BE%D0%BC%D0%B0/kibana.yaml.png)`

  - http://51.250.47.34:5601
 
  - Kibana

Проверка ELK, filebeat в kibana

Индексы

![GET _catindices.png](https://github.com/oleghamov/Diplom_Netology_29.02.24/blob/master/%D0%A1%D0%BA%D1%80%D0%B8%D0%BD%D1%8B%20%D0%B4%D0%BB%D1%8F%20%D0%B4%D0%B8%D0%BF%D0%BB%D0%BE%D0%BC%D0%B0/GET%20_catindices.png)`

Кластер

![GET _clusterhealth.png](https://github.com/oleghamov/Diplom_Netology_29.02.24/blob/master/%D0%A1%D0%BA%D1%80%D0%B8%D0%BD%D1%8B%20%D0%B4%D0%BB%D1%8F%20%D0%B4%D0%B8%D0%BF%D0%BB%D0%BE%D0%BC%D0%B0/GET%20_clusterhealth.png)`

Индексы kibana

![GET kbnapiindex_managementindices.png](https://github.com/oleghamov/Diplom_Netology_29.02.24/blob/master/%D0%A1%D0%BA%D1%80%D0%B8%D0%BD%D1%8B%20%D0%B4%D0%BB%D1%8F%20%D0%B4%D0%B8%D0%BF%D0%BB%D0%BE%D0%BC%D0%B0/GET%20kbnapiindex_managementindices.png)`

Шарды

![GET_catshards.png](https://github.com/oleghamov/Diplom_Netology_29.02.24/blob/master/%D0%A1%D0%BA%D1%80%D0%B8%D0%BD%D1%8B%20%D0%B4%D0%BB%D1%8F%20%D0%B4%D0%B8%D0%BF%D0%BB%D0%BE%D0%BC%D0%B0/GET_catshards.png)`

Логи ELK

![еластик логи.png](https://github.com/oleghamov/Diplom_Netology_29.02.24/blob/master/%D0%A1%D0%BA%D1%80%D0%B8%D0%BD%D1%8B%20%D0%B4%D0%BB%D1%8F%20%D0%B4%D0%B8%D0%BF%D0%BB%D0%BE%D0%BC%D0%B0/%D0%B5%D0%BB%D0%B0%D1%81%D1%82%D0%B8%D0%BA%20%D0%BB%D0%BE%D0%B3%D0%B8.png)`

### Задание 4

Сеть

Развернул один VPC. Сервера web, Elasticsearch поместил в приватные подсети. Сервера Zabbix, Kibana, application load balancer определил в публичную подсеть.

Общая сеть для размещения ресурсов

![Общая сеть для размещения ресурсов.png](https://github.com/oleghamov/Diplom_Netology_29.02.24/blob/master/%D0%A1%D0%BA%D1%80%D0%B8%D0%BD%D1%8B%20%D0%B4%D0%BB%D1%8F%20%D0%B4%D0%B8%D0%BF%D0%BB%D0%BE%D0%BC%D0%B0/%D0%9E%D0%B1%D1%89%D0%B0%D1%8F%20%D1%81%D0%B5%D1%82%D1%8C%20%D0%B4%D0%BB%D1%8F%20%D1%80%D0%B0%D0%B7%D0%BC%D0%B5%D1%89%D0%B5%D0%BD%D0%B8%D1%8F%20%D1%80%D0%B5%D1%81%D1%83%D1%80%D1%81%D0%BE%D0%B2.png)`

Подсети

![Подсети.png](https://github.com/oleghamov/Diplom_Netology_29.02.24/blob/master/%D0%A1%D0%BA%D1%80%D0%B8%D0%BD%D1%8B%20%D0%B4%D0%BB%D1%8F%20%D0%B4%D0%B8%D0%BF%D0%BB%D0%BE%D0%BC%D0%B0/%D0%9F%D0%BE%D0%B4%D1%81%D0%B5%D1%82%D0%B8.png)`

IP адреса

![ip адреса.png](https://github.com/oleghamov/Diplom_Netology_29.02.24/blob/master/%D0%A1%D0%BA%D1%80%D0%B8%D0%BD%D1%8B%20%D0%B4%D0%BB%D1%8F%20%D0%B4%D0%B8%D0%BF%D0%BB%D0%BE%D0%BC%D0%B0/ip%20%D0%B0%D0%B4%D1%80%D0%B5%D1%81%D0%B0.png)`


Настроил Security Groups соответствующих сервисов на входящий трафик только к нужным портам.

Группы безопасности

![Группы безопасности.png](https://github.com/oleghamov/Diplom_Netology_29.02.24/blob/master/%D0%A1%D0%BA%D1%80%D0%B8%D0%BD%D1%8B%20%D0%B4%D0%BB%D1%8F%20%D0%B4%D0%B8%D0%BF%D0%BB%D0%BE%D0%BC%D0%B0/%D0%93%D1%80%D1%83%D0%BF%D0%BF%D1%8B%20%D0%B1%D0%B5%D0%B7%D0%BE%D0%BF%D0%B0%D1%81%D0%BD%D0%BE%D1%81%D1%82%D0%B8.png)`

![Снимок экрана (109).png](https://github.com/oleghamov/Diplom_Netology_29.02.24/blob/master/%D0%A1%D0%BA%D1%80%D0%B8%D0%BD%D1%8B%20%D0%B4%D0%BB%D1%8F%20%D0%B4%D0%B8%D0%BF%D0%BB%D0%BE%D0%BC%D0%B0/%D0%A1%D0%BD%D0%B8%D0%BC%D0%BE%D0%BA%20%D1%8D%D0%BA%D1%80%D0%B0%D0%BD%D0%B0%20(109).png)`


Настроил ВМ с публичным адресом, в которой открыт только один порт — ssh. bastion host

![13 Разрешение на подключение к ВМ bastion по SSH из сети Интернет.png](https://github.com/oleghamov/Diplom_Netology_29.02.24/blob/master/%D0%A1%D0%BA%D1%80%D0%B8%D0%BD%D1%8B%20%D0%B4%D0%BB%D1%8F%20%D0%B4%D0%B8%D0%BF%D0%BB%D0%BE%D0%BC%D0%B0/13%20%D0%A0%D0%B0%D0%B7%D1%80%D0%B5%D1%88%D0%B5%D0%BD%D0%B8%D0%B5%20%D0%BD%D0%B0%20%D0%BF%D0%BE%D0%B4%D0%BA%D0%BB%D1%8E%D1%87%D0%B5%D0%BD%D0%B8%D0%B5%20%D0%BA%20%D0%92%D0%9C%20bastion%20%D0%BF%D0%BE%20SSH%20%D0%B8%D0%B7%20%D1%81%D0%B5%D1%82%D0%B8%20%D0%98%D0%BD%D1%82%D0%B5%D1%80%D0%BD%D0%B5%D1%82.png)`


### Задание 5

Резервное копирование

Создал snapshot дисков всех ВМ. Ограничил время жизни snaphot в неделю. Сами snaphot настроил на ежедневное копирование.

Диски HDD

![12 Диски HDD.png](https://github.com/oleghamov/Diplom_Netology_29.02.24/blob/master/%D0%A1%D0%BA%D1%80%D0%B8%D0%BD%D1%8B%20%D0%B4%D0%BB%D1%8F%20%D0%B4%D0%B8%D0%BF%D0%BB%D0%BE%D0%BC%D0%B0/12%20%D0%94%D0%B8%D1%81%D0%BA%D0%B8%20HDD.png)`

snapshot

![6 snapshot.png](https://github.com/oleghamov/Diplom_Netology_29.02.24/blob/master/%D0%A1%D0%BA%D1%80%D0%B8%D0%BD%D1%8B%20%D0%B4%D0%BB%D1%8F%20%D0%B4%D0%B8%D0%BF%D0%BB%D0%BE%D0%BC%D0%B0/6%20snapshot.png)`















