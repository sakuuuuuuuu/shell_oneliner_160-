  ## 練習1.3.e

  $ seq 5 | ワンライナー
  奇数　5
  偶数　2


$ seq 5 | awk '{print $1%2 ? "奇数":"偶数"}’ 
奇数
偶数
奇数
偶数
奇数

$ seq 5 | awk '{print $1%2 ? "奇数":"偶数"}’ | sort 
奇数
奇数
奇数
偶数
偶数

$ seq 5 | awk '{print $1%2 ? "奇数":"偶数"}’ | sort | uniq -c
　　　3奇数
   　 2偶数

$ seq 5 | awk '{print $1%2 ? "奇数":"偶数"}’ | sort | uniq -c| awk '{print $1,$1}
奇数 3
偶数 2

## 練習1.3.f

$ seq 4 | xargs mkdir
$ seq 4 | xargs rmdir
$ mkdir 1 3
$ seq 4 | xargs -n2 mv
$ seq 4 |xargs -I@ mkdir dir_@

$ ls -d dir_*
dir_1 dir_2 dir_3
