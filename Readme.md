# **[Modified-Zfile-Vue](https://github.com/ohh-haolin/Modified-Zfile-Vue)**

Original project：https://github.com/zhaojun1998/zfile-vue

**Warning:** Not Accept Further Issues! Fix it on you own.



只支持`Zfile2.9`，前端commit版本号为[f557851f61ee1898227f684e2be6adffe248049c](https://github.com/zhaojun1998/zfile-vue/tree/f557851f61ee1898227f684e2be6adffe248049c)

服务端解压目录中的`zfile-2.9.0.war`即可



## Change Log

1. 针对移动端优化响应式布局，包括
   - 主列表
   - 图片展示
2. 优化图片加载逻辑
3. 默认复制功能更改为获取当前直链，并在右键菜单中添加
4. 增加OD反代功能，详见HowTo（只支持当前直链，即保证网页访问效果）



## How To

1. 打开`/src/components/List.vue`，找到318，如下

   ```js
   data.forEach((item)=>{
       if(item.type == "FILE" && item.url)
       {
           item.url = item.url.replace("OD地址", "反代地址");
       }
   })
   ```

2. 按提示修改`item.url = item.url.replace("OD地址", "反代地址");`，可以配置若干个

3. 在`zfile-vue`的根目录下，运行

   ```bash
   npm install
   npm run-script build
   ```

   将生成的`dist`目录放到服务端`WEB-INF/classes/static/`下

4. 重启服务即可



## Debug

1. 修改`/public/zfile.config.json`中的`baseurl`
2. 在根目录输入`node server.js ./dist`，即可在`127.0.0.1:8080/index.html`进行debug



