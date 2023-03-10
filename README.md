本网站“椛椛的功能列表”即将删除，请勿依赖使用，如必须使用，请联系主人重新制作
## 下面是椛椛的功能列表
上次修改时间：2023年2月17日
#### 群主/管理指令
<details>
  <summary>插件控制</summary>

  - [x] /启用 xxx (在发送的群启用xx功能)

  - [x] /禁用 xxx (在发送的群禁用xx功能)

  - [x] /服务列表
  
  - [x] /用法 xxx

  * 以上功能仅群主/管理可使用

</details>

#### 高优先级
<details>
  <summary>睡眠记录</summary>

  - [x] 早安 | 晚安

</details>
<details>
  <summary>群管</summary>

  - [x] 禁言[@xxx][分钟]

  - [x] 解除禁言[@xxx]

  - [x] 我要自闭 | 禅定 x [分钟 | 小时 | 天]

  - [x] 开启全员禁言

  - [x] 解除全员禁言

  - [x] 升为管理[@xxx]

  - [x] 取消管理[@xxx]

  - [x] 修改名片[@xxx][xxx]

  - [x] 修改头衔[@xxx][xxx]

  - [x] 申请头衔[xxx]

  - [x] 踢出群聊[@xxx]

  - [x] 退出群聊[群号]@Bot

  - [x] \*入群欢迎

  - [x] \*退群通知

  - [x] 设置欢迎语[欢迎~]  可选添加 [{at}] [{nickname}] [{avatar}] [{id}]

  - [x] 在[MM]月[dd]日的[hh]点[mm]分时(用[url])提醒大家[xxx]

  - [x] 在[MM]月[每周 | 周几]的[hh]点[mm]分时(用[url])提醒大家[xxx]

  - [x] 取消在[MM]月[dd]日的[hh]点[mm]分的提醒

  - [x] 取消在[MM]月[每周 | 周几]的[hh]点[mm]分的提醒

  - [x] 在"cron"时(用[url])提醒大家[xxx]

  - [x] 取消在"cron"的提醒

  - [x] 列出所有提醒

  - [x] 翻牌

  - [x] [开启 | 关闭]入群验证

  - [x] [开启 | 关闭]gist加群自动审批

  - [x] 对信息回复:[设置 | 取消]精华

  - [x] 取消精华 [信息ID]

  - [x] /精华列表

  - [ ] 同意好友请求

  - [x] 对信息回复: 撤回

  - [ ] 警告[@xxx]

  - 注：使用gist加群自动审批，请在群介绍添加以下说明，同时开启`需要回答问题并由管理员审核`：加群请在github新建一个gist，其文件名为本群群号的字符串的md5(小写)，内容为一行，是当前unix时间戳(10分钟内有效)。然后请将您的用户名和gist哈希(小写)按照username/gisthash的格式填写到回答即可。

  - 设置欢迎语可选添加参数说明：{at}可在发送时艾特被欢迎者 {nickname}是被欢迎者名字 {avatar}是被欢迎者头像 {uid}是被欢迎者QQ号 {gid}是当前群群号 {groupname} 是当前群群名

</details>
<details>
  <summary>定时指令触发器</summary>

  - 注意：触发器具有限速，每 2s 仅允许最多一次触发

  - [x] 记录以"完全匹配关键词"触发的(代表我执行的)指令

  - [x] 取消以"完全匹配关键词"触发的(代表我执行的)指令

  - [x] 记录在"cron"触发的(别名xxx的)指令

  - [x] 取消在"cron"触发的指令

  - [x] 查看所有触发指令

  - [x] 查看在"cron"触发的指令

  - [x] 查看以"完全匹配关键词"触发的(代表我执行的)指令

  - [x] 注入指令结果：任意指令

  - [x] 执行指令：任意指令

  - 注：任意指令可以使用形如`?::参数1提示语::1!`,`?::参数2提示语::2!`,`?::?可选参数3提示语，不回答将填入空值::3!`,`!::从url获取的参数::4!`,`!::?可选的从url获取的参数，出错将填入空值::5!`的未定参数，在注入时一一匹配

  - 一些示例

> 每日9:30推送摸鱼人日历

```
记录在"30 9 * * *"触发的指令
run[CQ:image,file=https://api.vvhan.com/api/moyu]
```

> 每日12:00以1/2概率执行coser指令

```python
记录在"0 12 * * *"触发的指令
注入指令结果：>runcoderaw py
from random import random
if random() > 0.5: print('coser')
else: print('今天没有coser哦~')
```

