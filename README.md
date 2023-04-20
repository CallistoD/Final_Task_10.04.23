# Задание
> Процессы выполнения команд предоставлены в папке **Tasks**.

1. Используя команду cat в терминале операционной системы Linux, создать
два файла Домашние животные (заполнив файл собаками, кошками,
хомяками) и Вьючные животными заполнив файл Лошадьми, верблюдами и
ослы), а затем объединить их. Просмотреть содержимое созданного файла.
Переименовать файл, дав ему новое имя (Друзья человека).

[Task - 1](https://github.com/CallistoD/Final_Task_10.04.23/blob/main/Tasks/Task%20-%201.jpg)
        
        1. ls -l
        2. cat > pets
        3. cat pets
        4. cat > work-animals
        5. cat work-animals
        6. ls -l
        7. cat pets work-animals > human-friends
        8. ls -l
        9. cat human-friends

2. Создать директорию, переместить файл туда.

[Task - 2](https://github.com/CallistoD/Final_Task_10.04.23/blob/main/Tasks/Task%20-%202.jpg)
        
        1. mkdir 
        2. mv human-friends animals

3. Подключить дополнительный репозиторий MySQL. Установить любой пакет
из этого репозитория.

[Task - 3](https://github.com/CallistoD/Final_Task_10.04.23/blob/main/Tasks/Task%20-%203.jpg)

        1. sudo apt-get update
        
        2. sudo apt-get install \
    	 		ca-certificates \
    			 curl \
    	 		gnupg \
    	 		lsb-release
 	
        3. sudo mkdir -p /etc/apt/keyrings
 	
        4. curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg 
        
        5. echo \
                "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
  	        $(lsb_release -cs) stable" | sudo tee /eshowtc/apt/sources.list.d/docker.list > /dev/null
        
        6. sudo apt-get update


4. Установить и удалить deb-пакет с помощью dpkg.
> Скачал .deb пакет браузер Opera
   
   [Task - 4](https://github.com/CallistoD/Final_Task_10.04.23/blob/main/Tasks/Task-4.jpg)
   
        1. sudo dpkg -i opera-stable_97.0.4719.63_amd64.deb 
                : Проверил, что установился пакет [Task/Task-4 и Task-4.1]
        2. sudo dpkg -r opera-stable


5. Выложить историю команд в терминале ubuntu

[Task - 5](https://github.com/CallistoD/Final_Task_10.04.23/blob/main/Tasks/Task-5.jpg)

        1  history
        2  history -w
        3  Lucy124124124
        4  cat docker.list
        5  cd /etc/apt/sources.list.d
        6  cat docker.list
        7  cd ~
        8  ls -l
        9  cd snap
        10  ls -l
        11  cd /home
        12  ls- l
        13  ls -l
        14  cd apolon
        15  ls -l
        16  dpkg -l
        17  dpkg -i bluez
        18  cd /Download
        19  cd Downloads/
        20  ls -l
         21  cd Загрузки/
        22  ls -l
        23  sudo dpkg
        24  sudo dpkg -i google-chrome-stable_current_amd64.deb
        25  ls -l
        26  sudo dpkg -i opera-stable_97.0.4719.63_amd64.deb
        27  dpkg -r opera-stable_97.0.4719.63_amd64.deb
        28  sudo dpkg -r opera-stable_97.0.4719.63_amd64.deb
        29  dpkg --help
        30  sudo apt remove opera-stable
        31  sudo apt autoremove
        32  history 
        33  sudo dpkg -r opera-stable
        34  history

6. Нарисовать диаграмму, в которой есть класс родительский класс, домашние
животные и вьючные животные, в составы которых в случае домашних
животных войдут классы: собаки, кошки, хомяки, а в класс вьючные животные
войдут: Лошади, верблюды и ослы).

[Task - 6](https://github.com/CallistoD/Final_Task_10.04.23/blob/main/Tasks/Task-6.jpg)

![](https://raw.githubusercontent.com/CallistoD/Final_Task_10.04.23/main/Tasks/Task-6.jpg)

7. В подключенном MySQL репозитории создать базу данных “Друзья
человека”

[Task - 7](https://github.com/CallistoD/Final_Task_10.04.23/blob/main/Tasks/Task-7.jpg)

        DROP DATABASE IF EXISTS human_friends; 
        CREATE DATABASE human_friends; 
        USE human_friends;
        
8. Создать таблицы с иерархией из диаграммы в БД
        
           -->  Pets  <--                            -->  Work animals  <--
        CREATE TABLE cats(                           CREATE TABLE horses(
                name VARCHAR(45),                       name VARCHAR(45),
                command VARCHAR(45),                    command VARCHAR(45),
                birthday DATE                           birthday DATE
                );                                      );
                
        CREATE TABLE dogs(                           CREATE TABLE camels(
                name VARCHAR(45),                       name VARCHAR(45),
                command VARCHAR(45),                    command VARCHAR(45),
                birthday DATE                           birthday DATE
                );                                      );
                
        CREATE TABLE humsters(                       CREATE TABLE donkey(
                name VARCHAR(45),                       name VARCHAR(45),
                command VARCHAR(45),                    command VARCHAR(45),
                birthday DATE                           birthday DATE
                );                                      );
                
9. Заполнить низкоуровневые таблицы именами(животных), командами
которые они выполняют и датами рождения
 
                -->  Pets  <--                                                  -->  Work animals  <--
        INSERT INTO cats(name, command, birthday)                       INSERT INTO horses(name, command, birthday)
        VALUES                                                          VALUES
        ('Apolon', 'sleep', '2021-03-13'),                              ('Huch', 'sit', '2021-09-09'),
        ('Slivki', 'sit', '2023-01-01'),                                ('Puk', 'sleep', '2023-02-09'),
        ('Leto', 'run', '2000-08-13'),                                  ('Smouk', 'jump', '2018-12-12'),
        ('Ani', 'jump', '2015-12-15'),                                  ('Juli', 'jump', '2015-05-05'),
        ('Bella', 'spin', '2003-03-03');                                ('Poppy', 'run', '2003-01-01');
        
        INSERT INTO dogs(name, command, birthday)                       INSERT INTO camels(name, command, birthday)
        VALUES                                                          VALUES
        ('Selena', 'sit', '2021-12-21'),                                ('Golivud', 'voice', '2021-03-13'),
        ('Matilda', 'voic', '2023-03-03'),                              ('Persik', 'sleep', '2022-11-11'),
        ('Asterisk', 'run', '2000-10-09'),                              ('Miki', 'fly', '2022-11-11'),
        ('Umi', 'grab', '2015-11-11'),                                  ('Molli', 'sit', '2022-11-11'),
        ('Kratos', 'fly', '2003-09-19');                                ('Sue', 'run', '2003-02-13');

        INSERT INTO humsters(name, command, birthday)                   INSERT INTO donkey(name, command, birthday)
        VALUES                                                          VALUES
        ('Bubble', 'jump', '2021-06-06'),                               ('Ishak', 'voic', '2021-11-11'),
        ('Jam', 'sit', '2022-11-11'),                                   ('Campot', 'run', '2022-09-09'),
        ('Bond', 'run', '2018-03-03'),                                  ('Sharki', 'sit', '2018-07-27'),
        ('Vais', 'fly', '2015-09-09'),                                  ('Shrek', 'sleep', '2015-12-21'),
        ('Kuksi', 'jump', '2003-02-13');                                ('Bobby', 'fly', '2003-04-04');

10. Удалив из таблицы верблюдов, т.к. верблюдов решили перевезти в другой
питомник на зимовку. Объединить таблицы лошади, и ослы в одну таблицу.

[Task - 10](https://github.com/CallistoD/Final_Task_10.04.23/blob/main/Tasks/Task-10.jpg)

        TRUNCATE TABLE Верблюды;
        
        SELECT name, command, birthday FROM horses
        UNION
        SELECT name, command, birthday FROM donkey; 

11. Создать новую таблицу “молодые животные” в которую попадут все
животные старше 1 года, но младше 3 лет и в отдельном столбце с точностью
до месяца подсчитать возраст животных в новой таблице

        CREATE TABLE `Young animals`
        
        SELECT name, command, birthday, 
        (YEAR(CURRENT_DATE)-YEAR(birthday)) - (RIGHT(CURRENT_DATE,5)<RIGHT(birthday,5)) AS Age 
        FROM dogs  
        WHERE (YEAR(CURRENT_DATE)-YEAR(birthday)) - (RIGHT(CURRENT_DATE,5)<RIGHT(birthday,5)) < 3 
        AND (YEAR(CURRENT_DATE)-YEAR(birthday)) - (RIGHT(CURRENT_DATE,5)<RIGHT(birthday,5)) > 1
        UNION
        SELECT name, command, birthday, 
        (YEAR(CURRENT_DATE)-YEAR(birthday)) - (RIGHT(CURRENT_DATE,5)<RIGHT(birthday,5)) AS Age
        FROM cats
        WHERE (YEAR(CURRENT_DATE)-YEAR(birthday)) - (RIGHT(CURRENT_DATE,5)<RIGHT(birthday,5)) < 3 
        AND (YEAR(CURRENT_DATE)-YEAR(birthday)) - (RIGHT(CURRENT_DATE,5)<RIGHT(birthday,5)) > 1
        UNION
        SELECT name, command, birthday, 
        (YEAR(CURRENT_DATE)-YEAR(birthday)) - (RIGHT(CURRENT_DATE,5)<RIGHT(birthday,5)) AS Age
        FROM humsters
        WHERE (YEAR(CURRENT_DATE)-YEAR(birthday)) - (RIGHT(CURRENT_DATE,5)<RIGHT(birthday,5)) < 3 
        AND (YEAR(CURRENT_DATE)-YEAR(birthday)) - (RIGHT(CURRENT_DATE,5)<RIGHT(birthday,5)) > 1
        UNION
        SELECT name, command, birthday, 
        (YEAR(CURRENT_DATE)-YEAR(birthday)) - (RIGHT(CURRENT_DATE,5)<RIGHT(birthday,5)) AS Age
        FROM horses
        WHERE (YEAR(CURRENT_DATE)-YEAR(birthday)) - (RIGHT(CURRENT_DATE,5)<RIGHT(birthday,5)) < 3 
        AND (YEAR(CURRENT_DATE)-YEAR(birthday)) - (RIGHT(CURRENT_DATE,5)<RIGHT(birthday,5)) > 1
        UNION
        SELECT name, command, birthday, 
        (YEAR(CURRENT_DATE)-YEAR(birthday)) - (RIGHT(CURRENT_DATE,5)<RIGHT(birthday,5)) AS Age
        FROM camels
        WHERE (YEAR(CURRENT_DATE)-YEAR(birthday)) - (RIGHT(CURRENT_DATE,5)<RIGHT(birthday,5)) < 3 
        AND (YEAR(CURRENT_DATE)-YEAR(birthday)) - (RIGHT(CURRENT_DATE,5)<RIGHT(birthday,5)) > 1
        UNION
        SELECT name, command, birthday, 
        (YEAR(CURRENT_DATE)-YEAR(birthday)) - (RIGHT(CURRENT_DATE,5)<RIGHT(birthday,5)) AS Age
        FROM donkey
        WHERE (YEAR(CURRENT_DATE)-YEAR(birthday)) - (RIGHT(CURRENT_DATE,5)<RIGHT(birthday,5)) < 3 
        AND (YEAR(CURRENT_DATE)-YEAR(birthday)) - (RIGHT(CURRENT_DATE,5)<RIGHT(birthday,5)) > 1;

        ALTER TABLE `Young animals` ADD COLUMN Age_full VARCHAR (30);
        UPDATE `Young animals` SET Age_full = (CONCAT(TIMESTAMPDIFF(YEAR, birthday, CURRENT_DATE),' year ', 
        TIMESTAMPDIFF(MONTH, birthday, CURRENT_DATE) % 12, ' month '));

12. Объединить все таблицы в одну, при этом сохраняя поля, указывающие на
прошлую принадлежность к старым таблицам.
        
        SELECT name, command, birthday FROM cats
        UNION
        SELECT name, command, birthday FROM dogs
        UNION
        SELECT name, command, birthday FROM humsters
        UNION
        SELECT name, command, birthday FROM horses
        UNION
        SELECT name, command, birthday FROM donkey;
        
13. Создать класс с Инкапсуляцией методов и наследованием по диаграмме.

14. Написать программу, имитирующую работу реестра домашних животных.
В программе должен быть реализован следующий функционал:
* 14.1 Завести новое животное
* 14.2 определять животное в правильный класс
* 14.3 увидеть список команд, которое выполняет животное
* 14.4 обучить животное новым командам
* 14.5 Реализовать навигацию по меню

15. Создайте класс Счетчик, у которого есть метод add(), увеличивающий̆
значение внутренней̆ int переменной̆ на 1 при нажатии “Завести новое
животное” Сделайте так, чтобы с объектом такого типа можно было работать в
блоке try-with-resources. Нужно бросить исключение, если работа с объектом
типа счетчик была не в ресурсном try и/или ресурс остался открыт. Значение
считать в ресурсе try, если при заведении животного заполнены все поля.
