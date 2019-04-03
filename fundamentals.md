# Fundamentals
- [Essence of Mordern Web App We Build](#essence)
- [MVVM](#mvvm)

## <a name="essence" />Essence of Modern Web App We Build
Our application is mostly powered with SPA(Single Page Application) combined with backend API, where API is basically the model, SPA is consist of `View Model` and `View`. The whole paradiam is known as the MVVM(Model-View-ViewModel).

- Application
  - Backend API (Model)
  - SPA
    - View Model (State)
    - View (UI Component)
    
## MVVM
View model is the model consumed by `View`, it's usually not identical with the backend model, it adds or removes some fields for UI purpose, like if the dialog is shown or not, if the page is loading or not. `View` reflects the latest state of `View Model`, in other words, `View` is driven by `View Model` (or `State`). Take below code snippet as an example.
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
// Defined in front-end
{
  user: {
    id: 001,
    name: 'Peter',
    isLoading: false,
  },
  form: {
    userID: '',
    name: '',
    isEditing: false,
  }
}
```

- View
```jsx
// Reflects and manipulates view model
// Some code are omitted for demo

const User = (props) => {
  const { user, form } = props

  return (
    <div key={user.id}>
      <Loading loading={user.isLoading} />
      {
        form.isEditing
          ? (
            <form>
              <input name="name" value={form.name}/>
              <button>Save</button>
            </form>
          ) : (
            <div>
              <h1>{user.name}</h1>
              <button>Edit</button>
            </div>
          )
      }
    </div>
  )
}
```
