# VSCODE使用技巧


---
## 1.minimap使用
### 色块渲染
VSCODE默认，渲染每行的实际字符，而不是色块。将此修改为使用色块修改。
方法：在设置中搜索，Minimap: Render Characters，去掉勾选。
{{< figure src="/images/20220228_01/fg1.jpg" title="fig.1-默认效果" >}}
{{< figure src="/images/20220228_01/fg2.jpg" title="fig.2-修改后效果" >}}

### 控制mini地图大小
VSCODE默认，mini地图的大小配置是，迷你地图的大小与编辑器内容相同。我不喜欢这个的原因是，始终需要去拖动迷你地图。
将此默认proportional模式修改为fit模式，即fill模式。这样，迷你地图始终填充编辑器高度。
注：fill和fit的区别，还未清楚。
