# 这应该是最后一次的更改内容了。学校也已经不要求继续在这个网页上登记个人信息，这个程序继续更新就没有必要了。
注：学号是真的，密码是假的

第三方库需求：BeautifulSoup4,requests
    不在需要安装selenium以及浏览器驱动了，毕竟环境的太麻烦了

将程序调用添加到系统定时运行的功能，Linux中具体是crontab命令，Windows请自行探索，请将定时任务时间调整到凌晨(比如2:33)，以免填报人数过多造成错误

有待更新(但应该不会更新了)：
  1. 程序从网页上获取用户信息，而不是自己手动构建
  2. 完善程序逻辑中的捕获异常(总感觉现在程序不够健壮)
  3. 增加异常发生时对用户通知的功能

项目构成：
  1. main.py:      程序主体
  2. aes_crypt.py: 用于用户登录过程中对密码的加密，保证登录的成功
  3. s.json:       保存要提交的个人信息(每个人需要提交的信息除了具体地址外几乎都是相似的，但要注意，该文件中的地址仅适用于西北大学长安校区的用户，其他人慎用)

更多的更新要求其实也有很多，比如使用docker、加个网页前段、使用数据库什么的，但是精力有限，就先置之不理吧。
其实前一个版本的用户信息确实是从网页获得，但在程序第二次重构之后发现那种形式也不够健壮，索性就用抓包来获得信息。

要想使用的话，如果是个人那可以直接将solve函数中的参数替换成自己的学号与密码即可，如果是多人使用可将所有人的信息存储在一个列表中展开调用即可。最后使用crontab命令实现每日定时调用。
