## Easy X 图形库学习心得

> Written by Lee Kinyou, CS, CQUPT
>
> Words written before the text:
>
> *This markdown document is a little note about Easy X functions that I wrote in my busy schedule. Although it is not very comprehensive, it basically includes commonly used functions. QAQ*
>
> *Monday, June 20, 2022*



### 一、基本绘图与文字输出



#### 1.initgraph()

```cpp
initgraph(int width, int height, int flag = 0);
//绘制宽width，高height的窗口
initgraph(1024, 720);//只打开一个1024*720的绘图窗口
initgraph(1024, 720, EW_SHOWCONSOLE);//同时打开绘图窗口和控制台
```



#### 2.cleardevice()

```cpp
cleardevice();
//清空当前绘图窗口
```



#### 3.setbkmode()

 ```cpp
 setbkmode(int mode);
 //调整绘图框背景模式
 setbkmode(TRANSPARENT);//将文本的背景调为透明，outtextxy()函数输出后文字背景会透明
 ```

#### 

#### 4.setbkcolor()

```cpp
setbkcolor(COLORREF color);
//设置背景颜色，支持RGB(int RED, int GREEN, int BLUE) 每个颜色调色范围为0~255
//同时支持一些预设好的颜色如 RED、GREEN、BLUE、BLACK、WHITE、BLOWN等等
setbkcolor(RED);
setbkcolor(RGB(50, 50, 50));
```



#### 5.circle() like

```cpp
circle(int x, int y, int radius);//在坐标为(x,y)处建立一个半径为radius的空心圆
clearcircle(int x, int y, int radius);//在坐标为(x,y)处删除一个半径为radius的空心圆

fillcircle(int x, int y, int radius);//实心圆
solidcircle(int x, int y, int radius);//有其他颜色边线包裹的实心圆

fillrectangle(int left, int top, int right, int bottom);//确定矩阵的左上角和右下角，绘制矩阵

//其他基本图形的绘制，请自行探索。QAQ
```



#### 6.setlinecolor()

```cpp
setlinecolor(COLORREF color);//设置线条颜色

setlinecolor(GREEN);
setlinecolor(RGB(10, 1, 10));
```



#### 7.setfillcolor()

```cpp
setfillcolor(COLORREF color); //设置基本图形填充颜色

setfillcolor(GREEN);
setfillcolor(RGB(10, 1, 10));
```



#### 8.setlinestyle()

```cpp
setlinestyle(PS_SOLID, width); //设置线条的格式为PS_SOLID和宽度为width
```



#### *9.outtextxy()

//（必须要看见啊QAQ）**注: 所有成员必须修改字符集**

> 路径为:
>
> 项目 ->  属性 -> 高级 ->在字符集一栏   将   用Unicode 字符集   改为   **使用多字节字符集**
>
> **不修改会导致所有easy x 的库函数输出不了汉字**

```cpp
outtextxy(int x, int y, TCHAR c);
//在(x,y)处绘制内容为c的文本
outtextxy(50, 50, "你寄吧谁啊？");

//将文本居中放在绘制的矩形框的方法:
	setbkmode(TRANSPARENT);//使输出的文字取消背景
	setfillcolor(BROWN);
	settextstyle(20, 10, "宋体");
	fillroundrect(x, y, x + w, y + h, 10, 10);//输出一个矩阵
	//文字居中处理
	int tx = x + (w - textwidth(TEXT)) / 2;
	int ty = y + (h - textheight(TEXT)) / 2;
	outtextxy(tx, ty, TEXT);
```



#### 10.settextstyle()

```cpp
settextstyle(int width, int height, TCHAR mode);
//将文本文字的宽设定为width，高设定为height，字体为mode
settextstyle(20, 20, "华文行楷");
```



#### 11.closegraph()

```cpp
closegraph()//关闭绘图窗口
```





### 二、图片输出

#### 1.IMAGE

~~~cpp
IMAGE img;
//创建一个类型为图形的对象
~~~



#### 2.loadimage()

```cpp
loadimage(IMAGE *pDstImg, LPCTSTR pImgFile, int nWidth = 0, int nHeight = 0, bool bResize = false);
// 从文件中加载图片 (bmp/gif/jpg/png/tif/emf/wmf/ico)
//  ./代表从当前文件夹读取文件， ../代表从上一文件夹读取文件
//绝对路径：C:\\Users\\lee\\source\\repos\\EasyX Learning\\DingzhenFace.png

loadimage(&img, "./DingzhenFace.png", 50, 50);
```



