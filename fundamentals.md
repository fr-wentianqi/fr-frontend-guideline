# Fundamentals
- [Essence of Mordern Web App We Build](#essence)
- [Say What You Mean](#sayWhatYouMean)
- [Ask For What You Need](#askForWhatYouNeed)

## <a name="essence" />Essence of Modern Web App We Build
Our application is mostly powered with SPA(Single Page Application) combined with backend API, where API is basically the model, SPA is consist of `View Model` and `View`. The whole paradiam is known as the MVVM(Model-View-ViewModel).

- Application
  - Backend API (Model)
  - SPA
    - View Model ()
    - View (UI Component)
    
## View Model
View model is the model consumed by `View`, it's usually not identical with the backend model, it adds or removes some fields for UI purpose, like if the dialog is shown or not, is the page is loading or not. `View` reflects the latest state of `View Model`, in other words, `View` is driven by `View Model`. Take below code snippet as an example.
- Model
```js
// User table, defined in backend reflecting how data looks like
{
  id: string,
  name: string,
}
```

- View Model
```js
// Defined in front-end, usually stored as state
{
  user: {
    id: 001,
    name: 'Peter',
    isLoading: false,
  },
  form: {
    id: '',
    name: '',
    isEditing: true,
  }
}
```

- View
```jsx
// Reflects and manipulates view model
class UserPanel extends React.Component {
  render() {
    const { user, form } = this.props
    
    return (
      <div key={id}>
        <LoadingIcon loading={user.isLoading} />
        {
          form.isEditing
            ? (
              <form>
                <input type="text" value={form.name} />
                <button type="submit">Save</button>
              </form>
            ) : (
              <h1>{user.name}</h1>
            )
        }
      </div>
    )
  }
}
```


## <a name="sayWhatYouMean" />Say what you mean
- Code should be as much self-explained, declarative and concise as possible.
```js
// Array inclusion checking
// Bad
someArray.indexOf(item) !== -1 // The original intention of indexOf is to see where the item is

// Good
someArray.includes(item)
```

## <a name="askForWhatYouNeed" />Ask For What You Need
