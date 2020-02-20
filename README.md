# ml-project-template

機械学習の実験やプロジェクトの管理方法に関するメモやノウハウをまとめる．
SIGNATEの練習問題を解きながら実際の開発環境を構築

## 研究の進め方
研究の流れとともにそこで利用されるであろうツールを整理
### 1. データを見る．

jupyterが基本．実験しながら方針を固めていく．全てのデータに目を通し，人間である自分ならどれくらいの認識が可能かを見定める．
また，データの可視化(PCA,t-SNE,UMAPあたり)してみて，どういうモデルならできそうか(画像であればCNN, NNを使うまでもなければどんな特徴量が必要か)をあたりをつける．ここで全てが決まると思っても良い．全体の50%の時間をかける
### 2. ベースモデルの策定

データを観察することがだいたい終了したら，モデルを決める．
デファクトスタンダードになっている手法(これであれば〇〇%くらい精度がでそうとあたりがつくもの)を利用する．
ここで使うモデルによって前処理方法も異なるはず

### 3. 前処理

データの前処理を行う．Deep系ならAugmentationなども決めておく．



### 4. 学習
### 5. 予測



## ディレクトリ構造


## tips
- データはgitで管理しない．容量制限で大抵upできないから
- Dataフォルダは生データ，処理済み，データセット(訓練検証)用で構成
- パラメータ管理はhydraを使用
- 実験結果の管理はmflow or sacredを使用
- 環境はdockerで管理

## Data Leakageについて

https://towardsdatascience.com/data-leakage-in-machine-learning-10bdd3eec742
A very common error that people make is to leak information in the data pre-processing step of machine learning. It is essential that these transformations only have knowledge of the training set, even though they are applied to the test set as well. For example, if you decide that you want to run PCA as a pre-processing step, you should fit your PCA model on only the training set. Then, to apply it to your test set, you would only call its transform method (in the case of a scikit-learn model) on the test set. If, instead, you fit your pre-processor on the entire data-set, you will leak information from the test set, since the parameters of the pre-processing model will be fitted with knowledge of the test set.
## 参考
SIGNATEの問題はこちら
https://signate.jp/competitions/108/data

ディレクトリ構成はこちらを参考
https://drivendata.github.io/cookiecutter-data-science/

Deep Learnningのモデルの作成・学習時の実験管理を楽にするツールたち
https://qiita.com/TatsuyaShirakawa/items/db2c37ab21df109e72ab

情報系研究者のための研究ノート
https://qiita.com/guicho271828/items/9307ae12248329b71f12