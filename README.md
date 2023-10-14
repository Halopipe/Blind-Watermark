> *现在网络上有两种图片A和B.  A是我们嵌入水印后发表出去的,  B是破解者在A上添加了自己的水印生成的. 那么使用我们的密码可以从A和B中提取出我们的水印, 但是破解者只能从B中提取出破解者的水印, 而无法从A中提取出破解者的水印, 这便能说明这张图的创作者究竟是谁, 我认为这对保护创作者的权益是至关重要的一步.*
>
> #### 经测试开源库均存在以下几方面的问题, 非常不安全, 请大家谨慎选择.
> - 没有设置密码或标记, 带来的问题是A用户使用该工具添加的水印, B用户同样使用该工具, 可直接提取出来了A用户的水印标记.
> - 没有覆盖保护, 带来的问题是A用户使用该工具添加的水印, B用户同样使用该工具, 直接覆盖了A用户的水印, A用户再也无法获取到自己的水印.
> - 使用开源库添加的水印数据会很容易被覆盖, 让一切归零.

## 它是什么
* 它是一个隐形水印工具, 可保护你的图片版权.
* 它支持的图片格式 .PNG | .JPG | .BMP | .WEBP | .JPEG .
* 它支持的平台 macos-inter | windows-x64.
* 它采用离散小波变换以及奇异值分解等算法, 相比于传统的DFT和LSB算法, 具有较强抗干扰能力.

## 如何使用
* 支持的命令: brz | enc | dec | att | ncc , 支持批量操作.
* 使用者可设置自己的密码用于水印的添加和提取. (**6-12位数字/字母/符号**)
* 图片水印相较于文字水印等具有更强的识别能力, 它是一张**二值化**图片, **尺寸24\*24**.
* 小波算法承载信息量较小, 原图持的**最小尺寸为199\*199**(长宽乘积不小于).
* 只可以对原图进行操作, 保护水印不被覆盖, 为防止使用其他方式对算法进行覆盖, 因此本项目不开源.
* 可使用brz命令生成二值化水印图片.
* 可使用ncc命令对比两张水印图片.
```
    // 使用密码`123456` 给 `oriimg` 文件夹中的图片添加水印 `wm.png`
    > .\bwm-win-x64\bwm.exe enc 123456 wm.png oriimg

    // 提取上面命令添加的水印
    > .\bwm-win-x64\bwm.exe dec 123456 wm.png oriimg/encode

    // 生成二值化图片
    > .\bwm-win-x64\bwm.exe brz img.png

    // 对比两张水印图片
    > .\bwm-win-x64\bwm.exe ncc wm1.png wm2.png
```

### [查看攻击测试报告和获取该工具](https://store.cocos.com/app/detail/5318)
