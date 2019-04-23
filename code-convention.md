## Code Convention
- [Commas/Semicolons](#commas-semicolons)
- [Naming Conventions](#naming-conventions)
- [Say What You Mean](#sayWhatYouMean)
- [Ask For What You Need](#askForWhatYouNeed)

## <a name="commas-semicolons" />Commas/Semicolons
- Additional trailing comma: Yes
> Why? This leads to cleaner git diffs. Also makes adding/removing properties more convenient.
```diff
// Bad, without traling comma
const obj = {
     foo: '',
-    bar: ''
+    bar: '',
+    yah: ''
};

// Good, with traling comma
const obj = {
     foo: '',
     bar: '',
+    yah: '',
};
```

## <a name="naming-conventions" />Naming Conventions
- Boolean: `isXXXX`
```ts
const isVisible: boolean = true
```

- Function/Method: `verb + [target]`
```ts
// Good
function getNextPossibleStatus() {}
handleSubmit = () => {}

// Not very good
function nexPossibleStatusGetter() {}
submitHandler() {}

// Bad
function nextPossibleStatus() {}
submission = () => {}
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
