# PHP - функции

Функции PHP похожи на функции других языков программирования. Функция представляет собой фрагмент кода, который принимает другой код в качестве параметра, выполняет определенную обработку и возвращает значение.

![](https://camo.githubusercontent.com/1d9a9452bb7b12c21c0fb3b9e8e380b4cc2e4a8e/68747470733a2f2f6a6f696e7468656a6f792e72752f73697465732f64656661756c742f66696c65732f696d61676563616368652f706f73745f696d6167652f2544302539312544302542352544302542372544312538422544302542432544312538462544302542442544302542442544312538422544302542395f322e706e67)

Можно рассмотреть функцию как черный ящик, в который вкладывают параметры. Ящик что-то делает, вы можете даже не знать, что именно, а потом предоставляет вам возможность работать с результатами своей работы.

Существует 2 типа функций:
1. Встроенные - это функции которые идут из коробки в PHP
2. Пользовательские - это функции которые создает программист в программе для выполнения каких-либо рутинных задач.


Функции состоят из двух аспектов:
1. Создание функции 
1. Вызов

## Создание функции PHP

Собственную PHP-функцию создать очень просто. Предположим, вы хотите создать функцию PHP, которая просто выводит короткое сообщение, когда вы ее вызываете. В следующем примере мы создаем функцию writeMessage(), а затем вызывает ее сразу после создания.

```php
<?php
    /* Определение функции  PHP  */
    function writeMessage() {
        echo 'You are really a nice person, Have a nice time!';
    }
    
?>
```

Важнейшие элементы функции:
1. Ключевое слово `function` говорит о том, что дальше будет функция.
1. После `function` следует название функции, приведенная выше называется `writeMessage`.
1. Затем следуют скобки с параметрами функции.
1. В фигурных скобках идет непосредственно тело функции



## Вызов функции

```php
<?php    /*Вызов функции PHP */
    writeMessage();
?>
```

Функции создают по несольким причинам:

1. Дать имя кусочку кода.
1. Иметь возможность вызывать один и тот же кусочек кода несколько раз.
1. Абстрагироваться от реализации какого-то решения задачи, которое уже есть.
1. Объединить несколько действий в условное "одно" действие.

В любом случае созданную (объявленную) функцию необходимо вызвать, чтобы она выполнила свою задачу. До тех пор, пока функция не вызвана, она бесполезна и ничего не делает.



## Функции PHP с параметрами

PHP дает вам возможность передавать собственные параметры внутри функции. Вы можете передать столько параметров, сколько вам нужно. Эти параметры работают как переменные внутри функции. В следующем примере мы берем два целочисленных параметра и слагаем их, а затем выводим.

```php
<?php
function addFunction($num1, $num2) {
    $sum = $num1 + $num2;
    echo "Sum of the two numbers is : $sum";
}

addFunction(10, 20);
?>
```

### Передача аргументов по ссылке

В функции можно передавать аргументы по ссылке. Это означает, что ссылка на переменную управляется функцией, а не экземпляром значения переменной.

Любые изменения, внесенные в аргумент в этих случаях, изменяют значения исходной переменной. Вы можете передать аргумент по ссылке, добавив к имени переменной амперсанд (&) либо в вызове функции, либо в определении функции. В следующем примере продемонстрированы оба случая.

```php
<?php
 function addFive($num) {
     $num += 5;
 }
 
 function addSix(&$num) {
     $num += 6;
 }
 
 $orignum = 10;
 addFive( $orignum );
 
 echo "Original Value is $orignum<br />";
 
 addSix( $orignum );
 echo "Original Value is $orignum<br />";
 ?>
```


## Функции PHP, возвращающие значение

Функция может возвращать значение с помощью оператора `return` в сочетании со значением или объектом. Return останавливает выполнение функции и отправляет значение обратно вызывающему коду. Более одного значения вы можете вернуть из функции с использованием массива return (1,2,3,4).

В следующем примере мы принимаем два целочисленных параметра и слагаем их, а затем возвращаем сумму в вызывающую программу. Обратите внимание, что ключевое слово return используется для возврата значения из функции.

```php
<?php
 function addFunction($num1, $num2) {
     $sum = $num1 + $num2;
     return $sum;
 }
 $return_value = addFunction(10, 20);
 
 echo "Returned value from the function : $return_value";
 ?>
```


## Установка для параметров функций значений по умолчанию

Вы можете установить для параметра значение по умолчанию, если вызывающий функцию объект не передает его. Следующая функция выводит NULL в случае, если в эту функцию не было передано ни одного значения.

```php
<?php
function printMe($param = NULL) {
     echo $param;
 }
 
 printMe('This is test');
 printMe();
 ?>
```

## Использование рекурсии в PHP

Рекурсивная функция – это функция, которая в своем коде вызывает саму себя.

![](https://miro.medium.com/max/750/1*appBwh6_RtvocVxwqpplHA.jpeg)

----

![](telegram-cloud-photo-size-2-5395560027630185655-x.jpg)

```php
<?php
function myRecursion($number, $increment){
    if($number > 1000){
        return $number;
    }
    $number *= $increment;
    return myRecursion($number, $increment);
}
echo myRecursion(5, 6);

?>
```




![](https://i.ytimg.com/vi/L-TffdDY1RY/maxresdefault.jpg)
