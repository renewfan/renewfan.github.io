---
title: php图片合成
date: 2018-08-17 20:39:38
tags:
---
```
ob_clean();
header('Content-type:image/png');
//背景
$path_1 = "code_png/php_code.png";
//动态图
$path_2 = "code_png/logo.png";
//将背景和动态图片分别取到两个画布中
$image_1 = imagecreatefrompng($path_1);
$image_2 = imagecreatefrompng($path_2);
//创建一个和背景片一样大小的真彩色画布（ps：只有这样才能保证后面copy装备图片的时候不会失真）
$image_3 = imageCreatetruecolor(imagesx($image_1),imagesy($image_1));
//为真彩色画布创建白色背景，再设置为透明
$color = imagecolorallocate($image_3, 255, 255, 255);
imagefill($image_3, 0, 0, $color);
//设置透明,将image图像中的透明色设定为 color
imageColorTransparent($image_3, $color);
//首先将背景图片采样copy到真彩色画布中，不会失真
imagecopyresampled($image_3,$image_1,0,0,0,0,imagesx($image_1),imagesy($image_1),imagesx($image_1),imagesy($image_1));
//再将动态图片copy到已经具有人物图像的真彩色画布中，同样也不会失真
imagecopymerge($image_3,$image_2, 500,500,0,0,imagesx($image_2),imagesy($image_2), 100);
//将画布保存到指定的gif文件
imagegif($image_3);
```
