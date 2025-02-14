---
tags:
  - braindump
  - javascript
  - "#template"
created: 2025-02-13T22:29:00
---
# Components
React is made up of components. A component is a self contained item. I like to think of it like a modular piece of equipment. Imagine your working on a custom car build one component can be the chasis itself, or if you're further along in the build, a switch that controls the lights. 

A component is declared like you would a normal function, but the name is capitalized. 
```JSX
//notice the capitalized name. 
function MyButton() {
  return (
    <button>
      I'm a button
    </button>
  );
}

export default function MyApp() {
  return (
    <div>
      <h1>Welcome to my app</h1>
      <MyButton />  
    </div>
  );
}
```
Here, MyButton is simply a button. The component can be used inside of another component. JSX looks like html so to use the MyButton component you wrap it in < /> tags. 
# JSX 
React uses JSX which looks a lot like plain html, but it isn't html. The React documentation explains the anatomy of a component made with JSX well. 

>[!Note]
>JSX is stricter than HTML. You have to close tags like `<br />`. Your component also can’t return multiple JSX tags. You have to wrap them into a shared parent, like a `<div>...</div>` or an empty `<>...</>` wrapper:
```JSX
function AboutPage() {
  return (
    <>
      <h1>About</h1>
      <p>Hello there.<br />How do you do?</p>
    </>
  );
}
```
Essentially a main div/empty element holds the component together. Inside are the parts that the component is made of. 


```JSX
const products = [
  { title: 'Cabbage', id: 1 },
  { title: 'Garlic', id: 2 },
  { title: 'Apple', id: 3 },
];

const listItems = products.map(product =>
  <li key={product.id}>
    {product.title}
  </li>
);

return (
  <ul>{listItems}</ul>
);
```