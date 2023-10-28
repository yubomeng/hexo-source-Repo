---
title: Vue实现将页面转成PDF并下载或直接打印
date: 2023-10-26 21:47:27
aside: false
tags:
    - vue
categories: 
    - vue
top_img: "https://cdnjson.com/images/2023/10/26/be9def1c7f058bfb323518bf24d3535b.png"
cover: "https://cdnjson.com/images/2023/10/26/be9def1c7f058bfb323518bf24d3535b.png"
# abbrlink:
ai: 
   - 在Vue单页面中实现预览打印效果，可以通过调用浏览器的打印功能来实现。用户可以点击页面上的打印按钮，然后选择打印机并进行打印操作。另外，还可以使用第三方库将Vue单页面转换为PDF格式，并提供下载功能。用户可以点击页面上的PDF按钮，将当前页面转换为PDF文件并下载。
---

### 1.将Vue单页面转成pdf并下载

步骤1：下载对应的库

```shell
cnpm install html2canvas;
cnpm install jspdf --save
```

步骤2：创建一个htmlToPdf.js的js文件, 然后在main.js中全局引用一下，编写如下代码：

```js
// htmlToPdf.js
// 导出页面为PDF格式
import html2Canvas from 'html2canvas'
import JsPDF from 'jspdf'
export default {
  install(Vue, options) {
    Vue.prototype.getPdf = function () {
      var title = this.htmlTitle  //DPF标题
        html2Canvas(document.querySelector('#pdfDom'), {
          allowTaint: true,
          taintTest: false,
          useCORS: true,
          y:72, // 对Y轴进行裁切
          // width:1200,
          // height:5000,
          dpi: window.devicePixelRatio * 4, //将分辨率提高到特定的DPI 提高四倍
          scale: 4 //按比例增加分辨率 
        }).then(function (canvas) {
          let contentWidth = canvas.width
          let contentHeight = canvas.height
          let pageHeight = contentWidth / 592.28 * 841.89
          let leftHeight = contentHeight
          let position = 0
          let imgWidth = 595.28
          let imgHeight = 592.28 / contentWidth * contentHeight
          let pageData = canvas.toDataURL('image/jpeg', 1.0)
          let PDF = new JsPDF('', 'pt', 'a4')
          if (leftHeight < pageHeight) {
            PDF.addImage(pageData, 'JPEG', 0, 0, imgWidth, imgHeight)
          } else {
            while (leftHeight > 0) {
              PDF.addImage(pageData, 'JPEG', 0, position, imgWidth, imgHeight)
              leftHeight -= pageHeight
              position -= 841.89
              if (leftHeight > 0) {
              PDF.addPage()
            }
          }
        }
        PDF.save(title + '.pdf')
      })
    }
  }
}

```

```js
// main.js
import htmlToPdf from '@/util/htmlToPdf'
Vue.use(htmlToPdf)

```

步骤三：在vue页面中给需要打印的区域一个div标签，然后给div一个id，id名和htmlToPdf.js中选择的名字一致，代码如下:

```html
<div id="pdfDom">
  ... 打印的内容
</div>
```

步骤四：在data节点中声明一个htmlTitle变量，指定为pdf文件的文件名

```vue
data() {
	return {
    htmlTitle: 'pdf文件名'
  }
}

```

步骤五：在vue页面中添加一个button按钮，事件名和htmlToPdf.js中的方法名保持一致。

```vue
<el-button @click="getPdf()">PDF</el-button>
```

### 2.直接在将Vue单页面中预览打印效果

步骤一：下载打印的库

```shell
npm i print-js
npm i html2Canvas
```

步骤二：在要打印的页面引入库

```vue
import printJS from 'print-js'
import html2Canvas from 'html2Canvas'
```

步骤三：创建一个按钮，并绑定单击事件。编写对应的实现函数。

```vue
<el-button @click="goPrint">打印</el-button>
```

```vue
methods: {
  goPrint() {
  	this.isPrint = true
      html2Canvas(this.$refs.print, {
        allowTaint: true,
        taintTest: false,
        useCORS: true,
        dpi: window.devicePixelRatio * 4,
        scale: 4
      }).then((canvas) => {
        const url = canvas.toDataURL()
        printJS({
          printable: url, // 要打印的id
          type: 'image',
          style: '@page{size:auto;margin: 0cm 1cm 0cm 1cm;}' //去除页眉页脚
        })
       this.isPrint = false
    })
  }
}

```

#### 总结

以上两种打印功能的实现思路都是先将单页面通过[canvas](https://so.csdn.net/so/search?q=canvas&spm=1001.2101.3001.7020)转换成图片，然后再进行打印或下载PDF。

