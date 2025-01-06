## 練習1.3.g バッシュによるメタプログラミング

seq 4 | awk '{print "mkdir " ($1%2 ? "odd_" : "even_")$1}'

seq 4 | awk '{print "mkdir " ($1%2 ? "odd_" : "even_")$1}'  | bash


## 練習1.4.a　GitHub からリポジトリをクローン
練習問題
find shellgei160/ | grep files


問題1
cat files.txt | grep '\.exe$'

        ※　.　正規表現　任意の１文字と一致する　メタ文字
        　　　　　　→ . そのものを検索したいときは　\.　とする

          　$  終端を表すメタ文字
           



