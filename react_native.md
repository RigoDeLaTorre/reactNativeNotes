<h4>Console Log</h4>
- react-native log-android
- To debug on new window...Press Cmd + M on emulator screen
    Go to Dev settings > Debug server host & port for device
    Set localhost:8081
    Then set it to remote js debugging

<h2>Flat List</h2>

<FlatList <br>
data={this.props.libraries} <br>
renderItem={this.renderItem} <br>
keyExtractor={library => library.id.toString()} <br>
/>

- Must turn the "key" to string
- You can do the rendering in there if you wanted or pass a function like you normally would in React.
- renderItem passes each item in the array with an item tag. So if you have an array of objects.
  Example: you pass down this.props.people // to access each name would be, this.props.people.item.name
  Vs React you would just do this.props.people.name
- Or you could just destructure it with .. renderItem({item})

<h2>LayoutAnimation</h2>
-   LayoutAnimation.spring(); works for ios only

- For android you must put this in the constructor, and also import Platform,
  UIManager from react-native

if (Platform.OS === "android") {
UIManager.setLayoutAnimationEnabledExperimental &&
UIManager.setLayoutAnimationEnabledExperimental(true);
}
-Then call it on componentWillUpdate as you would with ios .. LayoutAnimation.spring()

<h4>Firebase</h4>
- Some issues with basic setup, v 5.0.3 didnt work
- instead of import firebase from "firebase", use
      -import firebase from "@firebase/app";
      -import "@firebase/auth";

<h2>Input</h2>
  -secureTextEntry to turn pass into astericks
  -onChangeText  ...ex similar to reacts onChange on an input.

<h2>Navigation</h2>
- react-native-router-flux
    -<Scene
        - key="login" component={LoginForm}
         - title="Login (navbar title)"
          - initial , shows initial scene

<h2>Inline Styling</h2>
  - You can pass in multiple sytles, the latter will over-ride the former. Ex: style={[styles.first, styles.second]}
