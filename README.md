# Reversi
黑白棋遊戲，有由經驗法則打造的AI對手

### 簡介
由python tkinter打造的視窗程式<br>
動機是觀看下黑白棋的時候常常會想記錄下高手們的棋譜<br>
因此想打造一個可以記錄每一步的黑白棋筆記本<br>
同時每一頁可以寫下筆記，以便分析戰況<br>

### 功能介紹
<img src="https://raw.githubusercontent.com/leooel97895750/Reversi/master/1.jpg" width="80%" height="80%">

* 左邊是棋盤，可以以正常的黑白旗邏輯規則下棋，會輔助預測可下點(黃色點)供使用者選擇
* 中間的按鈕可以選擇玩家對戰或與AI對戰
* 可以隨時儲存棋譜或開啟舊棋譜
* 右邊是筆記欄位，每一步棋都有自己的筆記欄位
* 中間下面的按鈕可以回顧棋譜，並且可以從中間分支出新的走法來儲存

### AI
此黑白棋AI是由經驗法則來打造的<br>

1. 開局吃少，終盤吃多
2. 對方可下點越少越好
3. 特殊位置有特殊意義

AI每次都會針對所有可下點進行計算，且會遞迴三層來預測局勢<br>
最後透過這個公式來決定AI該下哪一點<br>
decision = count+((tmp_chesscount*3)/int(total**0.5))-weight[tmp_x][tmp_y]*3<br>
decision越小越好<br>

* count = 遞迴三層後對方的可下點數目
* tmp_chesscount = 這點能翻的棋子數目
* total = 目前的總步數
* weight = 自訂的棋盤權重，例如:角落、邊這些特殊意義的位置


