## Installation

**1. Install `react-native-modalize`**

```bash
yarn add react-native-modalize
```

**2. Install `react-native-gesture-handler`**

This package use react-native-gesture-handler as a peer dependency. If you use [Expo](https://expo.io) this package is already included by default. Otherwise, here is the most simple setup. If you run under `react-native-navigation` or have issues to install it, look on [their documentation](https://kmagiera.github.io/react-native-gesture-handler/docs/getting-started.html).

```bash
  yarn add react-native-gesture-handler
```

```bash
  react-native link react-native-gesture-handler
```

`MainActivity.java`
```diff
package com.swmansion.gesturehandler.react.example;

import com.facebook.react.ReactActivity;
+ import com.facebook.react.ReactActivityDelegate;
+ import com.facebook.react.ReactRootView;
+ import com.swmansion.gesturehandler.react.RNGestureHandlerEnabledRootView;

public class MainActivity extends ReactActivity {

  @Override
  protected String getMainComponentName() {
    return "Example";
  }

+  @Override
+  protected ReactActivityDelegate createReactActivityDelegate() {
+    return new ReactActivityDelegate(this, getMainComponentName()) {
+      @Override
+      protected ReactRootView createRootView() {
+       return new RNGestureHandlerEnabledRootView(MainActivity.this);
+      }
+    };
+  }
}
```

## Usage

**1. Import Modalize**

```jsx
import Modalize from 'react-native-modalize';
```

**2. Add the modal in your render function, and use the `open` method to open the modal**

```jsx
export default class MyApp extends React.PureComponent {

  modal = React.createRef();

  onOpen = () => {
    if (this.modal.current) {
      this.modal.current.open();
    }
  }

  render () {
    return (
      <View>
        <TouchableOpacity onPress={this.onOpen}>
          <Text>Open the modal</Text>
        </TouchableOpacity>

        <Modalize ref={this.modal}>
          ...your content
        </Modalize>
      </View>
    )
  }
}
```
