头像上传
====
基于cropper的一款头像上传yii2组件

Installation
------------

The preferred way to install this extension is through [composer](http://getcomposer.org/download/).

Either run

```
php composer.phar require --prefer-dist hyii2/yii2-avatar "dev-master"
```

or add

```
"hyii2/yii2-avatar": "dev-master"
```

to the require section of your `composer.json` file.


Usage
-----

Once the extension is installed, simply use it in your code by  :

```php
<?= \hyii2\avatar\AvatarWidget::widget(); ?>```



简介

yii2 avatar是基于cropper的一款头像上传的yii2扩展，带图片裁剪功能，且能生成不同尺寸的缩略图，引用方式简单，安装即可立即使用，简单方便。

github:https://github.com/org-yii-china/yii2-avatar （扩展由本站原创，希望大家进入github点个赞，致谢）

安装

通过composer是安装该扩展的最佳方式

运行如下命令

php composer.phar require --prefer-dist hyii2/yii2-avatar "dev-master"
或者添加

"hyii2/yii2-avatar": "dev-master"
到对应的composer.json文件中require

使用

//在当前控制器的actions中添加如下配置
public function actions()
{
    return [
        'crop'=>[
            'class' => 'hyii2\avatar\CropAction',
            'config'=>[
                'bigImageWidth' => '200',     //大图默认宽度
                'bigImageHeight' => '200',    //大图默认高度
                'middleImageWidth'=> '100',   //中图默认宽度
                'middleImageHeight'=> '100',  //中图图默认高度
                'smallImageWidth' => '50',    //小图默认宽度
                'smallImageHeight' => '50',   //小图默认高度
                //头像上传目录（注：目录前不能加"/"）
                'uploadPath' => 'uploads/avatar',
            ]
        ]
    ]; 
}
//调用方式,imageUrl为默认图地址

<?= \hyii2\avatar\AvatarWidget::widget(['imageUrl'=>'/statics/images/avatar/avatar_1.jpg']); ?>
