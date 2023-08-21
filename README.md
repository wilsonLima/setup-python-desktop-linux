setup-python-desktop-linux
=========

Role do Ansible com passos para a instalação de pacotes de Desenvolvimento Python em Desktop Linux.

Distribuições Suportadas pela Role
------------

- Fedora 37 ou inferior
- Linux Mint 21.1 ou inferior
- openSUSE Leap 15.4 ou superior
- openSUSE Tumbleweed
- Ubuntu 22.10 ou superior


Tags da Role 
--------------

- main: Tag a ser utilizada em conjunto com outras tags, se alguma tag for especificada no comando.

- python: Instala os componentes do Python 3.


Variáveis da Role 
--------------

- python_version: Versão do Python a ser instalada. O valor padrão (String): "3.10".


Dependências da Role 
--------------

Linux Mint e Ubuntu:

- openssh-server. Ex.: sudo apt install openssh-server


Exemplo de Inventario
----------------

Exemplo de arquivo de hosts: pasta_invetario/hosts

    [NOME]
    IP ansible_connection=ssh ansible_ssh_user=USUARIO ansible_ssh_pass=SENHA_URUARIO ansible_become_pass=SENHA_ROOT


Especificar interpretador python 3: pasta_invetario/group_vars/all

    ansible_python_interpreter: "/usr/bin/python3"


Exemplo de Playbook
----------------

Exemplo de uso da Role, com as configurações padrão:

    - hosts: desktop
      roles:
         - setup-python-desktop-linux


Exemplo de Comandos
----------------

Comando para executar todas as tasks:

    ansible-playbook -i <caminho_inventario> <caminho_playbook>

Comando para executar a tag "python" (em caso de uso de tags, a tag "main" é obrigatória):

    ansible-playbook -i <caminho_inventario> <caminho_playbook> --tags "main, python"


License
-------

MIT License