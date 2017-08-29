> # 数组的解构赋值

#### 基本用法
ES6 允许按照一定模式，从数组和对象中提取值，对变量进行赋值，这被称为解构（Destructuring)

```JavaScript
  let [a, b, c] = [1, 2, 3];
  // babel ==>
  /*
  	var a = 1,
	    b = 2,
	    c = 3;
   */
```
```JavaScript
  let [a, , b] = [1, 2, 3];
  x // 1
  b // 3
  // babel ==>
  /*
  	var _ref = [1, 2, 3],
	    a = _ref[0],
	    b = _ref[2];
   */
```
```JavaScript
  let [a, ...b] = [1, 2, 3, 4]
  a // 1
  b // [2, 3, 4]
  // babel ==>
  /*
  	var a = 1,
	    b = [2, 3, 4];
   */
```
```JavaScript
  let [a, b, ...c] = [1];
  a // 1
  b // undefined
  c // []
  // babel ==>
  /*
  	var _ref = [1],
	    a = _ref[0],
	    b = _ref[1],
	    c = _ref.slice(2);
   */
```
如果解构不成功，变量的值就等于undefined

```JavaScript
  let [a] = [];
  a // undefined
  // babel ==>
  /*
  	var _ref = [],
	    a = _ref[0];
   */
```
```JavaScript
  let [a, b] = [1];
  a // 1
  b // undefined
  // babel ==>
  /*
  	var _ref = [1],
	    a = _ref[0],
	    b = _ref[1];
   */
```
对于 Set 结构，也可以使用数组的解构赋值

```JavaScript
  let [a, b] = new Set([1]);
  a // 1
  b // undefined
  // babel ==>
  /*
  	var _ref = new Set([1, 2]),
	    _ref2 = _slicedToArray(_ref, 2),
	    a = _ref2[0],
	    b = _ref2[1];

	var _slicedToArray = function() {
		function sliceIterator(arr, i) {
			var _arr = [];
			var _n = true;
			var _d = false;
			var _e = undefined;
			try {
				for (var _i = arr[Symbol.iterator](), _s; !(_n = (_s = _i.next()).done); _n = true) {
					_arr.push(_s.value);
					if (i && _arr.length === i) break;
				}
			} catch (err) {
				_d = true;
				_e = err;
			} finally {
				try {
					if (!_n && _i["return"]) _i["return"]();
				} finally {
					if (_d) throw _e;
				}
			}
			return _arr;
		}
		return function(arr, i) {
			if (Array.isArray(arr)) {
				return arr;
			} else if (Symbol.iterator in Object(arr)) {
				return sliceIterator(arr, i);
			} else {
				throw new TypeError("Invalid attempt to destructure non-iterable instance");
			}
		};
	}();
   */
```
#### 默认值
