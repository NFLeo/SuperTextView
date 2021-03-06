[![](https://jitpack.io/v/lygttpod/SuperTextView.svg)](https://jitpack.io/#lygttpod/SuperTextView)


# 重磅推出SuperTextView2.x版本，属性参数相比1.x有些变化，1.x的用户升级2.x的时候请注意

## 目录
* 1、功能描述
* 2、效果图
* 3、如何使用
  - 3.1、 Android Studio导入方法
  - 3.2、 项目中如何使用
    - 3.2.1、布局中使用
    - 3.2.2、在代码中使用
    - 3.2.3、属性介绍
* 4、更新日志

## 1、功能描述
> [**SuperTextView**](https://github.com/lygttpod/SuperTextView)是一个功能强大的View，可以满足日常大部分布局样式，开发者可已自行组合属性配置出属于自己风格的样式!可能描述起来没有概念，还是直接看效果图吧！

> 简化版 [**CommonTextView**](https://github.com/lygttpod/SuperTextView/blob/master/CommonTextView_Readme.md)只是逻辑简化，其实功能并不差少哦，有兴趣的可以看看

> 如果觉得对你有用的话，点一下右上的星星赞一下吧!

## 2、 效果 [**Demo下载地址**]( https://fir.im/eft1)

![demo.gif](https://github.com/lygttpod/SuperTextView/blob/master/screenshot/demo.gif)


## 3、如何使用
### 3.1、Android Studio导入方法，添加Gradle依赖

   先在项目根目录的 build.gradle 的 repositories 添加:
```
     allprojects {
         repositories {
            ...
            maven { url "https://jitpack.io" }
        }
    }
```
 然后在dependencies添加:
```
        dependencies {
        ...
        compile 'com.github.lygttpod:SuperTextView:2.0.1'
        }
```

> ## 重写SuperTextView，功能更加全面，部分方法及属性有变更，1.x版本的老用户请注意

### 3.2、项目中如何使用
##### 3.2.1、布局中如何使用（示例中只列出部分属性，开发者可根据具体需求使用其他属性）
```
            <com.allen.library.SuperTextView
                android:layout_width="match_parent"
                android:layout_height="80dp"
                stv:sCenterBottomTextColor="@color/colorAccent"
                stv:sCenterBottomTextString="限额说明>>"
                stv:sCenterTopTextString=" "
                stv:sCenterViewGravity="left_center"
                stv:sLeftBottomTextString="招商银行（8888）"
                stv:sLeftIconRes="@drawable/bank_zhao_shang"
                stv:sLeftTopTextString="银行卡支付"
                stv:sLeftViewGravity="left_center"
                stv:sRightCheckBoxRes="@drawable/circular_check_bg"
                stv:sRightCheckBoxShow="true" />
        注意：
                1、上下的线可以通过   sDividerLineType 设置  有四种显示方式 none，top，bottom，both
                2、通过设置 sUseRipple=true 开启水波效果
```
##### 3.2.2、代码中如何使用
```
       /**
     * 可以通过链式设置大部分常用的属性值
     */
         superTextView.setLeftTopString("")
                 .setLeftString("")
                 .setLeftBottomString("")
                 .setCenterTopString("")
                 .setCenterString("")
                 .setCenterBottomString("")
                 .setRightTopString("")
                 .setRightString("")
                 .setRightBottomString("")
                 .setLeftIcon(0)
                 .setRightIcon(0)
                 .setRightTvDrawableLeft(null)
                 .setRightTvDrawableRight(null)
                 .setCbChecked(true)
                 .setCbBackground(null);
```
###### 点击事件（可根据需求选择实现单个或者多个点击事件）
```
        /**
         * 根据实际需求对需要的View设置点击事件
         */
        superTextView.setOnSuperTextViewClickListener(new SuperTextView.OnSuperTextViewClickListener() {
            @Override
            public void onClickListener() {
                string = "整个item的点击事件";
                Toast.makeText(ClickActivity.this, string, Toast.LENGTH_SHORT).show();
            }
        }).setLeftTopTvClickListener(new SuperTextView.OnLeftTopTvClickListener() {
            @Override
            public void onClickListener() {
                string = superTextView.getLeftTopString();
                Toast.makeText(ClickActivity.this, string, Toast.LENGTH_SHORT).show();
            }
        }).setLeftTvClickListener(new SuperTextView.OnLeftTvClickListener() {
            @Override
            public void onClickListener() {
                string = superTextView.getLeftString();
                Toast.makeText(ClickActivity.this, string, Toast.LENGTH_SHORT).show();
            }
        }).setLeftBottomTvClickListener(new SuperTextView.OnLeftBottomTvClickListener() {
            @Override
            public void onClickListener() {
                string = superTextView.getLeftBottomString();
                Toast.makeText(ClickActivity.this, string, Toast.LENGTH_SHORT).show();
            }
        }).setCenterTopTvClickListener(new SuperTextView.OnCenterTopTvClickListener() {
            @Override
            public void onClickListener() {
                string = superTextView.getCenterTopString();
                Toast.makeText(ClickActivity.this, string, Toast.LENGTH_SHORT).show();
            }
        }).setCenterTvClickListener(new SuperTextView.OnCenterTvClickListener() {
            @Override
            public void onClickListener() {
                string = superTextView.getCenterString();
                Toast.makeText(ClickActivity.this, string, Toast.LENGTH_SHORT).show();
            }
        }).setCenterBottomTvClickListener(new SuperTextView.OnCenterBottomTvClickListener() {
            @Override
            public void onClickListener() {
                string = superTextView.getCenterBottomString();
                Toast.makeText(ClickActivity.this, string, Toast.LENGTH_SHORT).show();
            }
        }).setRightTopTvClickListener(new SuperTextView.OnRightTopTvClickListener() {
            @Override
            public void onClickListener() {
                string = superTextView.getRightTopString();
                Toast.makeText(ClickActivity.this, string, Toast.LENGTH_SHORT).show();
            }
        }).setRightTvClickListener(new SuperTextView.OnRightTvClickListener() {
            @Override
            public void onClickListener() {
                string = superTextView.getRightString();
                Toast.makeText(ClickActivity.this, string, Toast.LENGTH_SHORT).show();
            }
        }).setRightBottomTvClickListener(new SuperTextView.OnRightBottomTvClickListener() {
            @Override
            public void onClickListener() {
                string = superTextView.getRightBottomString();
                Toast.makeText(ClickActivity.this, string, Toast.LENGTH_SHORT).show();
            }
        });
```
###### 使用第三方库(Picasso或者Glide)加载网络图片
```
        Picasso.with(this).load("https://ss1.baidu.com/6ONXsjip0QIZ8tyhnq/it/u=3860616424,1789830124&fm=80&w=179&h=119&img.PNG")
                .placeholder(R.drawable.head_default).into(superTextView.getLeftIconIV());


        Glide.with(this).load("https://ss0.baidu.com/6ONWsjip0QIZ8tyhnq/it/u=219781665,3032880226&fm=80&w=179&h=119&img.JPEG")
                .placeholder(R.drawable.head_default).fitCenter().into(superTextView2.getRightIconIV());


        Glide.with(this).load("https://ss1.baidu.com/6ONXsjip0QIZ8tyhnq/it/u=3860616424,1789830124&fm=80&w=179&h=119&img.PNG")
                .placeholder(R.drawable.head_default)
                .into(new SimpleTarget<GlideDrawable>() {
                    @Override
                    public void onResourceReady(GlideDrawable resource, GlideAnimation<? super GlideDrawable> glideAnimation) {
                        superTextView3.setRightTvDrawableRight(resource);
                    }
                });
```

##### 3.2.3、属性说明(以下属性全部可以通过xml文件配置和代码进行设置)

属性名 | 字段 | 描述 | 默认值
----|------|----| ----
sLeftTextString | string  | 左边文字字符串
sLeftTopTextString | string  | 左上文字字符串
sLeftBottomTextString | string  | 左下文字字符串
sCenterTextString | string  | 中间文字字符串
sCenterTopTextString | string  | 中上文字字符串
sCenterBottomTextString | string  | 中下文字字符串
sRightTextString | string  | 右边文字字符串
sRightTopTextString | string  | 右上文字字符串
sRightBottomTextString | string  | 右下文字字符串
sLeftTextColor | color  | 左边文字颜色 | 默认0xFF373737
sLeftTopTextColor | color  | 左上文字颜色 | 默认0xFF373737
sLeftBottomTextColor | color  | 左下文字颜色 | 默认0xFF373737
sCenterTextColor | color  | 中间文字颜色 | 默认0xFF373737
sCenterTopTextColor | color  | 中上文字颜色 | 默认0xFF373737
sCenterBottomTextColor | color  | 中下文字颜色 | 默认0xFF373737
sRightTextColor | color  | 左边文字颜色 | 默认0xFF373737
sRightTopTextColor | color  | 右上文字颜色 | 默认0xFF373737
sRightBottomTextColor | color  | 右下文字颜色 | 默认0xFF373737
sLeftTextSize | dimension  | 左边字体大小 | 默认15sp
sLeftTopTextSize | dimension  | 左上字体大小 | 默认15sp
sLeftBottomTextSize | dimension  | 左下字体大小 | 默认15sp
sCenterTextSize | dimension  | 中间字体大小 | 默认15sp
sCenterTopTextSize | dimension  | 中上字体大小 | 默认15sp
sCenterBottomTextSize | dimension  | 中下字体大小 | 默认15sp
sRightTextSize | dimension  | 右边字体大小 | 默认15sp
sRightTopTextSize | dimension  | 右上字体大小 | 默认15sp
sRightBottomTextSize | dimension  | 右下字体大小 | 默认15sp
sLeftLines | integer  | 左边文字显示行数 | 默认1
sLeftTopLines | integer  | 左上文字显示行数 | 默认1
sLeftBottomLines | integer  | 左下文字显示行数 | 默认1
sCenterLines | integer  | 中间文字显示行数 | 默认1
sCenterTopLines | integer  | 中上文字显示行数 | 默认1
sCenterBottomLines | integer  | 中下文字显示行数 | 默认1
sRightLines | integer  | 右边文字显示行数 | 默认1
sRightTopLines | integer  | 右上文字显示行数 | 默认1
sRightBottomLines | integer  | 右下文字显示行数 | 默认1
sLeftMaxEms | integer  | 左边文字显示个数 | 默认10
sLeftTopMaxEms | integer  | 左上文字显示个数 | 默认10
sLeftBottomMaxEms | integer  | 左下文字显示个数 | 默认10
sCenterMaxEms | integer  | 中间文字显示个数 | 默认10
sCenterTopMaxEms | integer  | 中上文字显示个数 | 默认10
sCenterBottomMaxEms | integer  | 中下文字显示个数 | 默认10
sRightMaxEms | integer  | 右边文字显示个数 | 默认10
sRightTopMaxEms | integer  | 右上文字显示个数 | 默认10
sRightBottomMaxEms | integer  | 右下文字显示个数 | 默认10
sLeftViewGravity | enum  | 左边文字对齐方式<br>left_center(左对齐)<br>center(居中)<br>right_center(右对齐) | 默认center
sCenterViewGravity | enum  | 中间文字对齐方式<br>left_center(左对齐)<br>center(居中)<br>right_center(右对齐) | 默认center
sRightViewGravity | enum  | 右边文字对齐方式<br>left_center(左对齐)<br>center(居中)<br>right_center(右对齐) | 默认center
sLeftTvDrawableLeft | reference  | 左边TextView左侧的drawable
sLeftTvDrawableRight | reference  | 左边TextView右侧的drawable
sCenterTvDrawableLeft | reference  | 中间TextView左侧的drawable
sCenterTvDrawableRight | reference  | 中间TextView右侧的drawable
sRightTvDrawableLeft | reference  | 右边TextView左侧的drawable
sRightTvDrawableRight | reference  | 右边TextView右侧的drawable
sTextViewDrawablePadding | dimension  | TextView的drawable对应的Padding | 默认10dp
mLeftViewWidth | dimension  | 左边textView的宽度  为了中间文字左对齐的时候使用
sTopDividerLineMarginLR | dimension  | 上边分割线的MarginLeft和MarginRight | 默认0dp
sTopDividerLineMarginLeft | dimension  | 上边分割线的MarginLeft | 默认0dp
sTopDividerLineMarginRight | dimension  | 上边分割线的MarginRight | 默认0dp
sBottomDividerLineMarginLR | dimension  | 下边分割线的MarginLeft和MarginRigh | 默认0dp
sBottomDividerLineMarginLeft | dimension  | 下边分割线的MarginLeft | 默认0dp
sBottomDividerLineMarginRight | dimension  | 下边分割线的MarginRight | 默认0dp
sDividerLineColor | color  | 分割线的颜色 | 默认0xFFE8E8E8
sDividerLineHeight | dimension  | 分割线的高度 | 默认0.5dp
sDividerLineType | enum  | 分割线显示方式 <br>none(不显示分割线)<br>top(显示上边的分割线)<br>bottom(显示下边的分割线)<br>both(显示上下两条分割线) | 默认bottom
sLeftViewMarginLeft | dimension  | 左边view的MarginLeft | 默认10dp
sLeftViewMarginRight | dimension  | 左边view的MarginRight | 默认10dp
sCenterViewMarginLeft | dimension  | 中间view的MarginLeft | 默认10dp
sCenterViewMarginRight | dimension  | 中间view的MarginRight | 默认10dp
sRightViewMarginLeft | dimension  | 中间view的MarginLeft | 默认10dp
sRightViewMarginRight | dimension  | 中间view的MarginRight | 默认10dp
sLeftTextIsBold | boolean  | 左边文字是否加粗 | 默认false
sLeftTopTextIsBold | boolean  | 左上文字是否加粗 | 默认false
sLeftBottomTextIsBold | boolean  | 左下文字是否加粗 | 默认false
sCenterTextIsBold | boolean  | 中间文字是否加粗 | 默认false
sCenterTopTextIsBold | boolean  | 中上文字是否加粗 | 默认false
sCenterBottomTextIsBold | boolean  | 中下文字是否加粗 | 默认false
sRightTextIsBold | boolean  | 右边文字是否加粗 | 默认false
sRightTopTextIsBold | boolean  | 右上文字是否加粗 | 默认false
sRightBottomTextIsBold | boolean  | 右下文字是否加粗 | 默认false
sLeftIconRes | reference  | 左边图片资源  可以用来显示网络图片或者本地
sRightIconRes | reference  | 右边图片资源  可以用来显示网络图片或者本地
sLeftIconWidth | dimension  | 左边图片资源的宽度  用于固定图片大小的时候使用
sLeftIconHeight | dimension  | 左边图片资源的高度  用于固定图片大小的时候使用
sRightIconWidth | dimension  | 右边图片资源的宽度  用于固定图片大小的时候使用
sRightIconHeight | dimension  | 右边图片资源的高度  用于固定图片大小的时候使用
sLeftIconMarginLeft | dimension  | 左边图片资源的MarginLeft | 默认10dp
sRightIconMarginRight | dimension  | 右边图片资源的MarginLeft | 默认10dp
sCenterSpaceHeight | dimension  | 上中下三行文字的间距 | 默认5dp
sRightCheckBoxRes | reference  | 右边CheckBox的资源
sRightCheckBoxMarginRight | dimension  | 右边CheckBox的MarginRight | 默认10dp
sIsChecked | boolean  | 右边CheckBox是否选中 | 默认 false
sUseRipple | boolean  | 是否开启点击出现水波效果 | 默认 true
sBackgroundDrawableRes | reference  | SuperTextView的背景资源
sRightViewType | enum  | 右边显示的特殊View<br>checkbox<br>switchBtn | 默认都不显示
sRightSwitchMarginRight | dimension  | 右边SwitchBtn的MarginRight | 默认10dp
sSwitchIsChecked | boolean  | 右边SwitchBtn是否选中 | 默认 false
sTextOff | string  | TextOff | 默认""
sTextOn | string  | TextOn | 默认""
sSwitchMinWidth | dimension  | SwitchMinWidth | 系统默认
sSwitchPadding | dimension  | SwitchPadding | 系统默认
sThumbTextPadding | dimension  | ThumbTextPadding | 系统默认
sThumbResource | reference  | 右边SwitchBtn自定义选中资源 | 系统默认
sTrackResource | reference  | 右边SwitchBtn自定义未选中资源 | 系统默认




> 黑格尔曾说过：存在即合理。SuperTextView的出现应该就是某种需求下的产物。


## 4、更新日志

### V2.0.1
* 新增SwitchButton样式   

目前有switchBtn和checkbox两种特殊view
```
stv:sRightViewType="switchBtn"  
stv:sRightViewType="checkbox" 
```

### V2.0.0
* 	重写SuperTextView，功能更加全面，部分方法及属性有变更，使用者请注意

### V1.1.2
*   上下分割线添加单独设置左右边距的参数
```
                1、SuperTextVIew配置方法如下:下列两种方式都是单独使用
                
                //方法一
                stv:sTopLineMarginLeft="10dp"
                stv:sTopLineMarginRight="0dp"
                 
                stv:sBottomLineMarginLeft="10dp"
                stv:sBottomLineMarginRight="0dp"
                
                //方法二
                stv:sBothLineMarginLeft="10dp"
                stv:sBothLineMarginRight="0dp"
                                
                2、CommonTextView配置方法如下：下列两种方式都是单独使用
                
                //方法一
                ctv:cTopDividerLineMarginLeft="10dp"
                ctv:cTopDividerLineMarginRight="0dp"

                ctv:cBottomDividerLineMarginLeft="10dp"
                ctv:cBottomDividerLineMarginRight="0dp"
                
                //方法二
                ctv:cBothDividerLineMarginLeft="10dp"
                ctv:cBothDividerLineMarginRight="0dp"
```            

### V1.1.1
* 	1、SuperTextview和CommonTextview新增点击时候自定义选中和默认背景效果
```
                                sBackgroundDrawableRes="@drawable/selector_red"
                                
                                cBackgroundDrawableRes="@drawable/selector_red"
```
                                
*    2、CommonTextview新增中间布局左对齐属性
```
                                两个属性配合使用
                                ctv:cIsCenterAlignLeft="true"
                                ctv:cCenterViewMarginLeft="200dp"
               
```

### V1.1
* 	修复SuperTextView和CommonTextView点击事件被子View消耗掉的bug（具体使用请参考文档）

### V1.0.9
* 	SuperTextView新增左右图标可自定义大小的功能
```
                                stv:sRightIconWidth="30dp"
                                stv:sRightIconHeight="30dp"
                                stv:sLeftIconWidth="30dp"
                                stv:slefticonHeight="30dp"
 ```                               
### V1.0.8
* 	修复CommonTextView点击事件无效的bug

### V1.0.7
* 	CommonTextView新增支持加载网络图片

### V1.0.6
* 	新增设置分割线颜色和宽度的方法
* 	新增简化版CommonTextView

### V1.0.3
* 	新增左右两边图片支持常用三方库加载网络图片

### V1.0.2
* 修复文字内容过多，超过1行的处理，导致两边的文字会引起重叠的bug

### V1.0.1
* 修复编译版本不同导致无法正常使用的bug

### V1.0.0
* 功能强大的TextView

# 意见反馈

如果遇到问题或者好的建议，请反馈到我的邮箱：[lygttpod@163.com](mailto:lygttpod@163.com) 或者[lygttpod@gmail.com](mailto:lygttpod@gmail.com)

如果觉得对你有用的话，点一下右上的星星赞一下吧!

# License
```
         Copyright 2016 Allen

        Licensed under the Apache License, Version 2.0 (the "License");
        you may not use this file except in compliance with the License.
        You may obtain a copy of the License at

          http://www.apache.org/licenses/LICENSE-2.0

        Unless required by applicable law or agreed to in writing, software
        distributed under the License is distributed on an "AS IS" BASIS,
        WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
        See the License for the specific language governing permissions and
        limitations under the License.

```
