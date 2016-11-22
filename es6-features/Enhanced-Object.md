# Object对象扩展

Object扩展支持在构建函数中使用foo:foo简写对原型赋值，定义方法和调用超类方法。这使用object关键字与类定义更加接近，同时也更便于面向对象设计。

```js
var obj = { 
    // Sets the prototype. "__proto__" or '__proto__' would also work. 
    __proto__: theProtoObj, 
    // Computed property name does not set prototype or trigger early error for 
    // duplicate __proto__ properties. 
    ['__proto__']: somethingElse, 
    // Shorthand for ‘handler: handler’ 
    handler,
    // Methods 
    toString() { 
        // Super calls 
        return "d " + super.toString(); 
    }, 
    // Computed (dynamic) property names 
    [ "prop_" + (() => 42)() ]: 42 
};

```

