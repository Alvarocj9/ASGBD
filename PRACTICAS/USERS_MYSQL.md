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
![image](https://github.com/user-attachments/assets/5451459e-8f7e-48f3-a297-4743dff74888)
  - Para revisar si alguno de los usuarios ha logrado utilizar alguna tabla o función utilizaremos el comando "SELECT User, Host FROM mysql.user;"
## 7. Muestra el usuario con el que te ha registrado, utilizando para ello una función. Indica la sentencia que has utilizado para ello.
![image](https://github.com/user-attachments/assets/fc8eb84e-eab8-4fdf-8948-d549ada24fee)
  - Para mostrar el usuario con el que nos hemos registrado utilizaremos el comando "SELECT USER();"
## 8. Cambia la contraseña de Mati, de manera que la nueva contraseña sea "minuevacontraseña". Indica la sentencia que has utilizado para ello.
![image](https://github.com/user-attachments/assets/df1e1339-3d5e-420d-a2f6-1d352c618534)
  - Para cambiar la contraseña de Mati a otra nueva utilizaremos el comando "ALTER USER 'Mati'@'lasalleinstitucion.es' IDENTIFIED BY 'nuevacontraseña';"
## 9. Muestra los privilegios del usuario Con el que te has logado. Indica la sentencia que has utilizado para ello.
![image](https://github.com/user-attachments/assets/0da18b35-eb46-4c3f-a7c1-32b645e59ae2)
  - Para mostrar los privilegios del usuario Madi sobre su tabla utilizaremos el comando "SHOW GRANTS FOR 'Bego'@'localhost';"
## 10. Muestra los privilegios del usuario con el que te ha logado. Indica la sentencia que has utilizado para ello.
![image](https://github.com/user-attachments/assets/7ad09b86-ef57-48be-a2df-cc449709abf9)
  - Para mostrar los privilegios del usuario con el que nos hemos logado deberemos utilizar el comando "SHOW GRANTS FOR CURRENT_USER;"
## 11. Conéctate como Bego y lanza una sentencia SELECT y UPDATE sobre la tabla usuario. Lanza también una sentencia DELETE. Muestra las sentencias y sus efectos sobre la base de datos de la red social.
![image](https://github.com/user-attachments/assets/e1cb0759-56cf-4b0c-9e08-01e69738a2cc)
  - Para conceder permisos al usario Bego de lectura sobre la tabla grupo primero deberemos crear dicha tabla y después utilizar los comandos:
      - "GRANT SELECT ON users_mysql.grupo TO 'Bego'@'localhost';"
      - "GRANT SELECT, UPDATE ON base_de_datos.usuario TO 'Bego'@'localhost';"
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
## 14. Conéctate con el usuario Crispula.
![image](https://github.com/user-attachments/assets/09e611b6-7806-432c-a236-f94890a4bb1c)
  - Para conectarnos como Crispula utilizaremos el comando "mysql -u Crispula -p"
## 15. Inserta un registro en una tabla comentario. Actualiza un registro de la tabla grupo. Muestra las sentencias y su resultado al ejecutarlas sobre la base de datos de la red social.
![image](https://github.com/user-attachments/assets/06c2a516-ea0a-4652-8199-69f9949ebb1c)
  - Para insertar un registro en la tabla comentario y actualizar el registro de la tabla grupo utilizaremos los siguientes comandos:
      - INSERT INTO comentario (contenido) VALUES ('Nuevo comentario');
      - UPDATE grupo SET nombre = 'Nuevo nombre' WHERE id = 1;
## 16. Concede permiso de borrado sobre la tabla grupo a Bego. Muestra la sentencia utilizada y el resultado de su ejecución.
![image](https://github.com/user-attachments/assets/a9ffda96-5864-4c14-8002-8919fc165602)
  - Para coneceder permisos de borrado sobre la tabla usuario a Bego utilizaremos el comando 'GRANT DELETE ON base_de_datos.grupo TO 'Bego'@'localhost';'
## 17. Concede permisos de lectura y actualización sobre la tabla grupo a Mati.
![image](https://github.com/user-attachments/assets/74b556f6-6871-40a3-8af5-8b7a0a0b4e54)
![image](https://github.com/user-attachments/assets/b3ab61cf-7db1-41e4-88a2-281092befc64)
  - Para conceder permisos de lectura y atualización sobre la tabla grupo a Mati con los siguientes comandos:
      - "GRANT SELECT, UPDATE ON users_mysql.grupo TO 'Mati'@'lasalleinstitucion.es';"
      - "show grants for 'Mati'@'lasalleinstitucion.es';"
## 18. Vuelve a conectarte con el usuario de mysql.
![image](https://github.com/user-attachments/assets/1707e527-0fad-4a83-b5db-c13255a52898)
  - Para volver a consultar con el usuario de mysql utilizaremos el comando 'SELECT * FROM comentario WHERE autor = 'Mati';'
## 19.Concede permisos totales sobre todas las tablas de la base de datos de la red social a Mifi. Muestra la sentencia utilizada y el resultado de su ejecución.
![image](https://github.com/user-attachments/assets/704a9ca6-fe20-4cad-a980-fccbf023e491)
  - Para conceder permisos totales sobre todas las tablas de la base de datos de la red social a Mafi utilizaremos el comando 'GRANT ALL PRIVILEGES ON base_de_datos.* TO 'Mifi'@'lasalleinstitucion.es';'
## 20. Quita permisos de borrado sobre todas las tablas de la base de datos de la red social a Mifi. Muestra la sentencia utilizada y el resultado de su ejecución.
![image](https://github.com/user-attachments/assets/b0dd390d-c89a-49f8-adf5-3487fe681229)
  - Para quitar los permisos de borrado sobre todas las tablas de la base de datos de la red social a Mifli utilizaremos el comando 'REVOKE DELETE ON base_de_datos.* FROM 'Mifli'@'lasalleinstitucion.es';'
## 21. Muestra los usuarios creados y sus privilegios (los que están en la tabla usuario de la base de datos mysql). Indica la sentencia que has utilizado para mostrar a esos usuarios.
![image](https://github.com/user-attachments/assets/4cdadd3f-a855-4efd-9d55-6bb24d1cc7d8)
  - Para ver los usuarios creados y sus privilegios utilizaremos los siguientes comandos:
      - SELECT User, Host FROM mysql.user;
      - SHOW GRANTS FOR 'Bego'@'localhost';
      - SHOW GRANTS FOR 'Mati'@'lasalleinstitucion.es';
      - SHOW GRANTS FOR 'Mifi'@'lasalleinstitucion.es';
## 22. Cambia la contraseña del usuario Mifi modificándola directamente en la tabla user. Indica la sentencia que has utilizado para ello.
![image](https://github.com/user-attachments/assets/75f35925-446d-4835-b91e-66d6d920800b)
  - Para cambiar la contraseña del usuario Mifli modificándola directamente en la tabla user utilizaremos el comando 'UPDATE mysql.user SET authentication_string = PASSWORD('nuevaContraseña') WHERE User = 'Mifi' AND Host = 'lasalleinstitucion.es';'
## 23. ¿Es necesario hacer FLUSH PRIVILEGES después de la sentencia anterior? Explica el porqué y para qué sirve FLUSH PRIVILEGES.
  - No es necesario. MySQL aplica los cambios inmediatamente. FLUSH PRIVILEGES solo se necesita cuando se modifican manualmente los archivos de privilegios.
## 24. ¿Puedo utilizar la función PASSWORD con GRANT? Justifica tu respuesta.
  - No, la función PASSWORD se utiliza internamente por MySQL para cifrar contraseñas y no es necesaria con GRANT, ya que este gestiona las contraseñas automáticamente con IDENTIFIED BY.
## 25. Elimina el usuario Mifi. Muestra la sentencia utilizada y el resultado de su ejecución.
![image](https://github.com/user-attachments/assets/9f6c0a5f-de3a-4706-bfae-c52bd0b08d77)
![image](https://github.com/user-attachments/assets/64e5e755-5a0e-41aa-9e1c-245a82997ce7)
  - Para eliminar al usuario Mifi utilizaremos el coamndo 'DROP USER 'Mifi'@'lasalleinstitucion.es';'
