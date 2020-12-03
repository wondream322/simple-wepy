# 小程序 -- 基于 wepy 框架

> 不更新了, 我的wepy版本也很老~~ 不建议用
# wepay地址
https://github.com/Tencent/wepy

=========================================================================================================================================================================
### 特性：

- 类 Vue 开发风格
- 支持自定义组件开发
- 支持引入 NPM 包
- 支持 [Promise](https://github.com/wepyjs/wepy/wiki/wepy%E9%A1%B9%E7%9B%AE%E4%B8%AD%E4%BD%BF%E7%94%A8Promise)
- 支持 ES2015+ 特性，如 [Async Functions](https://github.com/wepyjs/wepy/wiki/wepy%E9%A1%B9%E7%9B%AE%E4%B8%AD%E4%BD%BF%E7%94%A8async-await)
- 支持多种编译器，Less/Sass/Stylus/PostCSS、Babel/Typescript、Pug
- 支持多种插件处理，文件压缩，图片压缩，内容替换等
- 支持 Sourcemap，ESLint 等
- 小程序细节优化，如请求列队，事件优化等

### Demo

```html
<style lang="less">
@color: #4D926F;
  .num {
  color: @color;
  }
</style>
<template>
  <div class="container">
    <div class="num" @tap="num++">
      {{num}}
    </div>
    <custom-component></custom-component>
    <vendor-component></vendor-component>
    <div>{{text}}</div>
    <input v-model="text"/>
  </div>
</template>
<config>
{
  usingComponents: {
    customComponent: '@/components/customComponent',
    vendorComponent: 'module:vendorComponent'
  }
}
</config>

<script>
  import wepy from '@wepy/core';

  wepy.page({
    data: {
      num: 0,
      text: 'Hello World',
    },
  });
</script>
```

=========================================================================================================================================================================

## 开发前准备

开发前请先熟悉[wepy文档](https://github.com/Tencent/wepy#/)

再认真阅读<a href="./CONTRIBUTING.md">开发指南</a>

### 模板下载

``` bash
# 先全局安装 wepy
npm i wepy-cli -g

# 推荐 （wepy-cli 版本 1.7.0 及以上）
wepy init qianzhaoy/simple-wepy project-name

# or

git clone https://github.com/qianzhaoy/simple-wepy.git
```

模板下载完成后

``` bash
# 项目使用minui做组件库，故需先全局安装min-cli
npm install -g @mindev/min-cli

# 进入项目文件夹安装模块依赖，强制用 npm，而非 cnpm，不然 min build 后会有冗余的依赖包产生
npm install

# 编译 min-ui 组件
min build
```

## Build Setup

``` bash
# watch file change
npm run dev

# build for production with minification
npm run build
```
