# Instalar Redmine en Vagrant - Provisionado con Ansible Playbook

Version de Ruby 2.7.0

Esta guía de [instalacion de Redmine en Ubuntu 20.04](https://kifarunix.com/install-redmine-on-ubuntu-20-04/) es más completa que la [guía en el sitio de Redmine](https://www.redmine.org/projects/redmine/wiki/HowTo_Install_Redmine_50x_on_Ubuntu_2004_with_Apache2).

Se genera un usuario 'redmine' con grupo 'redmine' en el cual correr el servicio passenger - [instalacion de Passenger en Ubuntu](https://www.phusionpassenger.com/library/install/apache/install/oss/rubygems_norvm/)

## Pasos 

Iniciar un ambiente virtual e instalar ansible
```shell
python3 -m venv ansible-env
source ansible-env/bin/activate
pip install ansible
ansible --version
```
Se provisiona Vagrant con ./provisioning/provision.yml

Estructura de directorios 
```
hosts                       # Inventory
provisioning/
    provision.yml           # Playbook
    roles/                  # Roles
        role1/
            tasks/
                main.yml    # Tasks
            templates/
                template.j2 # Templates de Jinja2
            vars/
                main.yml    # Variables locales al rol
    group_vars/
        all/
            main.yml        # Variables globales
Vagrantfile

```
## Documentacion util:

### Vagrant Provision Docs

[Ansible Intro](https://www.vagrantup.com/docs/provisioning/ansible_intro)

###  Ansible Docs

[Intro](https://docs.ansible.com/ansible/latest/user_guide/playbooks_intro.html#about-playbooks)
[Conceptos basicos](https://docs.ansible.com/ansible/latest/network/getting_started/basic_concepts.html#playbooks)
[Guia de usuario](https://docs.ansible.com/ansible/latest/user_guide/index.html)
[Tips](https://docs.ansible.com/ansible/latest/user_guide/playbooks_best_practices.html#playbooks-tips-and-tricks)
[Ejemplo](https://docs.ansible.com/ansible/latest/getting_started/get_started_playbook.html)


