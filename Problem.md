## 找不到模块“./App.vue”或其相应的类型声明。

TypeScript 编译器不支持处理 .vue 结尾的文件,需要我们自己去声明一下，就是在 vite-env.d.ts 文件中加入这一段代码：

```javascript
declare module "*.vue" {
  import type { DefineComponent } from "vue";
  const component: DefineComponent<{}, {}, any>;
  export default component;
}

```
