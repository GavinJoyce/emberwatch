---
title: Adding CSS classes to your components based on properties
section: Cookbook
cookbook-section: User Interface and Interaction
layout: cookbook-recipe
---
<span class="recipe-label">Recipe:</span>
## {{ page.title }}
-----
### Problem
You want to add or remove CSS class names to your Ember Components based on properties of the component.

### Solution
Add property names to the `classNameBindings` property of subclassed components.

### Discussion

You can apply classes based on properties of the component, or even by properties bound to data passed into the component. This is done by binding the class attribute using `classNameBindings`.

```js
classNameBindings: ['active'],
active: true
```

You can also set the class name based on a computed property.

```js
classNameBindings: ['isActive'],
isActive: Ember.computed('someAttribute', function() {
  return 'active';
})
```

Another way would be to bind the class name to a bound property.

```js
classNameBindings: ['isRelated:relative'],
isRelatedBinding: "content.isRelated" // value resolves to boolean
```

<!--- #### Example

<a class="jsbin-embed" href="http://jsbin.com/jogizaqepe/2/embed?live">JS Bin</a>

See [Customizing a Component's Element](../../components/customizing-a-components-element/) for further examples. -->
