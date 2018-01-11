
# React Fragments

---

## Resources

- https://blog.jmes.tech/react-fragment-and-semantic-html/
- https://reactjs.org/blog/2017/11/28/react-v16.2.0-fragment-support.html

---

## No thank you 👎

```html
<body>
  <div>
    <h1>Welcome to my website!</h1>
  </div>
  <div>
   <p>
     I'm james and I absolutely love HTML
   </p>
  </div>
  <div>
    <span>Copyright me forever</span>
  </div>
</body>
```

---

## Yes please! 👍

```html
<body>
  <header>
    <h1>Welcome to my website!</h1>
  </header>
  <main>
   <p>
     I'm james and I absolutely love HTML
   </p>
  </main>
  <footer>
    <span>Copyright me forever</span>
  </footer>
</body>
```

---

## < React 16.2
### You can't do this 👎

```jsx
const Heading = props => {
  return (
    <h1>{props.title}</h1>
    <p>{props.subtitle}</p>
  )
}

ReactDOM.render(
    <Heading title="wow" subtitle="very react"/>, 
    document.getElementById("main"),
)
```

---

## < React 16.2
### You have to wrap the headings in a containing element 👍

```jsx
const Header = props => {
  return (
    <header>
      <h1>{props.title}</h1>
      <p>{props.subtitle}</p>
    </header>
  )
}

ReactDOM.render(
    <Header title="wow" subtitle="very react"/>, 
    document.getElementById("main"),
)

```

---

## So it turns into 
```html
<div>
  <h1>Todo List</h1>
  <div>
    Todo Items
    <div>
      <div>
        <h2>Todo Title</h2>
        <p>Todo Project</p>
      </div>
      <div>
        Todo Content
        <div>
          Todo Author
          Todo Date Created
        </div>
      </div>
    </div>
    <div>
      <div>
        <h2>Todo Title</h2>
        <p>Todo Project</p>
      </div>
      <div>
        Todo Content
        <div>
          Todo Author
          Todo Date Created
        </div>
      </div>
    </div>
  </div>
</div>
```

---

## React 16.2+

```jsx
const Headings = props => {
  return [<h1>{props.title}</h1>, <p>{props.subtitle}</p>]
}
```

---

## 🥁Fragment🥁

```jsx
import React, { Fragment } from "react"

const Headings = props => {
  return (
    <Fragment>
      <h1>{props.title}</h1>
      <p>{props.subtitle}</p>
    </Fragment>
  )
}
```

---

## Turns into

```html
<h1>Cool title</h1>
<h1>Cooler subtitle</h2>
```

---

## JSX Syntax

```jsx
const Headings = props => {
  return (
    <>
      <h1>{props.title}</h1>
      <p>{props.subtitle}</p>
    </>
  )
}
```
