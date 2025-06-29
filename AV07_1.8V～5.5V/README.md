# LoRa Mary/AV07 1.8V～5.5V 検査手順
## はじめに
本内容は、LoRa MaryとAV07 1.8V～5.5Vを同時に検査する手順を記します。
## 用意するもの
### LoRa Mary AS/AV07 1.8V～5.5V
* AP03 STM32 MCU
* AC07 LoRa Mary[^1]
* AI01 4-Sensors
* AV07 1.8V～5.5V[^1]
* AX03 Leaf x2  
* AZ63 Nut Plate
* M2X14mm ネジ
[^1]:検査対象のリーフ

### Solar-charger-debugger AS
* [Solar-charger-debugger-Leaf](https://github.com/Leafony/HW-Design-Files/tree/master/Solar-charger-debugger-Leaf) [^2]
* AZ01 USB
* AZ63 Nut Plate
* M2X8mm ネジ
* USケーブル
* 6pin SHコネクタ・ケーブル 
[^2]:Solar-charger-debugger-Leafは、高さ約3mmなので必ず上段にします。
### その他
* PC
* テスター
* リーフ組立て治具(Leafx3)
* SHコネクタ付き単３x３本電池ボックス 

## ソースコード
* [STM32_LoRa_4-Sensors_Transmitter](https://github.com/Leafony/Sample-Sketches/tree/master/STM32_LoRa_4-Sensors_Transmitter)
## 組立て
<img src="./docs/AV07_1.8V～5.5V_L3Jig.jpg" width="400" />

**LoRa Mary AS/AV07 1.8V～5.5V**</br>

* AX03 Leaf x2の右側のコネクタは、外して使用します。 

|Stack No| Left Side Leaf| Right Side Leaf |
| :---:  | :--- | :--- |
|1 |   AI01 4-Sensors | － |
|2|  AX03 Leaf x2 | AX03 Leaf x2| 
|3|  AP03 STM32 MCU | AC07 LoRa Mary| 
|4|  － | AV07 1.8V～5.5V| 

**Solar-charger-debugger AS**</br>

|Stack No| Leaf | 
| :---  | :--- | 
|1 |   [Solar-charger-debugger-Leaf](https://github.com/Leafony/HW-Design-Files/tree/master/Solar-charger-debugger-Leaf) |
|2|  AZ01 USB| 
## 検査方法
1.Solar-charger-debuggerをRunモードにします。

<img src="https://github.com/Leafony/HW-Design-Files/blob/master/AC07_LoRa_Mary/docs/Solar-charger-debugger-Leaf_3d.png" width="400" />

2.Solar-charger-debugger-Leafにテスターを当て、3.3V±0.3Vを確認します。（**初回のみ、2回目以降は省略**)
 
3.Arduino IDEのシリアルモニタを開き、ボーレートを115200bpsにします。[^3]
[^3]:Arduino IDEの設定に関して、[こちら](https://docs.leafony.com/docs/environment/stm32/arduino_ide/)を参照願います。

4.STM32 MCUの[リセットスイッチ](https://docs.leafony.com/docs/environment/stm32/arduino_ide/#%E3%83%9E%E3%82%A4%E3%82%B3%E3%83%B3%E3%83%9C%E3%83%BC%E3%83%89%E3%81%AE%E5%8B%95%E4%BD%9C%E7%A2%BA%E8%AA%8D)を押すと、以下のように表示出来ればOKです。

```
Starting LoRa 4-Sensors Transmitter...
Initializing sensors...
Sensors initialized.
Successfully started!
Sending packet... 
Wakeup Sensors.
3.89V,30.97℃,49.99%,181.60lx,0.05g,0.03g,0.97g
end!
```
# Tips
###  AC07 LoRa Mary 外観
<img src="./docs/AV07_1.8V～5.5V_3D.png" width="400" />

## AV06 1.8V～5.5VとAV07 1.8V～5.5Vの主な相違点
|　| AV06 1.8V～5.5V| AV07 1.8V～5.5V |
| :---  | :--- | :--- |
|出力電圧|   3.3V |3.3V |
|出力電流|  1.0A | 400mA| 
|Debugコネクタ|  無 |JST製 SH 6pin | 
|電源スイッチ|  有 |無 | 
|電源コネクタ| JST製 PH 2pin | JST製 SH 2pin| 
|用途| 一般 | エッジ用電源リーフ| 



