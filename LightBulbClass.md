# Класс LightBulb: методы, возвращающие новое состояние

Этот пример показывает, как методы могут **менять состояние объекта и возвращать его**.  
У меня есть класс `LightBulb` с методами `turnOn()` и `turnOff()`, которые меняют состояние лампочки и возвращают его.

---

### Класс LightBulb (поля и методы)

```java
class LightBulb {
    boolean isOn;

    public boolean turnOn() {
        return isOn = true;
    }

    public boolean turnOff() {
        return isOn = false;
    }

    public boolean getIsOn() {
        return isOn;
    }
}
```
Класс LightBulbMain (создание объекта и вызов методов)
```java
public class LightBulbMain {
    public static void main(String[] args) {
        LightBulb bul = new LightBulb();
        bul.turnOn();
        bul.turnOff();
        System.out.println(bul.getIsOn());
    }
}
```
**Вывод в консоли**
```
false
```

---

### Что я узнала
- Метод может менять состояние объекта и возвращать его
- `return isOn = true` — сначала присваиваем `true`, потом возвращаем это значение
- `getIsOn()` — просто возвращает текущее состояние поля

| Метод | Что делает | Возвращает |
|-------|------------|------------|
| `turnOn()` | Устанавливает `isOn = true` | `true` |
| `turnOff()` | Устанавливает `isOn = false` | `false` |
| `getIsOn()` | Возвращает текущее состояние | `true` или `false` |

---

### Мои заметки
- `return isOn = true` — это сокращённая запись. Можно написать и так:

```java
public boolean turnOn() {
    isOn = true;
    return isOn;
}
```
Оба варианта работают одинаково

- `getIsOn()` — это геттер (метод для получения значения поля)
- Геттеры обычно начинаются с `get + имя поля` (с большой буквы)

---

## Эксперименты для практики
Попробуй изменить последовательность
```java
LightBulb bul = new LightBulb();
bul.turnOn();           // включили
System.out.println(bul.getIsOn());  // true
bul.turnOff();          // выключили
System.out.println(bul.getIsOn());  // false
```
Проверь, что возвращают методы включения/выключения
```java
System.out.println("Включили: " + bul.turnOn());   // Включили: true
System.out.println("Выключили: " + bul.turnOff()); // Выключили: false
```

---

⭐ Теперь я умею включать и выключать лампочку! А ещё — возвращать значения из методов и создавать геттеры.
