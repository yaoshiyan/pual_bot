# pual_bot 一个弱智的QQ机器人
pual_bot是一套建立在`Tornado`上的高效的支持并发的WebQQ机器人, 其主要功能有 执行Python代码, 贴代码, 英汉互译

# 安装配置
程序依赖tornado, 可使用 easy_install 安装
```bash
easy_install tornado
```

将`config.py.example`重命名为 `config.py`, 填入QQ号码和密码配置, 执行webqq.py脚本. 

# 更新
* 放弃原先的 pyxmpp2 mainloop 改为tornado
* 不在将验证图片放到网站上, 而是作为临时文件保存, 请使用图片查看器查看, 然后输入验证码

# 存在问题
1. 在线时间稍长, 当经过多次请求后会触发`socket.gaierror(-2, 'Name or service not known')` 异常
2. 在线时间过长会引发`httplib.BadStatusline`
3. 没有重试机制

# 问题解决
针对存在的`问题1`可以将WebQQ中所用到所有域名都加入到hosts文件中, `hosts`文件中提供了一份参考:
```bash
cat hosts >> /etc/hosts
```
