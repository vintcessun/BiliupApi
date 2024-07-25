# 一个基于biliup-rs已经封装好可以满足基本需求的自用库

[BiliupApi - crates.io: Rust Package Registry](https://crates.io/crates/BiliupApi)

默认是在当前目录下使用biliup-rs格式的cookie.json

然后函数就三个

pub fn upload_video(video_info:VideoInfo,filename:&String)->Result<String,Box<dyn Error>>

pub fn append_video(filename:&String,bv:&String)->Result<(),Box<dyn Error>>

pub fn show_video(bv:&String)->Result<Value,Box<dyn Error>>

都做了同步封装

如果要异步的是如下：

pub async fn _upload_video(video_info:VideoInfo,filename:&String)->Result<String,Box<dyn Error>>

pub async fn _append_video(filename:&String,bv:&String)->Result<(),Box<dyn Error>>

pub async fn _show_video(bv:&String)->Result<Value,Box<dyn Error>>

使用简单，下面是VideoInfo的实现，手动弄一下就好了

pub struct VideoInfo{

  title:String,//标题

  copyright:u8,//1自制 2转载

  source:String,//来源

  tag:String,//用逗号分割

  tid:u16,//分区号

  desc:String,//简介

}