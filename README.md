In the lesson on while loops, we learned how to use a while loop to display numbers 0 through 10. We started with a integer that we increased each cycle of the loop, and then switched to displaying the numbers from an array. To recap, here's what the code looks like for displayign each number from an array.

_displaying 0 through 10 from an array_
```javascript
//our array of numbers 0 through 10
var array = [0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10];

//our variable for tracking position in the array
var index = 0;

//loop while `index` is less than or equal to `array.legnth`
while(index <= array.length){
    //using indexing to get the next item from the array
    console.log(array[index]);

    //increase the position so we can get the next item in the array
    index = index + 1;
}
```

So what would happen if we changed what's inside the array? What if we made all the items strings rather than numbers.

```javascript
var array = ["a", "b", "c", "d"];
var index = 0;

//change `<=` to `<`
while(index < array.length){
    console.log(array[index]);
    index = index + 1;
}
```
It's no longer displaying numbers, but we're still displaying each item in the array. So what if we had an array of objects?

```javascript
var object1 = {};
var object2 = {};
var object3 = {};

object1.x = 1;
object2.x = 2;
object3.x = 3;

var array = [object1, object2, object3];
var index = 0;

while(index < array.length){
    console.log(array[index]);
    index = index + 1;
}
```

Still displays everhything one item at a time. So what if we had an array of sprites?

```javascript
//function that creates and returns a sprite
function createSprite(){
    var sprite = {};
    sprite.position = {};

    return sprite;
}

//use `createSprite` to create three sprites 
var sprite1 = createSprite();
var sprite2 = createSprite();
var sprite3 = createSprite();

var array = [sprite1, sprite2, sprite3];
var index = 0;

while(index < array.length){
    console.log(array[index]);
    index = index + 1;
}
```

Still works. But can we do things other than display what's inside the array? Absolutely! We can rewrite the code inside the curly brackets (`{}`) to do whatever we want. So what other kinds of problems could we solve with arrays and while loops? Let's take a look at a common problem that while loops can help with.

```javascript
var x0 = 1;
var x1 = 1;
var x2 = 1;
var x3 = 1;

x0 = x0 + 1;
x1 = x1 + 1;
x2 = x2 + 1;
x3 = x3 + 1;
```

In the example above, we have four variables `x0` through `x3`. Each variable has a value of 1, and later we increase each variable by 1. Notice how the code looks really similar? Almost the same? 

    1. All of the variable names start with 
    2. All of the variables names end with unique integers which increase by 1

Both are good signs that we could replace the individual variables with an array: (1) might be a good variable name and (2) is a good idea for where each variable should be placed in the array. We can use a table to help us plan everything out.

|variable name|position in the array|
|------------:|--------------------:|
|`x0`         |0                    |
|`x1`         |1                    |
|`x2`         |2                    |
|`x3`         |3                    |

So let's update the code by creating an array, and adding all the variables to the array.

```javascript
var x0 = 1;
var x1 = 1;
var x2 = 1;
var x3 = 1;
var array = [x0, x1, x2, x3];

x0 = x0 + 1;
x1 = x1 + 1;
x2 = x2 + 1;
x3 = x3 + 1;
```

So we have an array, but we're not using it. But, we can fix that by looking at code that's still really similar. What about how we update each variable? We're increassing each variable by the same amount, 1. We've learned that we can use while loops with arrays when we want to perform the same action with each item. Does this mean we could use an array and a while loop to increase each variable by 1? Let's say we create another variable to keep track of the position in the array. Like in the other examples, we'll call it `index`. And what if we use `index` to get each value and increase it by 1?

|`index`|`array[index]`|`array[index] += 1`|
|------:|-------------:|------------------:|
|0      |1             |2                  |
|1      |1             |2                  |
|2      |1             |2                  |
|3      |1             |2                  |

And let's use the table to update the code. We learned in the previous lesson how to use `index` and the array's length to create a condition (`index < array.length`) where the while loop cycles through all the items in the array. 

```javascript
var x0 = 1;
var x1 = 1;
var x2 = 1;
var x3 = 1;
var array = [x0, x1, x2, x3];
var index = 0;

while(index < array.length){
    array[index] += 1;
}
```

Success! And if we look at the code more, do we really need `x` variables? Instead of assigning 1 to each `x` variable, could we just add the values directly to the array?

```javascript
var array = [1, 1, 1, 1];
var index = 0;

while(index < array.length){
    array[index] += 1;
}
```

Looks like we can. So now that we've learned how to create while loops, use them with arrays, and how to rewrite code to use arrays and while loops, we now know everything we need to improve the squares code from a previous lesson.