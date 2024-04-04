# 同步delon源的更新
* 首先要先确定一下是否建立了主repo的远程源：

   ` git remote -v`

* 如果里面只能看到你自己的两个源(fetch 和 push)，那就需要添加主repo的源：
```
git remote add upstream https://github.com/ng-alain/delon.git
git remote -v
```
然后你就能看到upstream了。
* 如果想与主repo合并：
```
git fetch upstream
git merge upstream/master
```

---

# 修改说明

官方项目有些地方不能满足需求，故进行fork然后进行修改。
尽量以增量的方式进行修改，比如以新增行、新增代码的方式来修改代码。以免同步delon更新时产生冲突。

# packages


### abc


* reuse-tab

    支持带queryString的route

    修改文件：
    * reuse-tab.interfaces.ts

      ReuseItem新增了fullUrl字段

    * reuse-tab.component.ts
      

----

# 碰到的问题

* Dependency @delon-fork/util must be explicitly whitelisted.
build到某个包，比如是@delon-fork/acl，报了以上错误，原因请自行查询。
这里的解决办法是，
需要将当前包的ng-package.json中，whitelistedNonPeerDependencies字段下的依赖包的名称修改为与依赖包package.json中一致的名称。

