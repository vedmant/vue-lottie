# Lottie Animation View for Vue ([React](https://github.com/chenqingspring/react-lottie), [Angular](https://github.com/chenqingspring/ng-lottie))

[![npm version](https://badge.fury.io/js/vue-lottie.svg)](http://badge.fury.io/js/vue-lottie)

Generated by [create-vue-component](https://github.com/chenqingspring/create-vue-component)

## Wapper of bodymovin.js

[bodymovin](https://github.com/bodymovin/bodymovin) is [Adobe After Effects](http://www.adobe.com/products/aftereffects.html) plugin for exporting animations as JSON, also it provides bodymovin.js to render them as svg/canvas/html.

## Demo
https://chenqingspring.github.io/vue-lottie

## Why Lottie?

#### Flexible After Effects features
We currently support solids, shape layers, masks, alpha mattes, trim paths, and dash patterns. And we’ll be adding new features on a regular basis.

#### Manipulate your animation any way you like
You can go forward, backward, and most importantly you can program your animation to respond to any interaction.

#### Small file sizes
Bundle vector animations within your app without having to worry about multiple dimensions or large file sizes. Alternatively, you can decouple animation files from your app’s code entirely by loading them from a JSON API.

[Learn more](http://airbnb.design/introducing-lottie/) › http://airbnb.design/lottie/

Looking for lottie files › https://www.lottiefiles.com/


## Installation

Install through npm:
```
npm install --save vue-lottie
```

## Usage

```vue
<template>
    <div id="app">
        <lottie :options="defaultOptions" :height="400" :width="400" v-on:animCreated="handleAnimation"/>
        <div>
            <p>Speed: x{{animationSpeed}}</p>
            <input type="range" value="1" min="0" max="3" step="0.5"
                   v-on:change="onSpeedChange" v-model="animationSpeed">
        </div>
        <button v-on:click="stop">stop</button>
        <button v-on:click="pause">pause</button>
        <button v-on:click="play">play</button>
    </div>
</template>

<script>
  import Lottie from './lottie.vue';
  import * as animationData from './assets/pinjump.json';

  export default {
    name: 'app',
    components: {
      'lottie': Lottie
    },
    data() {
      return {
        defaultOptions: {animationData: animationData},
        animationSpeed: 1
      }
    },
    methods: {
      handleAnimation: function (anim) {
        this.anim = anim;
      },

      stop: function () {
        this.anim.stop();
      },

      play: function () {
        this.anim.play();
      },

      pause: function () {
        this.anim.pause();
      },

      onSpeedChange: function () {
        this.anim.setSpeed(this.animationSpeed);
      }
    }
  }
</script>

```
## Configuration

You can pass a configuration object through `options` property:
* animationData: an Object with the exported animation data.
* path: the relative path to the animation object. (animationData and path are mutually exclusive)
* loop: true / false / number
* autoplay: true / false it will start playing as soon as it is ready
* name: animation name for future reference
* renderer: 'svg' / 'canvas' / 'html' to set the renderer
* container: the dom element on which to render the animation

More information on [Bodymoving Documentation](https://github.com/bodymovin/bodymovin)

## Related Projects

* [Bodymovin](https://github.com/bodymovin/bodymovin) vue-lottie is a wrapper of bodymovin
* [Angular Lottie](https://github.com/chenqingspring/ng-lottie) angular implementation
* [React Lottie](https://github.com/chenqingspring/react-lottie) react implementation
* [React Native Lottie](https://github.com/airbnb/lottie-react-native) react native implementation by airbnb
* [IOS Lottie](https://github.com/airbnb/lottie-ios) ios implementation by airbnb
* [Android Lottie](https://github.com/airbnb/lottie-android) android implementation by airbnb

## Contribution

Your contributions and suggestions are heartily welcome.

## License
MIT
