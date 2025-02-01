# OM-DZ07
На виртуальной машине установлена CMS wordpress, которая включает в себя следующие компоненты:

nginx, php-fpm, database (MySQL)

На CMS развернут тестовый домен http://www.example.com/

---

На ВМ с CMS скачиваем и устанавливаем filebeat и metricbeat:

rpm -Uvh filebeat-8.17.0-x86_64.rpm

rpm -UVh metricbeat-8.17.1-x86_64.rpm

Включаем модули metricbeat nginx и mysql:

metricbeat modules enable nginx mysql

---

На ВМ мониторинга скачиваем и устанавливаем  elasticsearch, kibana и heartbeat:

rpm -ivh elasticsearch-8.17.0-x86_64.rpm

rpm -ivh kibana-8.17.1-linux-x86_64.tar.gz

rpm -ivh heartbeat-8.17.1-x86_64.rpm

---

В /etc/filebeat/filebeat.yml настраиваем сбор логов nginx, php-fpm и mysql

и доступ к elasticsearch и kibana. И запускаем filebeat.

В /etc/metricbeat/metricbeat.yml настраиваем метрики ВМ, nginx и mysql

и доступ к elasticsearch и kibana. И запускаем metricbeat

---

Подключаемся к веб-интерфейсу http://127.0.0.1:5601 и в разделе discover

можем видить логи с ВМ CMS

![dz5-1](https://github.com/user-attachments/assets/36532c77-3be7-4cd6-a906-b8721ba6a8b1)














