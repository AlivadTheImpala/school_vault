---
tags:
  - braindump
  - javascript
  - "#template"
created: 2025-02-13T22:29:00
---
# Components
React is made up of components. A component is a self contained item. I like to think of it like a modular piece of equipment. Imagine your working on a custom car build one component can be the chasis itself, or if you're further along in the build, a switch that controls the lights. 

# JSX 
React uses JSX which looks a lot like plain html, but it isnt html. The React documentation explain the anatomy of a component made with JSX well. 

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