## 配置方式
- 创建新文档系统
```text
创建一个完整的文档系统（独立网站），从版本库的 template-master 分支一个即可。
按规范一个完整的文档系统应当有 dev 和 master 两个分支，前者用于编辑，后者用于生产，例如新建 CKPay 文档执行以下命令：
```
```shell
git checkout template-master
git branch ckpay-dev
git branch ckpay-master
git push origin ckpay-dev
git push origin ckpay-master
```

- 左侧菜单配置参考：/docs/_sidebar.md

```md
- [首页](README.md)

- 语法演示
    - [Demo](demo.md)
    - [空文件](_null.md)
- 其他菜单
    - [aaa](a.md)
    - [bbb](b.md)
```

- 文档内容
```text
直接新建md文件，由菜单链接即可
```

- 顶部导航：/docs/_navbar.md

```md
- 切换语言
  - [中文](/)
  - [English](/en-us/)
```


## 常用参考语法
<pre>
## 大标题，可以在左侧生成菜单

- 列表项

带背景的内容块
```text
    该部分为带背景的内容块
    `键盘位置：左上角1的左侧，要英文半角状态输入
    注意使用三个 ` 结束，新起一行```结尾，内容写在两行中间，表示带背景的内容区域
```

插入代码
```html
    此处写代码，html可替换成其他语言名称
```

</pre>

## 插入表格

- 表格代码
```html
<table data-hy-role="doctbl">
    <tr>
        <th>表头</th>
        <th>表头</th>
        <th>表头</th>
    </tr>
    <tr>
        <td>数据</td>
        <td>数据</td>
        <td>数据</td>
    </tr>
    <tr>
        <td>数据</td>
        <td>数据</td>
        <td>数据</td>
    </tr>
</table>
```

- 表格样式
<table data-hy-role="doctbl">
    <tr>
        <th>表头</th>
        <th>表头</th>
        <th>表头</th>
    </tr>
    <tr>
        <td>数据</td>
        <td>数据</td>
        <td>数据</td>
    </tr>
    <tr>
        <td>数据</td>
        <td>数据</td>
        <td>数据</td>
    </tr>
</table>

