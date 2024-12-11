ru text

## На связи домашнее задание к уроку Spring и Mockito.


В текущем домашнем задании мы вновь вернемся к работе над книгой сотрудников, которую разрабатывали в ходе 1-го курса и к которой возвращались в 1-м задании. Задача данного домашнего задания — покрыть проект (его сервисы) максимальным количеством тестов.
Напишите новый контроллер DepartmentController, который будет получать информацию по департаментам. Контроллер должен делегировать задачи сервису DepartmentService.


Запросы, которые должен реализовывать контроллер:


•	 GET http://localhost:8090/department/{id}/employees — возвращает список сотрудников по департаменту.


•	 GET http://localhost:8090/department/{id}/salary/sum  — возвращает сумму зарплат по департаменту.


•	 GET http://localhost:8090/department/{id}/salary/max — возвращает максимальную зарплату по департаменту.


•	 GET http://localhost:8090/department/{id}/salary/min — возвращает минимальную зарплату по департаменту.


•	 GET http://localhost:8090/department/employees  — возвращает сотрудников, сгруппированых по отделам в виде Map<Integer,List<Employees>>, где ключ — это номер отдела, а значение — список сотрудников данного отдела.


Подсказка:


Для того чтобы реализовать прием параметра id в контроллере, нужно использовать аннотацию @PathVariable из Spring Web.
Контроллер только принимает запросы и возвращает результаты. Самим вычислением занимается сервис DepartmentService, который берет всех сотрудников, используя EmployeeService, и производит необходимые операции.
В итоге реализуемые вами проекты имеют два сервиса. Подход в каждом из них будет немного отличаться.


•	 EmployeeService не имеет зависимостей, поэтому должен быть покрыт с помощью JUnit.


•	 DepartmentService имеет зависимость на EmployeeService, поэтому потребуется еще и Mockito.


### Шаг 1 

Необходимо покрыть тестами все операции по работе с сотрудниками из EmployeeService (добавление, удаление, поиск).
Нужно покрыть максимальное количество ситуаций, например добавление сотрудника, который уже есть в коллекции, или удаление сотрудника, которого нет.


### Шаг 2 

Необходимо покрыть тестами все операции по работе с отделами из DepartmentService.
Нужно «замокать» EmployeeService, который возвращает список сотрудников, а уже затем покрыть все методы сервиса тестами с максимальным количеством придуманных ситуаций. Например, когда переданный отдел отсутствует или вообще не передан пользователем.


### Критерии оценки
Работа будет оценена по следующим критериям:


• Реализован эндпойнт GET http://localhost:8090/department/{id}/employees.


• Реализован эндпойнт GET по адресу: http://localhost:8090/department/{id}/salary/sum.


• Реализован эндпойнт GET по адресу: http://localhost:8090/department/{id}/salary/max.


• Реализован эндпойнт GET по адресу: http://localhost:8090/department/{id}/salary/min.


• Реализован эндпойнт GET по адресу: http://localhost:8090/department/employees.


• Эндпойнт GET по адресу http://localhost:8090/department/{id}/employees возвращает список сотрудников в департаменте.


• Эндпойнт GET http://localhost:8090/department/{id}/salary/sum возвращает сумму зарплат по департаменту.


• Эндпойнт GET по адресу http://localhost:8090/department/{id}/salary/max возвращает максимальную зарплату по департаменту.


• Эндпойнт GET по адресу http://localhost:8090/department/{id}/salary/min возвращает минимальную зарплату по департаменту.


• Эндпойнт GET по адресу http://localhost:8090/department/employees возвращает сотрудников, сгруппированных по отделам.


• В папке test создан package с тестовыми классами.


• Код полностью покрыт тестами.


• Все тесты проходят успешно.


• Корректно применены инструменты библиотеки Mockito.


• Соблюден паттерн MVC.


• Созданы пакеты model, service, controller.


• В контроллере есть только метод вызова сервиса и нет лишней логики.


• Соблюдена инкапсуляция.


• Название метода начинается с глагола и описывает действия метода. Применяется принцип camelCase.


• Код компилируется, и каждое действие расположено на отдельной строке.


• Использовано автоматическое форматирование кода.


• В репозитории нет лишних файлов.


• Переданная ссылка — это pull request.


• Отсутствуют лишние блоки и переменные.


• Имена классов начинаются с большой буквы.


