# 加载 vue-i18n

在 index.js 文件中

```
import Vue from 'vue'
import VueI18n from 'vue-i18n'
```

因为只有本地开发用到了语言包，所以要判断环境来调用 vue-i18n

```
if (process.env.NODE_ENV !== 'production') {
  console.log('开发环境')
  Vue.use(VueI18n)
  let currLang = document.documentElement.getAttribute('data-lang')
  Vue.locale(currLang, window.$locale[currLang], () => {
    Vue.config.lang = currLang
  })
}
```



