
 ## 練習　1.3.c

$ echo 中村 山田 田代 上田 | grep -o "[^ ]田"
山田
上田

　　　　　　　　　　　　　　　　⇒　スペースでない1文字の後ろに田が付く　という正規表現

$ echo 中村 山田 田代 上田 | sed 's/[^ ][^ 田]//g'
山田 上田
$ echo 中村 山田 田代 上田 | tr ' ' '\n' | grep '田＄'
山田
上田

                          ※　$ echo abc | tr ac bq
                                bbq
                             ⇒　tr 文字1　文字2　　
                             　　文字1を文字2に置き換える


 ## 練習　1.3.d

$ seq 5 | awk '/[24]/'
2
4

$ seq 5 | awk '$1%2==0'
2
4

$ seq 5 | awk '$1%2==0{printf("%s 偶数\n",$1)}'
2 偶数
4 偶数
　　　　　　　　　　　　※　\n  改行
            　　　　　　　　%s  文字列
                    　　　

$ seq 5 | awk '$1%2==0{print $1"偶数"}$1%2{print $1,"奇数"}'
1 奇数
2 偶数
3 奇数
4 偶数
5 奇数


　　　　　　　　　　　　※　条件:　パターン
            　　　　　　　処理:　アクション
                   　　　非ゼロの値:　真


$ seq 5 | awk 'BEGIN{a=0}$1%2==0{print $1,"偶数"}$1%2{print $1,"奇数"}{a+=$1}END{print"合計",a}'
1 奇数
2 偶数
3 奇数
4 偶数
5 奇数
合計 15

　　　　　　　　　　　　　※　BEGINパターン:  awkが1行目の処理を始める前
             　　　　　　　　ENDパターン:　awkが最終行の処理を終えた後
                           {a+=$1}  →　数字をaに足し込む処理
                


 
