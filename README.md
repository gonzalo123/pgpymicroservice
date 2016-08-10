Simple sql microservice
===========

Simple sql microservice using Flask

# run the server

* start the server

´´´
python server.py
´´´

The idea is to use a template engine (jinja2) to create SQL statements

* perform GET resquest:
´´´
http://127.0.0.1:5000/sql/folder.example1?_authToken=superSecretToken&_assoc=1
´´´

This will execute this sql
´´´
SELECT
  *
FROM
  myTable
{% if id is defined %}
where
  id = %(id)s
{% endif %}

´´´

* and with parameters
http://127.0.0.1:5000/sql/folder.example1?_authToken=superSecretToken&_assoc=1&id=2
