```javascript
undefined==null //true; takes undefined and null both as false so false==false => true;
undefined===null //false; // strict checking 
2=='2'//true;
2==='2'//false;
NaN==NaN //false;
NaN===NaN//false;
null==null//true;
null===null//true;
undefined==undefined//true;
undefined===undefined//true;
[]==[] //false; address of both the objects are different so ans is false.
{}=={} //false as memory address is different.
```

```javascript
5 && 2 && 3 || 3 && 5 => 3 || 5 // 3
// && will give last true output if it gets any 0 than overall output is 0.
// || will give first true value.
5 && 5>4 // true
```

```java
var arr=[1,2,3,4,5];
for(var i=0;i<arr.length;i++)
{
    setTimeOut(()=>console.log(arr[i],i),i*1000);
}
// for loop will run so fast and now value of i is 5 and all the five setTimeOut are waiting in the queue. when they will come out of queue they will see i as 5 and now arr[5] is undefined. 
// undefined 5
// undefined 5
// undefined 5
// undefined 5
// undefined 5
```

```java
var arr=[1,2,3,4,5];
for(let i=0;i<arr.length;i++) // here we have used let in place of var.
{
    setTimeOut(()=>console.log(i),i*1000);
}
    0
    1
    2
    3
    4
```

```java
var arr=[1,2,3,4,5];
for(let i=0;i<arr.length;i++) // here we have used let in place of var.
{
    setTimeOut(function(i)
    {
      return console.log(i) // concept of closure. function has stored the value of i
    }(i), i*1000);
}
    0
    1
    2
    3
    4
```

**Closure and currying::**Read about it.

**Debouncing and Throttling**