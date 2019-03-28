## git branch改名的處理方式（包括本地與遠端同步）

我們知道在專案中第一次push到遠端時候可以加入 --set-upstream / -u 讓git追蹤這個分支

`git push -u origin master`

之後要push就不必再加後面的參數

直接下`git push`
即可

那麼如果今天我們需要修改現有分支的名稱，該怎麼做呢？( github是不支援直接在網站上修改的 )

因此我們先刪除要改名的分支，在重新建立一個分支

# 1.刪除遠端分支

```
git remote <REMOTE_REPOSITORY> <SOURCE_BRANCH_NAME>:<DESTINY_BRANCH_NAME>
git remote origin :old_branch
```
*<SOURCE_BRANCH_NAME>:<DESTINY_BRANCH_NAME>意思是將本地的SOURCE_BRANCH_NAME推到遠端的DESTINY_BRANCH_NAME

如果SOURCE_BRANCH_NAME在遠端分支中找不到的話就以SOURCE_BRANCH_NAME為分支名稱推到遠端的DESTINY_BRANCH_NAME

利用這個特性我們可以把SOURCE_BRANCH_NAME留空

那麼git就會將空白的名字推到遠端的DESTINY_BRANCH_NAME

也就是刪除掉這個分支

ref: [https://git-scm.com/docs/git-push#OPTIONS](https://git-scm.com/docs/git-push#OPTIONS)

## 1.2刪除本地分支

```
git branch -d branch_to_delete
```
指令會把 **已經完成合併的分支** 刪除，如果該分支有尚未合併的工作則會報錯
```
error: The branch 'branch_to_delete' is not fully merged.
If you are sure you want to delete it, run 'git branch -D branch_to_delete'.
```
因此這邊分成兩個狀況：該分支是否完成合併，可以下`git branch --no-merged`來檢查尚未完成合併的分支，
最後從錯誤訊息可以知道這裡也有強制的選項，也就是`-D`，如果真的確定不需要這些動作就可以直接強制刪除分支

# 2.建立本地分支

`git branch -m new_branch`

這個就沒什麼特別就是把當前branch名稱改為new_branch

另外這個建立完後不會移動分支

必須下`git checkout new_branch`才會移動至新分支

要直接在建立完之後移動至該分支的話可以下`git checkout -b new_branch`

# 3.將新分支重新推到遠端

`git push origin -u new_branch`

記住這邊一樣要使用第一次push用的指令組合

這樣git才會更新refs

否則直接下`git push`會看到`fatal: The upstream branch of your current branch does not match
the name of your current branch.`

可以下`git branch -vv`或是`git show-ref`查看目前分支設定

## 記錄一下git add指令說明

`git add directory_or_file`

會將選定的目錄或檔案加進提交暫存區(stage)

加進去後才可下`git commit`提交修改

directory_or_file可以是當前目錄`git add .`

或者是特定子目錄`git add path/to/dir/.`
