# atmaCup 10th

## 内容
美術作品の属性情報から、その作品がどのぐらい人々に評価されるのか?を予測する

## 評価指標
root mean squared logarithmic error によって評価

## directries
* input<br>
  提供データ
* notebook<br>
  メインコード
* output<br>
  提出ファイル

## 特徴量作成  
複数のテーブルデータがあるコンペであったので、各々から特徴量を作成していくこととした。

* title言語 -> train, testから作成 

* 文字数を抽出 ->  'title', 'long_title','sub_title','more_title','description'  

* color.csv, palette.csv  
 kyoheiさんのdiscussionをベースに、分散など追加。
 https://www.guruguru.science/competitions/16/discussions/55aab41f-0395-4213-8d3d-04cc6fffd055/

* historical_person.csv  
　cha_kabuさん参考
  https://www.guruguru.science/competitions/16/discussions/4e8bbf3e-af2c-47bb-9620-51e3b00336b6/

* maker.csv  
　使用せず

* object_collection.csv,material.csv,technique.csv  
　Word2Vecを使ってmaterial, technique, object_collectionなどを特徴ベクトル化

* production_place.csv  
　国名を抽出
 
 * CountEncoder, LabelEncoder, aggression
 
## モデル  
LightGBM(n=10)
