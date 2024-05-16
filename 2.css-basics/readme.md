# Из чего состоит CSS
Селекторы: Селекторы используются для выбора элементов HTML, к которым вы хотите применить стили

```css
селектор {  
    свойство: значение
}
```

[Все свойства](https://www.w3schools.com/cssref/index.php)




Селекторы могут быть по имени тега, классу или идентификатору
```css
p {
    color: red;
}
.myClass {
    color: blue;
}
#myID {
    color: green;
}
```

Свойства: Свойства определяют, какие именно стили должны быть применены к выбранным элементам. Например, color, font-size, margin, padding, display и так далее.
```css
p {
  color: red;
  font-size: 16px;
  padding: 10px;
  margin: 0 auto;
  display: block;
} 
```

#### Псевдо-классы и псевдо-элементы
Псевдо-классы
* :hover
* :first-child
* :nth-child
* [все](https://developer.mozilla.org/ru/docs/Web/CSS/Pseudo-classes)
```css 
a:hover {
  color: red;
}
```

Псевдо-элементы
* ::before
* ::after
* [все](https://developer.mozilla.org/ru/docs/Web/CSS/Pseudo-elements)
```css 
p::before {
    content: "Привет! ";
}
```

```+ / > / ~```

div > p  - Выбрать все p в которых div родитель

div + p - Выбрать первый p, который идет после div

div + p - Выбрать все p, у которых перед которыми был div



### [Медиа-запросы](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Media_queries)
позволяют вам применять разные стили в зависимости от размера экрана или других характеристик устройства просмотра
```css
@media screen and (min-width: 600px) {
  body {
    background-color: lightblue;
  }
}
```

```css 
@media print {
  body {
    font-size: 12pt;
  }
}
```

!important
```css
meta name="viewport" content="width=device-width,initial-scale=1" />
```

## Каскадность
Каскадность в CSS определяет то, как будут комбинироваться стили из разных источников

Источники:
* User-agent stylesheets
* User stylesheets
*  Author stylesheets


Специфичность: 

Селекторы тегов (например, h1) имеют наименьшую специфичность.

Селекторы классов, атрибутов и псевдоклассов (например, .myClass, [type="text"], :hover) имеют среднюю специфичность.

Селекторы идентификатора (например, #myID) имеют наибольшую специфичность.

Встроенные стили (например, style="font-weight:bold") имеют еще большую специфичность.

Стили, помеченные как !important, имеют наибольшую специфичность.


```css
[type="password"]             /* 0-1-0 */
input:focus                   /* 0-1-1 */
:root #myApp input:required   /* 1-2-1 */
```


```css
#myElement {
  color: green; /* 1-0-0  - WINS!! */
}
.bodyClass .sectionClass .parentClass [id="myElement"] {
  color: yellow; /* 0-4-0 */
}
```

```css
.sectionClass {
    color: green;
}

.bodyClass .sectionClass {
  color: yellow;
}
```

```css
:root {
    color: green; /* 0-1-0  - WINS!! */
}

html {
  color: green; /* 0-0-1 */
}
```

Inline 

Всегде всегда будет самым специфичным ```1-0-0-0```, перебить может только ```!important```

## Important
Important не имеет ничего общего специфичностью, он напрямую меняет каскадный порядок таблиц

Если в вашем источнике есть два одинаковый селектора и один из них имеет свойство с пометкой !important, то селективность уже не важна

Использование !important для переопределения специфичности считается плохой практикой, и его следует избегать любой ценой

Понимание специфичности и каскада может избавить от необходимости в флаге !important


## Функции
* calc
* min / max / clamp
* rgb / rgba / hsl / hsla
* var


## Units
#### Абсолютные единицы

Пример: px, pt


#### Относительные
Пример: em, rem, %, vw/vh
