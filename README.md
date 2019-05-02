# React Native Workshop

In this course we will see the fundamental concepts of react native

### Table of Contents

+ [Values & Types](#values-and-types)

## What is React Native

React Native is a framework created by Facebook to enable a smooth and easy cross-platform mobile development.   

React Native helps you create real and exciting mobile apps with the help of JavaScript only, which is supportable for both platforms (**iOS and Android**).

>It basically means that you don’t have to create an iOS and Android app separately.

## Why?

+ It’s got ios and android covered
+ Reusable components allow hybrid apps to render natively
+ Apply react native ui components to an existing app’s code—without any rewriting at all

## How?

Give me a **state** and a **_render()_** method that depends on it and forget about how and when to render.*

>Unless you want more control

## ¿React & React Native?

React Native

+ Is a **framework** (it comes with everything you need to develop)
+ It doesn't use html, it provides **components** that work similar way than **html elements** 
+ The react native components map the actual real native **iOS or Android UI** components
+ To run your app, we will need to have **Xcode** (for iOS) and **Android Studio** (for android), _and emulators or physical devices_
+ The styling is achieve with **style sheets in Javascript**
+ Routing is achieved with `react navigation` (for Mobile development)
+ **Platform specific code** for both _platforms iOS and Android_

~~~jsx
// React Base Modules
import React from 'react';
// Only for react native
import { View, Text, StyleSheet } from 'react-native';

export default class App extends React.Component {
  render() {
    return (
      <View style={styles.container}>
        <Text >Hello world!</Text>
      </View>
    );
  }
}

const styles = StyleSheet.create({
	container: {
    flex: 1
    , backgroundColor: 'black'
    , color: '#FFFFFF'
	}
});
~~~

React 

+ It's a **library** for UI (you have to use it in complement with other libraries like **webpack**, google closure compiler, **redux**, mobx, react router, react mini router, **babel**, **polyfills**)
+ It uses the **DOM**
+ Styling is achieved with **CSS**
+ Routing is achieved with `react router` (for Web)
+ **Platform specific code** term _doesn't exists_

~~~jsx
// React Base Modules
import React from 'react';

class HelloMessage extends React.Component {
  render() {
    return (
      <div>
        Hello {this.props.name}
      </div>
    );
  }
}
~~~

## Starting a project

## Expo and React Native (_Vanilla_)

**Why Expo?**

Expo is really great when you are starting with mobile apps, at first pure React Native (_Vanilla_) feels overwhelming, with all that tooling you need to install and learn.

Expo is a set of tools, libraries and services that allow you develop native apps for iOS and Android written in js.

Advantages:

* Fast and simple project installation (in just several minutes)
* An utility Expo CLI opens in a browser and helps to check app status
* **Expo client app**, is an app and it allows opening projects during development without build via **XCode** or **Android Studio**
* **_Expo SDK_ offers the collection of ready solutions**
* OTA Updates
* Develop apps for ios Without macOS with ios device and test them with Expo client
>"The Ruby on Rails for React Native"

Drawbacks:

* You can't add native modules written in Objective-C, Swift, Java, Kotlin
* You cant use packages with native languages that require **linking**
* Thje app has a big size as it is built with all **Expo SDK solution.**
* Often everything works well in Expo client during testing, but certain problems may occur in a standalone app
* Dependence on Expo infrastructure
* Dependence on a particular React Native version


Development Requirements:  
+ Node.js (_latest version_ at moment of writing this _10.15.3_ for **LTS** and _12.1.0_ for **current**)
+ Git (_latest version_ at moment of writing this _2.21.0_)
+ Install [Expo](https://play.google.com/store/apps/details?id=host.exp.exponent "Expo") app on your iOS or Android phone
+ Physical device for testing purposes

\* Only mac users install `watchman`

#### Getting Start

1. Install Expo CLI

  ~~~console
  ~$ npm install -g expo-cli
  ~~~

2. Create a new React Native project called _"MyHybridApp"_

  ~~~console
  ~$ expo init MyHybridApp
  ~~~

3. Change to the new project folder and start the development server.

~~~console
~/MyHybridApp$ npm start
~~~

4. The last step will open a web development console, after that open _**expo** app_ on your mobile and **scan** the **QR** code provided by the web console, this will open the app on your physical device

### React Native

React Native is like React, but it uses native components instead of web components as building blocks. So to understand the basic structure of a React Native app, you need to understand some of the basic React concepts, like **JSX**, **components**, **state**, and **props**. If you already know React, you still need to learn some React-Native-specific stuff, like the native components.

Advantages:

* You can add native modules written in Objective-C, Swift, Java, Kotlin, and packages that require linking
* You can decide by yourself what React Native version to use
* You depend on your local environment
* You can use native modules (you can link the packages written in native languages)

Drawbacks:

* You won't have an opportunity to develop iOS without macOS, as you have to use XCode
* If you have started to work with React Native recently or have switched to it from Expo, setting a project will take a fair amount of time.

Development Requirements:  
+ Node.js (_latest version_ at moment of writing this _10.15.3_ for **LTS** and _12.1.0_ for **current**)
+ Git (_latest version_ at moment of writing this _2.21.0_)
+ Java (_8.2.11_)
+ Android Studio IDE
  + SDK Manager
  + Emulator
+ XCode IDE
+ Physical or virtual device
+ [Additional Software](https://facebook.github.io/react-native/docs/getting-started)

>Ejecting to ExpoKit
>
>ExpoKit is an Objective-C and Java library that allows you to use the Expo platform and your existing Expo project as part of a larger standard native project -- one that you would normally create using Xcode, Android Studio, or react-native init

#### Getting Start

1. Install React Native CLI

~~~console
npm install -g react-native-cli
~~~

2. Configure android or ios local development requirements

[React native Guide](https://facebook.github.io/react-native/docs/getting-started)

3. Create a new application

~~~console
$ react-native init MyHybridApp
~~~

4. Change to the new project folder and start the development server.

~~~console
~/MyHybridApp$ react-native run-android
~~~

## Props

Components usually can be customized when they are created with different parameteres

>Props are Unchangeable — Immutable

~~~jsx
import React from 'react';
import { AppRegistry, Text, View } from 'react-native';

class Greeting extends React.Component {
  render() {
    return (
      <View style={{ alignItems: 'center' }}>
        <Text>Hello {this.props.name}!</Text>
      </View>
    );
  }
}
~~~

_Usage:_

`<Gretting name='Oscar'>`

## State

There are two types of data that control a component: props and state. props are set by the parent and they are fixed throughout the lifetime of a component. State works differently when compared to props. State is internal to a component, while props are passed to a component.

You should initialize state in the **constructor**, and then call `setState` when you want to change it.

>State can Change — Mutable

~~~jsx
import React from 'react';
import { } from 'react-native';

class Counter extends React.Component{
  
  constructor(props){
    super(props);
    //Initialize state
    this.state = { counter: 0 };
  }

  addToCounter= ()=>{
    const counter = ++this.state.counter
    
    //Mutating the state
    this.setState({
      counter
    })
  }

  render(){
    <View>
      <Text>{ this.state.counter }<Text/>
      <Button onPress={ addToCounter }/>
    </View>
  }
} 

~~~

## Style

With React Native, you don't use a special language or syntax for defining styles. You just style your application using JavaScript. All of the core components accept a prop named style. The style names and values usually match how CSS works on the web, except names are written using camel casing, e.g `backgroundColor` rather than backgrond-color


~~~jsx
import React from 'react';
import { StyleSheet, Text, View } from 'react-native';

const styles = StyleSheet.create({
  bigGreen: {
    color: 'green',
    fontWeight: 'bold',
    fontSize: 30,
  },
  yellow: {
    color: 'yellow',
  },
});

export default class StyleExamples extends Component {
  render() {
    return (
      <View>
        <Text style={styles.yellow}>Yellow</Text>
        <Text style={styles.bigGreen}>Big Green!</Text>
        <Text style={[styles.bigGreen, styles.yellow]}>Big Green, then Yellow</Text>
        <Text style={[styles.yellow, styles.bigGreen]}>Yellow, then Big Green</Text>
      </View>
    );
  }
}
~~~

### Height and Width

A component's height and width determine its size on the screen. The simplest way to set the dimensions of a component is by adding a fixed width and height to style. All dimensions in React Native are unitless, and represent density-independent pixels.

~~~jsx
import React, { Component } from 'react';
import { View } from 'react-native';

export default class FixedDimensionsBasics extends Component {
  render() {
    return (
      <View>
        <View style={{ width: 50, height: 50, backgroundColor: 'powderblue'}} />
        <View style={{ width: 100, height: 100, backgroundColor: 'skyblue'}} />
        <View style={{ width: 150, height: 150, backgroundColor: 'steelblue'}} />
      </View>
    );
  }
}
~~~

Use Constants (**Dimensions**)

~~~jsx
import React from 'react';
import { Dimensions } from 'react-native';


const windowSize = Dimensions.get('window');

class myContainer extends React.Component{
  render(){
    return(
      <View style={ styles.container }>
      </View>
    )
  }
}


const styles = StyleSheet.create({
  container: {
    height: windowSize.height
    , width: windowSize.width
    , backgroundColor: 'white'
  }
});

~~~

Use Constants (**Absolute Fill from _StyleSheet_ Object**)

~~~jsx
import React from 'react';
import { View, StyleSheet } from 'react-native';

class myContainer extends React.Component{
  render(){
    return(
      <View style={ styles.container }>
      </View>
    )
  }
}

const styles = StyleSheet.create({
  container: {
    ...StyleSheet.absoluteFill
    , backgroundColor: 'red'
  }
});

~~~

## Layout and Flexbox

**Flex**

Use flex in a component's style to have the component expand and shrink dynamically based on available space. Normally you will use flex: 1, which tells a component to fill all available space, shared evenly amongst other components with the same parent.



+ flexDirection 
  + enum(`column`,`row`)
+ justifyContent 
  + enum(`flex-start`, `flex-end`, `center`, `space-around`, `space-between`)
+ alignItems
  + enum(`flex-start`, `flex-end`, `center`, `space-around`, `space-between`)
+ alignSelf
  + enum(`auto`, `flex-start`,`flex-end`, `center`, `stretch`, `baseline`)
+ flex 
  + number
+ flexWrap
  + enum(`nowrap`, `wrap`)
+ alignContent
  + enum(`flex-start`, `flex-end`, `center`, `space-around`, `space-between`)
+ flexBasis
  + number (_percent %_)
+ flexGrow
  + number (relative to the rest of the flexible items)
+ flexShrink
  + number (relative to the rest of the flexible items)


## Handling Text Input

`TextInput` is a basic component that allows the user to enter text. It has an onChangeText prop that takes a function to be called every time the text changed, and an onSubmitEditing prop that takes a function to be called when the text is submitted.

~~~jsx
import React, { Component } from 'react';
import { AppRegistry, Text, TextInput, View } from 'react-native';

export default class PizzaTranslator extends Component {
  constructor(props) {
    super(props);
    this.state = {text: ''};
  }

  render() {
    return (
      <View style={{padding: 10}}>
        <TextInput
          style={{height: 40}}
          placeholder="Type here to translate!"
          onChangeText={(text) => this.setState({text})}
        />
        <Text style={{padding: 10, fontSize: 42}}>
          {this.state.text.split(' ').map((word) => word && '🍕').join(' ')}
        </Text>
      </View>
    );
  }
}
~~~

## Handing Touches

Users interact with mobile apps mainly through touch. They can use a combination of gestures, such as tapping on a button, scrolling a list, or zooming on a map. React Native provides components to handle all sorts of common gestures, as well as a comprehensive gesture responder system to allow for more advanced gesture recognition

**Touchables**


If the basic button doesn't look right for your app, you can build your own button using any of the "Touchable" components provided by React Native. The "Touchable" components provide the capability to capture tapping gestures, and can display feedback when a gesture is recognized. These components do not provide any default styling, however, so you will need to do a bit of work to get them looking nicely in your app.

+ **TouchableHighlight**: On press down, the opacity of the wrapped view is decreased, which allows the underlay color to show through, darkening or tinting the view.
+ **TouchableNativeFeedback**: A wrapper for making views respond properly to touches (**Android only**). On Android this component uses native state drawable to display touch feedback.
+ **TouchableOpacity**: A wrapper for making views respond properly to touches. On press down, the opacity of the wrapped view is decreased, dimming it.
+ **TouchableWithoutFeedback**: Do not use unless you have a very good reason. All elements that respond to press should have a visual feedback when touched.s

## Navigation

## Networking

## React Main Concepts




Guides

---

## Basic Components

##  Platform Specific Code

## ScrollView

## Lists

