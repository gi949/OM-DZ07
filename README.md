# OM-DZ07
На виртуальной машине установлена CMS wordpress, которая включает в себя следующие компоненты:

nginx, php-fpm, database (MySQL)

На CMS развернут тестовый домен http://www.example.com/

---

На ВМ с CMS скачиваем и устанавливаем filebeat и metricbeat:

rpm -Uvh filebeat-8.17.0-x86_64.rpm
rpm -UVh metricbeat-8.17.1-x86_64.rpm

---


На ВМ мониторинга скачиваем и устанавливаем  elasticsearch, kibanan и heartbeat:

