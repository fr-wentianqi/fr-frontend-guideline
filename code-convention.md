## Code Convention
- [Say What You Mean](#sayWhatYouMean)
- [Ask For What You Need](#askForWhatYouNeed)

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
