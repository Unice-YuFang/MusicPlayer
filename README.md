# MusicPlayer
课程：大型软件应用 - Team Project

Date: 2020/12/20

Contributer: Qi Tong, Ma Xin Ru, Liao Kai Yin, Liao YuFang, Huang Wan Ling, Lei Shu Meng

## 一、引言

《音乐播放器APP说明书》是为音乐播放器APP的设计而编写的文档。为此我们对现在的音乐播放器以及大家对音乐播放器的需求进行了全面以及认真的调查。通过这说明书，能够让用户确认项目的功能和性能，和用户的需求形成一致的理解以及确认。

## 二、总体描述
### 1. 项目背景
   
音乐的魅力在生活中是极大的，不同的国家、不同语言的人，可以从音乐中体会到相同的情感，可以加强人与人之间的联系，它也可以让身体放轻松，纾解压力。为了使人们能够通过手机等设备在任何时候都欣赏到音乐，因此我们希望能设计出一个基于Android系统的音乐播放器APP。

### 2. 项目目标

本项目的目的是开发一个可以播放主流的音乐文本格式的播放器。设计的主要功能是播放MP3格式的音乐文件，并且能控制播放，暂停，停止，音量控制，选择上一曲，选择下一曲，更改皮肤，歌曲列表文件的管理操作，在线播放，读取存储卡播放等多种播放控制，界面简洁明了，操作简单清晰。软件系统检测到错误行为时，报告错误，并提示处理操作。


### 3. 运行环境

Android 手机/平板基于Windows操作系统

## 三、假定和约束

1. 开发时限的约束：由2019年10月到12月约两个月的时间完成。
2. 人员限制：在小组6人的合作以及老师的指导下共同完成。
3. 数据安全性和稳定性的约束：所有信息保存在主服务器的数据库中，能够防止信息被窃取和篡改。
4. 系统稳定性的约束：系统能够长时间稳定运行。

## 四、类图
<img width="468" alt="image" src="https://github.com/Unice-YuFang/MusicPlayer/assets/74975816/03b4bf69-b678-4672-a183-d35a7402eda8">


## 五、布局
### 1. 列表介面功能
<img width="907" alt="Screenshot 2023-10-24 at 12 09 58 AM" src="https://github.com/Unice-YuFang/MusicPlayer/assets/74975816/926966fc-7da9-4b82-b6b2-e5e9e4ee78e9">
<img width="234" alt="image" src="https://github.com/Unice-YuFang/MusicPlayer/assets/74975816/3c05ada6-b2b8-430f-bfef-56f4569f7b09">

### 2. 播放界面
<img width="789" alt="Screenshot 2023-10-24 at 12 10 58 AM" src="https://github.com/Unice-YuFang/MusicPlayer/assets/74975816/a073ae31-7f7e-46c3-8de1-fd48f2d07373">
<img width="236" alt="image" src="https://github.com/Unice-YuFang/MusicPlayer/assets/74975816/dd6d4622-12b4-4ba3-802d-7b442f985e48">

# 六、开发时出现的主要问题
### 1. 虚拟机的文件管理
   A. 加入英文外的字体的名字的音乐时app闪退了

   可能是由于虚拟机字体不兼容。因此我们在虚拟机测试时只加入了全英文的歌曲。
   
   <img width="476" alt="image" src="https://github.com/Unice-YuFang/MusicPlayer/assets/74975816/0da6f6b4-9104-4b13-8ce3-fcefcdc4eeda">
   
   B. 多媒体无法识别新加入的音乐
   
   开发IDE在虚拟机打开的状态下开启虚拟机文件管理的方法是view菜单中的tool子菜单中的device file explorer选项，把需要的文件放入storage或sdcard文件夹中的相应位置。加入音乐文件后多次刷新文件管理页面，使音乐被识别并加入多媒体列表即可。
   
   <img width="522" alt="image" src="https://github.com/Unice-YuFang/MusicPlayer/assets/74975816/2fd464bf-e0b8-4059-9acf-efbdd0d2ba5d">

### 2. SystemBarTint的使用

   如何使手机本身顶部导航栏与app色调一致。利用[开源库](https://github.com/jgilfelt/SystemBarTint)的代码，将windowTranslucentStatus和windowTranslucent-Navigation属性设置为true就可以使顶部导航栏变为透明，进而达到导航栏与app界面的色调一致。
   
   <img width="289" alt="image" src="https://github.com/Unice-YuFang/MusicPlayer/assets/74975816/e305572e-1bbe-49d8-85bc-8a0a19c98df8">

### 3.渐变字

如何使App顶部歌名有渐变字的效果。利用支持文字颜色渐变的自定义文本控件GradientTextView。 设置setGradientColor(int startColor, int endColor)和setGradientColors(int startColor, int centerColor, int endColor)后在xml布局中使用。

<img width="381" alt="image" src="https://github.com/Unice-YuFang/MusicPlayer/assets/74975816/dba73c20-139b-4d7f-a5f6-d4cf05234cfb">
<img width="379" alt="image" src="https://github.com/Unice-YuFang/MusicPlayer/assets/74975816/4131b8db-9cc9-429a-ab3b-9e61713dff07">
<img width="379" alt="image" src="https://github.com/Unice-YuFang/MusicPlayer/assets/74975816/f410a751-20b5-4630-bb43-3c48a24ed2f5">
<img width="378" alt="image" src="https://github.com/Unice-YuFang/MusicPlayer/assets/74975816/f589612c-47f0-4fa7-b488-517207fd87ee">

### 4. 图片旋转
   
   如何使App正在播放歌曲的专辑封面图片有旋转的效果。利用支持图片旋转的自定义文本控件GradientTextView。 设置imageview.-startAnimation(AnimationUtils.loadAnimation(MainActivity.this, R.anim.imageview_rotate))。
   
   <img width="381" alt="image" src="https://github.com/Unice-YuFang/MusicPlayer/assets/74975816/2414d09f-1ebd-468b-bc24-557e81102eb6">
   <img width="378" alt="image" src="https://github.com/Unice-YuFang/MusicPlayer/assets/74975816/05d615b5-c122-4cd9-884e-6f07c6020db6">
   <img width="380" alt="image" src="https://github.com/Unice-YuFang/MusicPlayer/assets/74975816/e9d1d14a-ed2d-4fba-8fc0-b01c9be90d4e">
   <img width="378" alt="image" src="https://github.com/Unice-YuFang/MusicPlayer/assets/74975816/02593fe9-0fbf-4be5-846e-97e84faf50ef">
   
## 七、成果展示


https://github.com/Unice-YuFang/MusicPlayer/assets/74975816/57154b93-19ad-47ce-8775-0ba7acf5555c



## 八、开发的不足及展望
<img width="762" alt="Screenshot 2023-10-24 at 12 19 10 AM" src="https://github.com/Unice-YuFang/MusicPlayer/assets/74975816/6251210f-f754-4ec9-8a5b-0123b9f4358c">

