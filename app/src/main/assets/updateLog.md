# 更新日志
* 关注公众号 **[开源阅读]()** 菜单•软件下载 提前享受新版本。
* 关注合作公众号 **[小说拾遗]()** 获取好看的小说。
- 旧版数据导入教程：先在旧版阅读(2.x)中进行备份，然后在新版阅读(3.x)【我的】->【备份与恢复】，选择【导入旧版本数据】。

**2020/10/12**
* 优化预下载,防止同时下载太多卡顿

**2020/10/11**
* 优化书源校验
* 语言切换bug修复 by [h11128](https://github.com/h11128)

**2020/10/07**
* 更新时预下载10章
* 支持更多分组
* url添加js参数,解析url时执行,可在访问url时处理url,例
```
https://www.baidu.com,{"js":"java.headerMap.put('xxx', 'yyy')"}
https://www.baidu.com,{"js":"java.url=java.url+'yyyy'"}
```
* 修复bug

**2020/10/02**
* 优化规则解析
* 优化正文搜索
* 翻页动画跟随背景
* 双击发现折叠发现,再次双击滚动至顶端
* 修复bug

**2020/09/29**
* 增加了几个方法用于处理文件 by [Celeter](https://github.com/Celeter)
```
//文件下载,content为十六进制字符串,url用于生成文件名，返回文件路径
downloadFile(content: String, url: String): String
//文件解压,zipPath为压缩文件路径，返回解压路径
unzipFile(zipPath: String): String
//文件夹内所有文件读取
getTxtInFolder(unzipPath: String): String
```
* 增加type字段，返回16进制字符串,例:`https://www.baidu.com,{"type":"zip"}`
* 底部操作栏阴影跟随设置调节

**2020/09/24**
* 修复规则解析bug

**2020/09/21**
* 修复规则解析bug
* 换源时无最新章节信息时可加载详情页来获取(默认关闭)

**2020/09/20**
* 优化正文搜索
* 阅读界面信息添加书名

**2020/09/18**
* 解决正文替换{{title}}问题
* 修复共用布局配置不能读取的问题
* 添加自定义源分组功能 by KKL369
* 解决跨进程调用ReaderProvider出现CursorIndexOutOfBoundsException问题

**2020/09/17**
* 优化正文搜索文字颜色
* 优化书源校验 by KKL369
* 缓存导出到webDav by 10bits
* 导入的字体在字体选择界面显示

**2020/09/15**
* 修复导入排版字体重复报错的bug
* 添加正文搜索 by [h11128](https://github.com/h11128)

**2020/09/12**
* web看书同步最新章
* web写源增加图片样式等规则
* 正文规则可以使用@get:{title}获取目录标题,js里使用title

**2020/09/11**
* 修复一些bug
* 背景配置自由添加

**2020/09/10**
* 修复自动换源的bug
* 修复保存主题的bug
* 书源排序，分享，注释优化 by [h11128](https://github.com/h11128)

**2020/09/09**
* 修复主题导入导出bug
* 优化分屏模式状态栏
* 书源基本属性增加“书源注释”

**2020/09/08**
* 页眉页脚跟随背景
* 主题导入导出

**2020/09/07**
* 订阅源和替换规则添加滑动选择
* 修复排版配置导入导出
* 订阅界面添加下载文件功能

**2020/09/06**
* 优化翻页
* EInk模式独立背景
* 阅读排版配置导入导出,包括背景和字体,支持网络导入

**2020/09/03**
* 修复替换中的回车消失的bug
* 所有内容恢复htmlFormat, 在想其它办法解决丢失一些内容的问题
* 图片(漫画)支持导出

**2020/09/02**
* 搜索url支持put,get,js里使用java.put,java.get
* 对于搜索重定向的源，可以使用此方法获得重定向后的url
```
<js>
var url='https://www.yooread.net/e/search/index.php,'+JSON.stringify({
"method":"POST",
"body":"show=title&tempid=1&keyboard="+key
});
String(java.connect(url).raw().request().url())
</js>
```
* 正文合并后替换规则支持所有规则写法,包括js

**2020/09/01**
* 导入书源列表添加全不选
* 详情页菜单添加清理缓存,清理当前书籍缓存
* 修复滑动选择,选择数量不更新的bug
* 字体跟随背景,每个背景对应一个字体
* 优化图片下载

**2020/08/29**
* 修复一个null引起的崩溃bug
* 修复我的界面滚动时图标消失的bug
* 修复从详情页目录打开章节内容不对的bug
* 书源选择增加滑动选择, 选择框区域滑动时进行选择 by [Mupceet](https://github.com/Mupceet)
* 请求头,支持http代理,socks4 socks5代理设置 by [10bits](https://github.com/10bits)
```
socks5代理
{
  "proxy":"socks5://127.0.0.1:1080"
}
http代理
{
  "proxy":"http://127.0.0.1:1080"
}
支持代理服务器验证
{
  "proxy":"socks5://127.0.0.1:1080@用户名@密码"
}
注意:这些请求头是无意义的,会被忽略掉
```

**2020/08/28**
* 修复一些bug
* 换源不再改变书名和作者，防止换到一些错误的书源后不能再换源

**2020/08/27**
* 修复主题bug
* 修复封面bug
* 优化书籍更新,搜索,换源
* e-ink模式不再固定背景

**2020/08/26**
* js添加java.encodeURI(speakText),用于解决js编码时有~的语句朗读不出来
* 修复书名太长删除阅读记录按钮不显示的bug
* 完成本地书籍编码选择

**2020/08/25**
* 阅读记录可以删除了
* 修复翻页模式选择颜色问题
* 修复toolbar在一些情况下文字颜色不对的bug
* 多设备阅读记录叠加
* 封面链接支持修改headers

**2020/08/24**
* 应用被杀死时停止朗读
* 默认封面添加删除操作
* 备份阅读记录
* 书源添加移除分组支持多选，多个分组以逗号(中英均可)隔开
* 可以自定义在线朗读了

**2020/08/22**
* 添加阅读时间记录

**2020/08/21**
* 图片(漫画源)支持离线下载了

**2020/08/20**
* 正文图片(漫画源)链接支持修改headers

**2020/08/19**
* 选择文本替换时带入书名和书源

**2020/08/16**
* 添加亮度调节控件显示开关
* 添加应用内语言切换
* 底栏颜色限制去除,自动适配

**2020/08/12**
* 增加了Content Provider 接口支持 by [w568w](https://github.com/w568w)
* 修复阅读界面加入书架后,书籍详情页还是显示加入书架按钮的bug
* 修复低版本手机自动阅读速度拉动最左边崩溃的bug
* 给亮度调节加个半透明背景,很多人找不到
* 修复替换分组选择无效的bug
* 备份添加书签
* 修复web端进度更新后手机端进入阅读界面进度不变的bug
* 增加了txt目录规则备份
* 优化了导入功能,导入之前对比已有书源,可选择性导入
* 其它一些bug修复

**2020/08/08**
* 继续适配主题,现在应该所有地方都按照主题变色了
* 朗读定时增加到3个小时,朗读暂停恢复后继续定时
* 优化了主题颜色选择,会影响体验的颜色禁止选,会有提示
* 订阅规则下一页支持页数,下一页规则填page

**2020/08/07**
* 修复其它一些主题色没有适配到的地方
* 添加默认启用替换配置

**2020/08/06**
* 菜单背景根随主题色
* 修复其它一些主题色没有适配到的地方
* 取消图片颜色为FULL时的自动滚动
* 其它一些优化,升级库文件之类
* 显示订阅加入恢复忽略列表

**2020/08/03**
* 修复一些主题色没有适配到的地方
* 尝试修复书架最新章节更新不及时的bug

**2020/08/02**
* 阅读菜单底部几个按钮的背景动态设置为底部操作栏颜色
* 优化书签功能,解决一些bug

**2020/07/29**
* 正文图片样式为FULL的自动为滚动模式

**2020/07/28**
* 长图正文规则添加图片样式FULL,可以滚动浏览了

**2020/07/26**
* 优化翻页,加快翻页速度

**2020/07/25**
* 正文规则添加多页合并后的替换规则,格式同样是##regex##replaceTo
* 正文图片添加长按缩放
* 正文规则添加图片样式规则,可以设置为FULL
* 其它一些bug修复

**2020/07/21**
* 优化文字选择,不再缓存
* 添加忽略恢复列表,方便不同手机配置不同
* 其它一些bug修复

**2020/07/19**
* 添加自定义默认封面
* 修复封面选择本地图片时书架不显示的bug

**2020/07/14**
* 添加英文语言 by [52fisher](https://github.com/52fisher)

**2020/07/13**
* 在线阅读图片支持测试成功,最好把替换净化关了,防止图片url不对
* 书源保留img标签就行,@html自动保留标签

**2020/07/12**
* epub显示图片,未完善
* 在线阅读也支持图片,还未测试

**2020/07/11**
* epub可以正确识别书名和作者了
* epub封面正确显示

**2020/07/10**
* 修复一些窗口再墨水屏上背景透明的问题
* 添加epub支持
* web阅读时记住进度
* 导入书源时系统文件选择器可以选择json文件

**2020/07/06**
* 优化下载

**2020/07/05**
* 修复夜间模式底栏颜色调整无效的bug
* 【web看书】加了翻页、排序等 by [Celeter](https://github.com/Celeter)
* 两部xx' is recognized as a title by [52fisher](https://github.com/52fisher)
* 添加下载错误日志,从下载菜单浏览
* 修复vip标识引发的bug

**2020/07/04**
* 修复滚动bug
* 其它一些优化

**2020/07/03**
* 修复关闭两端对齐是朗读高亮不准确的bug
* 添加文字底部对齐开关

**2020/06/25**
* E-Ink模式合并到主题模式里, E-Ink模式不能修改阅读界面背景和文字颜色
* 添加判断,防止背景透明引起重影,花屏问题

**2020/06/22**
* 修复xpath获取正文多了许多逗号的bug
* 修复检验有效书源移除失效分组失败的bug

**2020/06/21**
* 双击书架图标返回顶部

**2020/06/20**
* 适配NavigationBar

**2020/06/19**
* 修复eInk bug
* 修复分组下载bug
* 导入本地添加滚动条

**2020/06/18**
* fadeapp.widgets:scrollless-recyclerView导致有些手机重影,暂时去除
* 下载界面添加分组
* 修复eInk bug

**2020/06/17**
* 修复更新书架时更新禁止更新的问题
* 修复导入旧版本数据问题

**2020/06/16**
* 刷新时只刷新当前书架
* 修复恢复备份需要退出重进的问题
* 保存打开 E-Ink 模式前的主题、翻页动画，关闭后恢复之前的配置, 现在可以切着玩了
* 修复因繁体语言导致的崩溃bug

**2020/06/15**
* 添加 E-Ink 模式 by [Modificator](https://github.com/Modificator)
* 修复发现打开书时可能的错误

**2020/06/14**
* 修复txt文件目录识别
* 书源分组添加已启用已禁用

**2020/06/13**
* 优化搜索

**2020/06/12**
* 修复分组变化的bug

**2020/06/10**
* 正文字体的粗细选择增加可以选择细体(Android O生效) by [hingbong](https://github.com/hingbong)
* 修复bug

**2020/06/09**
* 修复从发现界面打开已在书架的书时,显示不对的问题

**2020/06/07**
* 优化书源检测,自定义搜索关键词
* 失效书源如果校验为有效会去掉失效标志

**2020/06/06**
* 修复一些bug,包括从阅读界面退出后还是显示红色更新的bug

**2020/06/03**
* zh-TW translation by david082321
* 修复音频播放时播放速度调节会再下一章失效的bug

**2020/05/31**
* 更新到android studio 4.0
* 书源排序添加按url
* 去除朗读通知的进度条
* 修复恢复问题,暂时去除混淆

**2020/05/24**
* 添加自动翻页速度调节

**2020/05/23**
* 添加文字两端对齐配置

**2020/05/20**
* Rss列表增加一种显示样式

**2020/05/18**
* 修复http://alanskycn.gitee.io/书源导入失败问题,被屏蔽UA了
* Rss列表添加样式切换

**2020/05/17**
* 自动翻页功能完成
* 替换规则输入时弹出辅助输入条

**2020/05/10**
* 添加识别rss分组中的频道信息，在菜单中可以切换频道 from [yangyxd](https://github.com/yangyxd)
* 源管理添加置底,批量置顶,批量置地
* 封面选择本地图片完成

**2020/05/04**
* 优化txt文件目录解析

**2020/05/03**
* 优化一些界面显示问题
* 订阅源添加style
* 修复一些重复目录的bug

**2020/05/02**
* 修复不停换源的bug
* 修复本地书籍自动换源
* 修复书源校验的一些问题

**2020/05/01**
* 尝试修复朗读时可能错位的bug
* 添加自动换源配置
* 换源添加禁用菜单

**2020/04/29**
* 修复bug
* 订阅界面添加长按菜单

**2020/04/26**
* 添加导入旧的书源转换
* 修复不自动朗读下一章的bug

**2020/04/25**
* 修复翻页按键设置为空时崩溃的bug
* 翻页按键优先自定义按键,可覆盖音量按键
* 写书源时的辅助键盘添加※
* 更改了书源格式,不再需要转义符

**2020/04/24**
* 坚果云最近调整了策略,必须使用应用密码才能备份,用户信息,安全,第三方应用
* text目录规则添加id字段,负值为系统自带规则
* 其它一些优化

**2020/04/20**
* 优化阅读界面信息显示

**2020/04/19**
* 添加阅读界面各种信息设置

**2020/04/18**
* feat: 中文简繁处理库换成 HanLP, 中文增加 zh-rHK 翻译, [hingbong](https://github.com/hingbong)
* 修复更新时间不对的bug

**2020/04/13**
* 去除rss朗读时的引号

**2020/04/13**
* 修复调用webView返回结果多了引号的bug

**2020/04/12**
* 解决无法取消加粗的bug
* 修复换源自动加入书架的bug

**2020/04/09**
* 修复书架刷新闪烁

**2020/04/08**
* 可以隐藏书架未分组

**2020/04/07**
* 书架添加未分组,有未分组书籍时自动显示
* 其它一些优化

**2020/04/04**
* 优化备份逻辑
* 修复订阅分类太多显示不全的bug
* 修复一些分类要手动刷新的问题

**2020/04/02**
* 书架书名和作者作为唯一值
* 添加订阅分类,分类规则和发现一样,分类一::url1 && 分类2::url2

**2020/03/29**
* 添加退出软件后是否响应耳机按键的开关
* 优化书源校验

**2020/03/26**
* 修复txt目录bug
* 最近工作比较忙,只有晚上有时间写软件,bug之类的不要催,白天不回消息

**2020/03/25**
* 修复7.1.1的网络问题,是retrofit2库最新版本的bug,暂时退回上版本
* 去除下载路径的配置,减少错误
* 添加隐藏状态栏是否扩展到刘海

**2020/03/24**
* txt文件第一章之前的文字不再放到简介里
* 优化txt目录识别,章节超过3万字判断为目录识别错误重新识别
* 修复文件关联 by [wqfantexi](https://github.com/wqfantexi)

**2020/03/22**
* 添加文件关联 by [wqfantexi](https://github.com/wqfantexi)
* 手动排序可以了,在书架整理里面拖动排序
* 删除分组时同时删除书籍里的分组信息,下次添加新分组时不会自动出现在分组内
* 修复换源丢失分组信息的bug
* 修复部分朗读引擎不自动朗读下一章的bug

**2020/03/21**
* 详情页点击书名搜索

**2020/03/20**
* 自动备份文件和手动备份文件分开
* 修复一些rss收藏取消不了的bug
* 修复rss请求头无效bug

**2020/03/19**
* 美化界面我的 by [yangyxd](https://github.com/yangyxd)
* 优化搜索

**2020/03/18**
* 尝试修复搜索时崩溃
* 解决看过书籍的移到顶部需要向上滚动才能看到的bug
* 只有再书源被删除找不到书源时才会自动换源
* 美化界面 by [yangyxd](https://github.com/yangyxd)
* 订阅后台播放

**2020/03/16**
* 修复滚动模式切换章节位置不归0的bug
* 修复文字选择更多菜单在部分手机上报错的bug
* 修复文字选择菜单问题

**2020/03/15**
* 加载正文无书源时自动换源

**2020/03/14**
* 修改导航栏图标

**2020/03/13**
* 更改书架控件,ViewPager2替换回2.0使用的ViewPager,解决下拉不流畅问题
* 修复点击作者搜索后,打开的详情页还是原来的书籍的bug
* 修改朗读菜单
* 优化rss朗读

**2020/03/12**
* 导入本地添加需要权限模式

**2020/03/11**
* 修复调节上边距时下边距一起动的bug
* 适配沚水的web阅读 by [六月](https://github.com/Celeter)
* 分组管理页面调整 by [yangyxd](https://github.com/yangyxd)

**2020/03/10**
* 优化文字选择菜单弹出位置
* 添加屏幕方向控制
* 添加点击作者搜索

**2020/03/09**
* 底部文字对齐
* 主题添加阴影调节 by [yangyxd](https://github.com/yangyxd)

**2020/03/08**
* 订阅长按保存图片
* 订阅全屏播放
* 书架全部分组可以隐藏了
* 内置web书架基本能用了 by [六月](https://github.com/Celeter)
* 书架整理加入未分组
* 显示总进度
* 隐藏状态栏时,标题显示在上方

**2020/03/07**
* 添加标题上下间距调整
* 添加标题大小调整
* 书籍整理添加批量启用禁用更新
* 换源禁用书源不显示
* 修复搜索界面简介最下面显示半行文字
* 搜索历史改为多行

**2020/03/06**
* 添加隐藏标题
* 行距段距改成倍距,根据字体大小变化
* 修复翻页时右下角页数闪烁
* 修复朗读错行
* 添加底部分隔线,开关在边距设置里

**2020/03/05**
* 修复翻页动画
* 修复主题模式跟随
* 修复滚动翻页切换章节时跳动
* 适配阅读3.0的web做源
* 本地目录规则网络导入

**2020/03/04**
* 修复仿真翻页动画
* 添加阅读记录同步,正常退出进入软件时同步阅读记录

**2020/03/03**
* 修复bug
* 优化排版,确保段距为0时每行在相同的位置
* 修复底部遮挡

**2020/03/02**
* 添加书源登录
* 替换规则实时生效
* 页面最后一行计算是否能放下时不计算行距
* 优化翻页动画
* 优化书源校验
* 按键翻页有动画了

**2020/03/01**
* 修复书源解析的一个bug
* 添加底部操作栏颜色配置
* 修复滚动点击翻页,修复滚动最后一页显示加载中
* 去除备份恢复默认路径
* 尝试修复部分手机一键导入书源报错
* 翻页还有些bug不用反馈了,我已经知道,会修复的

**2020/02/29**
* 添加书源一键导入
* 修复主题模式跟随系统
* 修复书源校验
* 添加书架排序
* 添加点击翻页开关
* 修复共用布局没有记住配置的bug

**2020/02/28**
* 解决阅读界面部分字体超出范围的问题
* 修复背景切换有时空白的bug
* 修复滚动翻页问题

**2020/02/27**
* 修复bug,边距调节,换源等一些bug,记不清了
* 修复默认字体问题
* 改了下包名,好上架应用市场

**2020/02/26**
* 修复仿真翻页
* 功能添加: 选择默认字体时, 可选择字体默认字体(非衬线), 系统衬线字体, 系统等宽字体by [hingbong](https://github.com/hingbong)

**2020/02/25**
* 优化文本选择和滚动,感觉很完美了

**2020/02/24**
* 滚动暂时可以滚了,先这样吧,头大
* 紧急修复朗读报错的bug

**2020/02/23**
* 修复BUG
* 本地目录正则自定义完成
* 选择文本修复框选不全的问题,增加操作按钮

**2020/02/22**
* 长按选择完成

**2020/02/21**
* 重写了阅读界面,实现了段距调整,两端对齐,页眉页脚调整
* 选择文本暂不可用,滚动暂不可用,仿真翻页还有问题

**2020/02/19**
* 导出功能完成
* 其它一些优化,仿真翻页有点问题,还没找到问题所在

**2020/02/15**
* 修复bug
* 添加一个图标
* 阅读界面文本选择开关
* 书源管理发现开启关闭标志

**2020/02/14**
* 书籍分组支持一本书籍在多个分组,既可以在追更,又可以在玄幻
* 搜索界面限制刷新频率,每秒刷新一次
* 添加一种图标,2.0的老图标

**2020/02/13**
* 修复BUG
* 优化已下载检测,解决目录卡顿
* 添加切换图标

**2020/02/12**
* 修复bug
* 优化,网页编码优先使用书源配置的编码
* 其它一些优化
* 添加简繁转换

**2020/02/10**
* 多页目录并行获取解析
* 优化详情页
* 优化换源页面,添加换源是否加载目录配置
* 换源顺序按书源顺序排列

**2020/02/09**
* 优化书源管理,备份恢复
* 主题色修改,底部操作栏更明显

**2020/02/08**
* 书架分组调整顺序后,书架及时变动

**2020/02/07**
* 优化
* 书源校验
* 书架整理

**2020/02/05**
* 修复bug
* Rss收藏功能完成
* Rss已读标记不会再丢失

**2020/02/04**
* 主界面切换时自动隐藏键盘
* 添加本地书籍完成,解析txt文件完成,本地txt可以看了
* 封面换源,书籍信息界面点击封面弹出封面换源界面
* 默认封面绘制书名和作者
* 修复在线朗读遇到单独标点,停止朗读的问题

**2020/02/02**
* merged commit e584606, rss修复BaseURL模式下部分图片无法加载, 修复可能出现的乱码
* 菜单添加网址功能完成

**2020/01/31**
* 修复搜索闪退,因为默认线程为0了

**2020/01/30**
* 优化缓存文件夹选择,不再需要存储权限
* 修复替换净化导入报错的bug

**2020/01/27**
* 添加根据系统主题切换夜间模式
* 合并Modificator提交的代码

**2020/01/26**
* 修复bug
* 未加入书架可查看目录

**2020/01/24**
* 添加线程数配置
* 记住退出时的书架
* 添加屏幕超时配置

**2020/01/11**
* RSS阅读界面添加朗读功能
* 其它一些优化
* 合并KKL369提交的代码,重写LinearLayoutManager，修复书籍目录模糊搜索后scrollToPosition在可见范围不置顶

**2020/01/10**
* 合并KKL369提交的代码

**2020/01/08**
* 导入本地源不再需要存储权限

**2020/01/07**
* 修复备份问题
* 设置背景不再需要存储权限

**2020/01/06**
* 适配Android 10 权限
* 备份恢复不再需要存储权限

**2020/01/03**
* 适配Android 10 权限
* 导入旧版本配置不在需要存储权限
* 选择字体不在需要存储权限
* 修改书源调试
  - 调试搜索>>输入关键字，如：`系统`
  - 调试发现>>输入发现URL，如：`月票榜::https://www.qidian.com/rank/yuepiao?page={{page}}`
  - 调试详情页>>输入详情页URL，如：`https://m.qidian.com/book/1015609210`
  - 调试目录页>>输入目录页URL，如：`++https://www.zhaishuyuan.com/read/30394`
  - 调试正文页>>输入正文页URL，如：`--https://www.zhaishuyuan.com/chapter/30394/20940996`
* 修改订阅中自动添加style的情景
  订阅源的内容规则中存在`<style>`或`style=`时，直接显示内容规则的原始内容
