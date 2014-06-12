移动WEB开发BUG集锦
=========================

暂时没有分类整理，先堆一起，不一定都是bug。不要问我原理，踩一个记一个而已。

**问题：** Android 4.1 input placeholder 对不齐，设置 height == line-height 无用

**解决：** 为 input 设置高度，并设置 line-height: normal;

**问题：** 滑动卡顿

**解决：** -webkit-overflow-scrolling: touch; (iOS only)

**问题：** Android 下 fixed 定位左右偏移

**解决：** 同时设置 left:0; right:0;

**问题：** 呼出 iOS 数字键盘

**解决：** 设置 input 的 type＝"tel"

**问题：** Android 2.3 max-height 失效

**解决：** 要和 overflow:hidden; 同时使用，需要飘出的元素用 padding 露出

**问题：** Android 下 transform: translate 的内部绝对定位元素不可点

**解决：** 不用绝对定位或不可点元素添加 transform: translateX(0px)

**问题：** 取消点击时半透明背景色

**解决：** -webkit-tap-highlight-color: rgba(0,0,0,0)

**问题：** 使用 -webkit-line-clamp:2; 时正好两行和超出两行渲染高度不同

**解决：** 未知

**问题：** 禁止 iOS 呼出菜单/保存图片/新窗口打开链接/彻底干掉点击效果

**解决：** -webkit-touch-callout: none;

**问题：** 去掉 input 首字母大写及联想功能

**解决：** <input autocomplete="off" autocorrect="off" />

**问题：** 让 input 显示“搜索”而不是“换行”

**解决：** 1，input 加上 type＝"search"; 2，外层套上 form 标签，同时监听 submit 事件并阻止默认行为

**问题：** 阻止被特定区域挡住的 DOM 元素响应事件

**解决：** pointer-events: none; 如果该特定区域内部需要响应事件，则将内部元素设置为 pointer-events: auto;

**问题：** 三星 Note 3 中 text-indent 撑开的 box 使用 overflow:hidden; 挡不住

**解决：** 使用其他方案如 color:rgba(0,0,0,0) 来隐藏文字

**问题：** Android 下 input focus 高亮外框无法消除

**解决：** 

    textarea, input{
        -webkit-tap-highlight-color: rgba(255, 255, 255, 0);    
        -webkit-user-modify: read-write-plaintext-only;
        outline: none !important;
    }
    



