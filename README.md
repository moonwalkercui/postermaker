# Postermaker 海报生成器
A poster make base on gd lib. (PHP)  一个用php生成海报的神器

# Usage 用法

比如在文件someaction.php中使用：
```
$poster = new \PosterMaker\Postermaker(800, 1100);
$poster
    ->addImg('./bg.jpg', [0,0], [800, 1100])
    ->addImg('./data/upload/cover.jpg', [30,30],[740, 500])
    ->addImg('./data/upload/avatar.png', [520,620],[200, 200])
    ->addText('2020雅思口语刷题班', 30, [30,610], [255, 255, 255])
    ->addText('授课老师：Rico', 24, [30,720], [255, 255, 255])
    ->addText('coolhand', 24, [30,870], [255, 255, 255])
    ->addText('邀请你一起学习', 24, [30, 910], [255, 255, 255])
    ->addText('长按扫码听课', 24, [30,950], [255, 255, 255])
    ->addQrCode('http://com/123', [500,800],[250,250])
    ->render();
```

### 安装
```
composer require moonwalkercui/postermaker:0.1.4
```
### addImg
按大小创建一个海报 
```
$poster = new \PosterMaker\Postermaker(800, 1100); // (width, height)
```
### addImg
添加图片 (图片路径, [x坐标, y坐标], [width, height])
```
$poster->addImg('./data/upload/cover.jpg', [30,30],[740, 500])
```
### addText
添加图片 (文字内容, 字体大小, [x坐标, y坐标], 颜色[R,G,B])
```
$poster->addText('2020雅思口语刷题班', 30, [30,610], [255, 255, 255])
```
### addQrCode
添加二维码 (文字内容, [x坐标, y坐标], [width, height])
```
$poster->addQrCode('http://com/123', [500,800],[250,250])
```
### render
添加图片 (文字内容, 字体大小, [x坐标, y坐标], 颜色[R,G,B])
```
$poster->render('./save.png'); // 保持为图片
// or
$poster->render(); // show image in html: `<img src="someaction.php" style="border-radius: 20px;"/>`
```
# Thinkphp等框架里中的使用
因为有些php框架的控制器默认输出html，所以如果在控制器里直接输出图片的话，需要在控制器最后一行加上：
```
return response()->contentType('image/png');
```
或者用exit
```
exit();
```

# Author
Ryan
Email:541720500@qq.com