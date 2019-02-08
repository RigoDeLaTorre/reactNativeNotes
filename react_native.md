<h4>Console Log</h4>
- react-native log-android

<h4>Flat List</h4>

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
