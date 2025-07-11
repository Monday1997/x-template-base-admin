stylelint安装如下插件

```sh
pnpm add --save-dev stylelint  stylelint-config-rational-order stylelint-config-standard stylelint-declaration-block-no-ignored-properties stylelint-order eslint-config-prettier eslint-plugin-prettier
```

postcss-html 添加这个解决vue中出现的问题
// 使用 customSyntax 来告诉 Stylelint 如何解析 .vue 文件
// postcss-html 会智能地从 .vue 文件中提取 <style> 标签内容进行 lint
// 而忽略 <script> 和 <template> 部分。
并添加如下配置
"customSyntax": "postcss-html",

添加如项目中的.stylelintrc
记得设置
.vscode/setting.json
`"vs-code-prettier-eslint.prettierLast": true`

lint命令修改如下
添加缓存并关闭导入导出order
"lint": "eslint --cache --fix --ext .js,.ts,.vue,.jsx,.tsx src --rule \"simple-import-sort/imports: off\" --rule \"simple-import-sort/exports: off\"",

eslint-plugin-simple-import-sort // 添加排序
分组配置可以查看这里
https://github.com/import-js/eslint-plugin-import/blob/main/docs/rules/order.md
