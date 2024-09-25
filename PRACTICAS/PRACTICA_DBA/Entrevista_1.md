# Configuración de Parámetros MySQL/MariaDB para Commerce Boquerón Caliente

Esta tabla muestra los parámetros de configuración, los valores asignados y una breve explicación del porqué se eligieron dichos valores.

| Parámetro                    | Valor       | Explicación                                                                 |
|------------------------------|-------------|-----------------------------------------------------------------------------|
| innodb_buffer_pool_size       | 8G          | Tamaño de la pool de buffer incrementado para manejar la alta carga de usuarios y datos en memoria. |
| innodb_log_file_size          | 1G          | Aumentado para manejar más escrituras de transacciones concurrentes sin perder rendimiento. |
| max_connections               | 1000        | Dado el alto número de usuarios simultáneos, se incrementa para evitar cuellos de botella. |
| query_cache_size              | 128M        | Cache ajustada para mejorar el rendimiento de consultas frecuentes en un entorno de alta concurrencia. |
| table_open_cache              | 2048        | Aumentado para soportar el acceso a muchas tablas simultáneamente. |
| tmp_table_size                | 256M        | Mayor tamaño para evitar que las tablas temporales se escriban en disco, acelerando las operaciones. |
| max_heap_table_size           | 256M        | Ajustado igual que `tmp_table_size` para gestionar mejor las tablas en memoria. |
| innodb_flush_log_at_trx_commit| 1           | Asegura que cada transacción se grabe inmediatamente en el disco, garantizando integridad en cada operación. |
| log_bin                       | ON          | Activado para habilitar la replicación y garantizar recuperación de datos en caso de fallo. |
| slow_query_log                | ON          | Permite detectar consultas lentas, esenciales para la optimización continua en entornos de alto rendimiento. |
| slow_query_log_file           | /var/log/mysql/slow.log | Archivo donde se almacenan las consultas lentas para análisis posterior. |
| long_query_time               | 1           | Ajustado a 1 segundo para detectar rápidamente cualquier consulta que supere ese tiempo en este entorno crítico. |
| bind-address                  | 0.0.0.0     | Configurado para escuchar en todas las interfaces de red, permitiendo acceso desde múltiples IPs. |
| innodb_file_per_table         | ON          | Activado para mejorar la administración del almacenamiento de datos por tabla, lo que es útil en entornos con gran cantidad de datos. |
| performance_schema            | OFF         | Desactivado para evitar la sobrecarga en el rendimiento, ya que la empresa prioriza tiempos de respuesta rápidos. |

# Justificación de los valores:
  - innodb_buffer_pool_size: Un tamaño más grande es esencial para manejar la alta carga de usuarios simultáneos y mantener datos en memoria, lo que mejora el rendimiento de las consultas.
  - innodb_log_file_size: Un mayor tamaño del archivo de log permite manejar mejor las transacciones concurrentes sin impactar el rendimiento.
  - max_connections: Se incrementa sustancialmente para permitir que miles de usuarios accedan simultáneamente sin problemas de conexiones limitadas.
  - innodb_flush_log_at_trx_commit: Se establece en 1 para garantizar la integridad de cada transacción, lo cual es crucial en un entorno de comercio electrónico.
  - long_query_time: Se ajusta a 1 segundo, ya que en un entorno con tanta carga, cualquier consulta lenta debe ser identificada y optimizada rápidamente.

Este es un enfoque para maximizar el rendimiento y la seguridad de la base de datos en un entorno con alta concurrencia de usuarios y muchas operaciones de escritura y lectura simultáneas.
