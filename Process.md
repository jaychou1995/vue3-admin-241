### 1.vite 命令初始化程序

npm init vite@latest my-vue-app --template-vue-ts

### 2.解决ts对.vue文件的报错

TypeScript 编译器不支持处理 .vue 结尾的文件,需要我们自己去声明一下，就是在 vite-env.d.ts 文件中加入这一段代码：

```javascript
declare module "*.vue" {
  import type { DefineComponent } from "vue";
  const component: DefineComponent<{}, {}, any>;
  export default component;
}

```

### 3.eslint 安装

npm i eslint -D
npx eslint -init
根目录创建 .eslintignore 过滤不适用eslint检查的文件

```javascript
node_modules;
dist;
```

### 4.安装 prettier

npm i prettier eslint-config-prettier eslint-plugin-prettier -D

使用默认配置或者创建.prettierrc文件, 创建.prettierignore过滤不需要prettier的文件

### 5.创建git仓库

…or create a new repository on the command line
echo "# vue3-admin-241" >> README.md
git init
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin https://github.com/jaychou1995/vue3-admin-241.git
git push -u origin main

…or push an existing repository from the command line
git remote add origin https://github.com/jaychou1995/vue3-admin-241.git
git branch -M main
git push -u origin main

### 6. 配置husky 强制代码 在提交到git的时候必须格式化

安装npm i -D husky
