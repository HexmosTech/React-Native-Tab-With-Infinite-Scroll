# react-native-collapsible-tab-view-with-infinite-scroll

[![Build Status][build-badge]][build]
[![Version][version-badge]][package]
[![MIT License][license-badge]][license]
[![runs with expo][expo-badge]][expo]

- [Features](#features)
- [Installation](#installation)
- [Quick Start](#quick-start)

  - [Core](#core)
    - [Tabs.FlatList](#tabsflatlist)
    - [Tabs.SectionList](#tabssectionlist)
    - [Tabs.ScrollView](#tabsscrollview)
    - [Ref](#ref)
  - [Hooks](#hooks)

- [Contributing](#contributing)
  - [Documentation changes](#documentation-changes)

**Courtesy**

extended version of the [react-native-collapsible-tab-view](https://github.com/PedroBern/react-native-collapsible-tab-view) with a bug fix and new feature.

<!-- todo -->

# Features

- support infinite scrolling in tab contents
- support multiple `onScroll`
- Animations and interactions on the UI thread
- Highly customizable
- Fully typed with [TypeScript](https://typescriptlang.org)

# Installation

Open a Terminal in the project root and run:

```sh
yarn add react-native-collapsible-tab-with-scroll
```

# Quick Start

```tsx
import React from 'react'
import { View, StyleSheet, ListRenderItem } from 'react-native'
import { Tabs } from 'react-native-collapsible-tab-view'

const HEADER_HEIGHT = 250

const Header = () => {
  return <View style={styles.header} />
}


  return (
    <Tabs.Container
      renderHeader={Header}
      headerHeight={HEADER_HEIGHT} // optional
    >
      <Tabs.Tab name="A">
        <Tabs.ScrollView
        onScroll={({nativeEvent})=>console..log(nativeEvent)}>
          <View style={[styles.box, styles.boxA]} />
          <View style={[styles.box, styles.boxB]} />
        </Tabs.ScrollView>
      <Tabs.Tab name="B">
        <Tabs.ScrollView
        onScroll={({nativeEvent})=>console..log(nativeEvent)}>
          <View style={[styles.box, styles.boxA]} />
          <View style={[styles.box, styles.boxB]} />
        </Tabs.ScrollView>
      </Tabs.Tab>
    </Tabs.Container>
  )
}

const styles = StyleSheet.create({
  box: {
    height: 250,
    width: '100%',
  },
  boxA: {
    backgroundColor: 'white',
  },
  boxB: {
    backgroundColor: '#D8D8D8',
  },
  header: {
    height: HEADER_HEIGHT,
    width: '100%',
    backgroundColor: '#2196f3',
  },
})

export default Example

```

## Props

- support all props provided in `react-native-collapsible-tab-view`

### Tabs.Tab

Wrap your screens with `Tabs.Tab`. Basic usage looks like this:

```tsx
<Tabs.Container ...>
  <Tabs.Tab name="A" label="First Tab">
   <ScreenA />
  </Tabs.Tab>
  <Tabs.Tab name="B">
   <ScreenA />
  </Tabs.Tab>
</Tabs.Container>
```

### Tabs.FlatList

Use like a regular FlatList.

### Tabs.ScrollView

Use like a regular ScrollView.

#### Props

|   name   |         type         |
| :------: | :------------------: |
| onScroll | `event \| undefined` |

### Tabs.SectionList

Use like a regular SectionList.

### Ref

You can pass a ref to `Tabs.Container`.

```tsx
const ref = React.useRef()
<Tabs.Container ref={ref}>
```

|     method      |             type             |
| :-------------: | :--------------------------: |
|    jumpToTab    |    `(name: T) => boolean`    |
|    setIndex     | `(index: number) => boolean` |
|  getFocusedTab  |          `() => T`           |
| getCurrentIndex |        `() => number`        |

## Hooks

- support all hooks provided by `react-native-collapsible-tab-view`

# Contributing

While developing, you can run the [example app](/example/README.md) to test your changes.

Please follow the [angular commit message format](https://github.com/angular/angular/blob/master/CONTRIBUTING.md#-commit-message-format).

Make sure your code passes TypeScript and ESLint. Run the following to verify:

```sh
yarn typescript
yarn lint
```

To fix formatting errors, run the following:

```sh
yarn lint -- --fix
```

Remember to add tests for your change if possible.

<!-- badges -->

[build-badge]: https://img.shields.io/circleci/build/github/PedroBern/react-native-collapsible-tab-view/main.svg?style=flat-square
[build]: https://app.circleci.com/pipelines/github/PedroBern/react-native-collapsible-tab-view
[version-badge]: https://img.shields.io/npm/v/react-native-collapsible-tab-view.svg?style=flat-square
[package]: https://www.npmjs.com/package/react-native-collapsible-tab-view
[license-badge]: https://img.shields.io/npm/l/react-native-collapsible-tab-view.svg?style=flat-square
[license]: https://opensource.org/licenses/MIT
[expo-badge]: https://img.shields.io/badge/Runs%20with%20Expo-4630EB.svg?style=flat-square&logo=EXPO&labelColor=f3f3f3&logoColor=000
[expo]: https://github.com/expo/expo
