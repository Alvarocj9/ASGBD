# EJERCICIOS BÁSICOS DE MYSQL
## 1. Indica el nombre de las tablas que aparecen en tu base de datos de mysql.
![image](https://github.com/user-attachments/assets/5f2d8189-cde6-45e5-aecd-d07ef551d347)
  - Para ver las tablas que hay en la BBDD pondremos el comando "SHOW tables;". En este caso como no hay ninguna tabla creada dentrpo de la BBDD no nos aparecerá ninguna.
## 2. Crea el usuario "Bego" con contraseña "BegiNa" para que pueda acceder desde localhost.
![image](https://github.com/user-attachments/assets/40932328-abe2-436a-9287-8a11e97c5846)
  - Para crear el usuario con la contraseña de manera que pueda acceder desde localhost utilizaremos el comando "CREATE USER 'Bego'@'localhost' IDENTIFIED BY 'BegiNa';"
## 3. Crea el usuario "Mati" con contraseña "Miti30" para que pueda acceder desde el dominio lasalleinstitucion.es.
![image](https://github.com/user-attachments/assets/dac09fc6-9b53-49dc-8ed8-4f5c70665dc7)
  - Para crear el usuario con la contraseña de manera que pueda acceder desde lasalleinstitucion.es utilizaremos el comando "CREATE USER 'Mati'@'lasalleinstitucion.es' IDENTIFIED BY 'Miti30';"
## 4. Crea el usuario "Mifi" con contraseña "lopoL45" para que pueda acceder desde el dominio lasalleinstitucion.es.
![image](https://github.com/user-attachments/assets/3ee1824d-b298-4971-b7bf-f670d0ab425e)
  - Para crear el usuario con la contraseña de manera que pueda acceder desde lasalleinstitucion.es utilizaremos el comando "CREATE USER 'Mifi'@'lasalleinstitucion.es' IDENTIFIED BY 'lopoL45';"
## 5. Muestra los usuarios creados (los que están en la tabla user de la base de datos mysql). Indica la sentencia que has utilizado para mostrar estos usuarios.
![image](https://github.com/user-attachments/assets/478944ea-f4a1-47c0-82a3-b37335e59447)
  - Para mostrar los usuarios que hemos creado utilizaremos el comando "SELECT User, Host FROM mysql.user;"
## 6. Indica si alguno de estos usuarios ha logrado utilizar alguna tabla o una función. Indica la sentencia que has utilizado para ello.
![image](https://github.com/user-attachments/assets/dedded6b-5b37-456a-abd3-2168516c12e2)
  - Para revisar si alguno de los usuarios ha logrado utilizar alguna tabla o función utilizaremos el comando "SELECT * FROM mysql.general_log WHERE user_host LIKE '%Bego%' OR user_host LIKE '%Mati%' OR user_host LIKE '%Mifi%';"
## 7. Cambia la contraseña de Mati, de manera que la nueva contraseña sea "nuevacontraseña". Indica la sentencia que has utilizado para ello.
## 8. Muestra los privilegios del usuario Mati sobre la tabla usuario que has utilizado para ello.
## 9. Muestra los privilegios del usuario Mifi sobre la tabla grupo. Indica la sentencia que has utilizado para ello.
## 10. Concede permisos al usuario Bego de lectura y actualización sobre la tabla usuario.
## 11. Concede permisos al usuario Bego de lectura sobre la tabla grupo. Indica las sentencias y sus efectos sobre la base de datos de la red social.
## 12. Indica la sentencia para asignar a Mati el borrado sobre la tabla grupo.
## 13. Crea el usuario Crispula con contraseña "rosita" para que pueda acceder desde el dominio lasalleinstitucion.es y con permisos de lectura, actualización y borrado sobre las tablas usuario, grupo y comentario. Concede además permisos a Crispula para que pueda conceder sus permisos a otros usuarios.
## 14. Indica si el usuario Crispula ha utilizado alguna tabla.
## 15. Inserta un registro en una tabla comentario. Actualiza un registro de la tabla grupo. Muestra las sentencias y su resultado al ejecutarlas sobre la base de datos de la red social.
## 16. Elimina el registro creado por Crispula en la tabla usuario a Bego. Muestra la sentencia utilizada y el resultado.
## 17. Cambia el comentario de Mati a un texto donde se mencione que ha hablado bien del grupo a Mati. Muestra la sentencia utilizada con el usuario de mysql.
## 18. Vuelve a consultar con el usuario de mysql.
## 19. Inserta tres comentarios sobre tres grupos distintos en la base de datos de la red social a Mati, Bego y Crispula. Muestra las sentencias y su ejecución.
## 20. Inserta dos comentarios realizados en dos grupos distintos en la base de datos de la red social a Bego. Muestra las sentencias y su ejecución.
## 21. Muestra los permisos otorgados al usuario Crispula en la base de datos de la red social. Indica la sentencia que has utilizado para ello y los resultados tras otorgar los permisos.
## 22. Elimina los permisos otorgados a Crispula sobre la tabla usuario de la red social. Muestra la sentencia utilizada para ello y los resultados tras borrar los permisos.
## 23. ¿Es necesario hacer FLUSH PRIVILEGES después de la sentencia anterior? Explica el porqué y para qué sirve FLUSH PRIVILEGES.
## 24. ¿Puedo utilizar la función PASSWORD con GRANT? Justifica tu respuesta.
## 25. Elimina el usuario Mifi. Muestra la sentencia utilizada y el resultado de su ejecución.
