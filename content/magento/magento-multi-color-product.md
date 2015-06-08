---
title: "magento 多颜色产品配置"
date: 2015-06-08 12:48
---

###多颜色产品配置（magento)

　　对于大多数产品来说，如T恤、鞋子等，同一款产品都会拥有不同尺寸以及不同颜色，尤其对于颜色，很多时候人们会习惯于通过选择不同的色块来选择对应颜色的产品。这一点在Magento 1.9.1中得以更新为默认设置．    
  
  　它针对Configurable产品，当然要实现这一功能还要做一些准备工作，首先需要在Catalog > Attributes > Manage Attributes下添加相应的属性 ，如果是颜色的话，可以选择修改已存在的Color属性，主要修改的地方有Apply To下添加Configurable Product以及在Manage Label / Options部分添加对应的颜色。然后System > Configuration > Catalog > Configurable Swatches > General Settings将Enabled后勾选Yes,并选择需要应用Swathes的属性，如Color,本版块还可以配置色板在各页面显示的尺寸。  
   
　　完成以上的操作后即可将Color添加到属性组中，并创建Configurable Product,，流程这里不再赘述，对可配置产品的Iventory部分在Manage Stock后选择No,然后添加基于不同颜色的Associated Products。  
  
　如果想要显示各种颜色的图片的话需上传对应颜色名称的png图片，如black.png,而多个单词的颜色，则在中间加横杠，如light-green.png，颜色命名时请使用小写。上传时可通过添加描述用的WYSIWYG Editor，然后使用Insert Image…将图片上传到Storage Root下的swatches文件夹(media/wysiwyg/swatches)说了这么多，最终效果是什么样呢?请参见下图    
 
![Alt text](/img/1.jpg)  

>将普通产品改成可配置产品，可在数据库进行更改:

    update catalog_product_entity set type_id = "configurable" where sku = "your sku";

＞可配置产品，点击颜色不同．
