当我们使用的某个库满足不了要求时，就需要对这个库进行fork，修改后发布为npm包来使用。

下面以@delon/abc为例进行说明。



* 注册npm账号

* 添加组织

@delon/abc这个包中的delon表示一个npm中的组织，我们要使用`@delon-fork/abc`这个包名称，就必须先添加一个组织: `delon-fork`.

* npm adduser

  输入npm的用户名和密码

  或者使用 npm login登录

* fork delon这个项目

* git clone 到本地

* npm install 

* npm run build


* 发布
 
进入dist/@delon/abc目录，修改package.json中的name为"delon-fork/abc"、version为"9.0.0-rc.4", 然后执行 ``` npm publish --access=public  ```

然后就可以在`https://www.npmjs.com/package/@delon-fork/abc`看到了 

> 参考文档
https://segmentfault.com/a/1190000006250554
https://www.jianshu.com/p/134fd2d62287

> 撤销发布

* npm unpublish @delon-fork/abc@9.0.0-rc.4 --force
或npm deprecate @delon-fork/abc@0.0.1

* 在项目中使用

```npm install @delon/abc@npm:@delon-fork/abc@9.0.0-rc.4 --save```


这条命令会使用别名```@delon/abc```来安装我们刚发布的```@delon-fork/abc@9.0.0-rc.4```,这样，我们的项目中就能依旧使用@delon/abc来引入我们发布的@delon-fork/abc了。

> 其他格式的版本号

```npm install @delon/abc@npm:@delon-fork/abc@9.0.0-rc.4 --save```


# build


如果将package.json中的name修改为@delon-fork/abc
Cannot find module '@delon/abc/

Error during template compile of 'DelonABCModule'