#### 3.putimage()

```cpp
putimage(int dstX, int dstY, const IMAGE *pSrcImg, DWORD dwRop = SRCCOPY);
putimage(int dstX, int dstY, int dstWidth, int dstHeight, const IMAGE *pSrcImg, int srcX, int srcY, DWORD dwRop = SRCCOPY);
//打印加载好的图片
putimage(50, 50, &img);
```



### 三、鼠标读入

#### 1. ExMessage

```cpp
ExMessage msg;//定义一个消息变量
msg=getmessage(EM_MOUSE);
//获取鼠标消息
//但实际上不止有EM_MOUSE,还有其他的消息类型
```



#### 2.PeekMessage()

```cpp
PeekMessage(LPMSG lpMsg, HWND hWnd, UINT wMsgFilterMin, UINT wMsgFilterMax, UINT wRemoveMsg);
//返回值为bool
//使用方法如下

if (peekmessage(&msg, EM_MOUSE)) {
	switch (msg.message)
	{
	case WM_LBUTTONDOWN://WM_LBUTTONDOWN 为左键
		if (msg.x >= 50 && msg.x <= 200 && msg.y >= 50 && msg.y <= 100) {
			cout << "我是按钮，我被左键点击了！\n坐标为：" << msg.x << " " << msg.y << endl;
		}
		break;
	case WM_RBUTTONDOWN://WM_LBUTTONDOWN 为右键
		if (msg.x >= 50 && msg.x <= 200 && msg.y >= 50 && msg.y <= 100) {
			cout << "我是按钮，我被右键点击了！\n坐标为：" << msg.x << " " << msg.y << endl;
		}
		break;
	}
}
```



### 四、键盘读入

### 1.#include<conio.h>

>包含 _getch()函数

### 2._getch()

```cpp
//用法如下：
while (TRUE) {    
    char key = _getch();
	switch (key)
	{
	case 'w':
	case 'W':
		pos_y -= Movingdistance;
		cout << "当前输入的键为：上键" << endl;
		break;
            
	case 's':
	case 'S':
		pos_y += Movingdistance;
		cout << "当前输入的键为：下键" << endl;
		break;
            
	case 'a':
	case 'A':
		pos_x -= Movingdistance;
		cout << "当前输入的键为：左键" << endl;
		break;
            
	case 'd':
	case 'D':
		pos_x += Movingdistance;
		cout << "当前输入的键为：右键" << endl;
		break;

	case 'k':
	case 'K':
		pos_x += LongMovingdistance;
		break;
	}
}
```



### 五、音乐读入读出

### 1.#include<mmsystem.h>

```
#include<mmsystem.h> //包含多媒体设备接口头文件
```



### 2.#pragma comment(lib,"winmm.lib") 

```cpp
#pragma comment(lib,"winmm.lib") 
//加载静态库 支持MPEG,AVI,WAV,MP3格式
```



#### 3.mciSendString()

```cpp
//打开音乐 播放音乐 alias 取别名 repeat 重复播放
mciSendString("open ./孤勇者.mp3", 0, 0, 0);
mciSendString("play ./孤勇者.mp3", 0, 0, 0);

//或者
//mciSendString("open ./孤勇者.mp3 alias BGM", 0, 0, 0);
//mciSendString("play BGM repeat", 0, 0, 0);
```



### 六、弹窗

#### 1.HWND

```cpp
HWND hnd;
hnd = GetHWnd();
//设置窗口标题
```



#### 2.SetWindowText()

```cpp
SetWindowText(hnd, TEXT);
//设置窗口为名称为TEXT
```



#### 3.MessageBox()

```cpp
MessageBox(hnd, "你寄吧谁啊？", "提示", MB_OKCANCEL);
//弹出的窗口的标题为“提示”，内容为“你寄吧谁啊？”，有确定和取消键
//MessageBox()的返回值为bool

//例如：
    HWND hnd = GetHWnd();
	//设置窗口标题
	SetWindowText(hnd, "鼠鼠我呀，头发要掉光了。");
	//弹出窗口，提示用户操作
	int isok = MessageBox(hnd, "你寄吧谁啊？", "提示", MB_OKCANCEL);
	settextstyle(500, 100, "华文行楷");
	settextcolor(RGB(100, 120, 130));
	if (isok == IDOK) {
		outtextxy(100, 100, "正确的");
	}
	else if (isok == IDCANCEL) {
		outtextxy(100, 100, "sabbly");
	}
```







































