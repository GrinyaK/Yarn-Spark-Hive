# Yarn-Spark-Hive
# YARN  
YARN (Yet Another Resource Negotiator) — это компонент из экосистемы Hadoop, отвечающий за управление ресурсами в кластерной архитектуре.  

- Главная роль:
  - Управляет распределением ресурсов (CPU, память) между различными приложениями в кластере Hadoop.
  - Поддерживает выполнение задач на нескольких узлах кластера одновременно.
  
- Как работает:
  - Resource Manager: Центральный компонент, который управляет доступными ресурсами кластера.
  - Node Managers: Контролируют ресурсы отдельных узлов.
  - Работает с различными фреймворками (например, MapReduce или Spark).
  
- Пригоден для:  
  - Распределенных вычислений и обеспечения эффективного использования ресурсов.
# Hive  
Hive — это хранилище данных (Data Warehouse) поверх Hadoop, которое позволяет писать SQL-запросы к данным в HDFS.  

- Главная роль:  
  - Позволяет аналитикам и разработчикам использовать SQL-подобный язык (HiveQL) для работы с большими данными без необходимости писать код MapReduce.
  
- Ключевые особенности:
  - Поддерживает обработку структурированных данных, хранящихся в HDFS.
  - Включает функции создания таблиц, работы с данными, их анализа и агрегации.
  - Может быть интегрирован со сторонними инструментами BI.
- Пригоден для:  
  - Запросов к огромным объемам данных с использованием SQL.
Как говорилось ранее Hive позволяет писать SQL-подобные запросы для работы с данными в HDFS (Hadoop Distributed File System). Это проще, чем писать MapReduce вручную. Вот пример запроса в Hive :
--Создаем таблицу для хранения информации о студентах
-CREATE TABLE IF NOT EXISTS students (
    -id INT,
    -name STRING,
    -age INT,
    -grade STRING
-)
-ROW FORMAT DELIMITED
-FIELDS TERMINATED BY ','
-STORED AS TEXTFILE;

--Загружаем данные из локального файла в таблицу Hive
-LOAD DATA LOCAL INPATH '/path/to/students.csv' INTO TABLE students;

--Запрос для подсчета количества студентов в каждой категории "grade"
-SELECT grade, COUNT(*) AS students_count
-FROM students
-GROUP BY grade;

# Spark  
Apache Spark — это фреймворк для высокопроизводительных параллельных вычислений, предназначенный для обработки больших данных.

- Главная роль:  
  - Заботится об ускорении обработки данных за счет вычислений в памяти, минимизируя операции с дисками (в сравнении с MapReduce).

- Ключевые особенности:
  - Унифицированная обработка данных: ETL, потоковые данные, машинное обучение, SQL-запросы.
  - Работает быстрее традиционных Hadoop MapReduce.
  - Поддерживает работу как с HDFS, так и с другими источниками данных.
  
- Компоненты Spark:
  - Spark SQL: Для работы с данными через SQL.
  - Spark Streaming: Для обработки потоковых данных в реальном времени.
  - MLlib: Для задач машинного обучения.
  - GraphX: Для графовых вычислений.
- Пригоден для:  
  - Высокоскоростной обработки, потоковой обработки, многосложного анализа в распределенных системах (кластерах).
