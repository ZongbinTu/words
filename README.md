# words

### 提取文章单词
### 对比学习过的单词
#### 获取已学习过的单词
[扇贝网页版](https://web.shanbay.com/wordsweb/#/study/entry)
进入单词书，选择“词表”
![选择词表](/doc/word_list.png)
选择“在学单词”
![在学单词](/doc/word_learning.png)
打开chrome开发者模式，在console里面输入下面的代码并回车，会自动翻页读取单词并打印到窗口

``` javascript
(function () {

    var winw = window.open ("vocabulary.html",'new windiw',"scrollbars=yes,height=1000,width=500")
    var n = 0
    var b = document.getElementsByTagName('li')
    var n1 = Number(b[b.length-2].innerText)

    function get_next_page() {

        t3 = document.getElementsByClassName('index_word__3waO0')
        for (var i = t3.length - 1; i >= 0; i--) {
            text = t3[i].innerText.split('\n')
            t = text[0]
            winw.document.write(t)
            winw.document.write("</br>")
        }
        var b = document.getElementsByTagName('li')
        n = n+1
        n1 
        b[b.length-1].click()
        if (n>=n1) {
            clearInterval(num)
            console.log('循环结束，爬取完毕')
        }
    }
    num =setInterval(get_next_page,300)
})()
```
### 得到新词，作为新单词书上传
