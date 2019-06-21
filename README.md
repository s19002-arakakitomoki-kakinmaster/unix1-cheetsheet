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
<<<<<<< HEAD
>>>>>>> bbe57d288848acad436cfc41b49ad430ba87b574
コマンド
ln -s to from
　作成：シンボリックリンク

telnet IP
　動作：対象のサーバーに対話モードで接続する

cmd1 | cmd2
　記号：コマンド1の結果をコマンド2に渡して実行

cmd1 &
　記号：コマンド1をバックグランドで実行

cmd1 && cmd2
　記号：コマンド1実行、成功したらコマンド2も実行

cmd1 || cmd2
　記号：コマンド1実行、失敗したらコマンド2も実行

ps -ef
　表示：プロセスを一覧で示す

jobs
　表示：ジョブを一覧で示す
　　bg jobID
　　　　バックグラウンドで実行
　　fg jobID
　　　　フォアグラウンドで実行
　　kill jobID
　　　　ジョブを停止する

source file
　動作：対象ファイルを実行する。変数変更などの影響を受ける

bash file
　動作：対象ファイルを実行する。変数変更などの影響を受けない

export
　作成：環境変数を設定する
　　export -p
　　　環境変数を一覧表示する
　　export -n 変数名
　　　環境変数を消去する

wc file
　表示：テキストファイルの行数、単語数、バイト数を示す

head file
　表示：最初の10行表示

tail file
　表示：最後の10行表示

find -type d hoge
　表示：ディレクトリ検索
find -type f hoge
　ファイル検索

cmd1 > file1
　作成：cmd1の結果をfile1として出力

cmd1 >> file1
　作成：cmd1の結果をfile1に追加（なければ作る）

$1
　記号：引数の1つ目を示す

sed
　変更：文字列を置換して標準出力する
　　cat hoge.txt | sed -e 's/a/A/g' | diff - hoge.txt
　　cat hoge.txt | sed -e 's/a/A/g' > hoge.txt
　　　hoge.txtのaをAに置換。確認した後上書き

rm -r (file or dir)
　変更：対象を削除する
　　rm
　　　ファイル削除
　　rmdir
　　　ディレクトリ削除

cp -r from to
　作成：対象をコピーする

grep 'word' file
　表示：対象文字列を検索する
　　'\.'
　　　. (エスケープ)
　　'test[1-4]'
　　　test1~4
　　't[eo]st'
　　　test または tost
　　'te*st'
　　　eが0回以上繰り返し
　　'te{1,4}st'
　　　eが1回以上4回以下繰り返し
　　'my {test | task}'
　　　「my test」または「my task」　　　

=======
リポジトリ下にディレクリ(0611)を作成し、以下のスクリプトを格納
シェル内のコマンドはすべて一般ユーザで実行する
#!/bin/bash

echo $((($(date --date="2019/9/1" +'%s') - $(date +'%s'))/(60 * 60 *24)))
>>>>>>> 864b5a2871de98b65435761674ba637fa8a04c1e

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

