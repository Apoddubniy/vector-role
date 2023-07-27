Ansible Role: Vector
=========

Install **Vector**

Role Variables
--------------
Все переменные задаются в файле `defaults/main.yml`

| Переменная | Значение по умолчанию | Описание | 
| :-----:|:---------------------:|:-----:|
|`vector_ver`|        0.31.0         | Указывается желаемая версия ПО |

Support platforms:
----------------

| Name | Version |
| :----: | :-----:|
| Centos| 7,8|
| Rhel | 7,8 |


Description role
--------
#### Tasks Vector

* Хендлер, с ролью перезапуска `state: restarted` сервиса `name: vector` с правами суперпользователя `become: true`
* Скачивание дистрибутива с помощью модуля `ansible.builtin.get_url` по ссылкам.
* Переменная `{{ vector_ver }}` принимает значения указанные в `default/main.yml` / `vector_ver`
* С помощью модуля `ansible.builtin.yum` происходит установка пакетов.
* С помощью модуля `template` из шаблона, прописывается конфигурация в файл `/etc/vector/vector.toml`, и добавляются права на файл `mode: "0644"`

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:
```yaml
    - hosts: servers
      roles:
         - role: vector-role 
```
License
-------

MIT

Author Information
------------------

Aleksandr Poddubniy