# 目前支付宝依然有用，可以刷步数。跟你的号有关。不少人账号黑了。那么用下面的办法。

1、在支付宝设置-隐私-个人授权管理-取消对zepp Life的授权，然后注销zeppLIfe账号，重新绑定

2、在支付宝取消授权后，新注册一个zepp Life邮箱账号并绑定支付宝即可，接下来就是利用action来刷步数。

注：目前发现是zepp life的账号变黑号导致无法同步。

手上几个号，原来是手机号，利用新注册的邮箱账号均可成功。另有2个号是手机号，没有黑，依然可用继续同步。

新注册一个zepp Life账号尽可能别用的设备，比如电脑下个安卓模拟器去注册，因为用老设备注册的号可能依然是黑号。

以上办法仅做尝试，并不能保证所有人都有效。

有人反馈绑定手环的账号是不受影响。如果无效可以考虑这个方案，


# 小米运动自动刷步数For Email    Github Actions 部署指南

# 一、Fork 此仓库

# 二、设置账号密码
> 添加名为  **USER**、**PWD**、**OPEN_GET_WEATHER**、**AREA**、**SCKEY**的变量: Settings-->Secrets-->New secret  

| Secrets |  格式  |
| -------- | ----- |
| USER |   小米运动登录账号,仅支持小米运动账号邮箱账号，不支持手机号（请注意，账号不是 [小米账号]，而是 [小米运动] 的账号。）|
| PWD |   小米运动登录密码,仅支持小米运动账号对应的密码|
|SCKEY|Server酱sckey，如无填写NO（Server酱：https://sct.ftqq.com/）（有的人填写NO会报错，那就不要输入NO，随意输入一串字符即可）|
| OPEN_GET_WEATHER|   开启根据地区天气情况降低步数**False**关闭,**True**开启|
| AREA |   设置获取天气的地区（上面开启后必填）如：**北京**，当**OPEN_GET_WEATHER**为**False**时填写**NO**|
| PAT （在登入状态下步骤3链接即可一键获取）|此处**PAT**需要申请，值为github token，需要repo和workflow权限,此项必填，避免git push的权限错误。<br><br><br>1、在 https://github.com 登录你的帐号，登录以后点击右上角你的头像的Settings<br><br>2、 点击 Developer settings 下的 Personal access tokens，如果您老人家觉得上面两个步骤很麻烦，那么您就直接进入这个链接(前提是你要先登陆你的帐号)：https://github.com/settings/tokens<br><br><br>3、点击 https://github.com/settings/tokens/new 这个超链接，就是创建你的token。<br><br>4、在Token description中随便填一个描述名称，下面的复选框是你这个token需要的权限，全部勾上就可以了。<br><br>5、生成的这个就是你的token了，可以直接复制使用。|<br>

# 最后，点击action，点击刷步数，点击 run workflow 即可运行

# 部分人配置完毕之后并没有运行，需要先点击action，点击刷步数，点击 run workflow 即可运行


# 三、自定义启动时间多账户(用不上请忽略)

>多账户请用 **#** 分割 然后保存到变量 **USER** 和 **PWD**
>
>#### 例如

>*12345@qq.com#54321@qq.com* 变量 **USER**

>**abc123qwe#abcqwe2** 变量 **PWD**

# 四、自定义启动时间(用不上请忽略)

**编辑 .github/workflows/run.yml 修改其中cron语句的判断时间为UTC时间，即北京时间-8，如北京时间8点为UTC时间0点，需要运行的时间-8就是UTC时间**

# 五、自定义随机步数范围(用不上请忽略)

**在main.py 87~88行处修改计算方法**


# 六、注意事项

**1. 每天运行六次，整由run.yml中的cron控制，分钟为随机值**

**2. 多账户的数量和密码请一定要对上 不然无法使用!!!**

**3. 启动时间得是UTC时间!**

**4. 如果支付宝没有更新步数,到小米运动->设置->账号->注销账号->清空数据,然后重新登录,重新绑定第三方**

**5. 小米运动不会更新步数，只有关联的会同步！！！！！**

**6. 请注意，账号不是 [小米账号]，而是 [小米运动] 的账号。**

**7. 本人业余，东拼西凑机缘巧合做成的，反馈问题本人不会处理**

# 七、本项目Fork别人的项目
**1. 原项目：https://github.com/great-otto/mimotion-for-email/tree/main/.github/workflows**

**2. 感谢该项目提供者**
