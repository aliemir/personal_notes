# React Native Tips <!-- omit in toc -->

- [Access OS level dark mode preference](#access-os-level-dark-mode-preference)
  - [package: react-native-dark-mode](#package-react-native-dark-mode)
- [Using custom tabbar in react-navigation tab navigation](#using-custom-tabbar-in-react-navigation-tab-navigation)
  - [package: @react-navigation/bottom-tabs](#package-react-navigationbottom-tabs)
- [Implementing ghost loader/skeleton design](#implementing-ghost-loaderskeleton-design)
  - [package: react-native-shimmer-placeholder](#package-react-native-shimmer-placeholder)
- [Using AsyncStorage](#using-asyncstorage)
  - [package: @react-native-community/async-storage](#package-react-native-communityasync-storage)

## Access OS level dark mode preference

### package: [react-native-dark-mode](https://github.com/codemotionapps/react-native-dark-mode)

```jsx
import { useDarkMode, useDarkModeContext } from 'react-native-dark-mode'

const Component = () => {
  // returns true or false
  const isDarkMode = useDarkMode()
  // returns 'light' or 'dark'
  const mode = useDarkModeContext()
}
```

## Using custom tabbar in react-navigation tab navigation

### package: [@react-navigation/bottom-tabs](https://reactnavigation.org/docs/bottom-tab-navigator/)

```jsx
import { createBottomTabNavigator } from '@react-navigation/bottom-tabs'

const Tab = createBottomTabNavigator()

const MyTabBar = ({ state, descriptors, navigation }) => {
  /* ... */
}

const MyNavigation = () => (
    <Tab.Navigator tabBar={props => <MyTabBar {...props}>}>

    {/* ... */}

    </Tab.Navigator>
)
```

## Implementing ghost loader/skeleton design

### package: [react-native-shimmer-placeholder](https://github.com/tomzaku/react-native-shimmer-placeholder)

```jsx
import ShimmerPlaceHolder from 'react-native-shimmer-placeholder'

;<ShimmerPlaceHolder autoRun={true} visible={!isLoading}>
  <Text>{data.text}</Text>
</ShimmerPlaceHolder>
```

## Using AsyncStorage

### package: [@react-native-community/async-storage](https://github.com/react-native-community/async-storage)

```jsx
import AsyncStorage from '@react-native-community/async-storage'

// Store data
storeData = async () => {
  try {
    await AsyncStorage.setItem('@storage_Key', 'stored value')
  } catch (e) {
    // saving error
  }
}

// Read data
getData = async () => {
  try {
    const value = await AsyncStorage.getItem('@storage_Key')
    if(value !== null) {
      // value previously stored
    }
  } catch(e) {
    // error reading value
  }
}
```
