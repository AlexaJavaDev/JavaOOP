# Класс Temperature: методы, возвращающие значения

Этот пример показывает, как методы могут **возвращать** результат вычислений.  
У меня есть класс `Temperature` с методами `toFahrenheit()` и `toKelvin()`, которые возвращают значения, а не выводят их напрямую.

---

### Класс Temperature (поля и методы)

```java
class Temperature {
    double celsius;

    public double toFahrenheit() {
        return celsius * 9 / 5 + 32;
    }

    public double toKelvin() {
        return celsius + 273.15;
    }
}
```
Класс TemperatureMain (создание объекта и вызов методов)
```java
public class TemperatureMain {
    public static void main(String[] args) {
        Temperature temp = new Temperature();
        temp.celsius = 25;
        System.out.println(temp.toFahrenheit());
        System.out.println(temp.toKelvin());
    }
}
```
**Вывод в консоли**
```
77.0
298.15
```

---

### Что я узнала
- Метод может возвращать значение — вместо `void` указывается тип возвращаемого значения `(double, int, String и т.д.)`
- `return` — возвращает результат и завершает метод
- Метод можно вызвать внутри `System.out.println()`, потому что он возвращает число

---

### Мои заметки
- `double` — возвращаем дробное число
- `return` — ключевое слово для возврата значения
- Метод с `return` можно использовать в выражениях:

```java
double f = temp.toFahrenheit();
System.out.println(f + 10);
```
- `return` завершает метод — код после него не выполняется

---

### Дополнительные примеры
Вывод с пояснениями
```java
System.out.println("По Фаренгейту: " + temp.toFahrenheit());
System.out.println("По Кельвину: " + temp.toKelvin());
```

**Вывод в консоли**
```
По Фаренгейту: 77.0
По Кельвину: 298.15
```

---

⭐ Теперь я умею создавать методы, которые возвращают значения. Это полезно для вычислений и переиспользования кода!
