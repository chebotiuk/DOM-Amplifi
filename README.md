# JS library that makes DOM API more wide and useful

```js
;(function() {
	// Query sellectors
	var qs = function(css) {
		return document.querySelector(css);
	};
	var qsa = function(css) {
		return document.querySelectorAll(css);
	};

	// Create elements
	var el = function(type, props, children) {
		return document.createElement(type, props, children);
	};
	var txt = function(string) {
		return document.createTextNode(string);
	};

	// Find text on a page (returns true or false) *
	var find = function(string) {
		var result = document.documentElement.innerHTML.indexOf(string);
	  	result = (result != -1) ? true : false;
	  	return result;
	};



	// Class Replacement 
	Element.prototype.replaceClass = function(oldClass, newClass) {
		this.classList.remove(oldClass);
	  this.classList.add(newClass);
	};

	// Function check if the element included on a page body *
	Element.prototype.isInPage = function() {
		return (this === document.body) ? false : document.body.contains(this);
	};

	window.dom = {
		qs: qs,
		qsa: qsa,
		el: el,
		txt: txt,
		find: find
	};
})();
```