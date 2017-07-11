# vue-ui-swipe

vue2.0的的图片轮播指令

文档：<a href="https://cgygd.github.io/vue2-countdown/">https://cgygd.github.io/vue-ui-swipe/</a>  
demo：<a href="https://cgygd.github.io/vue-ui-swipe/example/index.html" target="_blank">https://cgygd.github.io/vue-ui-swipe/example/index.html</a>

## Install
```
npm install vue-ui-swipe --save

```

## Usage

```js
import swipeDirective from 'vue-ui-swipe'
export default {
  data () {
    return {
      list: [],
      swipeInit: {
        delay: 3500,
        autoPlay: false
      }
    }
  },
  directives: {
    swipe: swipeDirective
  },
  mounted: function () {
    let listData = [
      {
        img: 'http://opkvnn2sq.bkt.clouddn.com//test/b4ece1c7748bf985bc01ae44acd1cd6b.jpg',
        smallImg: 'http://opkvnn2sq.bkt.clouddn.com//test/b4ece1c7748bf985bc01ae44acd1cd6b.jpg?imageView2/2/w/60'
      },
      {
        img: 'http://opkvnn2sq.bkt.clouddn.com//test/3e75d8ffc3c28393f61eea25ed986888.png',
        smallImg: 'http://opkvnn2sq.bkt.clouddn.com//test/3e75d8ffc3c28393f61eea25ed986888.png?imageView2/2/w/60'
      },
      {
        img: 'http://opkvnn2sq.bkt.clouddn.com//test/9156b0f365ac42c3236be7915b8a6428.png',
        smallImg: 'http://opkvnn2sq.bkt.clouddn.com//test/9156b0f365ac42c3236be7915b8a6428.png?imageView2/2/w/60'
      },
      {
        img: 'http://opkvnn2sq.bkt.clouddn.com//test/1f337fd118f9f27ec869a2b3581fe2ae.jpg',
        smallImg: 'http://opkvnn2sq.bkt.clouddn.com//test/1f337fd118f9f27ec869a2b3581fe2ae.jpg?imageView2/2/w/60'
      },
      {
        img: 'http://opkvnn2sq.bkt.clouddn.com//test/ed25b2550ba66eda2059d5e939ae8a2c.jpg',
        smallImg: 'http://opkvnn2sq.bkt.clouddn.com//test/ed25b2550ba66eda2059d5e939ae8a2c.jpg?imageView2/2/w/60'
      }
    ]
    setTimeout(() => {
      this.$set(this, 'list', listData)
    }, 10)
  }
}
```

```html
<p class="demo-title">自动播放</p>

<div class="ui-swiper-demo">
  <div v-swipe class="ui-swiper-container">
    <div class="ui-swiper">
      <div class="ui-swiper-box" v-for="item in list">
        <img class="ui-swiper-filter" :src="item.smallImg" :data-src="item.img" alt="">
      </div>
    </div>
  </div>
</div>

<hr />

<p class="demo-title">不自动播放</p>

<div class="ui-swiper-demo">
  <div v-swipe="swipeInit" class="ui-swiper-container">
    <div class="ui-swiper">
      <div class="ui-swiper-box" v-for="item in list">
        <img class="ui-swiper-filter" :src="item.smallImg" :data-src="item.img" alt="">
      </div>
    </div>
  </div>
</div>
```

### options
1. **delay** - 轮播时间，默认3000ms 
    - **type**: Number
    - **required** : false
    - **default** : 3000
2. **autoPlay** - 是否自动播放
    - **type**: Boolean
    - **required** : true
    - **default** : true
    
