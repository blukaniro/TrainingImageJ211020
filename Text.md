ImageJ Training 211020 by Ryosuke TAJIMA  
==============  
  
# 手動操作
## 線の計測  
- 画像を開くOpen image  
- +と-でズームイン/アウトができる  
- ラインツールで線を引いて，Analyse > Measure  
    設定がなければピクセル単位で表示
  
## 折線の計測
- ラインツールを右クリック，後は同様  
  
## 面積測定，その他
- Polygon，Angle，Multi-point tool  
  
## Analyse particle  
### 基本
- グレースケール -> 二値化
    二値化は自動と手動がある．選んでApply  
- Analyze > Analyze Particle  
    チェックボックスの左側はわりと有用，右側は特殊  
    求めるサイズや真円度を書く  
- OKで測定  
  
## RGB解析
- RGB分解: Image > Color > Split channels  
- 例えばgreenを選んで二値化して解析
    反転invertを使う場合もある: Edit > Invert  
- Analyze > Analyze Particle  
    被度はsummarizeとimage sizeから求められる．  
- Image calculatorで加減乗除できる: Process > Image calculator  
  
## ヒストグラムの取得
- RGB分解: Image > Color > Split channels  
    あるいはImage > Type > RGB stack  
    Image > Type > Lab stackでLab解析もできるが・・・
- 例えばgreenを選んで．．．
- ヒストグラム取得: Analyze > histgram  
- "List"をクリックするとヒストグラムのリストが得られる -> ImageJの外に出して解析  
  
## 画像の切り抜き
- 選択して，Image>Crop  
  
# 自動化に向けてマクロ作成
## 先に使い方
- マクロファイルを選ぶ．Plugins > Macros > Install...  
    拡張子はtxt, ImageJmacro, ijmくらい．
- マクロを動かす．Plugins > Macros > "CoverageOne"  
  
# 簡単なマクロの作り方
## 自分の作業を記録する
- 記録開始: Plugins > Macros > Record...  
- 例えば以下の作業  
    - RGB分解: Image > Color > Split channels  
    - Image calculatorの利用: Process > Image calculator  
        - Green - Blue  
        - Green - Red  
        - (Green-Blue) + (Green-Red)  
    - 二値化: Image > Adjust > Threshold  
    - もしかしたら反転: Edit > Invert  
    - Analyze Particle: Analyze > Analyze Particle  
  
## テストする
- "Recorder"を選択
- "Create"をクリックすると試用画面が出る  
- 画像を開いて，"Run"をクリック
  
## マクロを編集する
- メモ帳などテキスト編集アプリにコピペする．  
- よく使うコードを覚えておいて使う．  
    "selectImage"，"rename"等
- できたら使ってみる  
- "function"や"for"を使えるとより発展的なことができる．  