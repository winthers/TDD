# TDD
Tdd configuration 



# Node 

Setup for testing in node.

**Install deps**

```
$ npm i chai mocha sinon sinon-chai --save-dev
```


**package.json** *looking for testfiles with .spec.js extension in the src directory*
```
 "scripts": {
    "test": "./node_modules/.bin/mocha src/**/*.spec.js --reporter spec"
  },
 ```
 
 **run tests**
 ```
 $ npm test
 ```
  
  **example of test file**
 ```
 
var chai = require("chai");
var sinon = require("sinon");
var sinonChai = require("sinon-chai");
var expect = chai.expect;
    
chai.use(sinonChai);

describe("helloworld", () => {
  it("nothing", () => {
     var cb = sinon.spy();
     cb("foo");
     expect(cb).to.have.been.calledWith("foo");
  })
})
 
 ```
 
 
 # Vanilla
 
**Install deps**

```
$ npm i jasmine-core karma karma-chrome-launcher karma-jasmine --save-dev
```


**configure karma**

[reference](http://karma-runner.github.io/1.0/intro/configuration.html)

```
$ karma start my.conf.js
```

**example of test file**
```
describe("helloworld", ()=> {
 it("nothing", ()=> {
   var radio = { $emit: function () {}};
   spyOn(radio, "$emit");
   radio.$emit("foo");
   expect(radio.$emit).toHaveBeenCalledWith('foo');
 })
})

```

 
