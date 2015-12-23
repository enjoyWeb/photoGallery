#高清组图
    高清组图是基于swiper3.0的查看高清图片的插件，有评论列表、关注、分享、图片信息、评分等模块，主区域是用来显示图片，可以查看原图和相关简介，适用于移动端。如果不需要评论列表，可以将相关的HTML代码删除即可。
####官方地址
swiper3.0：http://www.swiper.com.cn/

##兼容性

* ie9+
* Chrome8+

##样例：

###1、使用步骤
* 引入样式文件（photoGallery.css，swiper.css，font-awesome.min.css）

```javascript
<link href="style/photoGallery.css" rel="stylesheet" type="text/css" />
<link href="style/swiper.css" rel="stylesheet" type="text/css" />
<link href="style/font-awesome.min.css" rel="stylesheet" type="text/css" />
```
* 引入Jquery库：jquery.js
* 引入raty插件：jquery.raty.js
* 引入iscroll插件：iscroll.js
* 引入swiper插件：swiper.min.js
* 组图的实现代码：photoGallery.js
* 入口代码：api.js

```javascript
<script src="javascript/jquery.js" type="text/javascript"></script>
<script src="javascript/jquery.raty.js" type="text/javascript"></script>
<script src="javascript/iscroll.js" type="text/javascript"></script>
<script src="javascript/swiper.min.js" type="text/javascript"></script>
<script src="javascript/photoGallery.js" type="text/javascript"></script>
<script src="javascript/api.js" type="text/javascript"></script>
```

* 在页面上添加代码

```javascript
<div class="photoGallery">
    <ol class="pic-list">
        <li>
            <a>
                <img src="images/1.jpg">
            </a>
            <div class="example"><span class="entrance"><i class="fa fa-fw fa-search-plus"></i> 查看大图</span></div>
        </li>
        <li>
            <a>
                <img src="images/2.jpg">
            </a>
            <div class="example"><span class="entrance"><i class="fa fa-fw fa-search-plus"></i> 查看大图</span></div>
        </li>
    </ol>
    <div class="gallery contain-score" id="gallery1">//此处的id必须为gallery+数字
            <div class="album">
                <header>
                    ......//具体组图代码查看demo页面
                </header>
                <div class="swiper-container gallery-top" id="gallery-top1">//此处的id必须为gallery-top+数字
                    <div class="swiper-wrapper">    
                        ......//具体组图代码查看demo页面
                    </div>
                    <div class="swiper-button-next swiper-button-white" title="下一张"></div>
                    <div class="swiper-button-prev swiper-button-white" title="上一张"></div>
                </div>
            </div>
            <div class="handle-tab-wrap">
                ......//具体组图代码查看demo页面
            </div>
            <div class="photo_layer">
                ......//具体组图代码查看demo页面
            </div>
    </div>
</div>    
```
###2、demo
* [高清组图demo](http://192.168.14.97:8080/plugin/photoGallery)

##配置和API
###1、配置
```javascript
//此处触发组图弹开的代码可根据实际场景自己更改，只需将组图插件初始化的入口写好即可。
$('.photoGallery').each(function(){
	var _this = $(this);
	_this.find('.entrance').click(function(){
		_this.find('.gallery').css('display','block');
		$('body').css('overflow','hidden');
		var t = $(document).scrollTop();
        _this.find('.gallery .close').unbind('click');
		new picSwiper('#'+_this.find('.gallery')[0].id,_this.parent().parent().index()+1,t,{});//组图插件入口
	});
});
```
###2、API
* [Swiper3.0的API详细参数地址](http://www.swiper.com.cn/api/index.html)








