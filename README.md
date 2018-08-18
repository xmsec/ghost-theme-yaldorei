# Yaldorei
A Simple And Elegant Ghost Theme Yadorei Modified From [Kaldorei](https://github.com/xiaoluoboding/ghost-theme-kaldorei) Which Derive From Default Theme Casper. **Most development was made by the former author**. Maybe the former author xiaoluoboding will update kaldorei soon and then I will also modify it. 

Suport ghost 1.25.0
# Preview
## Former
![img](assets/img/preview.png)
## Now
[Blog](http://www.xmsec.cc)
## How to use

### 统计
Kaldorei使用了ghost的api来做统计，所以需要开启ghost的实验室中的`Public API`功能。

> 方法：ghost后台 > `labs` > `Enable Beta Features` > `勾选 Public API`

### 图片幻灯片
Kaldorei集成了fancyBox，支持图片暗箱效果、幻灯片轮播、全屏预览、缩略图预览等功能。预览&使用方法[图片预览](http://xlbd.me/how-to-use-fancybox-in-ghost-blog/)


```js
<script>
    var disqus_shortname = 'your_disqus_shortname';
</script>
```

### 开启归档功能
Kaldorei提供了简单的归档功能，使用ghost的api来生成归档，预览[博客归档](http://xlbd.me/archives-post)。

> 方法：ghost后台:
> * New Post > 标题输入`Archives`，这时文章的地址默认为`archives-post`;
> * Post Settings > 勾选`Turn this post into a static page`，然后Publish;
> * Navigation > 创建一个`归档`导航，地址为：http://your_blog_url/`archives-post`;
> * 去博客首页看看你的归档吧，Have fun.

## About ghost helpers

Kaldorei用两种方法实现了标签云，方法参见[原作者博客](http://xlbd.me/how-to-add-the-tag-cloud-into-ghost-blog/)。

Kaldorei优化了发布文章的时间展示，并汉化为中文，需要修改时间(date)助手，方法参见[原作者博客](http://xlbd.me/ghost-date-i18n/)。

## About Google AMP
Ghost with something not set value may cause AMP image cover error.     
What can be done is as follows:     
In Helpers folder and helpers/ghost_head.js we can found:
```
        if (metaData.schema) {
            head.push('<script type="application/ld+json">\n' +
                JSON.stringify(metaData.schema, null, '    ') +
                '\n    </script>\n');
        }
```
Then Modify it to be     
```
        if (metaData.schema) {
	        if(!metaData.schema.hasOwnProperty('image')){
				metaData.schema['image']={}
			}
            head.push('<script type="application/ld+json">\n' +
                JSON.stringify(metaData.schema, null, '    ') +
                '\n    </script>\n');
        }
```
At last, restart the ghost
## About Modified Theme Yaldorei

Modified theme support ghost 1.25.0     
What is modified is as follows:    

1. The nav's hight
2. The footer's padding
3. Tag clould in post page removed
4. Post pages' fence layout
5. Color simplified  
6. Disqus removed & should modify Comments partial to use
7. SOHU changyan used for comment
8. CSS not mentioned above modified slightly
9. Some author info removed

Theme name was made by someone Yan DY I met before.

## Credit

* [kaldorei](https://github.com/xiaoluoboding/ghost-theme-kaldorei)
* [font-awesome](https://github.com/FortAwesome/Font-Awesome)
* [bootstrap](https://github.com/twbs/bootstrap)
* [highlight.js](https://github.com/isagalaev/highlight.js)
* [velocity.js](https://github.com/julianshapiro/velocity)
* [jquery.toc.js](https://github.com/jgallen23/toc)
* [anijs](https://github.com/anijs/anijs)
* [jquery.githubRepoWidget.js](https://github.com/JoelSutherland/GitHub-jQuery-Repo-Widget)
* [fancyBox](https://github.com/fancyapps/fancyBox)

