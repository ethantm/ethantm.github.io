---
layout: single
title: How to React Native Map Callouts
date: 2018-8-1
toc: true
toc_label: "Contents"
toc_sticky: false
excerpt: "Creating components on top of MapView"
---

![MapView component with callouts](https://camo.githubusercontent.com/3ec3eaaa8f44a0f79694b59fa3ecf8774b371cb9/687474703a2f2f692e67697068792e636f6d2f7854373758576a7145437664676a78396f412e676966)

### Search Bar

To create **components on top of a MapView component**, like the map above, you can use the callout component. Just put the components **inside of a callout**. The following example creates a TextInput at the top of the MapView which functions as a search bar.

```jsx
render() {
  return (
    <View style={styles.container}>
      <MapView>
      </MapView>
      <Callout>
        <View>
          <TextInput style={styles.searchBar}
            placeholder={"Search"} />
        </View>
      </Callout>
    </View>
  )
}
```

### Marker Callout
