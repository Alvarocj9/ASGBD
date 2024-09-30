# Configuración de Parámetros MySQL/MariaDB para Inverna Forever

Esta tabla muestra los parámetros de configuración, los valores asignados y una breve explicación del porqué se eligieron dichos valores.

| Parámetro                    | Valor       | Explicación                                                                 |
|------------------------------|-------------|-----------------------------------------------------------------------------|
| innodb_buffer_pool_size       | 12G         | Tamaño suficiente para manejar la alta carga de lecturas de perfiles, publicaciones y comentarios. |
| innodb_log_file_size          | 512M        | Aumentado para manejar escrituras esporádicas sin afectar el rendimiento general. |
| max_connections               | 500         | Se ajusta para manejar una concurrencia moderada de usuarios conectados simultáneamente. |
| query_cache_size              | 256M        | Cache optimizada para mejorar la eficiencia de las consultas repetidas (lecturas de perfiles y publicaciones). |
| table_open_cache              | 1024        | Valor ajustado para abrir tablas de manera eficiente en un entorno con muchas lecturas de datos. |
| tmp_table_size                | 128M        | Suficiente para manejar las tablas temporales creadas durante las lecturas sin usar espacio en disco. |
| max_heap_table_size           | 128M        | Igual que `tmp_table_size` para optimizar las tablas en memoria. |
| innodb_flush_log_at_trx_commit| 1           | Asegura que las modificaciones en perfiles o publicaciones sean visibles inmediatamente, garantizando la consistencia. |
| log_bin                       | ON          | Activado para mantener la integridad y permitir recuperación de datos en caso de fallos. |
| slow_query_log                | ON          | Activado para identificar consultas lentas que pueden afectar la experiencia del usuario. |
| slow_query_log_file           | /var/log/mysql/slow.log | Archivo donde se almacenan las consultas lentas para análisis posterior. |
| long_query_time               | 2           | Ajustado a 2 segundos para detectar rápidamente consultas que afecten la experiencia de los usuarios. |
| bind-address                  | 0.0.0.0     | Configurado para aceptar conexiones desde múltiples interfaces de red. |
| innodb_file_per_table         | ON          | Activado para gestionar mejor el almacenamiento de datos por tabla, permitiendo un crecimiento más ordenado. |
| performance_schema            | OFF         | Desactivado para reducir la sobrecarga y mejorar el rendimiento en un entorno de alta concurrencia de lecturas. |


# Justificación de los valores:
  - innodb_buffer_pool_size: Se asigna un tamaño considerable para manejar el volumen de lecturas de perfiles, publicaciones y comentarios.
  - innodb_flush_log_at_trx_commit: Se asegura la consistencia inmediata para que los cambios realizados en los perfiles o publicaciones sean visibles rápidamente para otros usuarios.
  - max_connections: Configurado para manejar la concurrencia moderada típica de una red social sin sobrecargar el servidor.
