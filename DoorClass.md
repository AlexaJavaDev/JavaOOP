# Класс Door: методы с логикой переключения состояния

Этот пример показывает, как метод может **изменять состояние объекта на противоположное**.  
У меня есть класс `Door` с методами `open()`, `close()` и `toggle()` — последний переключает состояние двери.

---

### Класс Door (поля и методы)

```java
class Door {
    boolean isOpen;

    public boolean open() {
        return isOpen = true;
    }

    public boolean close() {
        return isOpen = false;
    }

    public boolean toggle() {
        if (isOpen == true) {
            return isOpen = false;
        } else {
            return isOpen = true;
        }
    }

    public boolean getIsOpen() {
        return isOpen;
    }
}
```
Класс DoorMain (создание объекта и вызов методов)
```java
public class DoorMain {
    public static void main(String[] args) {
        Door door = new Door();
        door.open();       // открываем дверь
        door.toggle();     // переключаем состояние
        System.out.println(door.getIsOpen());
    }
}
```
**Вывод в консоли**
```
false
```

---

### Что я узнала
- `toggle()` меняет состояние на противоположное
- Если дверь открыта `(true)` → закрывает `(false)`
- Если дверь закрыта `(false)` → открывает `(true)`
- Это называется переключение состояния `(toggle)`

### Как работают методы

| Метод | Что делает | Возвращает |
|-------|------------|------------|
| `open()` | Устанавливает `isOpen = true` | `true` |
| `close()` | Устанавливает `isOpen = false` | `false` |
| `toggle()` | Меняет состояние на противоположное | новое состояние (`true` или `false`) |
| `getIsOpen()` | Возвращает текущее состояние | `true` или `false` |

### Пошагово: что происходит в коде

| Шаг | Действие | isOpen | Результат |
|-----|----------|--------|------------|
| 1 | `door.open()` | `false` → `true` | Дверь открылась |
| 2 | `door.toggle()` | `true` → `false` | Дверь закрылась |
| 3 | `door.getIsOpen()` | `false` | Вывод: `false` |

---

### Мои заметки
- `toggle()` можно написать короче:

```java
public boolean toggle() {
    isOpen = !isOpen;   // ! — оператор "не" (переворачивает true/false)
    return isOpen;
}
```
Оба варианта работают одинаково, но короткая запись читается легче
- `!` — логическое отрицание: если `true` → становится `false`, если `false` → становится `true`

---

## Эксперименты для практики
Попробуй разные последовательности
```java
Door door = new Door();

door.open();
System.out.println(door.getIsOpen());  // true

door.toggle();
System.out.println(door.getIsOpen());  // false

door.toggle();
System.out.println(door.getIsOpen());  // true
```
Проверь, что возвращает toggle()
```java
System.out.println("После toggle: " + door.toggle());  // После toggle: false
```
Открой, закрой, переключи
```java
door.open();          // true
door.close();         // false
door.toggle();        // true
System.out.println(door.getIsOpen());  // true
```

---

⭐ Теперь я умею переключать состояние объектов! Это пригодится для игр, интерфейсов и любой логики "вкл/выкл".
