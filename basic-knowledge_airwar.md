# 航空戦

下記の順番で発生。

1. 制空戦
2. 触接判定
3. 対空砲火・対空カットイン
4. 航空機による開幕航空攻撃

## 制空戦

制空戦フェーズにおける敵艦載機の撃破率は下記。

制空権    |撃墜率 
:---------|:------
制空権確保|0～90％
航空優勢  |0～80％
表示なし  |0～60％

## 対空砲火
### 基本知識

* 水上艦は敵の艦攻・艦爆装備スロット1個をランダムで攻撃
* 割合撃墜、固定撃墜を順番に実施(それぞれ50%の確率で発動)
* 最低撃墜保証として1機撃墜が可能

それぞれの撃墜フェーズにおける計算式は下記。

分類              |計算式
:-----------------|:-----
割合撃墜          |[ (加重対空値/400) × 敵スロット機数 ]
固定撃墜          |[ (加重対空値＋艦隊防空値) × 変動ボーナス補正/10 ]
割合撃墜(連合艦隊)|[ (加重対空値/400) × 敵スロット機数 × 連合艦隊補正 ]
固定撃墜(連合艦隊)|[ (加重対空値＋艦隊防空値) × 連合艦隊補正 × 変動ボーナス補正/10 ]

※連合艦隊補正：水上第一艦隊＝0.72、第二艦隊＝0.48


個々の艦における「加重対空値」と艦隊全体における「艦隊防空値」が存在する。

分類            |計算式
:---------------|:-----
加重対空値(概算)|素対空値＋&sum;{(装備倍率×装備対空値)＋(改修係数×&radic;{改修値})}
艦隊防空値      |[ 陣形補正 × &sum;{艦隊対空ボーナス} ]×(2.0/1.3)
艦隊対空ボーナス|[ &sum;{(装備対空値×装備倍率)＋(改修係数×&radic;{改修値})} ]

※加重対空値は、上記の概算値で概ね問題なし。詳細はwiki参照。

### 装備における補正値

装備種別        |装備倍率<br>(加重対空) |改修係数<br>(加重対空) |装備倍率<br>(艦隊防空) |改修係数<br>(艦隊防空) 
:---------------|:---------------------:|:---------------------:|:---------------------:|:---------------------:
高角砲          |4                      |2                      |0.35                   |2.0
高角砲+高射装置 |4                      |3                      |0.35                   |3.0
対空機銃        |6                      |4                      |0.20                   |0.0
電探            |3                      |0                      |0.40                   |1.5
高射装置        |4                      |2                      |0.35                   |2.0
主砲(赤)        |0                      |                       |0.20                   |
副砲(黄)        |                       |0                      |0.20                   |0.0
三式弾          |0                      |                       |0.60                   |
艦戦            |0                      |                       |0.20                   |
艦爆            |                       |                       |0.20                   |
水禎            |0                      |                       |0.20                   |

対空砲火フェーズにおいて重宝する装備は下記。

装備名                    |装備対空値 |加重対空値 |艦隊対空<br>ボーナス値
:-------------------------|:---------:|:---------:|:--------------------:
10cm高角砲+高射装置       |+10        |+40        |+3.5
10cm高角砲+高射装置★max  |+10        |+49.48     |+12.98
13号対空電探改            |+4         |+12        |+1.6
21号対空電探改            |+5         |+15        |+2.0
25mm三連装機銃 集中配備   |+9         |+54        |+1.8
Borors 40mm四連装機関砲   |+10        |+60        |+2.0
QF 2ポンド8連装ポンポン砲 |+10        |+60        |+2.0
FuMO25 レーダー           |+7         |+21        |+2.8
5inch連装砲 Mk.28 mod.2   |+9         |+36        |+3.15
90mm単装高角砲            |+8         |+32        |+2.8
90mm単装高角砲★max       |+8         |+41        |+12.2
三式弾                    |+5         |           |+3.0

### 陣形による補正

陣形    |補正値
:-------|:----:
単縦陣  |1.0
複縦陣  |1.2
輪形陣  |1.6
梯形陣  |1.0
単横陣  |1.0
第一警戒|1.1
第二警戒|1.0
第三警戒|1.5
第四警戒|1.0

### 対空カットイン

固定撃墜の発生や、対空砲火の変動ボーナスに影響。
発生条件は下記。

* 高角砲(+高射装置)と対空電探の組み合わせ
* 防空艦による特殊カットイン

#### カットインの優先順位(★重要)

カットイン発動が複数艦で重なった場合、優先順位判定が行われる。  
発動は一艦のみのため、秋月型や摩耶の発動を他艦で阻害しないように注意する必要がある。

|優先|艦名       |装備1          |装備2          |装備3    |装備4    |固定撃墜 |変動<br>ボーナス<br>補正
|:--:|:----------|:--------------|:--------------|:--------|:--------|:-------:|:----------------------:
|1   |鬼怒改二   |高角砲[^1]     |特殊機銃       |         |         |+5機     |1.45倍
|    |鬼怒改二   |特殊機銃       |               |         |         |+3機     |1.25倍
|?   |由良改二   |高角砲         |対空電探       |         |         |+5機     |1.45倍
|2   |皐月改二   |特殊機銃       |               |         |         |+2機     |1.20倍
|    |文月改二   |特殊機銃       |               |         |         |+2機     |1.20倍
|3   |霞改二乙   |高角砲         |対空機銃       |対空電探 |         |+4機     |1.40倍
|    |霞改二乙   |高角砲         |対空機銃       |         |         |+2機     |1.25倍
|4   |五十鈴改二 |高角砲         |対空機銃       |対空電探 |         |+4機     |1.45倍
|    |五十鈴改二 |高角砲         |対空機銃       |         |         |+3機     |1.30倍
|5   |全艦       |特殊機銃       |対空機銃       |対空電探 |         |+3機     |1.25倍
|6   |摩耶改二   |高角砲         |特殊機銃       |対空電探 |         |+8機     |1.65倍
|    |摩耶改二   |高角砲         |特殊機銃       |         |         |+6機     |1.50倍
|7   |全艦       |高角砲         |高射装置       |         |         |+2機     |1.30倍
|8   |全艦       |高角砲+高射装置|対空電探       |         |         |+4機     |1.40倍
|9   |全艦       |高角砲         |高射装置       |対空電探 |         |+3機     |1.35倍
|10  |戦艦       |大口径主砲     |三式弾         |高射装置 |         |+4機     |1.45倍
|11  |全艦       |高角砲+高射装置|高角砲+高射装置|対空電探 |         |+4機     |1.50倍
|12  |戦艦       |大口径主砲     |三式弾         |高射装置 |対空電探 |+6機     |1.50倍
|13  |秋月型     |高角砲         |高角砲         |電探     |         |+7機     |1.70倍
|    |秋月型     |高角砲         |電探           |         |         |+6機     |1.70倍
|    |秋月型     |高角砲         |高角砲         |         |         |+4機     |1.60倍
|?   |UIT-25     |対空機銃[^2]   |               |         |         |+?機     |?.??倍


---

[^1]:高角砲+高射装置以外
[^2]:特殊機銃以外
