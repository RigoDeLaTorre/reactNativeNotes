<FlatList
data={this.props.libraries}
renderItem={this.renderItem}
keyExtractor={library => library.id.toString()}
/>

- Must turn the "key" to string
- You can do the rendering login in there if you wanted or pass a function like you normally would in React.
- renderItem passes each item in the array with an item tag. So if you have an array of objects.
  Example: you pass down this.props.people // to access each name would be, this.props.people.item.name
  Vs React you would just do this.props.people.name
