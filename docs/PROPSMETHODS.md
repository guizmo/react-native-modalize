## Props

### `children`

A React component that will define the content of the modal.

Modalize is built-in with a `ScrollView` which mean you don't need to pass one.

Even though, if you need a horizontal scroll inside your modal, you can pass a `ScrollView`. But for this, you need to use the one from RNGH: `import { ScrollView } from 'react-native-gesture-handler';`.

| Type     | Required |
| -------- | -------- |
| node     | Yes      |

### `height`

A number that will enable the snapping feature and create an intermediate point before opening the modal to full screen.

The value you pass is the height of the modal before being full opened.

| Type     | Required |
| -------- | -------- |
| number   | Yes      |

### `handlePosition`

Define where the handle on top of the modal should be positioned.

| Type                      | Required | Default   |
| ------------------------- | -------- | --------- |
| enum('outside', 'inside') | No       | `outside` |

### `style`

Define the style of the modal.

| Type     | Required |
| -------- | -------- |
| style    | No       |

### `handleStyle`

Define the style of the handle on top of the modal.

?> Be aware that if you change the height of the handle, the modal height won't change. It's not dynamic yet, and it will be in the future.

| Type     | Required |
| -------- | -------- |
| style     | No      |

### `overlayStyle`

Define the style of the overlay.

| Type     | Required |
| -------- | -------- |
| style     | No      |

### `useNativeDriver`

Use the native thread by default to execute the animations.

It's not really recommanded to set it to `false`, but sometimes you don't have choice, so this option is here for that.

| Type     | Required | Default  |
| -------- | -------- | -------- |
| bool     | No       | `true`   |

### `adjustToContentHeight`

Shrink the modal to your content's height.

`Modalize` can calculate for you if your content is taller than the max height or not, if it isn't, it will adapt the height of the modal to fit your content.

| Type     | Required | Default  |
| -------- | -------- | -------- |
| bool     | Yes      | `false`  |

### `showsVerticalScrollIndicator`

Define if you want to toggle the vertical scroll indicator.

| Type     | Required | Default  |
| -------- | -------- | -------- |
| bool     | Yes      | `false`  |

### `keyboardShouldPersistTaps`

Define the behavior of the keyboard when having inputs inside the modal.

If you have any inputs inside your cont and you want to manage how to dismiss the keyboard. See [`react-native` documentation](https://facebook.github.io/react-native/docs/scrollview#keyboardshouldpersisttaps) for more informations.

| Type                               | Required | Default  |
| ---------------------------------- | -------- | -------- |
| enum('never', 'always', 'handled') | No       | `never`  |

### `withReactModal`

Define if `Modalize` has to be wrap with the Modal component from react-native.

Most of application are now using a router, either [react-navigation](https://snack.expo.io/@react-navigation/full-screen-modal-v3), [react-native-navigation](https://wix.github.io/react-native-navigation/#/docs/top-level-api?id=showoverlaylayout-) or others. On all of these libraries, there is something similar to `openOverlay` that will open a screen on top of your content. It's recommanded to wrap `Modalize` into it.

?> Since the `Modal` component from `react-native` will be move out of the core soon, it's not well maintain anymore. Besides, it doesn't work well along with `react-native-gesture-handler`. That's why the `withReactModal` props is only avaiable on iOS and not recommanded to use.

?> Examples for both react-navigation and react-native-navigation will be availables in a future version.

| Type     | Required | Default  | Platform |
| -------- | -------- | -------- | -------- |
| bool     | No       | `false`  | iOS      |

### `withHandle`

Define if the handle on top of the modal is display or not.

| Type     | Required | Default  |
| -------- | -------- | -------- |
| bool     | No       | `true`   |

### `header`

A header component outside of the ScrollView, on top of the modal.

- If your header has to be at the top of the modal, without floating on the content you pass `isAbsolute: false`
- If your header has to float on top of the content, like a close squared button, you have to `isAbsolute: true`. It will skip the height calculation of the header and avoid to change the scrollview height.

?> Don't forget to specify the `isAbsolute` props when defining an header.

| Type                                          | Required |
| --------------------------------------------- | -------- |
| object: { component: node, isAbsolute: bool } | No       |

### `footer`

A footer component outside of the ScrollView, on top of the modal.

See above for the details about the props.

| Type                                          | Required |
| --------------------------------------------- | -------- |
| object: { component: node, isAbsolute: bool } | No       |

### `onOpen`

Callback function when the `open` method is triggered.

| Type     | Required |
| -------- | -------- |
| function | No       |

### `onOpened`

Callback function when the modal is opened.

| Type     | Required |
| -------- | -------- |
| function | No       |

### `onClose`

Callback function when the `close` method is triggered.

| Type     | Required |
| -------- | -------- |
| function | No       |

### `onClosed`

Callback function when the modal is closed.

| Type     | Required |
| -------- | -------- |
| function | No       |

<br/>
<br/>
<br/>
<br/>

## Methods

### `open()`

The method to open the modal.

| Type     | Required  |
| -------- | --------- |
| function | Yes       |

### `close()`

The method to close the modal. You don't need to call it to dismiss the modal, since you can swipe down to dismiss.

| Type     | Required |
| -------- | -------- |
| function | No       |
