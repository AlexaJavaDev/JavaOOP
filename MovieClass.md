# Класс Movie: создание объектов и работа с полями

Это первый пример по ООП. У меня два класса:
- `Movie` — содержит поля и метод для вывода информации
- `MovieMain` — создаёт объекты и вызывает метод

---

### Класс Movie (поля и метод)

```java
class Movie {
    String title;
    int year;
    double rating;
    boolean isWatched;

    public void printInfo() {
        System.out.println("Название: " + title + " (" + year + ") " +
        "Рейтинг: " + rating + "\nПросмотрен: " + isWatched + "\n");
    }
}
```
Класс MovieMain (создание объектов)
```java
public class MovieMain {
    public static void main(String[] args) {
        Movie one = new Movie();
        one.title = "Интерстеллар";
        one.year = 2014;
        one.rating = 8.6;
        one.isWatched = true;
        one.printInfo();

        Movie two = new Movie();
        two.title = "Начало";
        two.year = 2010;
        two.rating = 8.8;
        two.isWatched = false;
        two.printInfo();

        Movie three = new Movie();
        three.title = "Матрица";
        three.year = 1999;
        three.rating = 8.7;
        three.isWatched = true;
        three.printInfo();

        Movie four = new Movie();
        four.title = "Джокер";
        four.year = 2019;
        four.rating = 8.4;
        four.isWatched = false;
        four.printInfo();

        Movie five = new Movie();
        five.title = "Паразиты";
        five.year = 2019;
        five.rating = 8.5;
        five.isWatched = true;
        five.printInfo();
    }
}
```
**Вывод в консоли**
```
Название: Интерстеллар (2014) Рейтинг: 8.6
Просмотрен: true

Название: Начало (2010) Рейтинг: 8.8
Просмотрен: false

Название: Матрица (1999) Рейтинг: 8.7
Просмотрен: true

Название: Джокер (2019) Рейтинг: 8.4
Просмотрен: false

Название: Паразиты (2019) Рейтинг: 8.5
Просмотрен: true
```

---

### Что я узнала
- `Класс` — это шаблон для создания объектов
- `Поля` — характеристики объекта (переменные)
- `Метод` — действие, которое может выполнять объект
- `Объект` — экземпляр класса, созданный через new

```java
Movie one = new Movie();     // создаю объект
one.title = "Интерстеллар";  // заполняю поле
one.printInfo();             // вызываю метод
```
---
### Мои заметки
- `boolean` выводится как `true` или `false`
- Позже я научусь выводить `"Да" / "Нет"` вместо `true / false` используя тернарный оператор
- Пока что мне нужно запомнить структуру: класс → поля → метод → объект

---

⭐ Отличный старт в ООП! Теперь я умею создавать классы, объекты и заполнять поля.
