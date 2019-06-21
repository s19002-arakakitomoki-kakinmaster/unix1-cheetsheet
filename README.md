# unix1-cheetsheet
<<<<<<< HEAD
=======
=======
# iiii
>>>>>>> 08597608881a1b7ee986ef29e13427b623cf407d
# test
# let's do our best
# test
# テスト頑張ろう
# kakenai
リポジトリ下にディレクリ(0611)を作成し、以下のスクリプトを格納
シェル内のコマンドはすべて一般ユーザで実行する
#!/bin/bash

echo $((($(date --date="2019/9/1" +'%s') - $(date +'%s'))/(60 * 60 *24)))

指定したディレクトリパス(サブディレクトリは含まない)の実行可能ファイルの一覧表示
但し、入力したパスがディレクトリでない場合以下のエラーメッセージを表示
入力したパス: ディレクトリではありません
060403.sh
解答
if [ -d "$1" ]; then
    #for file in $(ls "$1")
    for file in $(find $1 -maxdepth 1 -type f)
    do
        if [ -x "$file" ]; then
            echo "$file"
        fi
    done
else
    echo "$1":'ディレクトリではありません'
 fi

