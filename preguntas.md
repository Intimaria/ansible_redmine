# Ansible Playbook 

Version de Ruby 2.7.0

Todo el directorio /srv/redmine deberia tener el mismo usuario redmine, 
ngnix usa su usuario, redmine usa el suyo (separado), pueden compartir el grupo.

Load_Defaults requiere el modulo expect, o pasar REDMINE_LANG=en

Solo se necesita crear tmp/pdf en el path de redmine, el resto existe

Preguntas 

* como usar .env en Ansible?

* como mandar todo por https?

* en Upstream - diferencia entre poner el servidor:puerto y un socket

* deberia poner un firewall? 

* como cerrrar puertos y cuales? 

* usar capistrano3-puma en vez de systemd directo? 

Pendientes

* Usar variables de entorno Usar variables en jinja2 (tira errores por ahora)

* Sacar el become de los plays y hacerlo en cada task, para asegurar que no haya
  accessos indebidos a sudo. Quitarle el sudo access al usario redmine. 
