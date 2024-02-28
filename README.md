# Дипломная работа по профессии «Системный администратор» - `Хамов Олег`

### Задание 1

Для развёртки инфраструктуры использовал Terraform и Ansible.

![Снимок экрана (127).png](https://github.com/oleghamov/Diplom_Netology_29.02.24/blob/master/%D0%A1%D0%BA%D1%80%D0%B8%D0%BD%D1%8B%20%D0%B4%D0%BB%D1%8F%20%D0%B4%D0%B8%D0%BF%D0%BB%D0%BE%D0%BC%D0%B0/%D0%A1%D0%BD%D0%B8%D0%BC%D0%BE%D0%BA%20%D1%8D%D0%BA%D1%80%D0%B0%D0%BD%D0%B0%20(127).png)`

![1 Ansible -m ping all.png](https://github.com/oleghamov/Diplom_Netology_29.02.24/blob/master/%D0%A1%D0%BA%D1%80%D0%B8%D0%BD%D1%8B%20%D0%B4%D0%BB%D1%8F%20%D0%B4%D0%B8%D0%BF%D0%BB%D0%BE%D0%BC%D0%B0/1%20Ansible%20-m%20ping%20all.png)`

Сайт

Создал две ВМ website1 b web2 в разных зонах, установил на них сервер nginx

![Виртуальные машины.png](https://github.com/oleghamov/Diplom_Netology_29.02.24/blob/master/%D0%A1%D0%BA%D1%80%D0%B8%D0%BD%D1%8B%20%D0%B4%D0%BB%D1%8F%20%D0%B4%D0%B8%D0%BF%D0%BB%D0%BE%D0%BC%D0%B0/%D0%92%D0%B8%D1%80%D1%82%D1%83%D0%B0%D0%BB%D1%8C%D0%BD%D1%8B%D0%B5%20%D0%BC%D0%B0%D1%88%D0%B8%D0%BD%D1%8B.png)`

![nginx.yaml.png](https://github.com/oleghamov/Diplom_Netology_29.02.24/blob/master/%D0%A1%D0%BA%D1%80%D0%B8%D0%BD%D1%8B%20%D0%B4%D0%BB%D1%8F%20%D0%B4%D0%B8%D0%BF%D0%BB%D0%BE%D0%BC%D0%B0/nginx.yaml.png)`

Использовал набор статичных файлов для сайта.

Создал Target Group, включил в неё две созданные ВМ.

![Целевые группы.png](https://github.com/oleghamov/Diplom_Netology_29.02.24/blob/master/%D0%A1%D0%BA%D1%80%D0%B8%D0%BD%D1%8B%20%D0%B4%D0%BB%D1%8F%20%D0%B4%D0%B8%D0%BF%D0%BB%D0%BE%D0%BC%D0%B0/%D0%A6%D0%B5%D0%BB%D0%B5%D0%B2%D1%8B%D0%B5%20%D0%B3%D1%80%D1%83%D0%BF%D0%BF%D1%8B.png)`

![Целевые группы подробно.png](https://github.com/oleghamov/Diplom_Netology_29.02.24/blob/master/%D0%A1%D0%BA%D1%80%D0%B8%D0%BD%D1%8B%20%D0%B4%D0%BB%D1%8F%20%D0%B4%D0%B8%D0%BF%D0%BB%D0%BE%D0%BC%D0%B0/%D0%A6%D0%B5%D0%BB%D0%B5%D0%B2%D1%8B%D0%B5%20%D0%B3%D1%80%D1%83%D0%BF%D0%BF%D1%8B%20%D0%BF%D0%BE%D0%B4%D1%80%D0%BE%D0%B1%D0%BD%D0%BE.png)`

Создал Backend Group, настроил backends на target group, ранее созданную. Настроил healthcheck на корень (/) и порт 80, протокол HTTP.

![Роутер - группа бэкендов и проверка состояния.png](https://github.com/oleghamov/Diplom_Netology_29.02.24/blob/master/%D0%A1%D0%BA%D1%80%D0%B8%D0%BD%D1%8B%20%D0%B4%D0%BB%D1%8F%20%D0%B4%D0%B8%D0%BF%D0%BB%D0%BE%D0%BC%D0%B0/%D0%A0%D0%BE%D1%83%D1%82%D0%B5%D1%80%20-%20%D0%B3%D1%80%D1%83%D0%BF%D0%BF%D0%B0%20%D0%B1%D1%8D%D0%BA%D0%B5%D0%BD%D0%B4%D0%BE%D0%B2%20%D0%B8%20%D0%BF%D1%80%D0%BE%D0%B2%D0%B5%D1%80%D0%BA%D0%B0%20%D1%81%D0%BE%D1%81%D1%82%D0%BE%D1%8F%D0%BD%D0%B8%D1%8F.png)`

Создал HTTP router. Путь — /, backend group — созданную ранее.

![HTTP-роутер.png](https://github.com/oleghamov/Diplom_Netology_29.02.24/blob/master/%D0%A1%D0%BA%D1%80%D0%B8%D0%BD%D1%8B%20%D0%B4%D0%BB%D1%8F%20%D0%B4%D0%B8%D0%BF%D0%BB%D0%BE%D0%BC%D0%B0/HTTP-%D1%80%D0%BE%D1%83%D1%82%D0%B5%D1%80.png)`

Создал Application load balancer для распределения трафика на веб-сервера, созданные ранее. Указал HTTP router, созданный ранее, задал listener тип auto, порт 80.

![Балансировщик.png](https://github.com/oleghamov/Diplom_Netology_29.02.24/blob/master/%D0%A1%D0%BA%D1%80%D0%B8%D0%BD%D1%8B%20%D0%B4%D0%BB%D1%8F%20%D0%B4%D0%B8%D0%BF%D0%BB%D0%BE%D0%BC%D0%B0/%D0%91%D0%B0%D0%BB%D0%B0%D0%BD%D1%81%D0%B8%D1%80%D0%BE%D0%B2%D1%89%D0%B8%D0%BA.png)`

![Балансировщик подробно.png](https://github.com/oleghamov/Diplom_Netology_29.02.24/blob/master/%D0%A1%D0%BA%D1%80%D0%B8%D0%BD%D1%8B%20%D0%B4%D0%BB%D1%8F%20%D0%B4%D0%B8%D0%BF%D0%BB%D0%BE%D0%BC%D0%B0/%D0%91%D0%B0%D0%BB%D0%B0%D0%BD%D1%81%D0%B8%D1%80%D0%BE%D0%B2%D1%89%D0%B8%D0%BA%20%D0%BF%D0%BE%D0%B4%D1%80%D0%BE%D0%B1%D0%BD%D0%BE.png)`

![Балансировщик с обработчиком.png](https://github.com/oleghamov/Diplom_Netology_29.02.24/blob/master/%D0%A1%D0%BA%D1%80%D0%B8%D0%BD%D1%8B%20%D0%B4%D0%BB%D1%8F%20%D0%B4%D0%B8%D0%BF%D0%BB%D0%BE%D0%BC%D0%B0/%D0%91%D0%B0%D0%BB%D0%B0%D0%BD%D1%81%D0%B8%D1%80%D0%BE%D0%B2%D1%89%D0%B8%D0%BA%20%D1%81%20%D0%BE%D0%B1%D1%80%D0%B0%D0%B1%D0%BE%D1%82%D1%87%D0%B8%D0%BA%D0%BE%D0%BC.png)`

![Карта балансировки.png](https://github.com/oleghamov/Diplom_Netology_29.02.24/blob/master/%D0%A1%D0%BA%D1%80%D0%B8%D0%BD%D1%8B%20%D0%B4%D0%BB%D1%8F%20%D0%B4%D0%B8%D0%BF%D0%BB%D0%BE%D0%BC%D0%B0/%D0%9A%D0%B0%D1%80%D1%82%D0%B0%20%D0%B1%D0%B0%D0%BB%D0%B0%D0%BD%D1%81%D0%B8%D1%80%D0%BE%D0%B2%D0%BA%D0%B8.png)`

Протестируйте сайт curl -v <публичный IP балансера>:80

![]()`

### Задание 2

Мониторинг

Создал ВМ, развернул на ней Zabbix. На каждую ВМ установил Zabbix Agent, настроил агенты на отправление метрик в Zabbix.

![zabbix_server.yaml.png](https://github.com/oleghamov/Diplom_Netology_29.02.24/blob/master/%D0%A1%D0%BA%D1%80%D0%B8%D0%BD%D1%8B%20%D0%B4%D0%BB%D1%8F%20%D0%B4%D0%B8%D0%BF%D0%BB%D0%BE%D0%BC%D0%B0/zabbix_server.yaml.png)`

![zabbix-server active.png](https://github.com/oleghamov/Diplom_Netology_29.02.24/blob/master/%D0%A1%D0%BA%D1%80%D0%B8%D0%BD%D1%8B%20%D0%B4%D0%BB%D1%8F%20%D0%B4%D0%B8%D0%BF%D0%BB%D0%BE%D0%BC%D0%B0/zabbix-server%20active.png)`

![http51.250.44.181zabbixsetup.php.png](https://github.com/oleghamov/Diplom_Netology_29.02.24/blob/master/%D0%A1%D0%BA%D1%80%D0%B8%D0%BD%D1%8B%20%D0%B4%D0%BB%D1%8F%20%D0%B4%D0%B8%D0%BF%D0%BB%D0%BE%D0%BC%D0%B0/http51.250.44.181zabbixsetup.php.png)`

Настроил дешборды с отображением метрик, минимальный набор — по принципу USE (Utilization, Saturation, Errors) для CPU, RAM, диски, сеть, http запросов к веб-серверам. Добавил необходимые tresholds на соответствующие графики.

![zabbix dashbord.png](https://github.com/oleghamov/Diplom_Netology_29.02.24/blob/master/%D0%A1%D0%BA%D1%80%D0%B8%D0%BD%D1%8B%20%D0%B4%D0%BB%D1%8F%20%D0%B4%D0%B8%D0%BF%D0%BB%D0%BE%D0%BC%D0%B0/zabbix%20dashbord.png)`

![]()`

### Задание 3

Логи

Cоздал ВМ, развернул на ней Elasticsearch. Установил filebeat в ВМ к веб-серверам, настроил на отправку access.log, error.log nginx в Elasticsearch.

![elasticsearch.yaml.png](https://github.com/oleghamov/Diplom_Netology_29.02.24/blob/master/%D0%A1%D0%BA%D1%80%D0%B8%D0%BD%D1%8B%20%D0%B4%D0%BB%D1%8F%20%D0%B4%D0%B8%D0%BF%D0%BB%D0%BE%D0%BC%D0%B0/elasticsearch.yaml.png)`

![filebeat.yaml.png](https://github.com/oleghamov/Diplom_Netology_29.02.24/blob/master/%D0%A1%D0%BA%D1%80%D0%B8%D0%BD%D1%8B%20%D0%B4%D0%BB%D1%8F%20%D0%B4%D0%B8%D0%BF%D0%BB%D0%BE%D0%BC%D0%B0/filebeat.yaml.png)`

Создал ВМ, развернул на ней Kibana, сконфигурировал соединение с Elasticsearch.

![kibana.yaml.png](https://github.com/oleghamov/Diplom_Netology_29.02.24/blob/master/%D0%A1%D0%BA%D1%80%D0%B8%D0%BD%D1%8B%20%D0%B4%D0%BB%D1%8F%20%D0%B4%D0%B8%D0%BF%D0%BB%D0%BE%D0%BC%D0%B0/kibana.yaml.png)`

![GET _catindices.png](https://github.com/oleghamov/Diplom_Netology_29.02.24/blob/master/%D0%A1%D0%BA%D1%80%D0%B8%D0%BD%D1%8B%20%D0%B4%D0%BB%D1%8F%20%D0%B4%D0%B8%D0%BF%D0%BB%D0%BE%D0%BC%D0%B0/GET%20_catindices.png)`

![GET _clusterhealth.png](https://github.com/oleghamov/Diplom_Netology_29.02.24/blob/master/%D0%A1%D0%BA%D1%80%D0%B8%D0%BD%D1%8B%20%D0%B4%D0%BB%D1%8F%20%D0%B4%D0%B8%D0%BF%D0%BB%D0%BE%D0%BC%D0%B0/GET%20_clusterhealth.png)`

![GET kbnapiindex_managementindices.png](https://github.com/oleghamov/Diplom_Netology_29.02.24/blob/master/%D0%A1%D0%BA%D1%80%D0%B8%D0%BD%D1%8B%20%D0%B4%D0%BB%D1%8F%20%D0%B4%D0%B8%D0%BF%D0%BB%D0%BE%D0%BC%D0%B0/GET%20kbnapiindex_managementindices.png)`

![GET_catshards.png](https://github.com/oleghamov/Diplom_Netology_29.02.24/blob/master/%D0%A1%D0%BA%D1%80%D0%B8%D0%BD%D1%8B%20%D0%B4%D0%BB%D1%8F%20%D0%B4%D0%B8%D0%BF%D0%BB%D0%BE%D0%BC%D0%B0/GET_catshards.png)`

### Задание 4

Сеть

Развернул один VPC. Сервера web, Elasticsearch поместил в приватные подсети. Сервера Zabbix, Kibana, application load balancer определил в публичную подсеть.

![Общая сеть для размещения ресурсов.png](https://github.com/oleghamov/Diplom_Netology_29.02.24/blob/master/%D0%A1%D0%BA%D1%80%D0%B8%D0%BD%D1%8B%20%D0%B4%D0%BB%D1%8F%20%D0%B4%D0%B8%D0%BF%D0%BB%D0%BE%D0%BC%D0%B0/%D0%9E%D0%B1%D1%89%D0%B0%D1%8F%20%D1%81%D0%B5%D1%82%D1%8C%20%D0%B4%D0%BB%D1%8F%20%D1%80%D0%B0%D0%B7%D0%BC%D0%B5%D1%89%D0%B5%D0%BD%D0%B8%D1%8F%20%D1%80%D0%B5%D1%81%D1%83%D1%80%D1%81%D0%BE%D0%B2.png)`

![Подсети.png](https://github.com/oleghamov/Diplom_Netology_29.02.24/blob/master/%D0%A1%D0%BA%D1%80%D0%B8%D0%BD%D1%8B%20%D0%B4%D0%BB%D1%8F%20%D0%B4%D0%B8%D0%BF%D0%BB%D0%BE%D0%BC%D0%B0/%D0%9F%D0%BE%D0%B4%D1%81%D0%B5%D1%82%D0%B8.png)`

![ip адреса.png](https://github.com/oleghamov/Diplom_Netology_29.02.24/blob/master/%D0%A1%D0%BA%D1%80%D0%B8%D0%BD%D1%8B%20%D0%B4%D0%BB%D1%8F%20%D0%B4%D0%B8%D0%BF%D0%BB%D0%BE%D0%BC%D0%B0/ip%20%D0%B0%D0%B4%D1%80%D0%B5%D1%81%D0%B0.png)`

Настроил Security Groups соответствующих сервисов на входящий трафик только к нужным портам.

![Группы безопасности.png](https://github.com/oleghamov/Diplom_Netology_29.02.24/blob/master/%D0%A1%D0%BA%D1%80%D0%B8%D0%BD%D1%8B%20%D0%B4%D0%BB%D1%8F%20%D0%B4%D0%B8%D0%BF%D0%BB%D0%BE%D0%BC%D0%B0/%D0%93%D1%80%D1%83%D0%BF%D0%BF%D1%8B%20%D0%B1%D0%B5%D0%B7%D0%BE%D0%BF%D0%B0%D1%81%D0%BD%D0%BE%D1%81%D1%82%D0%B8.png)`

![Снимок экрана (109).png](https://github.com/oleghamov/Diplom_Netology_29.02.24/blob/master/%D0%A1%D0%BA%D1%80%D0%B8%D0%BD%D1%8B%20%D0%B4%D0%BB%D1%8F%20%D0%B4%D0%B8%D0%BF%D0%BB%D0%BE%D0%BC%D0%B0/%D0%A1%D0%BD%D0%B8%D0%BC%D0%BE%D0%BA%20%D1%8D%D0%BA%D1%80%D0%B0%D0%BD%D0%B0%20(109).png)`

Настроил ВМ с публичным адресом, в которой открыт только один порт — ssh. bastion host

![]()`

### Задание 5

Резервное копирование

Создал snapshot дисков всех ВМ. Ограничил время жизни snaphot в неделю. Сами snaphot настроил на ежедневное копирование.

![]()`

![]()`














