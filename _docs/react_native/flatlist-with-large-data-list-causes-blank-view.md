# Flatlist with large data list causes blank view

## Issue

* Using `Flatlist` in with 1 list with more than 100 items.
* Scrolling fastly

-&gt; Flatlist becomes white blank view in seconds  

[https://github.com/facebook/react-native/issues/13649](https://github.com/facebook/react-native/issues/13649)

## Tried

Flatlist with

* `PureComponent` Item
* Using `getItemLayout`

-&gt; Doesn't work

## Solution

I use `ScrollView` now. It's scrolling well in low device



