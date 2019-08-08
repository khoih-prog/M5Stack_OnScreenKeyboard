M5Stack OnScreenKeyboard library. (for ASCII code)
===

Add Keyboard for your M5Stack project.

あなたのM5Stackプロジェクトにキーボードを！  

## Description

OnScreenKeyboard which can be operated with 3 button.  

M5Stack本体の３ボタンで操作できるオンスクリーンキーボード。  
簡単な文字入力にお使いいただけます。  

Support FACES Keyboard and GameBoy and Encoder unit.  
Support PLUS Encoder unit.  
Support JoyStick unit.  
Support CardKB unit.  
Support morse code input.  

M5Stackの各種ユニットでの操作にも対応。
A+C 2ボタン同時押しでモールス入力モードに切替可能。  

![image](https://user-images.githubusercontent.com/42724151/52710266-45ab4280-2fd2-11e9-9897-f0b001cb0edf.png)  

Common operation:  
 `BtnA click` : キーボードパネル切替  Keyboard panel switches.  
 `BtnA and B hold and BtnC click` : 全消去  Clear all strings.  
 `BtnA hold and BtnC click` : モールス入力／フォーカス入力 モード切替  Switch between Morse code mode and focus selection mode.  
  
in focus mode:  
 `BtnA hold` :  左(上)に移動  The focus moves to the left (or up).  
 `BtnB click(or hold)` : 選択決定、行/列選択切替  The focused target is entered. Then switch the row/column selection.  
 `BtnC click(or hold)` : 右(下)に移動  The focus moves to the right (or down).  
 `BtnA hold and BtnB click` : 入力完了(または列選択に戻る)  Finish keyboard input. (or back to column selection.)  
  
![image](https://user-images.githubusercontent.com/42724151/51086670-c0dbc780-178c-11e9-8c97-bc415042c09c.png)  
in morse code mode:  
 `BtnB click` : モールス短音入力 Input a short pulse.  
 `BtnC click` : モールス長音入力 Input a long pulse.  
 `Release BtnB and C for 700 msec` : 入力確定  Fix input.  
 `BtnA hold and BtnB click` : 入力完了  Finish keyboard input.  


 Morse code is GBoard morse compliant.  
[GBoard morse code list](https://gist.github.com/natevw/0fce6b56c606632f8ee780b5d493f94e)

## Usage

```
#include <M5OnScreenKeyboard.h>

M5OnScreenKeyboard m5osk;

  m5osk.useFACES = true;       // FACES unit support.
  m5osk.useCardKB = true;      // CARDKB unit support.
  m5osk.useJoyStick = true;    // JoyStick unit support.
  m5osk.usePLUSEncoder = true; // PLUS Encoder unit support.
  m5osk.useFACESEncoder = true;// FACES Encoder unit support.
  // m5osk.swapBtnBC = true;   // BtnB/BtnC KeyAssign swap.

  m5osk.setup();
//m5osk.setup("Hello World."); // You can also set default text

  while (m5osk.loop()) {
    // You can write your code here.
    delay(1);
  }
  String text = m5osk.getString();
  m5osk.close();
```

## Licence

[MIT](https://github.com/lovyan03/M5Stack_OnScreenKeyboard/blob/master/LICENSE)  

## Author

[lovyan03](https://twitter.com/lovyan03)  
