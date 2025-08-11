マーメイドテンプレート
```mermaid
flowchart TB

%%オブジェクトの定義
OU1[外部要素]
NW1{{ネットワーク装置<br>LBとかWAFとか}}
CP1(EC2とか<br>Lamdaとか)
DB1[(データベース)]
ST1[(ストレージ)]

click OU1 href "https://example.com" "ツールチップ" _blank


%%================================================================
%%---グループスタイルの設定---

%%外部要素のスタイル
%% [ ]か( )で名前を括る
classDef SOU fill:#aaa,color:#fff,stroke:#fff
class OU1,OU2,OU3 SOU

%%Network関連のスタイル
%% {{ }}か[ ]で名前を括る
classDef SNW fill:#84d,color:#fff,stroke:none
class NW1,NW2,NW3 SNW

%%Compute関連のスタイル
%% ( )で名前を括る
classDef SCP fill:#e83,color:#fff,stroke:none
class CP1,CP2,CP3 SCP

%%DB関連のスタイル
%%[( )]で名前を括る
classDef SDB fill:#46d,color:#fff,stroke:#fff
class DB1,DB2,DB3 SDB

%%Storage関連のスタイル
%%[( )]で名前を括る
classDef SST fill:#493,color:#fff,stroke:#fff
class ST1,ST2,ST3 SST

%%---アイコンスタイルの設定---

%%AWS Cloudのスタイル
%% [ ]で名前を括る
classDef SGC fill:none,color:#345,stroke:#345
class GC SGC

%%Regionのスタイル
%% [ ]で名前を括る
classDef SGR fill:none,color:#59d,stroke:#59d,stroke-dasharray:3
class GR SGR

%%VPCのスタイル
%% [ ]で名前を括る
classDef SGV fill:none,color:#0a0,stroke:#0a0
class GV SGV

%%Availability Zoneのスタイル
%% [ ]で名前を括る
classDef SGA fill:none,color:#59d,stroke:#59d,stroke-width:1px,stroke-dasharray:8
class GA SGA

%%Private subnetのスタイル
%% [ ]で名前を括る
classDef SGPrS fill:#def,color:#07b,stroke:none
class GS1,GS2 SGPrS

%%Public subnetのスタイル
%% [ ]で名前を括る
%%  classDef SGPuS fill:#efe,color:#092,stroke:none
%%  class GS SGPuS

%%================================================================

```