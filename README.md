# JavaScript Best Practice Guide

## т.е. лучшие и давно устоявшиеся практики о том, как красиво и правильно кодить на JavaScript.

### 1. Названия объектов языка должны отражать их значение/функции
Названия переменных должны отражать тип значения и контекст, в котором они будут использоваться.
Названия функций должны отражать их назначение или получаемый результат.

**Bad practice**

``` js
  const a = 10;
  const anotherString = '...';
  const human = true;
  const date = () => {
    const currentTime = new Date();
    return currentTime;
  }
```

**Good practice**

``` js
  const length = 10;
  const thirdString = '...';
  const isHuman = true;
  const getDate = () => {
    const currentTime = new Date();
    return currentTime;
  }
```

### 2. Использовать camelCase для названий переменных, объектов и функций.

**Bad practice**
``` js
  const newlength = 10;
  function getNEWlength() {}
```

**Good practice**
``` js
  const newLength = 10;
  function getNewLength() {}
```
### 3. Используйте PascalCase для именования конструкторов или классов.

**Bad practice**
``` js
  function user(props) {
    this.name = props.name;
  }
  const john = new user({
    name: 'Olga',
  });
```

**Good practice**

``` js
  class User {
    constructor(props) {
      this.name = props.name;
    }
  }
  const mike = new User({
    name: 'Olga',
  });
```

### 4.Объявление переменных
Для объявления переменных следует всегда использовать `let` или `const`.
Если переменная не переназначается - следует использовать `const`.

**Bad practice**

``` js
  var value = 10;
  const response = 'Ok';
  newClass = new customClass();
  
  response = "Not ok";
```

**Good practice**

``` js
  const value = 10;
  let response = 'Ok';
  const newClass = new customClass();
  response = "Not ok";
```

### 5. Точка с запятой

Каждая инструкция должна заканчиваться точкой с запятой.

**Bad practice**

```js
  let luke = {}
  let leia = {}
  [luke, leia].forEach(jedi => jedi.father = 'vader')
```

**Good practice**

```js
  let luke = {};
  let leia = {};
  [luke, leia].forEach((jedi) => {
    jedi.father = 'vader';
  });
```

### 6. Для всех многострочных блоков следует использовать фигурные скобки

**Bad practice**

```js
  if (test)
  return false;
  function foo() { return false; }
```

**Good practice**

```js
  if (test) return false;
  function foo() {
    return false;
  }
```

### 7. При использовании конструкции if .. else else следует располагать на одной строке со скобкой закрывающей блок if.

**Bad practice**

```js
  if (ans === true) {
    alert('wow');
    congrats();
  }
  else {
    tryAgain();
  }
```

**Good practice**

```js
  if (ans === true) {
    alert('wow');
    congrats();
  } else {
    tryAgain();
  }
```

### 8. Объекты (в том числе и массивы) следует объявлять через фигурные скобки

**Bad practice**

```js
  const user = new Object();
  const cars = new Array();
```

**Good practice**

```js
  const user = {};
  const cars = [];
```

### 9. Каждое новое свойство следует писать с новой строки

**Bad practice**

```js
  const user = { firstName: "Olga", age: 23 }
```

**Good practice**

```js
  const user = {
    firstName: "Olga",
    age: 23,
  }
```

### 10. Рекомендуется использовать одиночные кавычки (''), либо обратные (``) при использовании шаблонных строк

**Bad practice**

```js
  const username = "Roman";
```

**Good practice**

```js
  const username = 'Roman';
  const greeting = `Oh hi ${username}!`
```

### 11. Следует использовать строгое сравнение (=== или !==) вместо нестрогого (== или !=)
Это позволит избавиться от неявного преобразования типа данных.

**Bad practice**

```js
  if (answer == 4) {
    console.log(true);
  }
  if (attempts != 0) {
    console.log('Ты пытался')
  }
```

**Good practice**

```js
  if (answer === 4) {
    console.log(true);
  }
  if (attempts !== 0) {
    console.log('Ты пытался')
  }
```

### 12. Следует использовать отступ 2 пробела
Также можно настроить tab на 2 пробела

**Bad practice**

```js
  if (answer == 4) {
     console.log(true);
  }
  if (attempts != 0) {
   console.log('Ты пытался')
  }
```

**Good practice**

```js
  if (answer === 4) {
    console.log(true);
  }
  if (attempts !== 0) {
    console.log('Ты пытался')
  }
```

#_*THE END*_