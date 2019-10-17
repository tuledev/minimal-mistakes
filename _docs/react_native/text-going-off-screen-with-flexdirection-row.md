# Text going off screen with flexDirection: 'row'

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

