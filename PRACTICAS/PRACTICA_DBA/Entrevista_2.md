
# Configuración de Parámetros MySQL/MariaDB para Data Warehouse People4

Esta tabla muestra los parámetros de configuración, los valores asignados y una breve explicación del porqué se eligieron dichos valores.

| Parámetro                    | Valor       | Explicación                                                                 |
|------------------------------|-------------|-----------------------------------------------------------------------------|
| innodb_buffer_pool_size       | 16G         | Tamaño incrementado para manejar grandes volúmenes de datos y mejorar el rendimiento de consultas intensivas de lectura. |
| innodb_log_file_size          | 256M        | Tamaño suficiente para manejar las pocas escrituras periódicas sin necesidad de un tamaño mayor. |
| max_connections               | 300         | Dado que no se trata de un sistema de acceso masivo simultáneo, este valor permite una concurrencia moderada. |
| query_cache_size              | 256M        | La cache se incrementa para mejorar la eficiencia de consultas repetidas en grandes conjuntos de datos históricos. |
| table_open_cache              | 1024        | Aumentado para permitir la apertura eficiente de tablas, especialmente con grandes volúmenes de datos. |
| tmp_table_size                | 512M        | Un tamaño mayor para evitar que las tablas temporales se escriban en disco durante consultas complejas. |
| max_heap_table_size           | 512M        | Ajustado igual que `tmp_table_size` para optimizar las consultas que usan tablas en memoria. |
| innodb_flush_log_at_trx_commit| 2           | Las escrituras periódicas permiten desactivar el commit en cada transacción, mejorando el rendimiento sin sacrificar integridad. |
| log_bin                       | OFF         | Desactivado ya que no se necesita replicación o recuperación detallada debido a la naturaleza de las escrituras periódicas. |
| slow_query_log                | ON          | Activado para detectar y optimizar consultas que tarden en completarse en grandes volúmenes de datos. |
| slow_query_log_file           | /var/log/mysql/slow.log | Archivo donde se almacenan las consultas lentas para su análisis posterior. |
| long_query_time               | 5           | Ajustado a 5 segundos debido a la naturaleza de las consultas complejas, que pueden tomar más tiempo. |
| bind-address                  | 0.0.0.0     | Configurado para escuchar en todas las interfaces de red, permitiendo acceso desde múltiples puntos de análisis. |
| innodb_file_per_table         | ON          | Activado para un mejor manejo de grandes cantidades de datos por tabla. Facilita la administración del almacenamiento. |
| performance_schema            | OFF         | Desactivado para evitar sobrecarga en el sistema, dado que el enfoque es en lectura intensiva y no requiere análisis en tiempo real. |

# Justificación de los valores:
  - innodb_buffer_pool_size: Se incrementa significativamente para manejar grandes volúmenes de datos históricos en memoria, optimizando las consultas intensivas de lectura.
  - innodb_flush_log_at_trx_commit: El valor 2 permite mejorar el rendimiento de las pocas escrituras que se realizan, ya que no es necesario asegurar la integridad de cada transacción de manera inmediata.
  - query_cache_size: Aumentado para almacenar resultados de consultas repetidas, lo que es ideal en un entorno de análisis con grandes conjuntos de datos.
  - log_bin: Desactivado debido a que la replicación no es crítica en este caso, ya que las escrituras no son frecuentes ni requieren seguimiento detallado.

