# Error Boundaries in React

* **Blog post**: https://edvins.io/error-boundaries-in-react/

## Snippet

```jsx
class ErrorBoundary extends React.Component {
  constructor(props) {
    super(props);
    
    this.state = { 
      hasError: false 
    };
  }

  static getDerivedStateFromError(error) {
    return { hasError: true };
  }

  componentDidCatch(error, info) {
    // do some logging here..
  }

  render() {
    if (this.state.hasError) {
      return <h1>Oops! Something went wrong.</h1>;
    }

    return this.props.children; 
  }
}
```