> 每日15:00询问设置定时者否想看coser

```python
记录在"0 15 * * *"触发的指令
注入指令结果：>runcoderaw py
if '?::想看coser吗？::1!' == '想': print('coser')
else: print('好吧')
```

> 自行编写简易的选择困难症助手小插件

```python
记录以"简易的选择困难症助手"触发的指令
执行指令：>runcoderaw py
from random import random
if random() > 0.5: print('您最终会选?::请输入您的选择1::1!')
else: print('您最终会选?::请输入您的选择2::2!')
简易的选择困难症助手
```

> 自行编写随机b站404页趣图插件

```python
记录以"随机b站404页趣图"触发的代表我执行的指令
注入指令结果：>runcoderaw py
import json
j = json.loads(r'''!::https://api.iyk0.com/bili_chart::1!''')
print("run[CQ:image,file="+j["img"]+"]")
随机b站404页趣图
```

![随机b站404页趣图](https://user-images.githubusercontent.com/41315874/157371451-c09ad3bb-c61a-4a42-9c47-fab3305bc0f8.png)

  - [x] [我|大家|有人][说|问][正则表达式]你[答|说|做|执行][模版]

  - [x] [查看|看看][我|大家|有人][说|问][正则表达式]

  - [x] 删除[大家|有人|我][说|问|让你做|让你执行][正则表达式]

  - 注：模版是指含有`$1` `$2`这样的未定参数，会在正则匹配时按顺序填入子匹配对应值

</details>

#### 中优先级
<details>
  <summary>ahsai tts</summary>

  - [x] 使[ 伊織弓鶴 | 紲星あかり | 結月ゆかり | 京町セイカ |東北きりたん | 東北イタコ | ついなちゃん標準語 | ついなちゃん関西弁 | 音街ウナ | 琴葉茜 | 吉田くん | 民安ともえ | 桜乃そら | 月読アイ | 琴葉葵 | 東北ずん子 | 月読ショウタ | 水奈瀬コウ ]说(日语)

</details>
<details>
  <summary>AIWife</summary>

  - [x] waifu | 随机waifu(从[100000个AI生成的waifu](https://www.thiswaifudoesnotexist.net/)中随机一位)

</details>
<details>
  <summary>触发者撤回时也自动撤回</summary>


  - [x] 你撤回了指令, 椛椛也会撤回

</details>
<details>
  <summary>base16384加解密</summary>

  - [x] 加密xxx

  - [x] 解密xxx

  - [x] 用yyy加密xxx

  - [x] 用yyy解密xxx

</details>
<details>
  <summary>百度一下</summary>

  - [x] 百度下[xxx]

</details>
<details>
  <summary>百度内容审核</summary>

  - [x] 获取BDAkey

  - [x] 配置BDAKey [API Key] [Secret Key]

  - [x] 获取BDAkey

  - [x] [开启|关闭]内容审核

  - [x] [开启|关闭]撤回提示

  - [x] [开启|关闭]详细提示

  - [x] [开启|关闭]撤回禁言

  - [x] [开启|关闭]禁言累加

  - [x] [开启|关闭]文本检测

  - [x] [开启|关闭]图像检测

  - [x] 设置最大禁言时间[分钟，默认:60,最大43200]

  - [x] 设置每次累加时间[分钟，默认:1]

  - [x] 设置撤回禁言时间[分钟，默认:1]

  - [x] 查看检测类型

  - [x] 查看检测配置

  - [x] 测试文本检测[文本内容]

  - [x] 测试图像检测[图片]

  - [x] 设置检测类型[类型编号]

  - [x] 设置不检测类型[类型编号]

    检测类型编号列表:[1:违禁违规|2:文本色情|3:敏感信息|4:恶意推广|5:低俗辱骂|6:恶意推广-联系方式|7:恶意推广-软文推广]
</details>
<details>
  <summary>base64卦加解密</summary>

  - [x] 六十四卦加密xxx

  - [x] 六十四卦解密xxx

  - [x] 六十四卦用yyy加密xxx

  - [x] 六十四卦用yyy解密xxx

</details>
<details>
  <summary>base天城文加解密</summary>

  - [x] 天城文加密xxx

  - [x] 天城文解密xxx

  - [x] 天城文用yyy加密xxx

  - [x] 天城文用yyy解密xxx

</details>
<details>
  <summary>bilibili</summary>

  - [x] >vup info [xxx]

  - [x] >user info [xxx]

  - [x] 查成分 [xxx]

  - [x] 查弹幕 [xxx] 2 (最后一个参数是页码)

  - [x] 设置b站cookie b_ut=7;buvid3=0;i-wanna-go-back=-1;innersign=0; (最好把cookie设全)

    获取Cookie可以使用[这个工具](https://github.com/XiaoMiku01/login_bili_go)
    
  - [x] 更新vup

</details>
<details>
  <summary>b站动态、专栏、视频、直播解析</summary>

  - [x] t.bilibili.com/642277677329285174 | bilibili.com/read/cv17134450 | bilibili.com/video/BV13B4y1x7pS | live.bilibili.com/22603245

</details>
<details>
  <summary>b站动态、直播推送,需要配合job一起使用</summary>

  - [x] 添加b站订阅[uid|name]

  - [x] 取消b站订阅[uid|name]
  
  - [x] 取消b站动态订阅[uid|name]
  
  - [x] 取消b站直播订阅[uid|name]
  
  - [x] b站推送列表
  
  - [x] 拉取b站推送 (使用job执行定时任务------记录在"@every 10s"触发的指令) 

</details>
<details>
  <summary>书评</summary>

  - [x] 书评[xxx]

  - [x] 随机书评

</details>
<details>
  <summary>打断复读</summary>

  - [x] (打断三次以上的复读)

</details>
<details>
  <summary>藏头诗</summary>

  - [x] 藏头诗[xxx]

  - [x] 藏尾诗[xxx]

</details>
<details>
  <summary>选择困难症帮手</summary>

  - [x] 选择[选择项1]还是[选项2]还是[更多选项]

</details>
<details>
  <summary>抽象话</summary>

  - [x] 抽象翻译[xxx]

</details>
<details>
  <summary>英文字符翻转</summary>

  - [x] 翻转 I love you

</details>
<details>
  <summary>coser</summary>

  - [x] coser

</details>
<details>
  <summary>cp短打</summary>

  - [x] 组cp[@xxx][@xxx]

  - [x] 磕cp大老师 雪乃

</details>
<details>
  <summary>DeepDanbooru二次元图标签识别</summary>

  - [x] 鉴赏图片[图片]

</details>
<details>
  <summary>嘉然</summary>

  - [x] 小作文

  - [x] 发大病

  - [x] 教你一篇小作文[作文]

</details>
<details>
  <summary>女装</summary>

  - [x] 女装

  - [x] 男装
  
  - [x] 随机女装
  
  - [x] 随机男装

</details>
<details>
  <summary>漂流瓶</summary>

  - [x] 捞瓶子 (随机捞一个漂流瓶)

  - [x] 丢瓶子 xxx (投递内容xxx,支持图片文字,投递内容需要大于10个字符或者带有图片)

  * 注：不要往里面丢涩图

</details>
<details>
  <summary>合成emoji</summary>

  - [x] [emoji][emoji]

</details>
<details>
  <summary>渲染任意文字到图片</summary>

  - [x] (用[终末体|终末变体|紫罗兰体|樱酥体|Consolas体|苹方体])渲染文字xxx
</details>
<details>
  <summary>每日运势</summary>

  - [x] 运势 | 抽签

  - [x] 设置底图[车万 DC4 爱因斯坦 星空列车 樱云之恋 富婆妹 李清歌 公主连结 原神 明日方舟 碧蓝航线 碧蓝幻想 战双 阴阳师 赛马娘 东方归言录 奇异恩典 夏日口袋 ASoul Hololive]

</details>
<details>
  <summary>笑话</summary>

  - [x] 讲个笑话[@xxx|qq号|人名] | 夸夸[@xxx|qq号|人名]

</details>
<details>
  <summary>原神抽卡</summary>

  - [x] 切换原神卡池

  - [x] 原神十连

</details>
<details>
  <summary>gif</summary>

  - [x] 爬[@xxx]

  - [x] 摸[@xxx]

  - [x] 搓[@xxx]

  - 注：更多指令请发送/用法 gif

</details>
<details>
  <summary>GitHub仓库搜索</summary>

  - [x] >github [xxx]

  - [x] >github -p [xxx]

</details>
<details>
  <summary>猜歌</summary>

  猜歌插件（该插件依赖ffmpeg）
	
  ---------主 人 指 令---------
  - [x] 设置猜歌歌库路径 [绝对路径]
  - [x] [创建/删除]歌单 [歌单名称]
  - [x] 下载歌曲[歌曲名称/网易云歌曲ID]到[歌单名称]
	
  -------管 理 员 指 令--------
  - [x] 设置猜歌默认歌单 [歌单名称]
  - [x] 上传歌曲[群文件的音乐名]到[歌单名称]
	
  ------公 用 指 令------
  - [x] 歌单列表
  - [x] [个人/团队]猜歌
	
  ------插 件 扩 展------
	
  - 本插件内置了[NeteaseCloudMusicApi](https://binaryify.github.io/NeteaseCloudMusicApi/#/)框架的一些功能
  - [x] 设置猜歌API帮助
  - [x] 设置猜歌API [API首页网址]
  - [x] 猜歌[开启/关闭][歌单/歌词]自动下载
  - [ ] 登录网易云
  - [x] 歌单信息 [网易云歌单链接/ID]
  - [x] [歌单名称]绑定网易云[网易云歌单链接/ID]
  - [x] 下载歌单[网易云歌单链接/ID]到[歌单名称]
  - [x] 解除绑定 [歌单名称]

</details>
<details>
  <summary>黑丝</summary>

  - [x] 来点黑丝/白丝/jk/巨乳/足控/网红

</details>
<details>
  <summary>炉石</summary>

  - [x] 搜卡[xxxx]

  - [x] [卡组代码xxx]

  - 注：更多搜卡指令参数：https://hs.fbigame.com/misc/searchhelp

</details>
<details>
  <summary>百人一首</summary>

  - [x] 百人一首

  - [x] 百人一首之n

</details>
<details>
  <summary>关键字搜图</summary>

  - [x] 来张 [xxx]

</details>
<details>
  <summary>注入指令</summary>

  - [x] run[CQ码]

</details>
<details>
  <summary>煎蛋网无聊图</summary>

  - [x] 来份[屌|弔|吊]图

  - [x] 更新[屌|弔|吊]图

  </details>
<details>
  <summary>兽语加密(嗷呜~)</summary>

  - [x] 兽语加密xxx

  - [x] 兽语解密xxx

</details>
<details>
  <summary>日语听力学习材料</summary>

  - [x] 随机日语听力
  
  - [x] 随机日语歌曲
  
  - [x] 日语听力 xxx
  
  - [x] 日语歌曲 xxx

</details>
<details>
  <summary>绝绝子</summary>

  - [x] 喝奶茶绝绝子 | 绝绝子吃饭

</details>
<details>
  <summary>MagicPrompt-Stable-Diffusion吟唱提示</summary>

  - [x] 吟唱提示[xxxx]

</details>
<details>
  <summary>日韩 VITS 模型拟声</summary>

  - [x] 让[宁宁|爱瑠|芳乃|茉子|丛雨|小春|七海]说(日语)

  - [x] 让[수아|미미르|아린|연화|유화|선배]说(韩语)

  - [x] 让[派蒙|空|荧|阿贝多|枫原万叶|温迪|八重神子|纳西妲|钟离|诺艾尔|凝光|托马|北斗|莫娜|荒泷一斗|提纳里|芭芭拉|艾尔海森|雷电将军|赛诺|琴|班尼特|五郎|神里绫华|迪希雅|夜兰|辛焱|安柏|宵宫|云堇|妮露|烟绯|鹿野院平藏|凯亚|达达利亚|迪卢克|可莉|早柚|香菱|重云|刻晴|久岐忍|珊瑚宫心海|迪奥娜|戴因斯雷布|魈|神里绫人|丽莎|优菈|凯瑟琳|雷泽|菲谢尔|九条裟罗|甘雨|行秋|胡桃|迪娜泽黛|柯莱|申鹤|砂糖|萍姥姥|奥兹|罗莎莉亚|式大将|哲平|坎蒂丝|托克|留云借风真君|昆钧|塞琉斯|多莉|大肉丸|莱依拉|散兵|拉赫曼|杜拉夫|阿守|玛乔丽|纳比尔|海芭夏|九条镰治|阿娜耶|阿晃|阿扎尔|七七|博士|白术|埃洛伊|大慈树王|女士|丽塔|失落迷迭|缭乱星棘|伊甸|伏特加女孩|狂热蓝调|莉莉娅|萝莎莉娅|八重樱|八重霞|卡莲|第六夜想曲|卡萝尔|姬子|极地战刃|布洛妮娅|次生银翼|理之律者|迷城骇兔|希儿|魇夜星渊|黑希儿|帕朵菲莉丝|天元骑英|幽兰黛尔|德丽莎|月下初拥|朔夜观星|暮光骑士|明日香|李素裳|格蕾修|梅比乌斯|渡鸦|人之律者|爱莉希雅|爱衣|天穹游侠|琪亚娜|空之律者|薪炎之律者|云墨丹心|符华|识之律者|维尔薇|芽衣|雷之律者|阿波尼亚]说(中文)

</details>
<details>
  <summary>摸鱼</summary>

  - [x] /启用 moyu

  - [x] /禁用 moyu

```
记录在"0 10 * * *"触发的指令
摸鱼提醒
```

</details>
<details>
  <summary>摸鱼人日历</summary>

  - [x] /启用 moyucalendar

  - [x] /禁用 moyucalendar

```
记录在"30 8 * * *"触发的指令
摸鱼人日历
```

</details>
<details>
  <summary>点歌</summary>

  - [x] 点歌[xxx]

  - [x] 网易点歌[xxx]

  - [x] 酷我点歌[xxx]

  - [x] 酷狗点歌[xxx]

</details>
<details>
  <summary>抽wife</summary>

  - [x] 抽wife[@xxx]

  - [x] 添加wife[名字][图片]

  - [x] 删除wife[名字]

  - [x] [让 | 不让]所有人均可添加wife

  - 注：不同群添加后不会重叠

</details>
<details>
  <summary>拼音首字母释义工具</summary>

  - [x] ?? [缩写]

</details>
<details>
  <summary>日语语法学习</summary>

  - [x] 日语语法 [xxx] (使用tag随机)
  
  - [x] 搜索日语语法 [xxx]

</details>
<details>
  <summary>小说</summary>

  - [x] 小说[xxx]

</details>
<details>
  <summary>nsfw图片识别</summary>

  - [x] nsfw打分[图片]

  - [x] 当图片属于非 neutral 类别时自动发送评价(默认禁用，启用输入 /启用 nsfwauto)

</details>
<details>
  <summary>浅草寺求签</summary>

  - [x] 求签 | 占卜

  - [x] 解签

</details>
<details>
  <summary>一群一天一夫一妻制群老婆</summary>

  - 引入好感度系统，好感度越高，自由恋爱成功率越高
  
  - [x] 设置CD为xx小时

  - [x] [允许|禁止]自由恋爱

  - [x] [允许|禁止]牛头人

  - [x] 娶群友

  - [x] [娶|嫁][@对方QQ]
  
  - [x] 当[对方Q号|@对方QQ]的小三

  - [x] 做媒 @攻方QQ @受方QQ
  
  - [x] 买礼物给[对方Q号|@对方QQ]

  - [x] 群老婆列表

  - [x] 查好感度[对方Q号|@对方QQ]

  - [x] 好感度列表

  - [x] 重置花名册

</details>
<details>
  <summary>权重查询</summary>

  - 来看看大家的账号分吧~据说越高越不容易封号哦

  - [x] 权重查询+@xxx

  - [x] 权重查询+QQ号(为空时匹配触发者QQ)

</details>
<details>
  <summary>qq空间表白墙</summary>

  - [x] 登录QQ空间 (Cookie过期很快, 要经常登录)
  
  - [x] 发说说[xxx]
  
  - [x] (匿名)发表白墙[xxx]
  
  - [x] [ 同意 | 拒绝 ]表白墙 1,2,3 (最后一个参数是表白墙的序号数组, 用英文逗号连接)
  
  - [x] 查看[ 等待 | 同意 | 拒绝 | 所有 ]表白墙 0 (最后一个参数是页码, 建议私聊审稿)

</details>
<details>
  <summary>Real-CUGAN清晰术</summary>

  - [x] 清晰术(双重吟唱|三重吟唱|四重吟唱)(强力术式|中等术式|弱术式|不变式|原式)[图片]

</details>
<details>
  <summary>投胎</summary>

  - [x] 投胎

</details>
<details>
  <summary>在线代码运行</summary>

  - [x] >runcode [language] help

  - [x] >runcode [language] [code block]

  - [x] >runcoderaw [language] [code block]

</details>
<details>
  <summary>搜图</summary>

  - [x] 以图搜图 | 搜索图片 | 以图识图[图片]

  - [x] 搜图[P站图片ID]

  - [x] 设置 saucenao api key [apikey]

</details>
<details>
  <summary>叔叔的AI二次元图片放大</summary>

  - [x] 放大图片[图片]

</details>
<details>
  <summary>签到得分</summary>

  - [x] 签到
  - [x] 获得签到背景[@xxx] | 获得签到背景
  - [x] 查看等级排名
  - 注:跨群排行
  - [x] 查看我的钱包
  - [x] 查看钱包排名
  - 注:本群排行，若群人数太多不建议使用该功能!!!

</details>
<details>
  <summary>沙雕app</summary>

- [x] 哄我
- [x] 渣我
- [x] 来碗绿茶
- [x] 发个朋友圈
- [x] 来碗毒鸡汤
- [x] 讲个段子
- [x] 马丁路德骂我

</details>
<details>
  <summary>shindan</summary>

  - [x] 今天是什么少女[@xxx]

  - [x] 异世界转生[@xxx]

  - [x] 卖萌[@xxx]

  - [x] 抽老婆[@xxx]

  - [x] 黄油角色[@xxx]

</details>
<details>
  <summary>抽塔罗牌</summary>

  - [x] 抽[塔罗牌|大阿卡纳|小阿卡纳]
  - [x] 抽n张[塔罗牌|大阿卡纳|小阿卡纳]
  - [x] 解塔罗牌[牌名]
  - [x] [塔罗|大阿卡纳|小阿卡纳|混合]牌阵[圣三角|时间之流|四要素|五牌阵|吉普赛十字|马蹄|六芒星]

</details>
<details>
  <summary>舔狗日记</summary>

  - [x] 舔狗日记

</details>
<details>
  <summary>搜番</summary>

  - [x] 搜番 | 搜索番剧[图片]

</details>
<details>
  <summary>翻译</summary>

  - [x] >TL 你好

</details>
<details>
  <summary>vits猫雷</summary>

  - [x] 让猫雷说[xxxx]

</details>
<details>
  <summary>vtb语录</summary>

  - [x] vtb语录

  - [x] 随机vtb

  - [x] 更新vtb

</details>
<details>
  <summary>网易云音乐热评</summary>

  - [x] 来份网易云热评

  </details>
<details>
  <summary>天气/拼音查询-名言</summary>

  - [x] xx天气

  - [x] xx拼音

  - [x] 每日情话/一言/鸡汤

  - [x] 绕口令

</details>
<details>
  <summary>百度文心AI</summary>

  基于百度文心API的一些功能

  key申请链接：https://wenxin.baidu.com/moduleApi/key
  
  - [x] 为[自己/本群/QQ号/群+群号]设置文心key [API Key] [Secret Key]
  
  - [x] 为[自己/本群/QQ号/群+群号]设置画图key [API Key] [Secret Key]
  
  例：“为10086设置画图key 123 456”；“为群10010设置画图key 789 101”
  
  文心key和画图key的API key 可以是相同的，只是文心key日限为200，画图日限为50，以此作区别。
  
  - [x] 文心作文 (x字的)[作文题目]
  
  - [x] 文心提案 (x字的)[文案标题]
  
  - [x] 文心摘要 (x字的)[文章内容]
  
  - [x] 文心小说 (x字的)[小说上文]
  
  - [x] 文心对联 [上联]
  
  - [x] 文心问答 [问题]
	
  - [x] 文心补全 [带“_”的填空题]
  
  - [x] 文心自定义 [prompt]

  - [x] [bot名称]画几张[图片描述]的[图片类型][图片尺寸]

  指令示例：

  - 文心作文 我的椛椛机器人

  - 文心作文 300字的我的椛椛机器人

  - 椛椛帮我画几张金凤凰，背景绚烂，高饱和，古风，仙境，高清，4K，古风的油画方图

</details>
<details>
  <summary>月幕galgame图</summary>

  - [x] 随机galCG

  - [x] 随机gal表情包

  - [x] galCG[xxx]

  - [x] gal表情包[xxx]

  - [x] 更新gal

</details>
<details>
  <summary>聊天热词</summary>

  - [x] 热词 [群号] [消息数目]|热词 123456 1000

</details>
<details>
  <summary>猜单词</summary>

  - [x] 个人猜单词

  - [x] 团队猜单词

  - [x] 团队六阶猜单词

  - [x] 团队七阶猜单词

</details>

#### 低优先级
<details>
  <summary>骂人</summary>

  - [x] 骂我

  - [x] 大力骂我

  - 注：默认禁用，开启请发送/启用 curse

</details>
<details>
  <summary>人工智能回复</summary>

  - [x] @Bot 任意文本(任意一句话回复)

  - [x] 设置回复模式[青云客 | 小爱]

</details>
