# Combining data types and Callbacks

## Lesson Objectives

1. Combine objects, arrays, and functions
1. Combine objects, arrays, and functions more than one level deep

## Combine objects, arrays, and functions

### 0
You can create a property for an object that is an array

```javascript
const foo = {
    someArray:[1,2,3]
};
foo.someArray[0]; //1
```

### 1
You can create a property for an object that is an object

```javascript
const foo = {
    someObject: {
        someProperty: 'oh hai!'
    }
};
foo.someObject.someProperty; //oh hai!
```

### 2
You can create a property for an object that is a function (method)

```javascript
const foo = {
    someMethod:()=>{
        console.log('oh hai');
    }
};

foo.someMethod();//logs 'oh hai!'
```

### 3
You can store an object in an array

```javascript
const foo = [{someProperty:'weee'}, 2, 3];

console.log(foo[0].someProperty);
```

### 4
You can store an array in an array

```javascript
const foo = [
    ["0,0", "0,1", "0,2"],
    ["1,0", "1,1", "1,2"],
    ["2,0", "2,1", "2,2"]
];

foo[1][2]; //1,2
```

### 5
You can store a function in an array

```javascript
const foo = [
    1,
    "hi",
    ()=>{
        console.log('fun');
    }
];

foo[2]();
```

### 6
You can loop over an array in an object

```javascript
const foo = {
    someArray:[1,2,3]
};

for(element of foo.someArray){
    console.log(element);
}

//same as above
for (var i = 0; i < foo.someArray.length; i++) {
    console.log(foo.someArray[i]);
}
```

### 7
You can loop over an array in an array.  Just add an additional [*index*] after the first [*index*]

```javascript
const foo = [
    ["0,0", "0,1", "0,2"],
    ["1,0", "1,1", "1,2"],
    ["2,0", "2,1", "2,2"]
];

for(row of foo){
    for(element of row){
        console.log(element);
    }
}

//same as above
for (let i = 0; i < foo.length; i++) {
    for (let j = 0; j < foo[i].length; j++) {
        console.log(foo[i][j]);
    }
}
```

## Combine objects, arrays, and functions more than one level deep

### 8
You can create a function that returns an object.  Just add the `.` after the `()` since the return value of the function is an object

```javascript
const foo = ()=>{
    return {
        someProperty: 'hi!'
    }
};

foo().someProperty;//hi
```

### 9
You can create a function that returns an array.  Just add `[index]` after the `()` since the return value of the function is an array

```javascript
const foo = ()=>{
    return ['apple','banana','pear'];
};

foo()[1]; //banana
```

### 10
You can create a function that returns an object that has an array

```javascript
const foo = ()=>{
    return {
        someArray: ['fun', 'awesome', 'sweet']
    }
};

foo().someArray[1]; //awesome
```

### 11
You can create a function that returns an object that has an object

```javascript
const foo = ()=>{
    return {
        someObject: {
            someProperty: 'some value'
        }
    }
};

foo().someObject.someProperty; //some value
```

### 12
You can create a function that returns an object that has a method

```javascript
const foo = ()=>{
    return {
        someMethod:()=>{
            console.log('oh hai!');
        }
    }
};

foo().someMethod(); //logs 'oh hai!'
```

### 13
You can create a function that returns a function.  Just add the `()` after the first `()` since the return value of the first function is another function

```javascript
const foo = ()=>{
    return ()=>{
        console.log('whaaaa?');
    }
};

foo()(); //logs 'whaaaa?'
```

### 14
You can create an object that has a method that returns an object

```javascript
const foo = {
    someMethod:()=>{
        return {
            someProperty: 'some value'
        }
    }
};

foo.someMethod().someProperty;
```

### 15
You can create an object that has a method that returns an object that has an array

```javascript
const foo = {
    someMethod:()=>{
        return {
            someArray: ['peach', 'apple', 'pear']
        }
    }
}

foo.someMethod().someArray[2]; //pear
```

### 16
You can create an object that has a method that returns an object that has an object

```javascript
const foo = {
    someMethod:()=>{
        return {
            someObject: {
                someProperty: 'some value'
            }
        }
    }
}

foo.someMethod().someObject.someProperty; //some value
```

### 17
You can create an object that has a method that returns an object that has another method

```javascript
const foo = {
    someMethod:()=>{
        return {
            someMethod:()=>{
                console.log('both methods can have the same name!');
            }
        }
    }
}

foo.someMethod().someMethod(); //logs 'both methods can have the same name!'
```

### 18
You can create an object that has a method that returns a function

```javascript
const foo = {
    someMethod:()=>{
        return ()=>{
            console.log('hi')
        }
    }
}
foo.someMethod()();//logs hi
```

### 19
You can create an array that has a function that returns an object

```javascript
const foo = [
    1,
    'apple',
    ()=>{
        return {
            someProperty: 'some value'
        }
    }
];

foo[2]().someProperty; //some value
```

### 20
You can create an array that has a function that returns an object that has an array

```javascript
const foo = [
    1,
    'apple',
    ()=>{
        return {
            someArray: ['cat', 'dog', 'baboon']
        }
    }
];

foo[2]().someArray[2]; //baboon
```

### 21
You can create an array that has a function that returns an object that has an object

```javascript
const foo = [
    1,
    'apple',
    ()=>{
        return {
            someObject: {
                someProperty: 'some value'
            }
        }
    }
];

foo[2]().someObject.someProperty; //some value
```

### 22
You can create an array that has a function that returns an object that has a method

```javascript
const foo = [
    1,
    'apple',
    ()=>{
        return {
            someMethod:()=>{
                console.log('fun');
            }
        }
    }
];

foo[2]().someMethod(); //logs fun
```

### 23

You can create an array that has a function that returns a function

```javascript
const foo = [
    1,
    'apple',
    ()=>{
        return ()=>{
            console.log('yes!');
        }
    }
];

foo[2]()(); //logs yes!
```

---

*Adapted from [SEI-MAE](https://git.generalassemb.ly/Software-Engineering-Immersive-Remote/SEIR-MAE-INSTRUCTORS/blob/master/unit_1/w03d3/instructor_notes/2.%20Combining%20Data%20Types.md)*