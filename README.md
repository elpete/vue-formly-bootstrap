#vue-formly-bootstrap
A plugin for [Vue Formly](https://github.com/matt-sanders/vue-formly) which adds multiple form fields according to Twitter Bootstrap.

##Installation
```
npm install vue-formly-bootstrap
```
or if you can just include the script:
```html
<script src="/path_to_folder/vue-formly-bootstrap/dist/vue-formly-bootstrap.js"></script>
```

##Usage
```js
import VueFormly from 'vue-formly';
import VueFormlyBootstrap from 'vue-formly-bootstrap';
Vue.use(VueFormly);
Vue.use(VueFormlyBootstrap);

let vm = new Vue({
   el: '#app',
   data: {
      form: {
         name: {
            type: 'input',
            label: 'Your name'
         },
         sex: {
            type: 'select',
            label: 'Sex',
            options: ['Male', 'Female']
         },
         comments: {
            type: 'textarea',
            label: 'Comments'
         }
      }
   },
   methods: {
      doSomething: function(){}
   }
});
```
```html
<div id="el">
   <formly-form :form="form" @submit="doSomething">
      <button>Submit</button>
   </formly-form>
</div>
```
If you include the script it will be installed for you.

Note that this is still a work in progress so some fields are under construction. See the To Do section for what's on the watchlist.

##Options

###Global options
These options are used by all the different field types. Some fields may have special options and these will be specified below.

| Property | Type | Default | Description |
| --- | --- | --- | --- |
| $dirty | `boolean` | `false` | ***RESTRICTED*** This is set by the system and is just there for your reference. It gets set to `true` upon blur or change, whichever happens first. |
| $active | `boolean` | `false` | ***RESTRICTED*** Also set by the system and is set to true on focus. |
| onBlur | `function(e)` | `null` | A function to run on @blur event |
| onFocus | `function(e)` | `null` | A function to run on @focus event |
| onClick | `function(e)` | `null` | A function to run on @click event |
| onChange | `function(e)` | `null` | A function to run on @change event |
| onKeyup | `function(e)` | `null` | A function to run on @keyup event |
| onKeydown | `function(e)` | `null` | A function to run on @keydown event |
| atts | `object` | `null` | Pass an object of attributes to be added to the element. eg `{ placeholder: 'hello world' }` |
| classes | `object` | `null` | Pass an object of classes to be added to the element. Follows the Vue bindings where each key matches a boolean value. eg `{ 'class-a': true, 'class-b': false }` In this case class-a will be attached. |
| id | `string` | `null` | An ID string to attach to the element |


###Input options

| Property | Type | Default | Description |
| --- | --- | --- | --- |
| inputType | `string` | `text` | The 'type' attribute to pass to the input. |


###Select options

| Property | Type | Default | Description |
| --- | --- | --- | --- |
| options | `array` | `null` | Pass either an array of strings or objects. Objects require a `label` and `value` property. If a string is passed then it will be used for the value and the label. eg: `options: ['Foo', 'Bar']` or `options: [{ label: 'Foo', value: 'bar'},{label: 'Bar', value: 'foo'}] |

##To Do
* [x] Input
* [x] Select
* [x] Text Area
* [ ] Checkbox
* [ ] Radio Buttons
* [ ] Date Picker
* [ ] Other funky form inputs
* [x] Dirty/Clean checking
* [ ] Hide/Show options
* [x] Custom attributes
* [x] Custom Classes
* [x] Custom events