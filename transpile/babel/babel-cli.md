# Babel

## babel-cli

1. install babel-cli
	
	```
	$ npm install babel-cli --save-dev
	```
	
2. open a new file, 'es6.js' for example

	```
	const obj = { a: 1, b: 2 };
	const fun = () => 'hello world';
	const { a, b } = obj;
	```
	
3. use ./node_modules/.bin/babel
	 	
	```
	$ babel es6.js --watch --out-file es5.js
	```
	
	You'll see that nothing has been transpiled. Because, "Babel 6.x does not ship with any transformations enabled. You need to explicitly tell it what transformations to run".
4. install babel-presets
	
	```
	$ npm install babel-preset-es2015
	```
	
5. run babel with presets
	
	```
	$ babel es6.js --presets babel-preset-es2015 --watch --out-file es5.js
	```
	
6. you will see the real es5 code
	
	```
	'use strict';
	var obj = { a: 1, b: 2 };
	var fun = function fun() {
	  return console.log('hello world');
	};
	var a = obj.a;
	var b = obj.b;
	```
	
7. To see what kind of syntax sugars you've got with babel-preset-es2015, see [this page](http://babeljs.io/docs/plugins/preset-es2015/)
8. To see the staging es6 syntax, see [babel-preset-stage-3](https://babeljs.io/docs/plugins/preset-stage-3/), [babel-preset-stage-2](https://babeljs.io/docs/plugins/preset-stage-2/), [babel-preset-stage-1](https://babeljs.io/docs/plugins/preset-stage-0/) and [babel-preset-stage-0](https://babeljs.io/docs/plugins/preset-stage-0/). The babel-preset-stage-[lower] includes the syntax in babel-preset-stage-[higher]
9. To explore the staging es6 syntax, for example
	
	```
	$ npm install babel-preset-stage-0 --save-dev
	```
	
	You can use stage-0 features with
	
	```
	$ babel es6.js --presets babel-preset-es2015,babel-preset-stage-0 --watch --out-file es5.js
	```


