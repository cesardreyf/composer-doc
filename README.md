# Traducción al español de la documentación de Composer

Esta es una traducción no oficial de la documentación de [Composer](https://getcomposer.org).

## Contenido

- [Introducción](#introducción)
  - [Gestión de dependencias](#gestión-de-dependencias)

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
