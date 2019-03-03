# Show and hide password in React

* **Blog post**: https://edvins.io/show-and-hide-password-in-react/

## Snippet

```jsx
import React, { Component } from "react";

class PasswordShowHide extends Component {
  constructor(props) {
    super(props);

    this.state = {
      hidden: true,
      password: ""
    };

    this.handlePasswordChange = this.handlePasswordChange.bind(this);
    this.toggleShow = this.toggleShow.bind(this);
  }

  handlePasswordChange(e) {
    this.setState({ password: e.target.value });
  }

  toggleShow() {
    this.setState({ hidden: !this.state.hidden });
  }

  componentDidMount() {
    if (this.props.password) {
      this.setState({ password: this.props.password });
    }
  }

  render() {
    return (
      <div>
        <input
          type={this.state.hidden ? "password" : "text"}
          value={this.state.password}
          onChange={this.handlePasswordChange}
        />
        <button onClick={this.toggleShow}>Show / Hide</button>
      </div>
    );
  }
}

export default PasswordShowHide;
```

## Usage

```jsx
<PasswordShowHide />
<PasswordShowHide password="12312312" />
<PasswordShowHide password={passwordVariable} />
```
