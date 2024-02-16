---
# https://vitepress.dev/reference/default-theme-home-page
layout: home

hero:
  name: "测试猿"
  text: "自动化测试工具赋能3k薪水的测试媛拥有15k的能力"
  tagline: 一次工作，自动完成重复性繁杂任务
  image:
    src: /logo.png
    alt: VitePress
  actions:
    - theme: brand
      text: 如何使用
      link: /examples
    - theme: alt
      text: 教程
      link: /howto
    - theme: alt
      text: API文档
      link: /api

features:
  - title: 安卓APP自动化
    details: 简单使用，无需root。不写代码也能完成自动化测试工作。    
    icon:
      src: /index/android.jpg
  - title: 浏览器自动化
    details: 谷歌工程师开发的浏览器自动化puppeteer接口规范，让你的浏览器自动化测试更加简单。 
    icon:
      src: /index/chrome.jpg
  - title: 手机网页自动化
    details: App混合开发webview自动化，让手机也能完成电脑端的自动化测试工作。 
    icon:
      src: /index/windows.jpg
---

<style>
.box .VPImage{
  width: 100%; 
  height:200px;
}
:root {
  
  --vp-home-hero-name-color: transparent;
  --vp-home-hero-name-background: -webkit-linear-gradient(120deg, #bd34fe, #41d1ff);
  --vp-home-hero-image-background-image: linear-gradient(-45deg, #bd34fe 40%, #47caff 60%);
      --vp-home-hero-image-filter: blur(68px);

}

</style>
