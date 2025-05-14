# AC07 LoRa Mary 検査手順
## はじめに
本内容は、AC07 LoRa Mary の検査検査手順を記す。
## 用意するもの
### AC07 LoRa Mary AS
* AP03 STM32 MCU
* AC07 LoRa Mary
* AI01 4-Sensors
* AV06 1.8V～5.5V
* AX03 Leaf x2
* [2.54x6P through hole](https://github.com/Leafony/HW-Design-Files/tree/master/2.54x6P_through_hole)
* AZ63 Nut Plate
* M2X4mm ネジ
### Solar-charger-debugger AS
* [Solar-charger-debugger-Leaf](https://github.com/Leafony/HW-Design-Files/tree/master/Solar-charger-debugger-Leaf) [^1]
* AZ01 USB
* AZ63 Nut Plate
* M2X8mm  
[^1]:Solar-charger-debugger-Leafは、高さ約3mmなので必ず上段にすること
### その他
* リーフ組立て治具(Leafx3)
* 単３x３本電池ボックス
* PC
* テスター
## ソースコード
* [STM32_LoRa_4-Sensors_Transmitter](https://github.com/Leafony/Sample-Sketches/tree/master/STM32_LoRa_4-Sensors_Transmitter)
## 組立て
<img src="./docs/L3Jig_LTE-M.jpg" width="400" />

|No | Left Side | Right Side |
| :---:  | :---: | :---: |
|1 |   AI01 4-Sensors | － |
|2|  2.54x6P through hole | － | 
|3|  AX03 Leaf x2 | AX03 Leaf x2| 
|4|  AP03 STM32 MCU | AC07 LoRa Mary | 
|5|  － | AV06 1.8V～5.5V | 

## 検査方法
1.Solar-charger-debuggerをRunモードにする

<img src="./docs/Solar-charger-debugger-Leaf_3d.png" width="400" />

2.Solar-charger-debugger-Leafにテスターを当て、3.3V±0.3Vを確認する(初物電気検査のみ)
 
3.xxx
