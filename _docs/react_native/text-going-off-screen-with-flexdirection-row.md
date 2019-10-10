# Bugs

## Text going off screen with flexDirection: 'row'

#### react-native: 0.59.5

The solution is wrap children in `View`  with `flex:1`

```text
<View style={{ flexDirection: 'row' }}>
  <View style={{ flex: 1 }}>
    <Text>Your Text</Text>
  </View>
</View>
```

