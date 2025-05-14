# AC08 LTE-M Mary/AV06 1.8V～5.5V 検査手順
## はじめに
本内容は、AC08 LTE-M MaryとAV06 1.8V～5.5Vの検査手順を記す。
## 用意するもの
### AC08 LTE-M Mary/AV06 1.8V～5.5V AS
* AP03 STM32 MCU
* AC08 LTE-M Mary[^1]
* AI01 4-Sensors
* AV06 1.8V～5.5V[^1]
* AX03 Leaf x2
* [2.54x6P through hole](https://github.com/Leafony/HW-Design-Files/tree/master/2.54x6P_through_hole)
* AZ63 Nut Plate
* M2X14mm ネジ
[^1]:検査対象のリーフ
### Solar-charger-debugger AS
* [Solar-charger-debugger-Leaf](https://github.com/Leafony/HW-Design-Files/tree/master/Solar-charger-debugger-Leaf) [^2]
* AZ01 USB
* AZ63 Nut Plate
* M2X8mm  
[^2]:Solar-charger-debugger-Leafは、高さ約3mmなので必ず上段にすること
### その他
* リーフ組立て治具(Leafx3)
* 単３x３本電池ボックス
* PC
* テスター
## ソースコード
* [STM32_LoRa_4-Sensors_Transmitter](https://github.com/Leafony/Sample-Sketches/tree/master/STM32_LoRa_4-Sensors_Transmitter)
## 組立て
<img src="./docs/L3Jig_LTE-M.jpg" width="400" />

**AC08 LTE-M Mary/AV06 1.8V～5.5V AS**</br>

|Stack No| Left Side Leaf| Right Side Leaf |
| :---:  | :--- | :--- |
|1 |   AI01 4-Sensors | － |
|2|  [2.54x6P through hole](https://github.com/Leafony/HW-Design-Files/tree/master/2.54x6P_through_hole) | － | 
|3|  AX03 Leaf x2 | AX03 Leaf x2| 
|4|  AP03 STM32 MCU | AC08 LTE-M Mary[^1] | 
|5|  － | AV06 1.8V～5.5V[^1] | 

**Solar-charger-debugger AS**</br>

|Stack No| Leaf | 
| :---  | :--- | 
|1 |   [Solar-charger-debugger-Leaf](https://github.com/Leafony/HW-Design-Files/tree/master/Solar-charger-debugger-Leaf) |
|2|  AZ01 USB| 
## 検査方法
1.Solar-charger-debuggerをRunモードにする

<img src="./docs/Solar-charger-debugger-Leaf_3d.png" width="400" />

2.Solar-charger-debugger-Leafにテスターを当て、3.3V±0.3Vを確認します。
 
3.Arduino IDEのシリアルモニタを開き、ボーレートを115200bpsにします。

4.STM32 MCUのリセットボタンを押すと、以下のように表示出来れば、OKです。

```
@@@@@ MurataLpwaCore::����n() init 1st time
<info> lpwa device power_up
<info> lpwa device ready.
Starting Arduino tcp client  ======================
<info> lpwa device ready.
<info> PDP: idle
<info> PDP: connect
LPWA connected
Signal Strength: -91.00dBm
time: 25/05/14,09:23:12+36
29.54[degC], 50.94[%]
Illuminance: 145.56
volt: 3.89
<info> TCP socket connected
connected
201
disconnecting.
<info> UDP socket closed
lpwaAccess end
<info> lpwa device power_down
Starting deep sleep for 600 sec
```

