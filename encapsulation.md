# Encapsulation

## Why Encapsulation
Encapsulation makes a piece of code more reusable and easier to use.
```jsx
// We want a generic custom text input field component
// with some additional features that the native one does not provide

import { TextField } from 'some-ui-lib'

export const CustomTextField = () => {
  return (
    <div
      key={props.key}
      className={props.className}
      style={props.style}
    >
      <TextField
        value={props.value}
        defaultValue={props.defaultValue}
        placeholder={props.placeholder}
      />
      

      {
        // Counting the current length of input characters when a max length constrain is set
        maxLength && (
          <div>
            {props.value.length}/{props.maxLength}
          </div>
        )
      }
    </div>
  )
}
```

Then we can use the new `CustomTextField` as easy as follows.
```jsx
import { CustomTextField } from 'custom-components'

export App extends React.Component {
  render () {
    return (
      <div>
        <CustomTextField
          className="text-field"
          value="some value"
          defaultValue="some default value"
          placeholder="please input"
          maxLength={100}
        />
      </div>
    )
  }
}
```

## Tips For Encapsulating
- Minimum changing to the API from the original component
> This assumes the native component is designed quite reasonable, the minimum changing to the schema of the original component makes it the most comfortable for users to use the encapsulated one.
```ts
// props of the source component
interface sourceComponentOwnProps {
  isDisabled: boolean;
  color: 'primary' | 'secondary';
  size: 's' | 'm' | 'l';
}

// Good
// props of the new encapsulated component extends the original props interface
// and expands it with new props
interface newComponentOwnProps extends sourceComponentOwnProps {
  theme: 'void' | 'solid';
  onClick: React.ReactEventHandler<{}>;
}

// Bad
// renaming some of the original props without any beneficial or solid reason
interface newComponentOwnProps {
  clickable: boolean;
  colored: 'primary' | 'secondary';
}
```
