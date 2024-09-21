# JavaScript Closures: House and Ball Example

A **closure** allows a function to "remember" variables from its outer scope even after the outer function has returned.

### House and Ball Analogy
- **House (Outer Function):** Creates a variable (ball).
- **Person (Inner Function):** Captures the ball and can play with it, even after the house is closed.

### Example

```javascript
function house() {
    let ball = 10;  // Outer function (house) creates a ball
    return function() {  // Inner function (person) captures the ball
        console.log(ball);  // The person can still use the ball
    };
}

const person = house();  // Outer function returns the inner function
person();  // Even after the house is closed, the person can play with the ball (prints 10)
```
# shallow vs deep copy

In JavaScript, when you assign an object to a new variable, you are creating a reference to the original object rather than a copy.
This means that if you modify the new variable (the assigned object), the original object will also reflect those changes, as both variables point to the same memory location.

## Object Assignment and References

### Shallow Copy
When you assign an object like this:

```javascript
const obj1 = { key: 'value' };
const obj2 = obj1;
obj2.key = 'newValue';
console.log(obj1.key); // Outputs: 'newValue'
```


Here, obj2 is a reference to obj1, so modifying obj2 also modifies obj1.
Nested Objects
For nested objects, the same reference behavior applies. If you change a property of a nested object through the new variable,
it will affect the original object:

```javascript
const nestedObj1 = { inner: { key: 'value' } };
const nestedObj2 = nestedObj1;
nestedObj2.inner.key = 'newValue';
console.log(nestedObj1.inner.key); // Outputs: 'newValue'
```
Objects in JavaScript are assigned by reference, meaning that when you assign an object to another variable, both variables refer to the same underlying object in memory.
Therefore, any changes made through one variable will be reflected in the other.

If you want to modify a nested property without affecting the original object, you need to create a deep copy of the object.
This can be done using methods like JSON.parse(JSON.stringify(obj)) or libraries such as Lodash's _.cloneDeep().
For example:

```javascript
const original = { inner: { key: 'value' } };
const copy = JSON.parse(JSON.stringify(original));
copy.inner.key = 'newValue';
console.log(original.inner.key); // Outputs: 'value', remains unchanged
````
In summary,
assigning objects in JavaScript creates references, and modifications to these references will affect the original object, including its nested properties. To avoid this, a deep copy is necessary.
