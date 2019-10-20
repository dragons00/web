https://atom-china.org/t/topic/4552

## simplified-chinese-menu:翻译组件  

## emmet:支持html和css格式文件中代码速写插件
* 1.新建空文件后,改变文本格式为html(点击atom最右下角显示的文本格式来改变)
* 2.然后在文本空白处输入标签名html、head、div、article、a…后按tab键.多倍数个的同类标签: li*3
* 3.快速设置class/id属性默认的div标签: .clsName/idName然后tab会出来class/id为clsName/idName的div标签
* 4.快速设置class/id属性的任意标签: 如h1.title/h1#title出来id/class为title的h1标签
* 5.>嵌套符来速写嵌套关系的标签: ul>li*3>a
* 6.{}设置标签内value值:如ul>li{value1}+li{value2}  
## color-picker:颜色查看器
## minimap:右侧代码浓缩框
## atom-html-preview

## atom-beautify    

## linter:
它可以轻松指出我们代码中的错误，不过它只是主模块，具体你想验证什么你的现在相应的分支，充分适应你的环境.






## javascript-snippets
## autocomplete-paths



一. 语法支持
1. Language-label
Ø ES2016、ESNext、JXS语法扩展
2. Language-postcss
Ø Postcss语法高亮
 
二. 自动补全
1. Autocomplete-modules
Ø 模块名自动补全
2. Autocomplete-paths
Ø 路径自动补全
3. Atom-ternjs
Ø ES5、ES6、ES7、Node.js、jQuery、Angular等等JS代码自动补全
4. Emmet
Ø 快速手写 HTML, CSS, Sass / SCSS / LESS
 
三．语法检查
1. Linter
Ø 基本语法检查框架
2. Linter-jshint
Ø 基本jshint的JavaScript语法检查插件
3. Linter-eshint
Ø 基本eshint的JavaScript语法检查插件
 
四．版本控制
1. git-plus
Ø 丢弃终端，在atom里执行Git命令
 
五．扩展功能
1. Mini map
Ø 小地图，源码预览图
2. file-icons
Ø 显示文件类型对应的图标
3. Atom-beautify
Ø 代码格式化
4. Pigments
Ø 代码颜色可视化
5. Color-picker
Ø 取色器
6. Highlight-selected
Ø 高亮选中
7. Mini map-Highlight-selected
Ø 小地图高亮选中
Ø 源码预览图高亮选中
8. Docblockr
Ø 注释插件
9. Hyperclick
Ø 跳转到变量定义文件，需要配合js-hyperclick使用
10. Travis-ci-status
Ø 底部状态栏扩展，添加项目Travis CI状态
11. sync-settings
Ø 备份atom的包和设置至GIstanbul,易还原
12. Atom-simplified-chinese-menu
Ø 汉化atom插件

作者：ALISA_LR 
来源：CSDN 
原文：https://blog.csdn.net/alisa_lr/article/details/78530030 
版权声明：本文为博主原创文章，转载请附上博文链接！



