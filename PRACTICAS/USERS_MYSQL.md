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
![image](https://github.com/user-attachments/assets/86faa773-97f1-4dea-a2e6-4a89d4334a1d)
  - Para cambiar la contraseña de Mati a otra nueva utilizaremos el comando "ALTER USER 'Mati'@'lasalleinstitucion.es' IDENTIFIED BY 'nuevacontraseña';"
## 8. Muestra los privilegios del usuario Mati sobre la tabla usuario que has utilizado para ello.
![image](https://github.com/user-attachments/assets/c9f7e0a1-7ec8-48ee-94d7-4321777bd76b)
  - Para mostrar los privilegios del usuario Mati sobre su tabla utilizaremos el comando "SHOW GRANTS FOR 'Mati'@'lasalleinstitucion.es';"
## 9. Muestra los privilegios del usuario Mifi sobre la tabla grupo. Indica la sentencia que has utilizado para ello.
![image](https://github.com/user-attachments/assets/6985868b-7d44-40e2-881a-d7caf0f8bbf7)
  - Para mostrar los privilegios del usuario Madi sobre su tabla utilizaremos el comando "SHOW GRANTS FOR 'Mifi'@'lasalleinstitucion.es';"
## 10. Concede permisos al usuario Bego de lectura y actualización sobre la tabla usuario.
![image](https://github.com/user-attachments/assets/7ab0249f-ad4b-4182-a2f2-6eb14a369905)
  - Para conceder permisos al usuario Bego sobre la tabla usario primero deberemos crearla y después utilizar el comando "GRANT SELECT, UPDATE ON users_mysql.usuario TO 'Bego'@'localhost';"
## 11. Concede permisos al usuario Bego de lectura sobre la tabla grupo. Indica las sentencias y sus efectos sobre la base de datos de la red social.
![image](https://github.com/user-attachments/assets/7b4d0f47-6266-43e0-bd48-277578980f7d)
  - Para conceder permisos al usario Bego de lectura sobre la tabla grupo primero deberemos crear dicha tabla y después utilizar el comando "GRANT SELECT ON users_mysql.grupo TO 'Bego'@'localhost';"
## 12. Indica la sentencia para asignar a Mati el borrado sobre la tabla grupo.
![image](https://github.com/user-attachments/assets/bdae947d-ea81-4527-a913-2ed92320aa68)
  - Para asignar a Mati el permiso de borrado dobre la tabla grupo utilizaremos el comando "GRANT DELETE ON users_mysql.grupo TO 'Mati'@'lasalleinstitucion.es';"
## 13. Crea el usuario Crispula con contraseña "rosita" para que pueda acceder desde el dominio lasalleinstitucion.es y con permisos de lectura, actualización y borrado sobre las tablas usuario, grupo y comentario. Concede además permisos a Crispula para que pueda conceder sus permisos a otros usuarios.
![image](https://github.com/user-attachments/assets/d1a3ebff-0566-497f-8697-3641aab8cdf6)
![image](https://github.com/user-attachments/assets/8459b35e-64f8-42c1-a0ec-43e7398481bc)
  - Para crear el usuario Crispula con la contraseña rosita, así como conceder permisos y demás funciones que se solucitan utilizaremos,los siguientes comandos:
      - 'CREATE USER 'Crispula'@'lasalleinstitucion.es' IDENTIFIED BY 'rosita';'
      - 'grant select, update, delete on users_mysql.usuario to 'Crispula'@'lasalleinstitucion.es';'
      - 'grant select, update, delete on users_mysql.grupo to 'Crispula'@'lasalleinstitucion.es';'
      - 'grant select, update, delete on users_mysql.comentario to 'Crispula'@'lasalleinstitucion.es';'
      - 'grant grant option on users_mysql.* to 'Crispula'@'lasalleinstitucion.es';'
## 14. Indica si el usuario Crispula ha utilizado alguna tabla.
![image](https://github.com/user-attachments/assets/88f0baba-d180-4b79-b7e6-75f194df5d48)
  - Para verificar si Crispula ha utilizado alguna tabla utilizaremos el comando 'SELECT * FROM mysql.general_log WHERE user_host LIKE '%Crispula%';'
## 15. Inserta un registro en una tabla comentario. Actualiza un registro de la tabla grupo. Muestra las sentencias y su resultado al ejecutarlas sobre la base de datos de la red social.
![image](https://github.com/user-attachments/assets/06c2a516-ea0a-4652-8199-69f9949ebb1c)
  - Para insertar un registro en la tabla comentario y actualizar el registro de la tabla grupo utilizaremos los siguientes comandos:
      - INSERT INTO comentario (contenido) VALUES ('Nuevo comentario');
      - UPDATE grupo SET nombre = 'Nuevo nombre' WHERE id = 1;
## 16. Elimina el registro creado por Crispula en la tabla usuario a Bego. Muestra la sentencia utilizada y el resultado.
![image](https://github.com/user-attachments/assets/985234ba-32cd-419a-aa79-10da5a2466d2)
  - Para eliminar el registro creado por Crispula en la tabla usuario a Bego utilizaremos el comando 'DELETE FROM usuario WHERE nombre = 'Bego''
## 17. Cambia el comentario de Mati a un texto donde se mencione que ha hablado bien del grupo a Mati. Muestra la sentencia utilizada con el usuario de mysql.
![image](https://github.com/user-attachments/assets/b8a1cb4d-4498-49d9-bd01-e15d140da1be)
  - Para cambiar el comentario de mati utilizaremos el comando 'UPDATE comentario SET contenido = 'Mati ha hablado bien del grupo a Mati' WHERE id = (SELECT id FROM comentario WHERE autor = 'Mati');'
## 18. Vuelve a consultar con el usuario de mysql.
![image](https://github.com/user-attachments/assets/1707e527-0fad-4a83-b5db-c13255a52898)
  - Para volver a consultar con el usuario de mysql utilizaremos el comando 'SELECT * FROM comentario WHERE autor = 'Mati';'
## 19. Inserta tres comentarios sobre tres grupos distintos en la base de datos de la red social a Mati, Bego y Crispula. Muestra las sentencias y su ejecución.
![image](https://github.com/user-attachments/assets/704a9ca6-fe20-4cad-a980-fccbf023e491)
  - Para insertar tres comentarios sobre tres grupos distintos utilizaremos los siguientes comandos:
      - 'INSERT INTO comentario (grupo_id, contenido) VALUES (1, 'Comentario en grupo 1');'
      - 'INSERT INTO comentario (grupo_id, contenido) VALUES (2, 'Comentario en grupo 2');'
      - 'INSERT INTO comentario (grupo_id, contenido) VALUES (3, 'Comentario en grupo 3');'
## 20. Inserta dos comentarios realizados en dos grupos distintos en la base de datos de la red social a Bego. Muestra las sentencias y su ejecución.
![image](https://github.com/user-attachments/assets/b0dd390d-c89a-49f8-adf5-3487fe681229)
  - Para insertar dos comentarios realizados en dos grupos distintos a Bego utilizaremos los siguientes comandos:
      - 'INSERT INTO comentario (grupo_id, contenido) VALUES (1, 'Comentario de Bego en grupo 1');'
      - 'INSERT INTO comentario (grupo_id, contenido) VALUES (2, 'Comentario de Bego en grupo 2');'
## 21. Muestra los permisos otorgados al usuario Crispula en la base de datos de la red social. Indica la sentencia que has utilizado para ello y los resultados tras otorgar los permisos.
![image](https://github.com/user-attachments/assets/c7145c26-ac18-403d-95ef-20fdbfc5207a)
  - Para ver los permisos otorgados al usuario Crispula utilizaremos el siguiente comando: 'SHOW GRANTS FOR 'Crispula'@'lasalleinstitucion.es';'
## 22. Elimina los permisos otorgados a Crispula sobre la tabla usuario de la red social. Muestra la sentencia utilizada para ello y los resultados tras borrar los permisos.
![image](https://github.com/user-attachments/assets/ba9b472e-3297-4999-a8eb-59d440a7fa65)
  - Para eliminar todos los permisos otorgados a Crispula sobre la tabla usuario utilizaremos el comando 'REVOKE ALL PRIVILEGES ON users_mysql.usuario FROM 'Crispula'@'lasalleinstitucion.es';'
## 23. ¿Es necesario hacer FLUSH PRIVILEGES después de la sentencia anterior? Explica el porqué y para qué sirve FLUSH PRIVILEGES.
  - No es necesario. MySQL aplica los cambios inmediatamente. FLUSH PRIVILEGES solo se necesita cuando se modifican manualmente los archivos de privilegios.
## 24. ¿Puedo utilizar la función PASSWORD con GRANT? Justifica tu respuesta.
  - No, la función PASSWORD se utiliza internamente por MySQL para cifrar contraseñas y no es necesaria con GRANT, ya que este gestiona las contraseñas automáticamente con IDENTIFIED BY.
## 25. Elimina el usuario Mifi. Muestra la sentencia utilizada y el resultado de su ejecución.
![image](https://github.com/user-attachments/assets/9f6c0a5f-de3a-4706-bfae-c52bd0b08d77)
![image](https://github.com/user-attachments/assets/64e5e755-5a0e-41aa-9e1c-245a82997ce7)
  - Para eliminar al usuario Mifi utilizaremos el coamndo 'DROP USER 'Mifi'@'lasalleinstitucion.es';'
