# React Native Tips <!-- omit in toc -->

- [Access OS level dark mode preference](#access-os-level-dark-mode-preference)
    - [package: react-native-dark-mode](#package-react-native-dark-mode)
- [Using custom tabbar in react-navigation tab navigation](#using-custom-tabbar-in-react-navigation-tab-navigation)
    - [package: @react-navigation/bottom-tabs](#package-react-navigationbottom-tabs)
- [Implementing ghost loader/skeleton design](#implementing-ghost-loaderskeleton-design)
    - [package: react-native-shimmer-placeholder](#package-react-native-shimmer-placeholder)

# Access OS level dark mode preference

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

# Using custom tabbar in react-navigation tab navigation

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

# Implementing ghost loader/skeleton design

### package: [react-native-shimmer-placeholder](https://github.com/tomzaku/react-native-shimmer-placeholder)

```jsx
import ShimmerPlaceHolder from 'react-native-shimmer-placeholder'

;<ShimmerPlaceHolder autoRun={true} visible={!isLoading}>
  <Text>{data.text}</Text>
</ShimmerPlaceHolder>
```
