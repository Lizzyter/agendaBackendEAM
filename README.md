<h1> 馃摓 Agenda Telef贸nica Backend 馃摓</h1>

## 馃摎 Contenido

- Introducci贸n
- Requerimientos
- Instalaci贸n
- Configuraci贸n
- Verificaci贸n
- Especificaciones
- Fronted
- Maintainer

## 馃搨 Introducci贸n
C贸digo backend que consta de realizar una agenda telef贸nica utilizando php, base de datos en mysql y haciendo el uso del framework symfony.

## 馃搨 Requerimientos
- PHP 8.0.8
- Composer 2.3.5
- Symfony 6.2
- Gestor de base de datos (MAMP)

## 馃搧 Instalaci贸n

1. Clonar el repositoria dentro de la carpeta 'htdocs' o af铆n de acuerdo al gestor de base de datos que tengas instalado.
2. Abrir una terminal cmd en la carpeta del repositorio clonado, a continuaci贸n, ejecutar el siguiente comando:
```bash
composer install
```
3. Una vez ejecutado el comando anterior podras visualizar las carpetas generadas desde tu gestor de c贸digo.


## 馃搨 Configuraci贸n
1. Configurar el URL para la base de datos en el archivo ".env"

En este caso el gestor de servicios para base de datos que se us贸 fue MAMP, as铆 que habra unas peque帽as modificaciones:

<p>
  <img src="https://user-images.githubusercontent.com/100662882/209512176-c8e2bfb4-4c90-4e01-b452-e2998db7ae04.png" />
</p>

Considerando el formato "usuario:password", deber谩s cambiar la palabra "root" por el nombre de usuario que usas para entrar a tu gestor (en caso de que uses el mismo usuario, dejalo de la misma forma) para el siguiente campo de "root" ser谩 tu contrase帽a en caso de que la tengas, de no ser as铆 deber谩s borrar ":root" del url.

Por 煤ltimo, revisando que puerto tienes para mysql deberas modificar la parte de 8809 por 3306, seg煤n sea el caso.

2. Inicializar tu gestor de servicio de base de datos, es importante que la mantengas inicializada durante este proceso.

<p>
  <img width="529" alt="image" src="https://user-images.githubusercontent.com/100662882/209513476-d91f185a-e07c-4408-a6da-53657b909a0c.png">
</p>

3. Dirigete a la consola del proyecto y ejecuta el siguiente comando para generar la base de datos:
```bash
php bin/console doctrine:database:create
```
4. Dirigite a la carpeta de migraciones y en caso de encontrar un documento ".php" borralo para poder realizar el siguiente paso.
<img width="164" alt="image" src="https://user-images.githubusercontent.com/100662882/209513874-d50a5e6e-b7d0-4bfa-8dea-11e9d9f96cba.png">

5. La base de datos a煤n no contiene la tablas, por lo tanto, ejecuta el siguiente comando para a帽adirlas:
```bash
php bin/console make:migration
```
6. Para finalizar, este comando ejecuta todos los archivos de migraci贸n que a煤n no se han ejecutado en su base de datos:
```bash
php bin/console doctrine:migrations:migrate
```
7. 隆Importante! En caso de que te marque alg煤n tipo de error dirigete a un gestor de base de datos y borra la base de datos manualmente, una vez hecho esto ejecuta los pasos desde el n煤mero 3.

## 馃搨 Verificaci贸n

Una vez hayas realizado los pasos anteriores en la secci贸n de configuraci贸n es necesesario corroborar que todo funcione correctamente, para ello:

1. Inicializa el servidor desde la consola ejecutada de tu proyecto:
 ```bash
php -S localhost:8000 -t public
```
2. Deber谩s poder visualizar la siguiente pantalla:
<img width="1381" alt="Captura de pantalla 2022-12-25 a la(s) 19 02 51" src="https://user-images.githubusercontent.com/100662882/209515410-cad541f1-0704-4a06-97fb-6bf2a1ce3632.png">

3. Dirigete a la url de tu navegador y agregale "api/contactos", similar a http://localhost:8000/api/contactos
4. Visualizar谩s en formato "JSON" un arreglo vac铆o debido a que no tienes datos en tu tabla contactos, pero si ingresaste de manera manual algun dato podras observar algo similar a la siquiete imagen:
<img width="1440" alt="Captura de pantalla 2022-12-25 a la(s) 21 36 33" src="https://user-images.githubusercontent.com/100662882/209515453-a52d9c19-9371-4ed2-9059-82bb61762493.png">

## 馃搨 Especificaciones

* 馃煟 Deber谩s tener el servidor encendido para poder usar la API.
* 馃煟 Los campos de la entidad contacto son los siguientes:
- Nombre
- Apellido 
- N煤mero telef贸nico
- Direcci贸n
- Email
* 馃煟 La tabla de otros n煤meros 煤nicamente registrar谩 el ide y el nuevo n煤mero telef贸nico.
* 馃煟 La tabla contacto otros n煤mero, establecer谩 la relaci贸n entre el id del nuevo n煤mero y el id del contacto al cual se le asignar谩. 

## 馃搨 Fronted
Podr谩s encontrar el repositorio del fronted para que puedas realizar las pruebas necesarias del CRUD.
<br>

[Fronted de la aplicaci贸n](https://github.com/Lizzyter/agendaFrontedEAM)


## Maintainer
En caso de encontrar alg煤n problema o bug en su ejecuci贸n, h谩zmelo saber lo m谩s pronto posible para dar una respuesta inmediata

<br>
<p align='center'>
  <img src='https://img.shields.io/badge/Versi贸n-1.0.0-9fc?style=flat-square' />
  <img src='https://img.shields.io/badge/Estatus-Terminado-blueviolet?style=flat-square' />
</p>

馃挓 Code by [Elizabeth Aguilar](https://github.com/Lizzyter)
