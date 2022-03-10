# Skill Factory Project 10

ЗАДАНИЕ B10.4.1 (HW-03)
1. Написать свой Playbook, который будет устанавливать и запускать Docker на локальной машине.
2. Написать свой Playbook, который будет запускать MySQL-сервер на локальной машине

ЗАДАНИЕ B10.5.1 (HW-03)
1. Напишите плейбук, который будет на удаленной системе создавать пользователя user1 и задавать ему SSH-ключ (создавая заданный ключ в /home/user1/.ssh/id_rsa.pub). Ключ не должен передаваться в открытом виде. Используйте для шифрования ключа ansible-vault. Ключ можете сгенерировать, используя SSH-keygen.
2. Создайте плейбук, который устанавливает, либо удаляет почтовый сервер postfix в зависимости от тега.

Закодировать ключ:
ansible-vault encrypt --ask-vault-pass /home/local/id_rsa.pub
Запустить плейбук:
ansible-playbook play.yaml -i hosts.txt --ask-vault-pass

postfix.yaml - устанавливает, либо удаляет почтовый сервер postfix в зависимости от тега

Установить почтовый сервер postfix: ansible-playbook -t 'init postfix' postfix.yaml -i hosts.txt

Удалить почтовый сервер postfix: ansible-playbook -t 'drop postfix' postfix.yaml -i hosts.txt