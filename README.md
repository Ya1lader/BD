Ф.И.О, № группы
Старовойтов Артём, группа ИС22-9/1

## Описание Базы Данных
База данных создана для хранения информации о студентах и курсах. Основные таблицы: `students`, `courses`, `student_courses`.

### Таблицы и их атрибуты

#### Таблица `students`
- `student_id`: SERIAL, PRIMARY KEY
- `first_name`: VARCHAR(50), NOT NULL
- `last_name`: VARCHAR(50), NOT NULL
- `group_number`: VARCHAR(10), NOT NULL

#### Таблица `courses`
- `course_id`: SERIAL, PRIMARY KEY
- `course_name`: VARCHAR(100), NOT NULL
- `description`: TEXT

#### Таблица `student_courses`
- `student_id`: INT, NOT NULL
- `course_id`: INT, NOT NULL
- PRIMARY KEY (student_id, course_id)
- FOREIGN KEY (student_id) REFERENCES `students`(student_id)
- FOREIGN KEY (course_id) REFERENCES `courses`(course_id)


Демонстрация запросов
#### 1. UNION
![](/image/1.png)
Описание: Результирующая таблица включает имена студентов и названия курсов.

#### 2. ORDER BY
![](/image/2.png)
Описание: Таблица отсортирована по фамилии студентов.

#### 3. HAVING
![](/image/3.png)
Описание: Таблица групп с количеством студентов более одного.

#### 4. Вложенный запрос
4.1. SELECT
![](/image/4.png)
Описание: Результат запроса включает имена студентов и названия их курсов.

4.2. WHERE
![](/image/5.png)
Описание: Таблица студентов, которые зарегистрированы на курс с ID 1.

#### 5. Оконные функции
5.1. Агрегатные функции
![](/image/6.png)
Описание: Количество студентов в каждой группе.

5.2. Ранжирующие функции
![](/image/7.png)
Описание: Ранжирование студентов по фамилии.

5.3. Функции смещения
![](/image/8.png)
Описание: Предыдущий студент в отсортированном списке по фамилии.

#### 6. Работа join'ов
INNER JOIN
![](/image/9.png)
LEFT JOIN
![](/image/10.png)
RIGHT JOIN
![](/image/11.png)
FULL OUTER JOIN
![](/image/12.png)
Описание: Информация о студентах и их курсах.

#### 7. CASE
![](/image/13.png)
Описание: Присвоение меток группам студентов.

#### 8. WITH
![](/image/14.png)
Описание: Использование временной таблицы для подсчета количества студентов в группах.
