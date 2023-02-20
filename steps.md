# first

 how to use a component in vue

  1. import the component in the script tag
  2. add the component to the components object in export default.-backdrop-hue-rotate-15
  3. use the component in the template
  ##How to bind data to a component:
  1. add a prop to the component example props : ['score'].
  2. add the prop to the component tag example
  **<HelloWorld :score="score" >
  What is a prop?
  A prop is a property that is passed to a component from the parent component.
  What is a component?
  A component is a reusable piece of code that can be used in multiple places.
  What is a template?
  A template is the html that is used in the component.
  What is a script?
  A script is the javascript that is used in the component.
  What is a style?
  A style is the css that is used in the component.
  What is a vue router?
  A vue router is a router that is used to navigate between pages in a vue application. examples:
  <RouterLink to="/">Home</RouterLink>
  <RouterLink to="/about">About</RouterLink>
  How to use a vue router?
  1. import the vue router in the script tag
  2. add the vue router to the components object in export default
  3. use the vue router in the template
  What is a vue router view?
  A vue router view is a component that is used to display the content of the current page.
  How to use a vue router view?
  1. import the vue router view in the script tag
  2. add the vue router view to the components object in export default
  3. use the vue router view in the template
  What is a vue router link?
  A vue router link is a component that is used to navigate between pages.
  How to use a vue router link?
  1. import the vue router link in the script tag
  2. add the vue router link to the components object in export default
  3. use the vue router link in the template
  What is a vue router link active class?
  How to create a custom events in vue?
  1. add the emits object to the export default object example emits: ['end']
  2. add the event to the component tag example @end="endGame"
  3. add the event to the component script example this.$emit('end', this.reactionTime)
  What is $emit?
  $emit is a function that is used to emit a custom event.
  What is ref?
  Ref is a property that is used to get a reference to an element in the template.
  How to use ref?
  1. add the ref property to the element in the template example ref="enable"
  2. get the reference to the element in the script example this.$refs.enable
  What is $refs?
  $refs is a property that is used to get a reference to an element in the template.
  What is a computed property?
  A computed property is a property that is calculated from other properties.
  calculated from other properties? means that the computed property is calculated from the other properties in the component
  an example of a computed property is the score property in the HelloWorld component that is calculated from the reactionTime property.

  How to use a computed property?

  1. add the computed object to the export default object example computed: { score() { return this.reactionTime } }
  2. use the computed property in the template example {{ score }}

  what is setup?
  setup is a function that is used to setup the component.it is called before the component is created.
  How to use setup?

  1. add the setup function to the script tag example setup() { return { score: 0 } }
  2. use the setup function in the template example {{ score }}

  What is a reactive object?
  A reactive object is an object that is used to store data that is used in the component.
  How to use a reactive object?

  1. add the reactive function to the setup function example const score = reactive({ score: 0 })
  2. use the reactive object in the template example {{ score.score }}
