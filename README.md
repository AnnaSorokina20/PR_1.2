# Практична робот № 1.2
## Розв’язання задачі лінійного програмування за допомогою модифікованих жорданових виключень

### ПОСТАНОВКА ЗАВДАННЯ

Під час виконання практичної роботи необхідно розробити програму, за допомогою якої на основі модифікованих жорданових виключень (МЖВ) можна реалізувати такі дії:
-	пошук опорного розв’язку задачі лінійного програмування;
-	пошук оптимального розв’язку задачі лінійного програмування.

**Варіант 20**

Задача лінійного програмування для варіанту 20:<br>

Z = 3x1 – x3 + x5 → min<br>
при обмеженнях:<br>
– x1 + 3x3 – 2x4 + x5 <= 3;<br>
x1 – x2 + x4 + x5 >= 3;<br>
x1 + 3x2 – x3 – x4 + x5 <=2;<br>
xj >= 0, j = 1, 5<br>

### ВИКОНАННЯ РОБОТИ

#### Опис програми

На мові програмування C# розроблено консольний додаток, який реалізує розв’язання задачі лінійного програмування з обмеженнями у вигляді нерівностей. Для пошуку опорного та оптимального розв’язків використовується симплекс-метод із модифікованими жордановими виключеннями. Програма підтримує задачі на максимум та мінімум, автоматично визначаючи тип задачі за введеною функцією мети. Усі проміжні обчислення відображаються у вигляді симплекс-таблиць у вікні консолі.

Вхідні дані
-	objectiveFunction – рядок символьного типу (тип string), що містить функцію мети, наприклад: «2x1 + 3x2 - x3 -> max».
-	constraints – список рядків (тип List<string>), кожен з яких представляє обмеження у форматі нерівності, наприклад: «x1 + 2x2 - x3 <= 5».
-	variableCount – ціле число (тип int), що визначає кількість змінних у задачі.
-	isMinimization – логічна змінна (тип bool), яка визначається автоматично під час розбору функції мети (true – для задачі на мінімум, false – на максимум).

Вихідні дані
-	simplexTable – двовимірний масив об’єктів (тип object[,]), який представляє симплекс-таблицю з поточними значеннями коефіцієнтів і базисних змінних.
-	X – масив дійсного типу (double[]), що містить значення змінних оптимального розв’язку задачі.
-	Z – дійсне число (тип double), що представляє значення цільової функції у точці оптимуму.
-	intermediateSteps – симплекс-таблиці, які виводяться у консоль на кожному кроці обчислень для демонстрації проміжних результатів.
-	messages – текстові повідомлення, що описують статус обчислення: знайдено опорний розв’язок, оптимальний розв’язок, попередження про необмеженість функції тощо.

#### Екранні форми роботи програми
На основі задачі лінійного програмування для варіанту 20 було проведено тестування програми, протоколи проміжних обчислень та їх результат зображено на рисунку 1.

![image](https://github.com/user-attachments/assets/768e9c68-cdd1-40ab-adcf-bf6d6a7d849d)<br>
Рисунок 1 – Тестування програми на задачі для варіанту 20

Також програма була перевірена на тестових прикладах. Тестовий приклад 1 наведено на рисунку 2. Результат тестування програми наведено на рисунку 3.

![image](https://github.com/user-attachments/assets/5cc25538-9291-465b-8146-8b50c2a71b50)<br>
Рисунок 2 – Тестовий приклад 1

 ![image](https://github.com/user-attachments/assets/f84ff6e7-fc46-4808-b5b5-97cc384ee278)<br>
Рисунок 3 – Тестування на прикладі 1

Тестовий приклад 2 наведено на рисунку 4. . Результат тестування програми наведено на рисунку 5.

 ![image](https://github.com/user-attachments/assets/efd54387-4287-42a6-aac6-ad9c9ff3837b)<br>
Рисунок 4 – Тестовий приклад 2

 ![image](https://github.com/user-attachments/assets/4f921972-6a35-4696-9086-8d88f4823827)<br>
Рисунок 5 – Тестування на прикладі 2

### ВИСНОВОК
У ході виконання практичної роботи було розроблено консольний застосунок мовою програмування C#, який реалізує розв’язання задачі лінійного програмування симплекс-методом. Програма підтримує два режими роботи: знаходження максимуму та мінімуму цільової функції. Для задачі мінімізації використовується перетворення у задачу на максимум, що забезпечує універсальність алгоритму.<br>
Програма підтримує інтерактивне введення вихідних даних, виводить проміжні симплекс-таблиці та фінальний оптимальний розв’язок, що дозволяє наочно простежити хід обчислень.<br>
Отриманий результат підтверджує правильність реалізованого алгоритму та дозволяє застосовувати програму для практичного розв’язання задач лінійного програмування.
