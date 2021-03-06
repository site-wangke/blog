# Awesome Angular 欢迎您！

欢迎访问 Awesome Angular！

作为发起者，我希望能把它做成 Angular 中文资源的荟萃之地，让它成为对中文官方文档的有益补充。

## 这里包含什么

这里主要包括原创和翻译两种类型。除了单体文章之外，我们还会为不同的作者或团队开设专栏，并且支持发布一些针对特定主题的长篇连载。

## 授权方式

除非特别注明，否则这里的所有中文原创和翻译内容都基于 [CC BY-NC 4.0（共享、演绎、署名、非商业）](https://creativecommons.org/licenses/by-nc/4.0/deed.zh)协议，如果要商业使用，请联系作者。

翻译文章的原稿均已取得原作者的定向授权，但不包含二次授权许可，因此原稿只限在本站使用，如果你需要在其它网站上使用原稿，请自行联系原作者。

## 共同参与

这里是开放之地。

非常欢迎您投稿或进行交叉授权，也欢迎其它形式的合作。

请到 <https://github.com/ng-docs/awesome-angular> 发 Pull Request。

如果在文章中没有特别声明，通过此渠道投稿进来的文章都默认为 [CC BY-NC 4.0（共享、演绎、署名、非商业）](https://creativecommons.org/licenses/by-nc/4.0/deed.zh)协议。

## 投稿指南

### 工作原理

本项目会使用 `scripts/build.ts` 自动采集 `src/assets/content/articles` 下各个 md 文件的 git 提交记录，以生成 `src/app/article/data/articles.json` 和 `src/app/author/data/authors.json`，应用会利用它们来显示导航树和文档。

### 注册作者

请参照[这里](https://github.com/ng-docs/awesome-angular/blob/master/src/assets/content/authors/%E6%B1%AA%E5%BF%97%E6%88%90.md)填写作者信息。注意，你往【邮箱：】中填写的邮箱必须包括你在 git 提交记录中可能用到的所有邮箱，应用会根据它来反查作者信息。其它部分可随意填写。

### 添加专栏

在 `src/assets/content/articles` 下创建目录，目录名可以随意，不过尽量跟专栏名有关，方便查找。

专栏名称取自该目录下一个名叫 `_cover.md` 的封面文件。专栏在导航中的名称取自封面文件中的第一个一级标题，如 `# xxx`。

此专栏下的第一篇文章永远是栏目介绍。栏目介绍在导航中的名称取自封面文件中的第一个二级标题，如 `## xxx`。

### 添加文档

对于原创类文章，直接在专栏下创建 md 文件即可。文章在导航树中的名称取自该文件中的一级标题。

对于翻译类文章的创建方式类似，但会存在两个一级标题和两个二级标题，前面是英文标题，后面是中文标题。这时候所取的名称都是中文标题。

### 编辑文档

除了一级标题外，其它内容都和普通的 md 没差别。但翻译类文章有一些需要注意的地方。

翻译类文章请遵循下列格式：

#### 普通段落

把翻译结果直接追加在原文之后，作为一个新的段落。如：
```markdown
Hello

你好

```

#### 列表

无论是无序列表和有序列表，都要在添加空行之后先缩进再写翻译结果，如：

```markdown
* one

  一
  
* two

  二

  * two-one

    二-一

```

#### 表格

对于 gfm 格式的表格，请用逐行对照的形式。如：

```markdown
| Header 1 | Header 2|
|----------|---------|
| 表头 1    | 表头 2  |
| Body 1   |  Body 2 |
| 表体 1    | 表体 2  |
```

注意，表头的翻译结果必须位于表头分割线的下方。

### 预览

用 `ng serve` 或 `npm start` 启动开发服务器之后，可以进行预览。预览过程中可以使用 `npm run build:docs` 命令来自动根据提交记录重建 `articles.json` 和 `authors.json` 文件。这些文件重建之后，界面也会跟着刷新。

### 提交文档

**注意！不要在一个提交中添加多篇文档，必须逐个添加。**

添加文档时使用的 "提交信息" 经过编码后会变成该文件的 ID，这个 ID 会出现在 URL 中，终生不变，它对 SEO 会有一定帮助，因此尽量填写一个足够表意的提交信息。

新增文档之后，要先把它提交才能进行构建，但不要提交空白的文档，否则可能会影响对后续改名操作的正确跟踪。

对文章进行审校时，请认真填写提交信息，这些提交信息将变成该文章的修改记录。
