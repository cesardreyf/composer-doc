# Traducción al español de la documentación de Composer

Esta es una traducción no oficial de la documentación de [Composer](https://getcomposer.org).

## Contenido

- [Introducción](#introducción)
  - [Gestión de dependencias](#gestión-de-dependencias)
  - [Requisitos](#requisitos)

## Introducción

Composer es una herramienta para gestionar dependencias en **PHP**. Este te permite declarar las bibliotecas de las que depende tu proyecto y administrarlas (**instalar**/**actualizar**).

### Gestión de dependencias

Composer **no** es un [gestor de paquetes](https://es.wikipedia.org/wiki/Sistema_de_gesti%C3%B3n_de_paquetes) como lo son Yum o Apt. Sí, gestiona *"paquetes"* o bibliotecas, pero los hace por cada proyecto, instalándolos en una carpeta (por lo general llamado *vendor*) dentro de su proyecto. Por defecto no instala nada de forma global; aunque, por conveniencia, soporta un proyecto *"global"* a través del comando [global](#a-implementar).

Esta idea no es para nada nueva y está fuertemente inspirada en [npm](https://www.npmjs.com/) de Node y en [bundler](https://bundler.io/) de Ruby.

Supón que:
- Tienes un proyecto que depende de varias bibliotecas, y
- Algunas de esas bibliotecas dependen de otras bibliotecas.

Composer:
- Permite declarar las bibliotecas de las que depende,
- Busca qué versiones de qué paquetes pueden y necesitan instalarse, y
- Actualiza todas las dependencias con un solo comando

Ver el capítulo de [Uso básico](#a-implementar) para obtener más detalles sobre la declaración de dependencias.

### Requisitos

Composer, en su última versión, requiere de **PHP 7.2.5** para funcionar. Una versión de soporte a largo plazo (2.2.x) todavía ofrece soporte para PHP 5.3.2+ en caso de que esté usando una versión antigua de PHP. También se requieren algunas configuraciones y flags de compilación sensibles de PHP, pero cuando utilice el instalador se le advertirá sobre cualquier incompatibilidad.

Composer es multiplataforma y funciona igual de bien en Windows, Linux y macOS.

### Instalación - Linux / Unix / macOS

#### Descargando el ejecutable de Composer

Composer ofrece un instalador que puede ejecutarse directamente desde la línea de comandos. Siéntase libre de [descargar este archivo](https://getcomposer.org/installer) o verlo en [GitHub](https://github.com/composer/getcomposer.org/blob/main/web/installer) si desea conocer más en profundidad sobre el funcionamiento interno del instalador.

En resumen, hay dos maneras de instalar Composer. Una es de forma local como parte de su proyecto y la otra es de forma global como un ejecutable de todo el sistema.

##### Localmente

Para instalar Composer localmente, ejecute el instalador en el directorio de su proyecto. Consulte la página de descarga para obtener instrucciones.

El instalador verificará algunas configuraciones PHP y luego descargará **composer.phar** a su directorio de trabajo. Este archivo es el binario de Composer. Es un archivo [PHAR](https://www.php.net/manual/es/book.phar.php), que es un formato de archivo para PHP que puede ser ejecutado en la línea de comandos.

Ahora ejecute php **composer.phar** para ejecutar Composer.

Puedes instalar Composer en un directorio específico usando la opción `--install-dir` y adicionalmente renombrarlo usando la opción `--filename`. Cuando ejecute el instalador siguiendo las instrucciones de la página de descarga añada los siguientes parámetros:

`
php composer-setup.php --install-dir=bin --filename=composer
`

Ahora ejecute php `bin/composer` para ejecutar Composer.

##### Globalmente

Puede colocar el Composer PHAR donde desee. Si lo colocas en un directorio el cual forme parte de tu [PATH](https://es.wikipedia.org/wiki/PATH_(inform%C3%A1tica)), puedes acceder a él globalmente. En sistemas Unix puedes incluso hacerlo ejecutable y usarlo sin necesidad de usar el intérprete php.

Después de ejecutar el instalador siguiendo [las instrucciones de la página de descarga](#a-implementar) puede ejecutar esto para mover **composer.phar** a una carpeta que esté en su ruta:

`
mv composer.phar /usr/local/bin/composer
`

Si quieres instalarlo sólo para tu usuario y evitar que requiera permisos root, puedes usar `~/.local/bin` en su lugar, que está disponible por defecto en algunas distribuciones de Linux.

>**Nota**: Si lo anterior falla debido a los permisos, puede que necesite ejecutarlo de nuevo con `sudo`.
>
>**Nota**: En algunas versiones de `macOS` el directorio `/usr` no existe por defecto. Si recibe el error *"/usr/local/bin/composer: No such file or directory"*, debe crear el directorio manualmente antes de continuar: `mkdir -p /usr/local/bin`.

Ahora puede ejecutar el comando `composer` para ejecutar directamente Composer en lugar de tener que escribir `php composer.phar`.
