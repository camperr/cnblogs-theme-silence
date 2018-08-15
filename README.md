![PC](https://images.cnblogs.com/cnblogs_com/esofar/972540/o_screenshot_1.png)

# Cnblogs Theme - Silence
[![Cnblogs](https://img.shields.io/badge/dependencies-jQuery-yellow.svg)](https://www.cnblogs.com)
[![GitHub issues](https://img.shields.io/github/issues/esofar/cnblogs-theme-silence.svg)](https://github.com/esofar/cnblogs-theme-silence/issues)
[![GitHub license](https://img.shields.io/github/license/esofar/cnblogs-theme-silence.svg)](https://github.com/esofar/cnblogs-theme-silence/blob/master/LICENSE)


## 介绍
Silence 是一套界面简洁、运行高效的博客园皮肤，主要面向于经常混迹博客园的朋友。

简单概括其几个主要特点：
* 专注阅读、精致漂亮的 UI；
* 事无巨细的部署文档；
* 兼容移动端浏览器；
* 源码结构清晰、易扩展。


## 安装

> 开始之前请确保你有一个正常的博客园账号并已经成功申请开通JS权限。

**Step1：皮肤下载**

通过下面git命令克隆到本地，或者直接下载ZIP到本地并解压。
```
git clone https://github.com/esofar/cnblogs-theme-silence.git
```
进入`dist`目录，获取`silence.min.css`和`silence.min.js`文件。


**Step2：上传博客园**

进入『博客园』-『管理』-『文件』，将上一步中获取的两个文件通过上传到自己的博客。获取上传后的URL地址，然后使用`<link>`和`<script>`标签分别将css和js文件包裹。效果请参考示例：
```
<link href="https://blog-static.cnblogs.com/files/esofar/silence.min.css" />

<script src="https://blog-static.cnblogs.com/files/esofar/silence.min.js"></script>
```

进入『博客园』-『管理』-『设置』，将生成的两个脚本复制到『博客侧边栏公告』文本域中。

**Step3：使用皮肤**

进入『博客园』-『管理』-『设置』，将下面脚本复制并追加到『博客侧边栏公告』文本域中。

```
<script type="text/javascript">
    $.silence();
</script>
```

博文详情页面重新定义了三个自动化模块：博客目录、博客签名、支持赞赏，并且支持参数配置。由于可能会影响页面加载速度，默认不启用。如需开启请修改上述脚本。使用示例：
```
<script type="text/javascript">
    $.silence({
        catalog: {
            enable: true,
            move: true,
            index: true,
            level1: 'h2',
            level2: 'h3',
            level3: 'h4',
        },
        signature: {
            enable: true,
            author: 'Esofar',
            home: 'https://esofar.cn',
            license: '署名 4.0 国际',
            link: 'https://creativecommons.org/licenses/by/4.0'
        },
        reward: {
            enable: true,
            title: '感谢您的支持，我会继续努力',
            wechat: 'https://images.cnblogs.com/cnblogs_com/esofar/972540/o_wechat.png',
            alipay: 'https://images.cnblogs.com/cnblogs_com/esofar/972540/o_alipay.png',
        }
    });
</script>
```

配置项说明详见下表：
<table>
    <thead>
        <tr>
            <td>模块</td>
            <td>属性</td>
            <td>说明</td>
            <td>类型</td>
            <td>默认值</td>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td rowspan="6">catalog</td>
            <td>enable</td>
            <td>是否启用</td>
            <td>Boolean</td>
            <td>false</td>
        </tr>
        <tr>
            <td>move</td>
            <td>是否允许拖拽</td>
            <td>Boolean</td>
            <td>true</td>
        </tr>
        <tr>
            <td>index</td>
            <td>是否显示索引</td>
            <td>Boolean</td>
            <td>true</td>
        </tr>
        <tr>
            <td>level1</td>
            <td>一级标题</td>
            <td>String</td>
            <td>h2</td>
        </tr>
        <tr>
            <td>level2</td>
            <td>二级标题</td>
            <td>String</td>
            <td>h3</td>
        </tr>
        <tr>
            <td>level3</td>
            <td>三级标题</td>
            <td>String</td>
            <td>h4</td>
        </tr>
        <tr>
            <td rowspan="5">signature</td>
            <td>enable</td>
            <td>是否启用</td>
            <td>Boolean</td>
            <td>false</td>
        </tr>
        <tr>
            <td>author</td>
            <td>作者显示名称</td>
            <td>String</td>
            <td>`currentBlogApp`，当前博客用户名</td>
        </tr>
        <tr>
            <td>home</td>
            <td>作者主页</td>
            <td>String</td>
            <td>https://www.cnblogs.com</td>
        </tr>
        <tr>
            <td>license</td>
            <td>许可证名称</td>
            <td>String</td>
            <td>署名 4.0 国际</td>
        </tr>
        <tr>
            <td>link</td>
            <td>许可证链接</td>
            <td>String</td>
            <td>https://creativecommons.org/licenses/by/4.0</td>
        </tr>
        <tr>
            <td rowspan="5">reward</td>
            <td>enable</td>
            <td>是否启用</td>
            <td>Boolean</td>
            <td>false</td>
        </tr>
        <tr>
            <td>title</td>
            <td>标题</td>
            <td>String</td>
            <td>null</td>
        </tr>
        <tr>
            <td>wechat</td>
            <td>微信二维码</td>
            <td>String</td>
            <td>null</td>
        </tr>
        <tr>
            <td>alipay</td>
            <td>支付宝二维码</td>
            <td>String</td>
            <td>null</td>
        </tr>
    </tbody>
</table>

**Step4：其他配置**

为了使页面达到最佳效果，还需要在修改一些博客园的配置项。

* 进入『博客园』-『管理』-『设置』，在『标题』文本域中设置博客标题，不支持子标题。

* 进入『博客园』-『管理』-『设置』，在『博客皮肤』处选择博客园官方标准模板**Custom**，并且把『禁用模板默认CSS』复选框取消勾选。

* 进入『博客园』-『管理』-『选项』，在『控件显示设置』需要勾选的模块有：随笔分类、公告、博客园链接、阅读排行榜、我的标签、首页链接、RSS订阅、推荐排行榜、联系，其他模块取消勾选(可选)。


至此，皮肤就安装并配置完成，赶快打开博客看看效果吧！