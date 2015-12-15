# nickro
Mobile H5 Upload
HTML5移动端图片上传并前端预览
用到了HTML5的FileReader对象，主要思想是由于移动端的网络不比PC快，故需要做上传前预览，采用base64编码目前是比较好的方法。前端用FileReader获取图片并转为base64编码并<img>预览，上传到服务器由后台解码生成图片并保存到磁盘。

知识点：
1.使用HTML5的FileReader对象，把图片存在内存，读取e.target.result的base64编码，前端预览<img src="data:image/png;base64,iVBORw0KG==">
2.使用canvas画img，然后使用canvas的toDataURL方法进行转码成base64编码并压缩。把压缩后的base64赋给img src属性上。
3.把base64值传给后台，后台进行解码并保存为图片。