• Нет двойной вложенности.


• Соблюдена конвенциональная структура класса: поля, конструкторы и методы.


• Полям присвоены имена, которые отражают их суть.


• Все классы находятся в отдельном файле.


• Классы корректно распределены по пакетам.


• Отсутствуют лишние нефункциональные комментарии.


• Отсутствуют методы, оперирующие с raw type.


• Повторяющийся хардкод вынесен в константы.


• Отсутствуют методы, чья логика может вернуть null.



eng text


## The homework for the Spring and Mockito lesson is in touch.


In the current homework assignment, we will return to work on the staff book, which we developed during the 1st course and returned to in the 1st task. The task of this homework assignment is to cover the project (its services) the maximum number of tests.
Write a new DepartmentController that will receive information on departments. The controller must delegate tasks to the DepartmentService service.


Requests that the controller should implement:


• GET http://localhost:8090/department/{id}/employees — returns a list of employees by department.


• GET http://localhost:8090/department/{id}/salary/sum — returns the amount of salaries for the department.


• GET http://localhost:8090/department/{id}/salary/max — returns the maximum salary for the department.


• GET http://localhost:8090/department/{id}/salary/min — returns the minimum salary for the department.


• GET http://localhost:8090/department/employees — returns employees grouped by departments in the form of Map<Integer,List<Employees>>, where the key is the department number and the value is the list of employees of this department.


Hint:


In order to implement the reception of the id parameter in the controller, you need to use the @PathVariable annotation from the Spring Web.
The controller only accepts requests and returns results. The Department Service is engaged in the calculation itself, which takes all employees using EmployeeService and performs the necessary operations.
As a result, the projects you are implementing have two services. The approach in each of them will be slightly different.


• EmployeeService has no dependencies, so it should be covered with JUnit.


• DepartmentService has a dependency on EmployeeService, so you will also need Mockito.


### Step 1 

It is necessary to cover all operations related to working with employees from EmployeeService (adding, deleting, searching) with tests.
You need to cover the maximum number of situations, for example, adding an employee who already exists in the collection, or deleting an employee who does not exist.


### Step 2 

It is necessary to cover all operations related to working with departments from DepartmentService with tests.
You need to "lock up" the EmployeeService, which returns a list of employees, and only then cover all the methods of the service with tests with the maximum number of invented situations. For example, when the transferred department is missing or not transferred at all by the user.


### Evaluation criteria
The work will be evaluated according to the following criteria:


• The GET endpoint is implemented http://localhost:8090/department /{id}/employees.


• The GET endpoint is implemented at: http://localhost:8090/department /{id}/salary/sum.


• The GET endpoint is implemented at: http://localhost:8090/department /{id}/salary/max.


• The GET endpoint is implemented at: http://localhost:8090/department /{id}/salary/min.


• The GET endpoint is implemented at: http://localhost:8090/department/employees .


• GET endpoint at http://localhost:8090/department/{id}/employees returns a list of employees in the department.


• GET Endpoint http://localhost:8090/department/{id}/salary/sum returns the amount of salaries for the department.


• GET endpoint at http://localhost:8090/department/{id}/salary/max returns the maximum salary for the department.


• GET endpoint at http://localhost:8090/department/{id}/salary/min returns the minimum salary for the department.


• GET endpoint at http://localhost:8090/department/employees returns employees grouped by department.


• A package with test classes has been created in the test folder.


• The code is completely covered by tests.


• All tests are successful.


• Mockito library tools have been applied correctly.


• The MVC pattern is followed.


• Model, service, and controller packages have been created.


• The controller only has a method for calling the service and there is no unnecessary logic.


• Encapsulation is observed.


• The name of the method begins with a verb and describes the actions of the method. The camelCase principle applies.


• The code is compiled, and each action is located on a separate line.


• Automatic code formatting is used.


• There are no unnecessary files in the repository.


• The passed link is a pull request.


• There are no extra blocks and variables.


• Class names start with a capital letter.


• There is no double nesting.


• The conventional class structure has been observed: fields, constructors, and methods.


• The fields are given names that reflect their essence.


• All classes are in a separate file.


• Classes are correctly distributed in packages.


• There are no unnecessary non-functional comments.


• There are no methods that operate with raw type.


• The repetitive hardcore code is rendered into constants.


• There are no methods whose logic can return null.
