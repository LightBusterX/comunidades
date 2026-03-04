### 11/I/2026

*Configuraciones en sistemas virtuales*
- Se han preparado 2 máquinas virtuales con:
	- FreeBSD 15.0-RELEASE
	- doas como PKG instalado y configurado.
	- Una de ellas usando los repositorios "latest" para acceder a Odoo 19
	- Nombres de host "F15R-Odoo18-test" y "F15R-Odoo19-test"
	- Se ha instalado _bastille_ en F15R-Odoo19-test.
		- Se han hecho pruebas y los repos de **host** y **jail** no son los mismos, cada uno tiene su propio archivo de repos.

*Modificaciones en software personalizado (freebsd15-install-odoo.sh)*
- Se ha añadido una función ("version_repo()") para cambiar de **quarterly** a **latest** y poder acceder al PKG de Odoo 19 ya disponible.
- Se ha modificado el flujo del guión para admitir este cambio de versión.

### 04/III/2026

__Se ha reiniciado el proyecto tras un parón por necesidades varias__ 

_Revisión del estado general del proyecto:_
- Se ha añadido Odoo 19 a los repositorios de FreeBSD, lo que hace necesario refactorizar algunos scripts.
- Se ha eliminado "wkhtmltopdf" de los repositorios de FreeBSD, lo que hace imposible su instalación desde la herramienta PKG y desde el árbol de __ports__.
- Se ha creado un conjunto de scripts para habilitar la emulación de Linux y poder instalar "wkhtmltopdf" desde un repositorio de CentOS 7 / Rocky 9 y hacerlo compatible con la instalación en jaula de Odoo 18/19.
- Se ha creado un script para buscar "bash" en el sistema e instalarlo si fuera necesario (algunas funciones personalizadas pueden ser muy útiles.)
- 