# 使用

在 vue 模板中

```
<a href="http://..." class="header-btn">
    {{ $t("comm.help-center") }}
</a>
```

在 vue 的 script 中用 this.$t\(\) 调用语言包内容

```
this.$alert(this.$t('portal.move-up'))
```

在 js 文件中调用语言包，首先要引用 vue，然后调用 vue.t\(\) 加载语言包内容

```
import Vue from 'vue'
Vue.t('comm.data-loading-failed')
```



