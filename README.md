Ф.И.О, № группы
Старовойтов Артём, группа ИС22-9/1

## Описание Базы Данных
База данных создана для хранения информации о студентах и курсах. Основные таблицы: `students`, `courses`, `student_courses`.

### Таблицы и их атрибуты

#### Таблица `students`
| Поле         | Тип         | Описание                        |
|--------------|-------------|---------------------------------|
| `student_id` | SERIAL      | Уникальный идентификатор студента |
| `first_name` | VARCHAR(50) | Имя студента                    |
| `last_name`  | VARCHAR(50) | Фамилия студента                |
| `group_number`| VARCHAR(10)| Номер группы студента           |

#### Таблица `courses`
| Поле         | Тип         | Описание                        |
|--------------|-------------|---------------------------------|
| `course_id`  | SERIAL      | Уникальный идентификатор курса  |
| `course_name`| VARCHAR(100)| Название курса                  |
| `description`| TEXT        | Описание курса                  |

#### Таблица `student_courses`
| Поле         | Тип         | Описание                        |
|--------------|-------------|---------------------------------|
| `student_id` | INT         | Идентификатор студента (внешний ключ к `students.student_id`) |
| `course_id`  | INT         | Идентификатор курса (внешний ключ к `courses.course_id`)    |
| PRIMARY KEY (`student_id`, `course_id`) | - | Первичный ключ, комбинирующий `student_id` и `course_id` |
| FOREIGN KEY (`student_id`) REFERENCES `students`(`student_id`) | - | Внешний ключ на таблицу `students` |
| FOREIGN KEY (`course_id`) REFERENCES `courses`(`course_id`)    | - | Внешний ключ на таблицу `courses`  |

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
