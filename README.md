# V.js
By Joel Dies

V.js was built to help with prototyping. Practcal use for production isnt what this library is meant for. Rather it is designed in a way to help with scaffolding and prototyping. This was built for when you do not have a backend template engine or you are not wanting to have to configure a bunch of javascript libaries. Its simple, effecient and requires no knowledge other than HTML so this is great for people who are not developers, or for developers who want to quickly prototype a project.

With that this can also be used to pass parameters to javascript and use them in code without to much effort, and you can access the variables with little effort using the built in functions.

[Demo](http://codepen.io/phreaknation/pen/XRgZNX?editors=1000)


**This is not 100% documented but is on its way to being 100% documented.**

Help support these efforts by becoming a [Patreon](https://www.patreon.com/diesoft)

## Including in a project
Include the script into your html page.



## Options:

Term | Object Type | Default Value | Definition
--- | --- | --- | ---
data-addTypeClass | {boolean} |  | Overrides the addTypeClass value on a single variable display element.
data-ns | {string} |  | Allows simple namespacing of variables.
data-set | {string} |  | REQUIRED. Name to save the value under.
data-get | {string} |  | REQUIRED. The value to return. Can, and must be used in conjunction with data-ns if data-ns was used to set the value.
data-type | {string} | string | Type of object to save as. Options are 'string', 'number', 'boolean'
data-value | {string-number-boolean} |  | Value to save. Not required.



## Methods:
Term | Definition
--- | ---
set(name, value, type, ns, el) | Sets a variable.
_ | @param {string} name - Name of the varible to set.
_ | @param {string} value - Value to be set.
_ | @param {(boolean|number|string)} [type=string] - description
_ | @param {string} [ns] - Namespace of the variable
_ | @param {node} [el] - Element to render to.
get(name, ns) | Gets a set variable.
_ | @param {string} name - Name of the varible to set.
_ | @param {string} [ns] - Namespace of the variable
render(el, v) | Renders an element with the variable data.
_ | @param {node} [el] - Element to render to.
_ | @param {object} v - Var data in its proper format.



## Supported types
This is a current list of supported type. Over time I will be adding support for other types.
* Boolean
* Number
* String



## Example:

### Verbose errors
If you wish to have loud errors I have provided some css for just that
```css
.v.error {
  background-color: #f0f000;
  border: 2px solid #f00000;
  color: #f00000;
  padding: 2px 4px;
}
```
### Hide errors
If you wish to not show any errors, this would be the css needed.
```css
.v.error {
  display: none;
}
```

### Setting variables

```html
<var data-ns="hello" data-set="world" data-type="string" data-value="Hello World"></var>
<var data-ns="myvars" data-set="test" data-type="number" data-value="12345"></var>
<var data-ns="asdf" data-set="string" data-value="This value is"></var>
<var data-ns="asdf" data-set="result" data-type="boolean" data-value="false"></var>
```

### Displaying variables

```html
<span data-ns="hello" data-get="world"></span>

<div data-ns="myvars" data-get="test"></div>

<div>
  <span data-ns="asdf" data-get="string"></span>: 
  <span data-ns="asdf" data-get="result"></span>.
</div>

<!-- This will cause an error to be displayed -->
<div data-get="err"></div>
```
