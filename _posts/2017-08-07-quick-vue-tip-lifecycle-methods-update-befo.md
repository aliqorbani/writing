---
ID: 5332
post_title: 'Quick Vue tip: lifecycle methods update &amp; befo&#8230;'
author: James DiGioia
post_excerpt: ""
layout: post
permalink: >
  http://jamesdigioia.com/quick-vue-tip-lifecycle-methods-update-befo/
published: true
post_date: 2017-08-07 15:57:17
---
Quick Vue tip: lifecycle methods `update` & `beforeUpdate` will not be called if the props that changed for a component aren't being used to render. In my case, I was using a prop not used by the render method to trigger some side effect, and couldn't get the callback to trigger the side effect. Use `this.$watch` to watch prop changes unrelated to a Vue component's rendering.