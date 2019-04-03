# Fundamentals
- [Essence of Mordern Web App We Build](#essence)
- [Architecture](#architecture)
- [Say What You Mean](#sayWhatYouMean)
- [Ask For What You Need](#askForWhatYouNeed)

## <a name="essence" />Essence of Modern Web App We Build
Our application is mostly powered with SPA(Single Page Application) combined with backend API.

- Application
  - Backend API
  - SPA
    - View Model
    - View

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
