---
# https://vitepress.dev/reference/default-theme-home-page
layout: home


hero:
  name: "Test Ape"
  text: "Automated testing tools enable testers with a salary of 3k to have the ability of 15k."
  tagline: Automate repetitive and tedious tasks with one-time work.

  image:
    src: /logo.png
    alt: VitePress
  actions:
    - theme: brand
      text: How to use
      link: /examples
    - theme: alt
      text: Tutorial
      link: /howto
    - theme: alt
      text: API documentation
      link: /api

features:
  - title: Android APP automation
    details: Easy to use, no root required. No coding needed to complete automated testing work. 
    icon:
      src: /index/android.jpg
  - title: Browser automation
    details: Google engineers have developed the Puppeteer interface specification for browser automation, making your browser automation testing even easier. 
    icon:
      src: /index/chrome.jpg
  - title: Mobile web automation
    details: App hybrid development webview automation, allowing mobile phones to complete desktop automation testing work. 
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
