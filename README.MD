### 学到了
1. 为啥我只改了pkg1,到lerna update的时候，会显示两个包呢？
  - 因为pkg2里面有个依赖是pkg1啊，pkg1如果update了，版本号会变，所有用到它的包（如pkg2）的依赖（pkg1）版本号也会变，所以会显示像个包多会update，嗯，机智！

2. 现在有俩package， pkg1和pkg2，如果想让pkg1添加依赖pkg2，但是pkg2我还没发到npm呢，这个时候怎么让pkg1添加依赖pkg2呢
   - 简单！就用lerna add pkg2 --scope=pkg1就行，他会关联当前packages下面的包的

3. 我这里测试的pkg，还不想发到npm呢，添加个配置就好
in lerna.json
```
 "command": {
    "publish": {
      "skipNpm": true
    }
  },
```