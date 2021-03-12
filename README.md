ansible-role-nfs
=========

Установка/настройка сервера NFS.

Требования
------------

- systemd на целевом хосте

Переменные
------------

| Variable | Type | Default | Comment |
| ------ | ------ | -------  | ---------- |
| nfs_exports | list | [] | Список экспортируемых каталогов |

Пример плэйбука
--------------

    - hosts: nfs
      remote_user: superuser
      become: yes
      vars:
        - nfs_exports: [ "/home/public *(rw,sync,no_root_squash)" ]
      roles:
        - ansible-role-nfs