## Авторские Права

Следующее заявление об авторских правах должно быть включено в верхнюю часть каждого файла-источника:

    /*
     * Copyright (c) 2020 Razeware LLC
     *
     * Permission is hereby granted, free of charge, to any person obtaining a copy
     * of this software and associated documentation files (the "Software"), to deal
     * in the Software without restriction, including without limitation the rights
     * to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
     * copies of the Software, and to permit persons to whom the Software is
     * furnished to do so, subject to the following conditions:
     *
     * The above copyright notice and this permission notice shall be included in
     * all copies or substantial portions of the Software.
     *
     * Notwithstanding the foregoing, you may not use, copy, modify, merge, publish,
     * distribute, sublicense, create a derivative work, and/or sell copies of the
     * Software in any work that is designed, intended, or marketed for pedagogical or
     * instructional purposes related to programming, coding, application development,
     * or information technology.  Permission for such use, copying, modification,
     * merger, publication, distribution, sublicensing, creation of derivative works,
     * or sale is expressly withheld.
     *
     * THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
     * IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
     * FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
     * AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
     * LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
     * OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
     * THE SOFTWARE.
     */

# Официальное raywenderlich.com C# руководство по стилю

Это руководство по стилю отличается от всех остальных, которые ты мог встречать,
потому как оно сконцентрировано на поставлении удобочитаемости для печати и интернета.
Мы создали этот Style Guide для поддержки последовательного кода в наших пособиях.

Нашими главными целями являются: **краткость**, **удобочитаемость**, **простота**. Кроме того руководство написано, учитывая соглашение **Unity**.

## Вдохновение

Это руководство по стилю основано на соглашениях от C# и Unity

## Содержание

