# Класс Battery: методы с проверкой границ

Этот пример показывает, как методы могут **проверять значения** и возвращать разные сообщения в зависимости от состояния объекта.  
У меня есть класс `Battery` с методами `drain()` (разрядить), `charge()` (зарядить) и `getCharge()` (проверить состояние).

---

### Класс Battery (поля и методы)

```java
class Battery {
    int charge = 100;

    public void drain(int amount) {
        charge -= amount;
    }

    public void charge(int amount) {
        charge += amount;
    }

    public String getCharge() {
        if (charge < 0) {
            return "Батарея разряжена!";
        } else if (charge > 100) {
            return "Батарея заряжена!";
        } else {
            return "Заряд: " + charge;
        }
    }
}
```
Класс BatteryMain (создание объекта и вызов методов)
```java
public class BatteryMain {
    public static void main(String[] args) {
        Battery battery = new Battery();
        battery.drain(75);
        System.out.println(battery.getCharge());
        battery.charge(70);
        System.out.println(battery.getCharge());
    }
}
```
**Вывод в консоли**
```
Заряд: 25
Батарея заряжена!
```

---

### Что я узнала
- Метод может возвращать разные сообщения в зависимости от состояния объекта
- `if-else` — проверяет несколько условий по порядку
- Границы — проверка, не выходит ли значение за допустимые пределы (0–100)

## Как работают методы

| Метод | Что делает | Возвращает |
|-------|------------|------------|
| `drain(int amount)` | Уменьшает заряд на `amount` | ничего (`void`) |
| `charge(int amount)` | Увеличивает заряд на `amount` | ничего (`void`) |
| `getCharge()` | Проверяет состояние и возвращает сообщение | `String` |

## Пошагово: что происходит в коде

| Шаг | Действие | charge | Результат |
|-----|----------|--------|------------|
| 1 | `new Battery()` | 100 | Батарея создана |
| 2 | `drain(75)` | 100 → 25 | Заряд уменьшился |
| 3 | `getCharge()` | 25 | "Заряд: 25" |
| 4 | `charge(70)` | 25 → 95 | Заряд увеличился |
| 5 | `getCharge()` | 95 | "Батарея заряжена!" |

---

## Эксперименты для практики
Разряди до нуля
```java
Battery battery = new Battery();
battery.drain(150);
System.out.println(battery.getCharge());  // Батарея разряжена!
```
Перезаряди
```java
Battery battery = new Battery();
battery.charge(50);  // charge = 150
System.out.println(battery.getCharge());  // Батарея заряжена!
```
Полный цикл
```java
Battery battery = new Battery();
battery.drain(30);    // charge = 70
System.out.println(battery.getCharge());  // Заряд: 70
battery.charge(100);  // charge = 170
System.out.println(battery.getCharge());  // Батарея заряжена!
```

---

### Мои заметки
- `charge > 100` — проверка на перезарядку
- `charge < 0` — проверка на полную разрядку
- Порядок `if-else` важен — проверяем сначала крайние случаи
- Метод возвращает `String`, поэтому можно использовать в `System.out.println()`

---

⭐ Теперь я умею проверять границы и возвращать разные сообщения в зависимости от состояния объекта!
