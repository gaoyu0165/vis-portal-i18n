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

在项目中的 index.html 或 ejs 模板中增加 data-lang 属性

```
<html data-lang="zh-CN">
```

 本地开发时，在项目中的 index.html 或 ejs 模板中增加测试语言包文件

```
<body>
    <app></app>
    <script src="/static/languages.js"></script>
</body>
```

本地开发测试用的 languages.js 文件内容，放在静态文件夹 static 中

```
window.$locale = {
  'zh-CN': {
    'var': {'current-lang': '\u4e2d\u6587'},
    // 公共
    'comm': {
      all:"全部"
      apps-list-request-failed: "请求 Apps 列表失败"
      data-loading-failed: "加载数据失败，请稍后重试"
      edit: "编辑"
    },
    // portal 项目
    'portal': {
      ...
    },
    // biw-vue 项目
    'dashboard': {
      ...
    }
  },
  // 用于展示可用语言列表
  'supportLang': {
    'zh-CN': '中文', 
    'en': 'english'
  }
}
```

测试用语言包内容下载地址 ....

