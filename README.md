# XXDialog 使用方式
##  添加依赖
1.在project目录的build.gradle的allprojects节点添加
```java maven { url "https://jitpack.io" }```
如下:
```java
    allprojects {
        repositories {
            jcenter()
            maven { url "https://jitpack.io" }
        }
    }
```
2.在自己Modul的build.gradle中添加```compile 'com.github.luoshihai:XXDialog:v1.0.2'```
如下:
```java
dependencies {
	        compile 'com.github.luoshihai:XXDialog:v1.0.2'
	}
```
## 开始使用
* 准备好自己的dialog布局文件 例如 ```R.layout.dialog```
```java
XXDialog xxDialog = new XXDialog(this, R.layout.dialog) {
              @Override
              public void convert(DialogViewHolder holder) {
                    //holder有很多操作布局方法  自己点进去看源码
                    holder.setText()
              }
          };
          xxDialog.fromBottom().backgroundLight(0.2).fullWidth().showDialog();
 ```
* XXDialog的API:
```java
showDialog() 显示dialog
dismiss()  dismiss dialog
backgroundLight(double light) 弹出时背景亮度 值为0.0~1.0    1.0表示全黑  0.0表示全白
fromBottomToMiddle() 从底部一直弹到中间
fromBottom() 从底部弹出 显示在底部
fromLeftToMiddle() 从左边一直弹到中间退出也是到左边
fromRightToMiddle() 从右边一直弹到中间退出也是到右边
fromTop() 从顶部弹出 从顶部弹出  保持在顶部
fromTopToMiddle() 从顶部谈到中间  从顶部弹出  保持在中间
showDialog( int style) 显示一个Dialog自定义一个弹出方式  具体怎么写 可以模仿上面的
showDialog(boolean isAnimation) 如果为true 就显示默认的一个缩放动画
fullScreen() 全屏显示
fullWidth() 全屏宽度
fullHeight() 全屏高度
setWidthAndHeight(int width, int height) 自定义宽高
setOnKeyListener(DialogInterface.OnKeyListener onKeyListener) 当dialog弹出是 按键的点击事件会被dialog获取
setDialogDismissListener(OnDismissListener listener) 设置dismiss监听
setOnCancelListener(OnCancelListener listener) 设置取消监听
setCancelAble(boolean cancel) 设置能否被取消
setCanceledOnTouchOutside(boolean cancel) 设置点击其他地方能否被取消
