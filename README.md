# Курс "Введение в язык Java и платформу разработки" от КРОК

## Содержание:
- [Задание 1 | Введение](#task1)
- [Задание 2 | FizzBuzz](#task2)
- [Задание 3 | Простые числа](#task3)
- [Задание 4 | Сумма арифметической прогрессии](#task4)
- [Задание 5 | Каталог интернет-магазина](#task5)
- [Задание 6 | Аннотирование изображений](#task6)
- [Задание 7 | Заказ из интернет-магазина](#task7)
- [Задание 8 | Создание приложения, проверяющего возможность прохождения последовательности клеток на шахматной доске ходом коня](#task8)
- [Задание 9 | Черный список](#task9)
- [Задание 10 | Черный список 2.0](#task10)
- [Задание 11 | Пиршество](#task11)
- [Задание 12 | Тернарный оператор](#task12)
- [Задание 13 | Аукцион](#task13)
- [Задание 14 | Клиент-серверное приложение](#task14)
- [Задание 15 | Бэкенд для ветеринарной клиники](#task15)
- [Задание 16 | Бэкенд для ветеринарной клиники 2.0](#task16)
- [Контакты](#contacts)

---

## <a id="task1">Задание 1 | Введение</a>

### Условие:
Начнём с простой разминки
Реализуйте программу, которая бы выводила на экран текст ‘Hello, Java ^^’
### [Решение](src/ArturKuznetsov/lab1/task1)

---

## <a id="task2">Задание 2 | FizzBuzz</a>
### Условие:
Напишите короткую программу, которая выводит на экран числа от 1 до 100, каждое в новой строке.
Вместо каждого числа, которое делится на 3, выводите ‘Fizz’.
Вместо каждого числа, которое делится на 5, выводите ‘Buzz’.
Вместо каждого числа, которое делится и на 3, и на 5, выводите ‘FizzBuzz’.
### [Решение](src/ArturKuznetsov/lab1/task2)

---

## <a id="task3">Задание 3 | Простые числа</a>
### Условие:
Напишите программу, которая для заданного числа от 2 до 10^10 (10 000 000 000) проверит является ли это число простым. Вывести на экран “Простое” или “Составное” число.
*  проверить является ли число - числом-близнецом
### [Решение](src/ArturKuznetsov/lab2/task3)

---

## <a id="task4">Задание 4 | Сумма арифметической прогрессии</a>
### Условие:
Написать программу, которая принимает 3 аргумента, и считает сумму арифметической прогрессии.
Аргументы: начальный элемент, разность арифметической прогрессии и кол-во членов прогрессии. Каждое число от -10 000 до +10 000
Решить с помощью использования циклов, а не формулы суммы.
### [Решение](src/ArturKuznetsov/lab2/task4)

---

## <a id="task5">Задание 5 | Каталог интернет-магазина</a>
### Условие:
Поступил заказ на написание интернет магазина для бытовых приборов.
Ваша часть задачи - реализовать классы - отвечающие за ассортимент магазина.
(Такие как холодильник (мини холодильник, с морозильной камерой или без), плита (газовая, электро, индукционная), стиралка (может быть с сушилкой), робот пылесос, и насколько фантазии хватит)

Определите набор характеристик каждого товара. Такие как цена, описание товара, габариты, мощность, время автономной работы от аккумулятора, температура морозильной камеры)

Добавьте позиции с общий массив.
Для всех элементов выведите на экран их характеристики в читаемом виде.
Определите методы для установки/получения характеристик.
Для импортных товаров реализуйте методы возвращающие наличие гарантии от производителя и страну производства.
### [Решение](src/ArturKuznetsov/lab3/task5)

---

## <a id="task6">Задание 6 | Аннотирование изображений</a>
### Условие:
Предположим, вы принимаете участие в разработке небольшого приложения по аннотированию (разметке) изображений с целью последующего использования этой разметки для обучения моделей computer vision. В этом приложении пользователь может выделять области на изображении с помощью прямоугольников и окружностей и подписывать их произвольным текстом.
Вся разметка для изображения представляется массивом `Annotation[]`.

В приложении определен класс аннотированного изображения:

```java
class AnnotatedImage {

   private final String imagePath;

   private final Annotation[] annotations;

   public AnnotatedImage(String imagePath, Annotation... annotations) {
       this.imagePath = imagePath;
       this.annotations = annotations;
   }

   public String getImagePath() {
       return this.imagePath;
   }

   public Annotation[] getAnnotations() {
       return this.annotations;
   }
}
```

Определите класс `Annotation` для представления данных разметки (данные: подпись и фигура) и классы `Figure`,`Rectangle`,`Circle` для задания размеченных областей.

Прямоугольники определяются координатами левого нижнего и правого верхнего углов, а окружности - координатами центра и радиусом.

Переопределите метод `toString()` класса `Annotation` так, чтобы в результат выводилась информация о полях и вложенных объектах. Формат вывода:


Окружность:

“Circle (x0, y0), r: Подпись”

Прямоугольник:

“Rectangle (x1, y1), (x2, y2): Подпись”

Например:
```
Circle (100, 100), 10: Tree
Rectangle (100, 100), (150, 200): Car
```

Так же от пользователей пришел запрос на возможность перемещать уже размеченные области. Для поддержки это функциональности вам требуется реализовать:

1. **Выбор аннотации по координатам точки (x, y);**

В массиве аннотаций требуется найти первую, фигура которой содержит точку с заданными координатами.

```java
Annotation findByPoint(int x, int y) {

// ...

}
```

2. **Выбор аннотации по шаблону подписи;**

В массиве аннотаций требуется найти первую, подпись которой содержит заданную подстроку.

```java
Annotation findByLabel(String label) {

// ...

}
```

Определить, содержит ли строка заданную подстроку, можно с помощью метода contains(CharSequence s) класса String.

3. **Перемещение фигуры выбранной аннотации на смещение (dx, dy);**

В рамках этого изменения вы решили доработать классы фигур таким образом, чтобы они реализовывали интерфейс

```java
public interface Movable {

void move(int dx, int dy);

}
```

Разработайте классы и реализуйте соответствующие методы.
### [Решение](src/ArturKuznetsov/lab3/task6)

---

## <a id="task7">Задание 7 | Заказ из интернет-магазина</a>
### Условие:
В задании 5 вы начали разработку интернет-магазина.

Вашей задачей было реализовать классы, отвечающие за ассортимент магазина.

Увы, команда, которая должна была разработать классы, отвечающие за заказы, провалила задание, так что теперь вам придётся взять эту часть на себя.

Определите набор характеристик класса `Order`. Заказчик (директор магазина) считает важным хранить номер, дату/время поступления, дату/время сборки, дату/время получения и состав заказа, а также ФИО и номер телефона клиента.

Ожидается, что **состав заказа и дата/время его поступления не меняются** с момента его создания.

Заказчик просит формировать номер заказа следующим образом:

*<год - 2 последних цифры><месяц - 2 цифры><день - 2 цифры><часы - 2 цифры><минуты - 2 цифры><секунды - 2 цифры><4 последних цифры номера телефона заказчика>*

То есть, для заказа, созданного 25.10.2023 в 19:50:25 клиентом с номером телефона +79990002545 номер будет **2310251950252545.**

К сожалению, у магазина есть некоторые проблемы с логистикой и площадями для хранения, так что **размер заказа ограничен 75 позициями**.

Другая команда разрабатывает модуль для отправки уведомлений клиентам. Тимлид этой команды связался с вами и обсудил возможность формирования уведомления следующего вида:

> Уважаемый <имя клиента>!
>
> Рады сообщить, что Ваш заказ <номер заказа> готов к выдаче.
>
> Состав заказа:
>
> <список товаров с важными характеристиками, каждый товар в новой строке>
>
> Сумма к оплате: <сумма заказа, 2 знака после запятой>₽
>
> Срок хранения заказа <дата сборки + 2 недели, формат вывода даты 25.10.2023>.
>
> С наилучшими пожеланиями, магазин “Кошки и картошки”

Вы ответили, что всё реализуете в лучшем виде, ведь недавно вы как раз проходили тему форматирования всего и вся, в том числе валют.

Так как время хранения заказа ограничено (2 недели с момента сборки), ещё одна команда разрабатывает модуль, который позволяет клиенту проверить возможность получения заказа.

Архитектор команды просит вас добавить метод, который бы работал по следующей логике:

- если заказ пока не собран, то получение недоступно, метод возвращает **false**,
- если заказ уже собран и срок его хранения пока не вышел, то заказ доступен для получения, метод возвращает **true**,
- если заказ собран, но срок хранения истёк, то метод бросает **исключение**.

Эта же команда разрабатывает рабочую панель для сотрудника зоны выдачи заказов, так что архитектор предложил вам добавить поле со статусом заказа, в качестве набора значений он предлагает использовать следующее перечисление:

```java
public enum OrderStatus {
CREATED,
COLLECTED,
EXPIRED,
CLOSED
}
```

От вас требуются методы, которые позволят:

- заказ “собрать”,
- заказ “выдать”,
- проверить не истёк ли срок хранения заказа и, если истёк, установит ему соответствующий статус.

Архитектор обещает, что напишет джобу по расписанию, которая будет проходиться по всем актуальным заказам в базе и опрашивать их на истечение сроков хранения, используя ваш метод.

**Чтобы смежные команды могли приступить к разработке как можно скорее, они просят вас предоставить им соответствующие интерфейсы.**
### [Решение](src/ArturKuznetsov/lab4/task7)

---

## <a id="task8">Задание 8 | Создание приложения, проверяющего возможность прохождения последовательности клеток на шахматной доске ходом коня</a>
### Условие:
Определить класс, описывающий позицию на шахматной доске 8x8.

Данные класса: компоненты x и y, отсчитываемые от левого нижнего угла (x = 0, y = 0 - левая нижняя клетка).

Все методы, позволяющие установить координаты, в том числе и конструкторы, должны проверять корректность аргументов и генерировать IllegalPositionException (необходимо определить это исключение самостоятельно) в случае ошибочных значений.

Переопределить метод toString(), выводящий координаты позиции в формате
<номер колонки в виде буквы от 'a' до 'h'><номер строки, начиная с 1>.
Например, позиция с координатами (1, 1) имеет строковое представление "b2".

Реализовать "фабричный метод" конструирования объекта позиции из строкового представления ("b2" -> объект):

```java
static ChessPosition parse(String position) {

// ...

}
```

В виде массива строк задана некоторая последовательность позиций на шахматной доске 8x8. Например, "b1", "a3", "c4", "d6".

Реализовать метод, проверяющий, что последовательность может быть пройдена фигурой конь в соответствии с правилами хода этой фигуры (буквой "Г"). На вход метод принимает массив объектов класса, определенных в текущей задаче.
Определить новый класс IllegalMoveException обрабатываемого исключения, которое генерируется методом проверки в случае ошибки.

Класс должен содержать информацию о неправильном ходе: из какой в какую позиции ход запрещен. При вызове метода проверки это исключение должно обрабатываться, а неправильный ход выводиться на экран. Последовательность ходов для проверки задается в аргументах командной строки программы.

```java
public class IllegalMoveException extends Exception {

// ...

}
```

Тестовые примеры

[in] "g8", "e7", "e6"

[out] "конь так не ходит: e7 -> e6"

[in] "g8", "e7", "c8"

[out] "OK"
### [Решение](https://github.com/I-am-DaKoTa/ws2023spb-knightsmove)

---

## <a id="task9">Задание 9 | Черный список</a>
### Условие:
Небольшой стартап разрабатывает социальный сервис, в котором пользователи могут оставлять комментарии. Со временем в комментариях появился спам и разработчики решили бороться с ним с помощью "черных списков" запрещенных слов. Они составили такие списки и поручили вам написать функцию, удаляющую из всех накопленных комментариев нежелательные.

Они предоставили вам интерфейс, который внедрили в свой продукт, и попросили написать его реализацию:

```java
import java.util.List;
import java.util.Set;

public interface BlackListFilter {

/**
* From the given list of comments removes ones
* that contain words from the black list.
*
* @param comments list of comments; every comment
*                 is a sequence of words, separated
*                 by spaces, punctuation or line breaks
* @param blackList list of words that should not
*                  be present in a comment
*/

void filterComments(List<String> comments, Set<String> blackList);

}
```

Реализуйте интерфейс BlackListFilter.

В методе main покажите вариант использования вашего фильтра.

Задача со *:

Доп сложности:

1. Надо не удалить комментарий, а заменить грязные слова на звёздочки.
2. Если слово написано с одной опечаткой - его также замаскировать
### [Решение](src/ArturKuznetsov/lab5/task9)
## <a id="task10">Задание 10 | Черный список 2.0</a>
### Условие:
Вы реализовали фильтрацию комментариев по “черному списку” слов (задача 12) и с чистой совестью ушли в отпуск на 3 недели.

По возвращении из отпуска вы обнаружили, что логика фильтрации усложнилась. Также выяснилось, что нет единого способа представления комментариев среди сервисов: где-то они представлены строками, где-то объектами специализированных классов. Вдобавок некоторым сервисам оказалось неудобным передавать набор комментариев на фильтрацию в виде списка и предпочтительнее коллекция другого типа.

В результате разработчики разных сервисов реализовали копии методов для применения правил “черного списка”, учитывающие специфику их сервисов. А так как правила фильтрации тоже менялись в процессе, эти методы правились не совместно, что привело к плохо читаемому и поддерживаемому коду: логика с одной стороны дублируется, но с другой - работает в каждом методе по-особенному.

Вы берете дело в свои руки и решаете реализовать единый метод фильтрации, учитывающий все обнаруженные особенности. В ходе анализа кода вы отмечаете для себя следующее:

1. Условия фильтрации в разных сервисах различаются и нет возможности обобщить их в рамках одного метода. Поэтому способ фильтрации вы решаете представлять в виде предиката (см. https://docs.oracle.com/javase/8/docs/api/java/util/function/Predicate.html) и позволять определять его вызывающим сервисам.

2. Набор используемых сервисами классов-представлений для комментариев обширен (String, Comment, CommentDto, …) и, возможно, будет и в дальнейшем расширяться.

3. Сервисы работают с наборами комментариев в виде коллекций разных типов (HashSet, ArrayList, ArrayDeque, …), но все они имплементируют интерфейс Iterable.

4. Результат фильтрации удобнее представлять в виде отдельной коллекции-возвращаемого значения метода, а исходную коллекцию при этом не модифицировать. Некоторым сервисам важен порядок следования комментариев, поэтому он должен быть сохранен в отфильтрованном результате.

Обновите интерфейс BlackListFilter и реализуйте новый механизм фильтрации в виде default-метода.

### [Решение](src/ArturKuznetsov/lab6/task10)
## <a id="task11">Задание 11 | Пиршество</a>
### Условие:
Вы служите при дворе короля Главным распорядителем пиров. И ваша задача, чтобы все на этих пирах были довольны. Особенно король.

Основная ваша задача — это составление меню. У вас есть перечень блюд, которые умеют готовить придворные повара.
Каждое блюдо имеет, как минимум, название и набор необходимых ингредиентов (тут для простоты можно использовать строки), категорию (закуска, горячее или десерт) оценку от 0 до 100 по мнению короля и оценку от 0 до 100 по мнению придворных. (Попробуйте провести анализ и подумать, какие ещё параметры могут быть полезны)

Для пиров вы составляете меню только из проверенных блюд, никаких экспериментов, так что оценки есть всегда.

Для составления меню, как правило, требуется проанализировать, кто из поваров работает в день пира и каких продуктов нет на дворцовой кухне в данный момент. После чего список возможных для приготовления блюд сортируется по оценкам (сортировка блюд происходит следующим образом: сравниваем два блюда по оценке короля, если оценки одинаковые, то сравниваем оценки придворных. Это считается естественным порядком).

Вы решаете написать класс, который хранил бы HashMap<Повар, Набор блюд>. Иногда на кухне появляются новые повара, иногда повара увольняются, так что вам важно предусмотреть методы, которые бы позволили внести изменения такого рода.

Основной задачей класса будет реализовать вышеуказанный алгоритм составления меню по двум параметрам: повара, которые работают в этот день, и продукты, которые отсутствуют на кухне. Третьим параметром метод принимает кол-во блюд, которые мы бы хотели приготовить, и возвращает в качестве ожидаемого меню отсортированный по приоритету набор блюд не более указанного размера.

Кроме того, иногда король капризничает и просит вас организовать меню с учётом особых требований (все блюда должны содержать клубнику в составе, все блюда должны иметь названия на “А”, только десерты и тд). Требования каждый раз разные, так что вы решаете добавить метод, который учитывал бы предыдущие условия и дополнительно мог бы отфильтровать список с учётом каких-то требований, определённых в качестве предиката.

В main продемонстрируйте работу вашего класса.


**Доп. задание:**

дворцовые повара не сидят сложа руки и активно расширяют меню. Добавьте метод, который бы позволил дополнить вашу мапу следующим образом: на вход метода получаем набор блюд и набор поваров, которые научились их готовит, после чего добавляем эти блюда к тем, которые указанные повара уже умеют готовить.
Учтите, что повар из списка может быть новеньким.


**Подсказки:**

Набор блюд для меню должен содержать только уникальные записи. Так как итоговое меню вида:
1. Жареная картошка
2. Жареная картошка
3. Жареная картошка
4. Пирог с голубями

не понравится ни королю, ни гостям. Меню дб разнообразным по мере возможностей.

Для каждого повара, аналогично, имеет смысл хранить только уникальные блюда. То есть хранение пары K,V вида:
Повар Аркадий - Пирог с голубями, Пирог с голубями, Пирог с голубями, Пирог с голубями, Булочка с корицей
не слишком оптимально.

Поразмышляйте над тем, какие инструменты помогут вам выполнить указанные условия. Учтите требования, которые необходимо выполнить, чтобы эти инструменты работали корректно.
Просмотрите, какие методы предоставляют классы, которые вы используете, вероятно, там найдутся те, которые позволяют красиво и лаконично выполнить некоторые задачи, с которыми вы столкнётесь.

### [Решение](src/ArturKuznetsov/lab6/task11)
## <a id="task12">Задание 12 | Тернарный оператор</a>
### Условие:
Напишите параметризованный статический метод, который бы реализовывал логику тернарного оператора на основе полученных предиката и двух функций.

В main приведите несколько примеров работы вышеуказанного метода.

### [Решение](src/ArturKuznetsov/lab6/task12)

## <a id="task13">Задание 13 | Аукцион</a>
### Условие:
Вы работаете над приложением для проведения аукциона. Начать разработку решили с самого важного - класса лота аукциона. В ходе анализа предметной области вы пришли к выводу, что каждый лот должен иметь 3 параметра: текущую стоимость, имя пользователя, предложившего ее, и время окончания торгов по этому лоту.

Также класс должен предоставлять методы
- метод “ставки”, который обновляет текущую стоимость лота и сохраняет предложившего ее пользователя, если торги по лоту еще ведутся по времени и предложенная цена выше текущей.
- метод получения размера текущей ставки
- метод получения имени пользователя победителя.

Делать ставки на лот одновременно могут сразу несколько пользователей.

Реализуйте класс по описанию так, чтобы одновременное участие в ставках большого количества пользователей не приводило к ошибкам в проведении аукциона (то есть, потокобезопасно).

Входные данные для старта аукциона лежат в двух файлах. Первый файл (lot.txt) содержит информацию о лоте: название  и цену. Пример содержимого файла:

```
“Поцелуй”, Густав Климт
100000
```

Второй файл (participants.txt) содержит имена участников аукциона, каждое в новой строке. Пример содержимого файла:

```
Евгения Штайнер
Карл Витгенштейн
Серена Ледерер
Адель Блох-Бауэр
Отто Примавези
Евгении Примавези
Виктор Цукеркандль
Антон Лёв
Густав Учицки
Аранка Мунк
Адель Блох-Бауэр
Август Ледерер
```

Для демонстрации напишите main метод, где запустите ваше приложение с 10 (как минимум) участниками, каждый из которых сделает до 100 попыток перебить текущую ставку, и выиграть лот.
Подсказки:
Не забывайте про принцип единственной ответственности. Проектируя класс, продумайте, за что он должен отвечать, какие задачи выполнять.


### [Решение](src/ArturKuznetsov/lab7/task13)

## <a id="task14">Задание 14 | Клиент-серверное приложение</a>
### Условие:
Напишите клиент-серверное приложение (это 2 отдельных приложения).
Сервер ждет подключения пользователей, принимает текстовые сообщения, которые пересылает всем подключенным клиентам.
Клиентское приложение сначала предлагает ввести никнейм, а далее отсылает на сервер каждую строку введённую пользователем
И выводит на консоль все сообщения полученные с сервера.
IP адрес - 127.0.0.1 - ведёт на так называемый localhost. Если запускаете клиент и сервер с одной машины - указывайте его. Если пробуете с кем то сконектиться - то надо указать или его IP адрес в локальной сети (Или если есть внешний IP - можно попробовать законектиться с любой точки мира указав его)

Ожидается в консоли пользователя увидеть чат.
Кому хочется посложнее: - выводите ник пользователя, и время в которое сообщение было отправлено. А кому и этого мало - учитывайте часовой пояс в котором клиентское приложение подключилось, и выводите локальное время в чат каждому пользователю. (Зону можно принять как аргумент запуска или предложить ввести пользователю после никнейма).

Идея не даёт запустить 2 клиента одновременно в своём окружении. Можно запустить через терминал (в том числе и через терминал идеи)

![Пример работы 14 задания](img/task14_example.png)

### [Решение](src/ArturKuznetsov/lab7/task14)

## <a id="task15">Задание 15 | Бэкенд для ветеринарной клиники</a>
### Условие:
Вы разрабатываете бэкенд приложения для ветеринарной клиники. Ветклиника уже работает некоторое время, информацию фиксируют вручную в excel-таблице.
В таблицу внесены данные за всё время существования клиники.

Заказчик выгрузил и передал вам эту таблицу в виде CSV-файла.

Формат файла\
*<порядковый_номер_клиента:integer>,<фамилия_клиента:string>,<имя_клиента:string>,<номер_телефона_клиента:string>,<номер_мед_карты_питомца:integer>,<имя_питомца:string>,<возраст_питомца:integer>*

Содержимое\
*1,Иванова,Ксения,+79995554433,1,Котик,2*
*2,Кириллов,Виктор,+75255121023,2,Бублик,7*
*3,Коровкин,Алексей,+79305162030,3,Чиписик,2*
*4,Цветова,Анастасия,+79315412063,4,Копуша,5*
*5,Тарасова,Варвара,+78521023656,5,Джек,4*
*1,Иванова,Ксения,+79995554433,6,Бегемотик,1*
*4,Цветова,Анастасия,+79315412063,7,Бантик,2*
*6,Синицина,Алиса,+79125236378,8,Donnar de Nordval,4*
*6,Синицина,Алиса,+79125236378,9,Dark von der Bismarckquelle,3*
*7,Неустроева,Ангелина,+79634152351,10,Коржик,1*
*8,Венедиктов,Пётр,+79526324563,11,Пушок,2*
*9,Буркин,Сергей,+79521415220,12,Зубастик,15*
*10,Иванов,Алексей,+79996654120,6,Бегемотик,1*
*10,Иванов,Алексей,+79996654120,1,Котик,2*
*11,Коржов,Арсений,+71234562102,13,Пират,15*
*12,Цветов,Аркадий,+79655002030,7,Бантик,2*


Спроектируйте структуру таблиц для представления информации о клиентах и их питомцах в базе данных и загрузите в них данные из файла. Для этого разработайте приложение, которое:
Создаст в базе данных все необходимые таблицы.
Импортирует в базу данных все записи исходного файла.

Путь к файлу с данными передается программе в качестве аргумента командной строки при запуске.

### [Решение](src/ArturKuznetsov/lab8/task15)

## <a id="task16">Задание 16 | Бэкенд для ветеринарной клиники 2.0</a>
### Условие:
Вы продолжаете разработку приложения для ветеринарной клиники. Уже спроектирована схема данных и есть 
первичное наполнение, следующим шагом вы решаете разработать DAO-классы для работы с базой данных клиники. 
Для этого вы добавляете в приложение классы сущностей клиента (Client) и питомца (Pet) 
и определяетесь с составом необходимых методов DAO-классов:

`Client createClient(Client client);`\
Создание нового клиента. Если в базе данных уже существует клиент с переданным номером телефона, метод выбрасывает исключение.

`Client findClient(Integer id);`\
Поиск клиента по идентификатору.

`Client updateClient(Client client);`\
Изменение информации о клиенте. Фамилия, имя и номер телефона клиента в базе данных заменяется на значения, указанные в полях параметра client. Идентификатор клиента, данные которого должны быть изменены, также задается полем объекта client.

`void deleteClient(Integer id);`\
Удаление клиента из базы.

`Pet createPet(String name, Integer age, List<Client> clients);`\
Создание нового питомца.  В базе создаётся запись о питомце с указанными данными и заданным списком клиентов.

`Pet findPet(Integer medicalCardNumber);`\
Поиск питомца по номеру мед карты.

`Pet updatePet(Pet pet);`\
Изменение информации о питомце. Имя и возраст питомца в базе данных заменяется на значения, указанные в полях параметра pet. Номер медицинской карты питомца, данные которого должны быть изменены, также задается полем объекта pet.

`void deletePet(Integer medicalCardNumber);`\
Удаление питомца из базы.

`List<String> findClientPhoneNumbersBy(Pet pet);`\
Поиск номеров телефонов клиентов-хозяев указанного питомца.

`List<Pet> getAllPetsOf(Client client);`\
Получение всех питомцев клиента.

Не забудьте протестировать собственное решение (любым способом, можно просто вызывать требуемые методы из main-метода с произвольными параметрами.\
Реализуйте программу с указанными операциями.

### [Решение](src/ArturKuznetsov/lab8/task16)

---

## <a id="contacts">Контакты</a>

- Имя и Фамилия: Артур Кузнецов
- Telegram: [@i_am_dak0ta](https://t.me/i_am_dak0ta)