language 
language-markdown 
language-babel 
language-source : Adds basic comment, indent, and outdent patterns used as a fallback by all source files in Atom. 
language-vue : Adds syntax highlighting and snippets to Vue component files in Atom. 
linter 
linter 
All linter : 列举了所有的 linter 
linter-markdown 
linter-csslint 
linter-eslint 
linter-htmlhint 
autocomplete 
atom-ternjs 
emmet 
autocomplete-plus : 内置的插件 
autocomplete-paths : 文件路径补全 
autocomplete-modules 
markdown 
markdown-preview : atom 自带的预览插件，可以用下面的替换 
markdown-preview-plus : Markdown Preview Plus (MPP) is a fork of Markdown Preview that provides a real-time preview of markdown documents. 
markdown-writer : 提供书写时的一些辅助特性 
Tidy Markdown : 文件保存的时候，帮助纠正书写错误 
markdown-assistant : 拖拽图片，自动上传云服务上。 
markdown-scroll-sync : 编辑和预览同步滚动 
markdown-pdf : 生成pdf, png, jpeg 图片 
代码书写辅助类 
dash : Simple Dash documentation integration for Atom.可在 windows 下使用，客户端用 zeal 即可。 
docblockr : 注释书写插件 
atom-beautify : 代码格式化 
color-picker : 颜色选取插件 
pigments : 颜色可视化插件 
elastic-tabstops : An experimental implementation of Elastic tabstops for Atom 
hyperclick : Pluggable text-clicking UI for Atom. 
js-hyperclick : 配合上面一个插件使用 
regex-railroad-diagram : 正则表达式可视化 
适合前端的 
atom-html-preview 
open-in-browsers 
css-comb : 这个插件支持读取 .csscomb.json 
git 相关 
git-time-machine : 可视化查看提交记录 
编辑器辅助类 
sync-settings : 通过 gist 同步 Atom 配置 
Editor-setting : 不同文件打开不同扩展 
open-recent : 查看最近打开的文件 
project-plus : 快速切换 project 
advanced-open-file : Open and create files and directories easily. 
file-icons : 增加文件图标的显示 
file-icon-supplement : file-icons 的提升 
minimap : 增加右侧代码预览 
minimal-highlight-selected : 在右侧minimap视图中标明高亮部分 
tool-bar : 增加快速导航栏，类似vs code 右侧那个 
tool-bar plugin : 上面的插件只是提供功能，还需要安装对应的插件，展示具体的内容 
typewriter : A better writing experience for Atom 
Zen : 书写的勿扰模式 
highlight-selected : 高亮所选择内容 
highlight-line : 高亮当前行 
editorconfig : 编辑器格式统一插件，借助 .editorconfig 文件，团队开发必备 
vim-mode-plus : vim-mode improved. 替代官方的 vim-mode 
vim-mode-plus-ex-mode : 提供 :w 类似功能，按键快捷键需要自己定义 
smalls : 光标快速跳转插件 
easy-motion-redux : 可是区域内光标快速跳转插件 
wakatime : 记录使用编辑器的时间，很多编辑器或IDE都有这个插件 
package-generator : Generates and opens a new sample package or syntax theme in Atom. 
spacemacs-evil-keys : 模拟 spacemacs evil 模式, 不建议使用，如果喜欢还是直接使用spacemacs 吧 
proton-mode : spacemacs and sublimious style editing in Atom. (效果和上面类似，功能应该更强大)，不建议使用，如果喜欢还是直接使用spacemacs 吧。因为这个插件会建立自己的插件系统，对你以后的配置会做修改。 
funny 
Activate Power Mode : 打字效果，配合tickeys音效，不用买机械键盘了。 
优秀的插件开发者 
atom : atom 官方, 应该基本都是内置的插件 
atom-community : atom 社区 
steelbrain’s Packages : linter 
t9md : vim-mode-plus 
管理配置 
配置同步 
使用上述提到的 sync-settings 插件完成。步骤如下: 
安装 sync-settings 插件 
打开 Create a new personal access token , 填入 Token description （如果快捷键或者某些配置在不同系统下不一致，建议分开多套备份）, 勾选 gist , 点击 Generate token , 完成后界面上有一串字符，可以拷贝。就是你的 Personal Access Token 
打开 Create new gist , 在输入框中随便填入内容。点击 Create secret gist . （如果你想要分享你的配置，也可以点击 publish）。完成后，选择生成文件的后缀字符， gitst:xxxxx ， xxxxx 就是你的 Gist Id 。 
将上述两个内容，填入 sync-settings 中对应字段 
通过 Command Palette 打开 sync-settings:backup 完成备份，其他功能也都是在 sync-settings: 命令下。 
备份成功，Atom 右上角会有绿色弹框提示，如果失败，可以打开 Toggle Developer Tools 查看控制台，看是否是网络原因报错，可能需要设置代理，可以参考： issue: Uncaught SyntaxError: Unexpected token c ， 其中有人提及。 
配置恢复 
安装 sync-settings 插件完成后，将 settings 设置完成，通过命令 sync settings: restore 即可开始恢复配置，在其恢复过程中，可切换开启 Toggle Developer Tools 查看过程，以及是否有 package 安装失败。 
Atom 默认的配置文件 
init.coffee 
config.cson 
keymap.cson 
snippets.cson 
style.less 
但是其实还有些是插件自身的配置，比如: 
projects.cson: 管理切换 project 的 
toolbar.cson: toolbar 管理 
project.json: sync-settings 添加的 
