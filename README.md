[![s9z3t0.png](https://s3.ax1x.com/2021/01/03/s9z3t0.png)](https://imgchr.com/i/s9z3t0)
# 实现思路
1. 获取页面中 `section` 标签的数目，根据 `section` 标签数生成控制栏
2. 在全局 `window` 上 分别对鼠标滚轮事件,触摸事件绑定事件监听
3. 获取 `index` , 调用原生dom api,`scrollIntoView` 跳转到属于该index的dom元素的位置
7. 点击侧边栏的时候把绑定着的 `index` 带给全局变量`activeSection` ，`class` 会根据`activeSection` 自动更新
8. 鼠标滚动到两头时如何处理？如果`activeSection`等于-1就跳到`index`是3的位置，如果`activeSection` 等于4就跳到`index` 是0的位置
9. 移动端如何处理？对比 `e.touches[0].clientY` 在 `touchStart` 与 `touchMove` 两个触摸事件过程中的差值，>0则向下滚动，<0则向上滚动
# 在线预览
- ![1609835634.png](https://i.loli.net/2021/01/05/6c5JUFDhR3iemQ9.png)

- http://ryansu.gitee.io/vue-fullpage-scroll/  

# 本地运行
- `parcel src/index.html`
# 打包发布
- `parcel build src/index.html --no-minify --public-url ./`
- `parcel build src/index.html --no-minify --public-url ./`
