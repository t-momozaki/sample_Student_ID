sample_Student_IDの使い方
================

関数`sample_Student_ID`は学生の学籍番号ベクトル (`Student_ID`) と人数
(`No`, 1以上学生数以下の整数) を引数とする関数で,
学籍番号ベクトルからランダムに指定した人数分だけ学籍番号を出力します.

まずは学生番号ベクトルを用意します.

``` r
id <- 1:100
id <- ifelse(nchar(id)==1, paste0("00",id), ifelse(nchar(id)==2, paste0(0,id), as.character(id)))
Student_ID <- paste0(6324, id)
head(Student_ID)
```

    ## [1] "6324001" "6324002" "6324003" "6324004" "6324005" "6324006"

今回はサンプルとして上記のように学生番号ベクトルを用意しましたが,
下記のようにcsvファイルから読み込むことも可能です.

``` r
Student_ID <- read.csv(file='ファイル名.csv')
```

関数`sample_Student_ID`を用いた結果は以下のようになります.
今回は5人の学生を選びたいとしました (`No=5`).

``` r
random_Student_ID(Student_ID, No=5)
```

    ## [1] "6324036" "6324048" "6324052" "6324076" "6324091"
