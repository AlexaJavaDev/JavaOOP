# Инкапсуляция и сеттеры/геттеры: защита данных через методы

В этих примерах я разбираю **инкапсуляцию** — один из главных принципов ООП.  
Вместо того чтобы напрямую обращаться к полям, я использую методы `setLogin()`, `setPassword()`, `setTitle()` и другие.

**Это помогает:**
- **Защитить данные** — поля не доступны напрямую
- **Добавить логику** — например, проверить пароль или форматировать вывод
- **Упростить изменения** — можно поменять логику внутри метода, не трогая остальной код

---

## Пример 1: Проверка логина и пароля (Account)

### Код

```java
class Account {
    String login;
    String password;

    public void setLogin(String log) {
        login = log;
    }

    public void setPassword(String pw) {
        password = pw;
    }

    public boolean check(String login, String password) {
        return this.login.equals(login) && this.password.equals(password);
    }
}
```
Класс AccountMain:

```java
public class AccountMain {
    public static void main(String[] args) {
        Account acc = new Account();
        acc.setLogin("admin");
        acc.setPassword("1234");
        System.out.println(acc.check("admin", "1234"));
        System.out.println(acc.check("admin", "0000"));
    }
}
```
**Вывод в консоли**
```
true
false
```

**Как это работает**
- `setLogin()` и `setPassword()` — устанавливают значения
- `check()` — проверяет, совпадают ли логин и пароль с сохранёнными
- `this.login` — обращается к полю объекта, а не к параметру метода
- `equals()` — сравнивает строки по значению, а не по ссылке

---

## Пример 2: Создание заметки (Note)

### Код

Класс Note:

```java
class Note {
    String title;
    String content;

    public void setTitle(String t) {
        title = t;
    }

    public void setContent(String c) {
        content = c;
    }

    public String getNote() {
        return "Заметка: " + title + " - " + content;
    }
}
```
Класс NoteMain:

```java
public class NoteMain {
    public static void main(String[] args) {
        Note one = new Note();
        one.setTitle("Список дел");
        one.setContent("1. Помыть кота");
        System.out.println(one.getNote());
    }
}
```
**Вывод в консоли**
```
Заметка: Список дел - 1. Помыть кота
```

**Как это работает**
- `setTitle()` и `setContent()` — заполняют поля
- `getNote()` — возвращает собранную строку с форматированием
- Вся логика форматирования спрятана внутри метода

---

## Пример 3: Игрок со счетом (Player)

**Код**

Класс Player:

```java
class Player {
    String name;
    int score;

    public void addScore(int points) {
        score += points;
    }

    public void reset() {
        score = 0;
    }

    public String getInfo() {
        return "Игрок: " + name + ", Очки: " + score;
    }
}
```
Класс PlayerMain:

```java
public class PlayerMain {
    public static void main(String[] args) {
        Player one = new Player();
        one.name = "Alex";
        one.score = 0;
        one.addScore(10);
        System.out.println(one.getInfo());
        one.addScore(15);
        System.out.println(one.getInfo());
        one.reset();
        System.out.println(one.getInfo());
        one.addScore(5);
        System.out.println(one.getInfo());
    }
}
```
**Вывод в консоли**
```
Игрок: Alex, Очки: 10
Игрок: Alex, Очки: 25
Игрок: Alex, Очки: 0
Игрок: Alex, Очки: 5
```
**Как это работает**
- `name` и `score` — заданы напрямую (но лучше через конструктор или сеттеры)
- `addScore()` — увеличивает счёт на переданное значение
- `reset()` — обнуляет счёт
- `getInfo()` — возвращает форматированную строку с состоянием игрока

---

## Сравнение подходов

**Пример 1 (Account):**
1. Сеттеры для установки данных
2. Метод `check()` проверяет совпадение

**Пример 2 (Note):**
1. Сеттеры для установки данных
2. Геттер `getNote()` форматирует вывод

**Пример 3 (Player):**
1. Прямой доступ к полям (менее защищённый способ)
2. Методы `addScore()`, `reset()`, `getInfo()` изменяют и возвращают состояние

---

## Что я запомнила
- Сеттеры — нужны для установки значений (вместо прямого обращения к полям)
- Геттеры — возвращают значения (часто с форматированием)
- Инкапсуляция — скрывает детали реализации внутри класса
- `this` — указывает на текущий объект
- `equals()` — сравнивает строки по значению

---

## Мои заметки
1. В примере с `Player` поля задаются напрямую `(one.name = "Alex")` — это быстрее, но небезопасно
2. В идеале все поля должны быть `private` и закрыты через геттеры/сеттеры
3. Сеттеры позволяют добавить проверку в будущем (например, пароль не короче 4 символов)

---

⭐ Инкапсуляция — это основа ООП. Теперь я умею защищать данные и управлять доступом к ним.
