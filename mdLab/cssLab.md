## 常用加密方法

###### base64编码

    Base64是基于64个可打印字符来表示二进制数据。主要实现打印不可打印内容的需求，例如图片。
    适用于小段内容的加密，例如token，但不可用于编码

###### 哈希算法

    哈希是将不同长度目标转为唯一长度的文本，所以是多对一的关系，因此结果不可逆。
    常用场景是将密码哈希加密后与数据库中已加密的密码对比，实现登录

###### 加盐

    在密码中引入一串无序的文本，并加密，这就是加盐。盐值不要存在本地或者程序中，应该从后台获取

[引用](https://jdc.jd.com/archives/212773)

## css语法糖

颜色翻转

    filter: invert(100%);

文字横向拉伸压缩

    font-stretch：ultra-condensed | extra-condensed | condensed | semi-condensed | normal | semi-expanded | expanded | extra-expanded | ultra-expanded
    默认值：normal

取值

    ultra-condensed：比正常文字宽度窄4个基数。
    extra-condensed：比正常文字宽度窄3个基数。
    condensed：比正常文字宽度窄2个基数。
    semi-condensed：比正常文字宽度窄1个基数。
    normal：正常文字宽度
    semi-expanded：比正常文字宽度宽1个基数。
    expanded：比正常文字宽度宽2个基数。
    extra-expanded：比正常文字宽度宽3个基数。
    ultra-expanded：比正常文字宽度宽4个基数。

文字描边

    text-stroke:1px #f00;


## [30-seconds造的轮子](https://30-seconds.github.io/30-seconds-of-css/)

创建一个正方形

    .constant-width-to-height-ratio {
      background: #333;
      width: 10%;
    }
    .constant-width-to-height-ratio::before {
      content: '';
      padding-top: 100%;
      float: left;
    }

    .constant-width-to-height-ratio::after {
      content: '';
      display: block;
      clear: both;
    }

动态阴影

    .dynamic-shadow {
      position: relative;
      width: 10rem;
      height: 10rem;
      background: linear-gradient(75deg, #6d78ff, #00ffb8);
      z-index: 1;
    }
    .dynamic-shadow::after {
      content: '';
      width: 100%;
      height: 100%;
      position: absolute;
      background: inherit;
      top: 0.5rem;
      filter: blur(0.4rem);
      opacity: 0.7;
      z-index: -1;
    }

印刷字

    .etched-text {
      text-shadow: 0 2px white;
      font-size: 1.5rem;
      font-weight: bold;
      color: #b8bec5;
    }

图片也能像背景一样显示

    background: #34495e;
    object-fit: cover;
    object-position: right top;

渐变文字

      background: -webkit-linear-gradient(pink, red);
      -webkit-text-fill-color: transparent;
      -webkit-background-clip: text;

屏幕分辨率

    .hairline-border {
      box-shadow: 0 0 0 1px;
    }
    @media (min-resolution: 2dppx) {
      .hairline-border {
        box-shadow: 0 0 0 0.5px;
      }
    }
    @media (min-resolution: 3dppx) {
      .hairline-border {
        box-shadow: 0 0 0 0.33333333px;
      }
    }
    @media (min-resolution: 4dppx) {
      .hairline-border {
        box-shadow: 0 0 0 0.25px;
      }
    }

下划线动画

    .hover-underline-animation {
      display: inline-block;
      position: relative;
      color: #0087ca;
    }
    .hover-underline-animation::after {
      content: '';
      position: absolute;
      width: 100%;
      transform: scaleX(0);
      height: 2px;
      bottom: 0;
      left: 0;
      background-color: #0087ca;
      transform-origin: bottom right;
      transition: transform 0.25s ease-out;
    }
    .hover-underline-animation:hover::after {
      transform: scaleX(1);
      transform-origin: bottom left;
    }

开关

    <input type="checkbox" id="toggle" class="offscreen" />
    <label for="toggle" class="switch"></label>

    .switch {
      position: relative;
      display: inline-block;
      width: 40px;
      height: 20px;
      background-color: rgba(0, 0, 0, 0.25);
      border-radius: 20px;
      transition: all 0.3s;
    }
    .switch::after {
      content: '';
      position: absolute;
      width: 18px;
      height: 18px;
      border-radius: 18px;
      background-color: white;
      top: 1px;
      left: 1px;
      transition: all 0.3s;
    }
    input[type='checkbox']:checked + .switch::after {
      transform: translateX(20px);
    }
    input[type='checkbox']:checked + .switch {
      background-color: #7983ff;
    }
    .offscreen {
      position: absolute;
      left: -9999px;
    }
垂直居中

    .parent {
      border: 1px solid #333;
      height: 250px;
      position: relative;
      width: 250px;
    }
    .child {
      left: 50%;
      position: absolute;
      top: 50%;
      transform: translate(-50%, -50%);
      text-align: center;
    }

单行省略

    .truncate-text {
      overflow: hidden;
      white-space: nowrap;
      text-overflow: ellipsis;
      width: 200px;
    }


