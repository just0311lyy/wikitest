# BLOCKPLACETYPE
------------------------------------------------------------------------------------------
## 枚举

|<div style="width:200px">BLOCKPLACETYPE</div>|<div style="width:100px"></div>|<div style="width:100px"></div>|
|:---   |:---|:---|
|文字水平对齐|
|**名称**   |**值**  |**描述**|
|COVER   |0   |覆盖。当前位置有方块，也会将方块替换掉（默认）|
|AIR|1   |空气。当前位置如果为空才会放置方块，若有则不放置|
|NOT_SAME  |2   |若相同不覆盖|
|NOT_SAMEID  |3   |只当ID不同时覆盖，仅blockdata不同时不会覆盖|