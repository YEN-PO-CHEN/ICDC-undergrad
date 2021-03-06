# ICDC

![](https://img.shields.io/badge/code_language-Verilog-blueviolet)  ![](https://img.shields.io/badge/HDL_simulator-ncVerilog-blue)
## ICDC-B 2015-II(Graduate) - Image Sorting Engine
[![](https://img.shields.io/badge/collaborator-%E8%91%89%E6%89%BF%E8%BB%92-red)](https://github.com/jacky40511) ![](https://img.shields.io/badge/Report_area-69842-blue) ![](https://img.shields.io/badge/Report_timing-6298980_ns-purple)

## ICDC-B 2017-I(Graduate) - [Distance Transform](https://icc.tsri.org.tw/ICC2017/)   
[![](https://img.shields.io/badge/collaborator-%E8%91%89%E6%89%BF%E8%BB%92-red)](https://github.com/jacky40511) ![](https://img.shields.io/badge/Report_area-6321-blue) ![](https://img.shields.io/badge/Report_timing-1374150_ns-purple)
- `DT.v` 
### 困難點
- 難點(1)：`Latch`
  - 假設一個 `reg` 出現 `latch` 一定要處理，有可能僅只有附值為1忘記給0
- 難點(2)：`Ram`
  - 這邊可以使用RAM去把ROM的值存起來
- 難點(3)：`面積`
  - 如果使用Default可以避免latch但是面積會小幅增加(對於壓面積不利)
### Conclusion
  - 本題比較需要看波形圖，尤其是讀檔案的部分需要特別注意
## ICDC-E 2019-I(Undergraduate) - Image Convolutional Circuit Design
- `CONV.v`
### 注意：
- 要將 `dat_univ` 資料夾向上層移動
### 困難點
- 難點(1)：`小數點乘法`
  - 解決方式：(~target+1)將質先轉乘正數，乘完之後再去變號
- 難點(2)：`小數點進位`
  - 解決方式：直接位數延長，看小數點後第16位為一還是0
- 難點(3)：`面積`
  - 解決方式：共用乘法器，用assign!
- 難點(4)：`initial`不要用
  - 直接放在reset裡面！
## ICDC-E 2018-I(Undergraduate) - [Image Display Control](http://icc.tsri.org.tw/ICC2018/)
## ICDC-E 2019-I(Undergraduate) - [Image Convolutional Circuit Design](http://icc.tsri.org.tw/ICC2019/)
## ICDC-E 2020-I(Undergraduate) - [String Matching Engine](http://icc.tsri.org.tw/ICC2020/)
[![](https://img.shields.io/badge/collaborator-%E8%91%89%E6%89%BF%E8%BB%92-red)](https://github.com/jacky40511) ![](https://img.shields.io/badge/report_area-20625-blue) ![](https://img.shields.io/badge/report_timing-18800_ns-purple)

### Viewpoint
- 使用 `combinational Circuit`
```Verilog
always @(*) 
begin
    is_D = 0;
    is_H = 0;
    if (str_idx == pat_max) is_H = 1;
    else if (string[str_idx - pat_max - 1] == Space) is_H = 1;
    else is_H = 0;
        
    if (str_idx == str_max) is_D = 1;
    else if (string[str_idx + 1] == Space) is_D = 1;
    else is_D = 0;
end
```
- 將Finite State Machine放到不同Always中
### 難點：
- 難點(1)：`RTL Simulation 成功` BUT `Gate-Level Simulation 失敗`
  - 如果將cycle條大還是沒用，那代表電路設計有問題
- 難點(2)：`combinational Circuit` (不要被`Sequential Circuit` 給綁著)

## ICDC-E 2021-I(Undergraduate) - [Geofence](http://icc.tsri.org.tw/ICC2021/)
![](https://img.shields.io/badge/Report_area-20850-blue)
## ICDC-E 2022-I(Undergraduate) - [Job Assignment Machine](http://icc.tsri.org.tw/ICC2022/)