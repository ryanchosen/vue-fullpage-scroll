# 自制的vue-fullpage-scroll组件
大致思路:
1. 获取页面中section标签的数目，根据section标签数生成控制栏
2. 在全局window上 分别对鼠标滚轮事件,触摸事件绑定事件监听
3. 获取index, 调用原生dom api,scrollIntoView跳转到属于该index的dom元素的位置
7. 点击侧边栏的时候把绑定着的index带给全局变量`activeSection，class会根据activeSection自动更新
8. 鼠标滚动到两头时如何处理？如果activeSection等于-1就跳到index是3的位置，如果activeSection等于4就跳到index是0的位置
9. 移动端如何处理？对比e.touches[0].clientY在touchStart与touchMove两个触摸事件过程中的差值，>0则向下滚动，<0则向上滚动
# 在线预览
http://ryansu.gitee.io/vue-fullpage-scroll/
# 本地运行
`parcel src/index.html`
# 打包发布
`parcel build index.html --no-minify --public-url ./`
