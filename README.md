[![](https://img.shields.io/npm/dm/@monterosa/react-native-parallax-scroll.svg?style=flat-square)](https://www.npmjs.com/package/@monterosa/react-native-parallax-scroll)

# react-native-parallax-scroll

A `ScrollView`-like component that:

- Has a parallax background
- Has a parallax foreground
- Has a fixed or sticky header
- Can be nested within other views
- Works on iOS and Android

## Installation

```
$ npm install @monterosa/react-native-parallax-scroll --save
```

## Demo

| ![](./demo/demo-1.gif) | ![](./demo/demo-2.gif) | ![](./demo/demo-3.gif) |

## Basic Usage

```js
import ParallaxScroll from '@monterosa/react-native-parallax-scroll';

// Inside of a component's render() method:
render() {
  return (
     <ParallaxScroll
      renderHeader={() => <Header />}
      headerHeight={50}
      isHeaderFixed={false}
      parallaxHeight={250}
      renderParallaxBackground={() => <Background />}
      renderParallaxForeground={() => <Foreground />}
      parallaxBackgroundScrollSpeed={5}
      parallaxForegroundScrollSpeed={2.5}
    >
      <Welcome />
    </ParallaxScroll>
  );
}
```

## Examples

Please clone the repo and run `npm run storybook` or `yarn storybook` to show examples of usages.

## Usage (API)

All of the properties of `ScrollView` are supported. Please refer to the
[`ScrollView` documentation](https://facebook.github.io/react-native/docs/scrollview.html) for more detail.

The `ParallaxScroll` component adds a few additional properties, as described below.

| Property | Type | Defaut | Description |
| -------- | ---- | -------- | ----------- |
| `style` | `object` | `{}` | Component's styles
| `width` | `number` | `Dimensions.get('window').width` | Component's width. |
| `height` | `number` | `Dimensions.get('window').height` | Component's height. |
| `innerRef` | `func` | `null` | To get a reference to the scrollable component. |
| `scrollStyle` | `object` | `{}` | These styles will be applied to the scroll view. |
| `headerHeight` | `number` | `45` | This is the height of sticky(fixed) header. |
| `renderHeader` | `func` | `null` | This renders an optional sticky(fixed) header that will be visible to the top of the view. |
| `isHeaderFixed` | `bool` | `false` | Is header fixed to top(not sticky)? |
| `parallaxHeight` | `number` | `Dimensions.get('window').width * 9 / 16` | This is the height of parallax. |
| `useNativeDriver` | `bool` | `false` | Enable [Native driver](https://facebook.github.io/react-native/blog/2017/02/14/using-native-driver-for-animated.html) for animated. NOTE: Works only with `Animated.ScrollView` component. |
| `scrollableComponent` | `class` | `Animated.ScrollView` | This is a class of scrollable component. |
| `isBackgroundScalable` | `bool` | `true` | Is background scalable on iOS? |
| `isForegroundTouchable` | `bool` | `false` | Should the ParallaxScroll pass touches to your foreground component? |
| `headerBackgroundColor` | `string` | `rgba(0, 0, 0, 0)` | The color of the unsticked(unfixed) header background. Can be empty `''` string. NOTE: Dosen't work with useNativeDriver.|
| `contentContainerStyle` | `object` | `{}` | These styles will be applied to the scroll view content container which wraps all of the child views. |
| `onChangeHeaderVisibility` | `func` | `null` | A callback function that is invoked when the parallax header is hidden or shown (as the user is scrolling). Function is called with a `boolean` value to indicate whether header is visible or not. |
| `renderParallaxBackground` | `func` | `() => <View />` | This renders the background of the parallax. |
| `renderParallaxForeground` | `func` | `() => <View />` | This renders the foreground of the parallax. |
| `fadeOutParallaxBackground` | `bool` | `false` | If `true`, the background will fade out as the user scrolls up. |
| `fadeOutParallaxForeground` | `bool` | `false` | If `true`, the foreground will fade out as the user scrolls up. |
| `headerFixedBackgroundColor` | `string` | `rgba(0, 0, 0, 1)` | The color of the sticked(fixed) header background. |
| `parallaxBackgroundScrollSpeed` | `number` | `5` | The speed factor that the background moves at relative to the scroll content. |
| `parallaxForegroundScrollSpeed` | `number` | `5` | The speed factor that the foreground moves at relative to the scroll content. |


## Contributing

I welcome contributions! Please open an issue if you have any feature ideas
or find any bugs. I also accept pull requests with open arms. I will
go over the issues when I have time. :)
