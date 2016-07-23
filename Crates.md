# Example: Using a Crate

Crates are central to Tinycrate and arguably the most important part of the app. To have a good developer experience, all crate types such as **Default** or **Profile** extend the `BaseCrateVC` file.

### Crate API - `Crate.js`

In the app, just import `Crate.js` and use it in the render section. Here is the full crate API. Not every type of crate uses all these types but know that you can

```js
  <Crate
    size={80}
    color={'GREEN'}
    preview={'http://google.com'}
    type={'DEFAULT'}
    subType={'TEXT'}
    attribution={'http://i.imgur.com/UEo39LN.jpg'}
    action={'PASS_ACTION_DOWN_TO_BASE'}
    //TODO: pop={TRUE}
    />
```
