# How to loop JSX in React

* **Blog post**: https://edvins.io/how-to-loop-jsx-in-react/

## Snippet #1

```jsx
import React from "react";

const languages = ["JavaScript", "Java", "TypeScript"];

const List = ({ children }) => <ul>{children}</ul>;

const ListItem = ({ language }) => <li>{language}</li>;

const App = () => (
  <List>
    {languages.map((language, index) => (
      <ListItem key={index} language={language} />
    ))}
  </List>
);

export default App;
```

## Snippet #2

```jsx
import React from "react";

const languages = ["JavaScript", "Java", "TypeScript"];

const List = ({ children }) => <ul>{children}</ul>;

const ListItem = ({ language }) => <li>{language}</li>;

const listItems = languages.map((language, index) => (
  <ListItem key={index} language={language} />
));

const App = () => <List>{listItems}</List>;

export default App;
```
