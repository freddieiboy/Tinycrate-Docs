# Example: Using a Crate

Crates are central to Tinycrate and arguably the most important part of the app. To have a good developer experience, all crate types such as **Default** or **Profile** extend the `BaseCrateVC` file.

    # Crate Hierarchy

    // HIGHEST: API that routes defined types to Mid level
    => Crate.js

      // MID: Extends base with individual icons and styles
      -> BaseCrateVC.js
      -> LoginCrateVC.js
      -> DefaultCrateVC.js
      -> EmptyCrateVC.js
      -> ProfileCrateVC.js

          // LOWEST: Defines Crate state & base style
          -> BaseCrateVC.js

### Crate API - `Crate.js`

In the app, just import `Crate.js` and use it in the render section. Here is the full crate API. Note: Not every type of crate uses all these types.

```js
import Crate from './Crate.js';

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

#### `size={ NUMBER }`
Define the size of a crate. It's usually 80.
#### `color={ STRING }`
Define the color of a crate. Firebase/Redux returns a string name such as 'GREEN'. Use color().light/dark for the appropriate hex in CrateColors.js.
#### `preview={ URL }`
Define the top preview of the crate. BaseCrateVC automagically gives previews a borderRadius. Just pass down the URL of the image.
#### `type={ STRING }`
There are currently 4 major crate types:
  - Default
      - Normal crates exist in `CrateList` and have pop.
  - Login
      - Special crates that have Google, Facebook, Twitter logos with pops.
  - Profile
      - Exist in the `ProfilePage` and `OpenCrate` doesn't always have pop animation.
  - Empty
      - Special crate with multiple emoji's that exist in `CrateList` and has pop animation.

#### `subType={ STRING }`
Subtypes of crates that belong to the 4 major crates. This option is for further defining the type of crate that you want to use.  
  - Parent: `Default`
      - Text
      - Photo
      - Reaction
      - Notification
  - Parent: `Login`
      - Google
      - Facebook
      - Twitter

#### `attribution={ URL }`
Define attribution for a crate. This is the small photo on the bottom. Just pass the URL down and BaseCrate will take care of style and states. Currently only active for `Default`.
#### `action={ FUNCTION }`
Defines the action that will fire on `pressUp` so that each crate has a limited amount of touch handlers. Try not to wrap a crate in another touch handler.
#### `POP={ BOOLEAN }`
TODO: add pop to Tinycrate
