example
=======

The dog style, or dog "pattern" is a practical way of writing JavaScript (EcmaScript) 
that affords clean modular coding practices that make it easy for others to read and adapt. This style
of writing code takes advantage of Javascript's scoping, and allows you to develop code in tandem with
Chrome's console to rapidly build pages in a testable way.

```JavaScript

function SomeFunction($obj, options) {

  options = options || { }
  options.someOption = options.someOption || 42

  var dog = {
    options : options
    , $obj : $obj
    , $someThingCool : undefined
  }
  
  function events() {
    dog.$someThingCool.click(function() {
      console.log("you just clicked me")
    })
  }
  
  function init() {
    dog.$someThingCool = $obj.find(".somethingCool")
  }
  
  init()
  
  return dog
}


$(document).ready(function() {
  someFunction = SomeFunction($("#myBox"), {  someOption : 21  })
})


```
