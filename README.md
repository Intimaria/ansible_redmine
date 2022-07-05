Guia mas completa de instalacion en Ubuntu 20.04
https://kifarunix.com/install-redmine-on-ubuntu-20-04/

Version de Ruby 2.7.0

Todo el directorio /srv/redmine deberia tener el mismo usuario redmine
Apache usa su usuario, redmine usa el suyo (separado)

Instalar Rbenv 

Generar un usuario redmine en el cual correr el servicio passenger
Instalacion de Passenger: 
https://www.phusionpassenger.com/library/install/apache/install/oss/rubygems_norvm/
Una vez corriendo el passenger configurar apache 

Load_Defaults requiere el modulo expect, o pasar REDMINE_LANG=en

Solo se necesita crear tmp/pdf, el resto existe

Pregunta - como usar .env en Ansible? 

Pregunta - como mandar todo por https?

Pendientes:
Asegurar SQL, quitar usuario root etc. 
Usar variables de entorno
Usar variables en jinja2 (tira errores por ahora)