- [Список](#Список)
  + [Именное Пространство](#Именное-Пространство)
  + [Классы & Интерфейсы](#Классы--Интерфейсы)
  + [Методы](#Методы)
  + [Поля](#Поля)
  + [Свойства](#Свойства)
  + [Параметры](#Параметры)
  + Делегаты
  + [События](#События)
  + [Разное](#Разное)
- [Декларации](#Декларации)
  + [Модификаторы Доступа](#Модификаторы-Доступа)
  + [Поля & Переменные](#Поля--Переменные)
  + [Классы](#Классы)
  + [Интерфейсы](#Интерфейсы)
- [Пространство](#Пространство)
  + [Отступы](#Отступы)
  + [Блоки Кода](#Блоки-Кода)
  + [Табуляция](#Табуляция)
  + [Длина Строки](#Длина-Строки)
  + [Вертикальное Пространство](#Вертикальное-Пространство)
- [Фигурные Скобки](#Фигурные-Скобки)
- [Условия](#Условия)
- [Оператор Switch](#Оператор-Switch)
- [Язык](#Язык)
- [Авторские Права](#Авторские-Права)
- [Смайл](#Смайл)
- [Кредиты](#Кредиты)


## Список

В целом, именование должно соответствовать стандартам C#.

### Именное Пространство

Всё именное пространство написано в **PascalCase**, несколько слов в одном соединенны вместе, без дефисов ( - ) или подчеркивания ( \_ ).
Исключением из этого правила являются аббревиатуры типа GUI или HUD, которые могут быть в верхнем регистре:

**Неверно**:

```csharp
com.raywenderlich.fpsgame.hud.healthbar
```

**Верно**:

```csharp
RayWenderlich.FPSGame.HUD.Healthbar
```

### Классы & Интерфейсы

Классы и интерфейсы написаны в **PascalCase**. Например: `RadialSlider`.

### Методы

Методы написаны в **PascalCase**. Например: `DoSomething()`.

### Поля

Все нестатические поля написаны **camelCase**. В соответствии с соглашением Unity, включая **общедоступные поля**.

For example:

```csharp
public class MyClass
{
    public int publicField;
    int packagePrivate;
    private int myPrivate;
    protected int myProtected;
}
```

**НЕВЕРНО:**

```csharp
private int _myPrivateVariable
```

**ВЕРНО:**

```csharp
private int myPrivateVariable
```

Статические поля являются исключением и следуют быть написаны в **PascalCase**:

```csharp
public static int TheAnswer = 42;
```
### Свойства

Все свойства записаны в **PascalCase**. Например:

```csharp
public int PageNumber
{
    get { return pageNumber; }
    set { pageNumber = value; }
}
```

### Параметры

Параметры написаны в **camelCase**.

**НЕВЕРНО:**

```csharp
void DoSomething(Vector3 Location)
```

**ВЕРНО:**

```csharp
void DoSomething(Vector3 location)
```

Следует избегать односимвольных значений, за исключением временных цикловых переменных.

### События

Действия написаны в **PascalCase**. Например:

```csharp
public event Action<int> ValueChanged;
```

### Разное

Аббревиатуры в коде следует трактовать в нижнем регистре. Например:

**НЕВЕРНО:**

```csharp
XMLHTTPRequest
String URL
findPostByID
```

**ВЕРНО:**

```csharp
XmlHttpRequest
String url
findPostById
```

## Декларации

### Модификаторы Доступа

Модификаторы доступа должны быть явно определены для классов, методов и участников переменных.

### Поля & Переменные

Преподчтительнее записывать переменные единой декларации в одну строку

**НЕВЕРНО:**

```csharp
string username, twitterHandle;
```

**ВЕРНО:**

```csharp
string username;
string twitterHandle;
```

### Классы

Ровно по одному классу на каждый исходный файл, хотя в соответствующих случаях одобряются внутренние классы.

### Интерфейсы

Все интерфейсы должны быть предопределены буквой **I**.

**НЕВЕРНО:**

```csharp
RadialSlider
```

**ВЕРНО:**

```csharp
IRadialSlider
```

## Пространство

Пространство особенно важно в коде raywenderlich.com, т.к. код должен быть легко читаемым как часть руководства.

### Отступы

Отступы должны всегда содержать только **пробелы**.

#### Блоки Кода

Отступы в блоках кода следует использовать длиной в **4 пробела** для оптимальной читабельности:

**НЕВЕРНО:**

```csharp
for (int i = 0; i < 10; i++)
{
  Debug.Log("index=" + i);
}
```

**ВЕРНО:**

```csharp
for (int i = 0; i < 10; i++)
{
    Debug.Log("index=" + i);
}
```

#### Табуляция

Мы советуем Вас использовать табуляцию в **4 пробела** (а не по умолчанию 8):

**НЕВЕРНО:**

```csharp
CoolUiWidget widget =
        someIncrediblyLongExpression(that, reallyWouldNotFit, on, aSingle, line);
```

**ВЕРНО:**

```csharp
CoolUiWidget widget =
    someIncrediblyLongExpression(that, reallyWouldNotFit, on, aSingle, line);
```

### Длина Строки

Вся строка должна быть длиной не более, чем в **100** символов.

### Вертикальное Пространство

Должна присутствовать одна пустая линия между методами, чтобы легко визуально ориентироваться и 
вести организованный код. Пробелы в методах должны разделять функциональность, но 
наличие слишком большого количества секций в методе зачастую означает, что вы должны проводить рефакторинг в
несколько методов.


## Фигурные Скобки

Все фигурные скобки расположены на *отдельно выделенной* строке (т.к. это является оф. соглашением C#):

**НЕВЕРНО:**

```csharp
class MyClass {
    void DoSomething() {
        if (someTest) {
          // ...
        } else {
          // ...
        }
    }
}
```

**ВЕРНО:**

```csharp
class MyClass
{
    void DoSomething()
    {
        if (someTest)
        {
          // ...
        }
        else
        {
          // ...
        }
    }
}
```

## Условия

Условные операторы всегда должны использоваться в комплекте со скобками,
независимо от количества строк.

**НЕВЕРНО:**

```csharp
if (someTest)
    doSomething();

if (someTest) doSomethingElse();
```

**ВЕРНО:**

```csharp
if (someTest)
{
    DoSomething();
}

if (someTest)
{
    DoSomethingElse();
}
```
## Оператор Switch

Оператор Switch привычно использовать с `default` в конце. Если кусок `default` никогда не используется, то смело от него избавляйтесь.

**НЕВЕРНО:**

```csharp
switch (variable)
{
    case 1:
        break;
    case 2:
        break;
    default:
        break;
}
```

**ВЕРНО:**

```csharp
switch (variable)
{
    case 1:
        break;
    case 2:
        break;
}
```

## Язык

Используйте правописание на американском английском языке.

**НЕВЕРНО:**

```csharp
string colour = "red";
```

**ВЕРНО:**

```csharp
string color = "red";
```

Исключение составляет `MonoBehaviour`, т.к. именно так на самом деле класс уже назван.

## Смайл

Улыбающиеся лица - очень заметная стилистическая особенность сайта raywenderlich.com!
Очень важно, чтобы правильная улыбка означала огромное количество счастья и азарта на тему кодирования. Закрывающаяся квадратная скобка ] используется потому, что она представляет собой самую большую улыбку, которую можно запечатлеть, используя ASCII-арт. Заключительная скобка ("**:)**") создает улыбку с полусердечием, и поэтому она не является предпочтительной.

**Неверно**:

:)

**Верно**:

:]

> **Заметка**: Не используйте смайлы в своих скриптах.

## Кредиты

Это руководство по стилю является результатом совместных усилий наиболее стильных
членов команды raywenderlich.com:

- [Darryl Bayliss](https://github.com/DarrylBayliss)
- [Sam Davies](https://github.com/sammyd)
- [Mic Pringle](https://github.com/micpringle)
- [Brian Moakley](https://github.com/VegetarianZombie)
- [Ray Wenderlich](https://github.com/rwenderlich)
- [Eric Van de Kerckhove](https://github.com/BlackDragonBE)

