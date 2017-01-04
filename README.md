# Glide
Glide图片加载框架  
一：Glide超级图片加载框架,支持GIF动态图片加载，可单张多张图片加载，支持本地图片，SD卡图片，网络图片等，大神请忽略  
1.1 菜鸟部分：先添加依赖在gradle如下，修改相应版本号即可  
1.2   
compile 'com.github.bumptech.glide:glide:3.7.0'  
二：使用方法：  
2.1 加载单张图片Glide.with(MainActivity.this).load(url)//加载的图片地址   
//.centerCrop()//这三个方法注释就是显示原图，否则会显示压缩图   
//.placeholder(R.mipmap.ic_launcher)//网络错误，打不开的预览图   
//.crossFade().into(myImageView);//要显示的图片控件  
2.2加载多张图片2.2.1：图片地址集合  
String[] ivUrl = new String[]  
{"http://s14.sinaimg.cn/orignal/515eea5bt7887fc7d907d&690",  
"http://s14.sinaimg.cn/mw690/00688S7nzy70gaJgOyF3d&690",   
"http://imgsrc.baidu.com/forum/w%3D580/sign=d55fffb10fb30f24359aec0bf897d192/f8198618367adab4e43b4f938bd4b31c8601e473.jpg",   
"http://img2.imgtn.bdimg.com/it/u=3988856370,599835174&fm=23&gp=0.jpg",   
"http://s3.sinaimg.cn/bmiddle/48dc665ax6c63fb891302&690",   
"http://hiphotos.baidu.com/penguin03/mpic/item/50d2a4019e86b506738da509.jpg",  
"http://imgsrc.baidu.com/forum/pic/item/a5f2debe066818af51da4b80.jpg",   
"http://img4.imgtn.bdimg.com/it/u=3989094408,3071353826&fm=23&gp=0.jpg",  
"http://img313.ph.126.net/Ptaiuj2dC0rdm9_yu3cEKQ==/3679722370539020604.gif",   
"http://b.hiphotos.baidu.com/zhidao/wh%3D450%2C600/sign=4f3073ee7fd98d1076810435140f9438/503d269759ee3d6d341662d940166d224e4aded4.jpg",   
"http://imgsrc.baidu.com/forum/w%3D580/sign=01c4c39e89d4b31cf03c94b3b7d7276f/a1f1f1fdfc0392459da139d28594a4c27c1e2592.jpg",   
"http://imgsrc.baidu.com/forum/w%3D580/sign=f194b4d60924ab18e016e13f05f8e69a/a90a3d12b31bb0515bebe2d8367adab448ede0f4.jpg",   
"http://imgsrc.baidu.com/forum/w%3D580/sign=890bf4b63c6d55fbc5c6762e5d234f40/07928201a18b87d688e33377060828381e30fd40.jpg",   
"http://d.hiphotos.baidu.com/zhidao/wh%3D450%2C600/sign=e5402dd64aed2e73fcbc8e28b2318dbd/4610b912c8fcc3ce10c70b619245d688d43f2059.jpg"};  
用listview显示即可，直接上代码，getview关键部分代码  
public View getView(int position, View convertView, ViewGroup parent) {   
ImageView myImageView;  
if (convertView == null) {   
myImageView = (ImageView) View.inflate(MainActivity.this, R.layout.my_image_view, null);  
} else {  
myImageView = (ImageView) convertView;   
}      
String url = ivUrl[position];      
Glide  
.with(MainActivity.this)  
.load(url)//   
.centerCrop()//这三个方法注释就是显示原图，否则会显示压缩图   
// .placeholder(R.mipmap.ic_launcher)//网络错误，打不开的预览图   
// .crossFade() .into(myImageView);      
return myImageView;}
