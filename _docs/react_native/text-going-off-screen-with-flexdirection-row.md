# Text going off screen with flexDirection: 'row'

#### [https://stackoverflow.com/questions/36284453/react-native-text-going-off-my-screen-refusing-to-wrap-what-to-do](https://stackoverflow.com/questions/36284453/react-native-text-going-off-my-screen-refusing-to-wrap-what-to-do)

#### react-native: 0.59.5

The solution is wrapping children in `View`  with `flex:1`

```text
<View style={{ flexDirection: 'row' }}>
  <View>
  // ....
  </View>
  <View style={{ flex: 1 }}>
    <Text>Your Text</Text>
  </View>
</View>
```

