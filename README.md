# wepy-tony-store
wepy store tony

### 项目构建
npm install wepy-cli -g

### 一些框架需要改进的地方 (Cannot read property 'script' of null)
- 同样有bug 一旦有wpy 就会被编译 等于有错误的代码会自动失败
- 就算新建一个文件夹frame 也会有同样的问题





### wxParse的wxParseImgTap的bug修复
- http://blog.csdn.net/zhuming3834/article/details/74380079

```

  wxParseImgLoad(e) {
    console.log('wxParseImgLoad')
    console.log(e)
  }

  wxParseImgTap(e) {
    console.log('wxParseImgTap')
    console.log(e)
    var that = this
    var nowImgUrl = e.target.dataset.src
    var tagFrom = e.target.dataset.from
    if (typeof (tagFrom) != 'undefined' && tagFrom.length > 0) {
      wx.previewImage({
        current: nowImgUrl, // 当前显示图片的http链接
        // urls: that.data[tagFrom].imageUrls // 需要预览的图片http链接列表
        urls: that.bindData[tagFrom].imageUrls  // 注释掉上面的 换着一行 (http://blog.csdn.net/zhuming3834/article/details/74380079)
      })
    }
  }
```

### 接口
- getKeyWordHisList X

### 知识点
- previewImage由wx提供
- contact-button (https://mp.weixin.qq.com/debug/wxadoc/dev/api/custommsg/receive.html)
- errMsg: "navigateTo:fail can not navigateTo a tabbar page"}

### 开发使用说明

使用微信开发者工具新建项目，本地开发选择dist目录。

微信开发者工具 --> 项目 --> 关闭ES6转ES5。

本地项目根目录运行npm run dev，开启实时编译。

### wepy开发文档地址
	https://tencent.github.io/wepy/

### 小程序开发文档
	http://mp.weixin.qq.com/debug/wxadoc/dev/

### 目录结构
