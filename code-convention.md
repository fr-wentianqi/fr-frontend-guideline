## Code Convention
- [Commas/Semicolons](#commas-semicolons)
- [Say What You Mean](#sayWhatYouMean)
- [Ask For What You Need](#askForWhatYouNeed)

## <a name="commas-semicolons" />Commas/Semicolons
- Additional trailing comma: Yes
> Why? This leads to cleaner git diffs. Also makes adding/removing properties more convenient.
```diff
const obj = {
     foo: '',
-    bar: ''
+    bar: '',
+    yah: ''
};

const obj = {
     foo: '',
     bar: '',
+    yah: '',
};
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
