# Instalar Redmine en Vagrant - Provisionado con Ansible Playbook

Version de Ruby 2.7.0

## Pasos
Para seguir este consejo:
> You can install Ansible with pip which means you can also control the version pretty well. Python environments can get messy though, so if possible, utilize pyenv and virtualenv or control your tool versions by other means

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
Vagrantfile                 # Configuracion Vagrant Machine

```

## Pasos 

* Instalacion de paquetes && update-upgrade
* Creacion de grupo y usuario 'redmine' que administrará redmine con autorizacion para usuario
* Creacion de base de datos redmine & usuario de db redmine
* Instalacion de rbenv para instalar versiones de Ruby
* Instalacion de Ruby
* Bajar Redmine en /srv/ o en /opt/ (variable global redmine_path) con permisos redmine
* Entrar al directorio redmine y correr bundle install
* Configurar firewall / cerrar puertos 
* Instalar Puma (agregar Gemfile, bundle & agregar Config)
* Agregar Servicio Puma a Systemd, Iniciar Servicio (puerto 3000)
* Instalar Nginx
* Agregar usuario www-data a grupo redmine para que tenga acceso al directorio de la aplicación
* Configurar Nginx como reverse proxy server, con Puma como upstream (lee 3000, sirve en 80)
* Reiniciar Servicio de Nginx
* Listo!

## Documentacion util:

### Buenas Practicas 

[Buenas Practicas parte 1](https://medium.com/polarsquad/ansible-best-practices-part-1-b3391b3c6f68)
[Buenas Practicas parte 2 (más útil)](https://polarsquad.com/blog/ansible-best-practices-part-2)
### Vagrant Provision Docs

[Ansible Intro](https://www.vagrantup.com/docs/provisioning/ansible_intro)

### Ansible Docs

* [Intro](https://docs.ansible.com/ansible/latest/user_guide/playbooks_intro.html#about-playbooks)
* [Conceptos basicos](https://docs.ansible.com/ansible/latest/network/getting_started/basic_concepts.html#playbooks)
* [Guia de usuario](https://docs.ansible.com/ansible/latest/user_guide/index.html)
* [Tips](https://docs.ansible.com/ansible/latest/user_guide/playbooks_best_practices.html#playbooks-tips-and-tricks)
* [Ejemplo](https://docs.ansible.com/ansible/latest/getting_started/get_started_playbook.html)


