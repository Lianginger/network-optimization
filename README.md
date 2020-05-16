# Network-optimization
透過壓縮檔案、壓縮圖片、Media Query、合併檔案，來優化網頁速度。

![before-optimize](https://github.com/Lianginger/network-optimization/blob/master/before-optimize.png)  

![after-optimize](https://github.com/Lianginger/network-optimization/blob/master/after-optimize.png)

## Minimize all text
- [HTML Minifier](https://www.willpeavy.com/tools/minifier/)
- [UglifyJS](https://skalman.github.io/UglifyJS-online/)
- [CSSMinifier](https://cssminifier.com/)

## Minimize images
除了壓縮，也將圖片裁減到需要的圖片寬度
- [TinyPNG](https://tinypng.com/)
- [jpeg-optimizer](http://jpeg-optimizer.com/)

## Media Queries
小銀幕寬度，就用小尺寸背景圖( 大尺寸背景圖並不會一起下載 )
```
@media screen and (max-width:500px) {
  body{
    background:url(small-background.jpg) no-repeat center center fixed;
    background-size:cover;
  }
}
```

## Minimize of files
因為[瀏覽器中的最大並行 HTTP 連接數](https://stackoverflow.com/questions/985431/max-parallel-http-connections-in-a-browser)( 先不考慮 http2 )，像 webpack 一樣，把分散的檔案統整成一個檔