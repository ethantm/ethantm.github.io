---
layout: single
classes: wide
title: How to add awesome maps to a react native app 🗺️
date: 2018-8-27
toc: true
toc_label: "Contents"
toc_sticky: false
excerpt: "🔥 Learn how to change the **style** of a map and create **search boxes**"
---

This post will teach you how to change the **style (colors and other visual elements)** of a react native map.
You will also learn how to use **callouts** to add **search boxes** and other components to a map.

### Get a map

If you haven't done this already, get yourself a nice basic map. If you have a map already, skip to the next section. If you don't, slap this into your terminal:

```javascript
npm install react-native-maps --save
```

And follow these [instructions](https://github.com/react-community/react-native-maps/blob/master/docs/installation.md). After you have installed react native maps, you are going to want to import react native maps and add a MapView component to the render of your app.

```javascript
import MapView from 'react-native-maps';
```

```javascript
// declare this outside of render
  var region = {
    latitude: 37.78825,
    longitude: -122.4324,
    latitudeDelta: 0.0922,
    longitudeDelta: 0.0421,
  };

// add this to render
  <MapView
    initialRegion={region}
  />
```

Verify that the map works and move on.

### Creating the style

According to the [MapView documentation](https://github.com/react-community/react-native-maps/blob/master/docs/mapview.md) you can add a custom style to a map with the prop **customMapStyle**. This prop accepts an **array** which contains the custom style. To generate a custom style go to the [Google Maps Styling Wizard](https://mapstyle.withgoogle.com/).

In this website you can change the color of text, roads, and all sorts of elements. This advanced editing is available once you click more options at the bottom of the page. You can also use the basic editor and select a theme from the six basic ones and adjust the density of features.

Once you have your custom style, click finish and copy the JSON. Put the JSON in your app and add it to customMapStyle. Done.

```javascript
var mapStyle = [] // too long to show
```

```javascript
  <MapView
    initialRegion={region}
    customMapStyle={mapStyle}
  />
```

An example of a custom map style:

<img src="/assets/images/splash/p2.png" alt="Example map" width="300"/>

### Search Boxes and Callouts

You can use the Callout component to add components to the map. Callouts can be used to create a search box for the map. **First** place a callout next to the MapView. By next I mean inside the same view.

```javascript
<View>
  <MapView
    initialRegion={region}
    customMapStyle={mapStyle}
  />
  <Callout>
    // put some components inside the map
  </Callout>
</View>
```

You can use a callout to put whatever you want inside the map. This next example is a search box.

```javascript
// on render
<View>
  <MapView
    initialRegion={region}
    customMapStyle={mapStyle}
  />
  <Callout>
    <View style={styles.calloutView} >
      <TextInput style={styles.calloutSearch}
        placeholder={"Search"}
      />
    </View>
  </Callout>
</View>
```

```javascript
// on the style sheet
calloutView: {
  flexDirection: "row",
  backgroundColor: "rgba(255, 255, 255, 0.9)",
  borderRadius: 10,
  width: "40%",
  marginLeft: "30%",
  marginRight: "30%",
  marginTop: 20
},
calloutSearch: {
  borderColor: "transparent",
  marginleft: 10,
  width: "90%",
  marginRightL 10,
  height: 40,
  borderWidth: 0.0  
}
```

This search box will look like this:

<img src="/assets/images/splash/p3.png" alt="Example map with search box" width="300"/>

### Conclusion

You have learned how to change the style of a react native map. You've also discovered the power of callouts. Some next steps would be to look at the documentation of MapView and **experiment** with the props and settings of your map. As for Callouts, you can experiment with different components and make the map more interactive. Some ideas for callouts: custom location button, different search modes activated by choosing from a drop down menu, list that shows recent searches, back button, side menu, show nearby coffee shops in a list.
