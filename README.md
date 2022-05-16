
# reto_tkambio

Estimado(a), Muchas gracias por tomar tu valioso tiempo en llevar a cabo este challenge. Como desarrolladores sabemos que es tedioso, así que tratamos de simplificarlo para que en el menor tiempo posible puedas demostrar tus asombrosas habilidades.
¡Te deseamos éxito!

Antes de empezar quisiéramos que tengas presente los siguientes criterios de evaluación

**Decisiones Técnicas**

Sabemos que en el mundo del software existen varios caminos para llegar al mismo resultado. Queremos que uses el camino más óptimo, que el código sea reutilizable y mantenible en el tiempo pensando que trabajarás en equipo, de esa forma demuestras tu experiencia.
Calidad de código
Lo que esperamos es que tu código sea ordenado , limpio y fácil de entender usando todas las buenas prácticas de desarrollo.
Número de requerimientos terminados.
Será el número de requisitos cumplidos según las especificaciones técnicas del challenge.
¡Por favor! no copies y pegues código de otros proyectos o de stackoverflow, nos daremos cuenta de eso! y podrías ser descalificado.

**Challenge Ingeniero Junior**

Se desea crear una aplicación web que pueda descargar  reportes en excel de los usuarios registrados. 
Desarrolla solo 1 de las dos partes Front end o backend (Si desarrollas ambas serán puntos extras)

**Para la parte front-end**

Desarrollar una aplicación SPA en Vue Js, la cual tenga como interfaz un botón para generar los reportes  de usuarios y una tabla que liste los reportes generados.
Considerar diseño responsivo y fidelidad con el diseño propuesto. Evitar el uso de librerías de estilos como vue-bootstrap u otros, lo que deseamos es saber que tanto dominas la parte del frontend.

Cada vez  que se aprieta el botón  “generar reporte” se abrirá un formulario para crear un nuevo reporte de usuarios filtrado por fecha debiendo ingresar el “título del reporte” así como la “fecha inicio” y “fecha fin” basadas en la fecha de nacimiento (birth_date) de los usuarios.

Considera todas las validaciones de seguridad que creas conveniente.

Piezas gráficas en figma https://www.figma.com/file/WLNrwT4SqLjVfdvq7h7olv/Challenge-Full-Stack---Tkambio?node-id=7%3A463

Prototipo en figma https://www.figma.com/proto/WLNrwT4SqLjVfdvq7h7olv/Challenge-Full-Stack---Tkambio?p%5B%E2%80%A6%5D246%2C48%2C0.38=&scaling=min-zoom&starting-point-node-id=5%3A74&node-id=7%3A463

Fuentes tipográficas https://drive.google.com/drive/folders/1X5P-F0cbbDlL2kQSvYA-4UL75uYDrKG-


**Para la parte backend**

Crear un seeder que llene la tabla de users con al menos 1000 registros con diferentes nombres y fechas de nacimiento desde el año 1980 hasta 2010 y esta sirva para la generación de reportes. Esta tabla deberá tener al menos los siguientes campos : created_at, id, name, birth_date
Crear una tabla reports con los campos : id, created_at, title, report_link
Desarrollar una API usando laravel 7.x o superior con 3 endpoints, la generación de los reportes se debe hacer usando el sistema de colas de Laravel.
Considera todas las validaciones de seguridad que creas conveniente.


Endpoint
Descripción
/api/generate-report
Al recibir la petición deberás encolar en un JOB la generación del reporte en excel, guardar el archivo generado en disco y crear un registro del reporte en la tabla reports. 
/api/get-report/{report_id}
Obtendrás la información del reporte para poder descargarlo.
/api/list-reports
Listar todos los  reportes generados y con esta información poder mostrarlo en el front end.



					Forma de entrega 

En github crear 2 repositorios 1 para el frontend  y otro para el backend (si aplicase) de manera pública para poder revisar tu código.
Si hiciste la parte de frontend publicarlo  como página estática en github, y simula la información  con data estática (el listado de reportes o usa localstorage, etc) para poder evaluar el acabado del diseño. (simula el back-end con data estática).
Compartir los links de los repos  por correo electrónico  a postulantes@tkambio.com  con asunto “Solución del challenge FullStack <nombre> <apellido>”
Tienes 1 semana para entregar el challenge.
