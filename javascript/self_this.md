# var self=this

JavaScript functions create a new `this` such that if you want to reference the
outer `this` (the `this` of the calling object), you cannot use `this`. 

There's considerable debate about using `.bind(this)` vs. using `var self = this` 
in order to handle the unexpected ways that `this` gets bound. 

```javascript
function foo() {
  return (function() {
    doSomething((function() {
      return this.name; // what is `this` again?
    }).bind(this));
  }).bind(this);
}
```

vs.

```javascript
function foo() {
  var self = this;
  return (function() {
    doSomething((function() {
      return self.name; // `self` is easy to know because its defined 
    })
  })
}
```

Though it feels odd to me, we'll use the `var self = this` approach.

See:
* https://gist.github.com/jashmenn/b306add36d3e6f0f6483
* https://news.ycombinator.com/item?id=2476761
