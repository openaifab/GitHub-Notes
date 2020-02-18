# Some notes for GitHub
### 創建新的Git檔案夾並與GitHub同步
開始一個專案時，先在專案資料夾內創一個.gitignore檔案，此檔案會設定不和GitHub同步的檔案。  
```
cd ~/django_projects (folder for projects)
nano .gitignore
```
在.gitignore輸入不想同步的檔案名稱，以下為範例。  
```
__pycache__
*.swp
*.sqlite3
```
在專案資料夾下~/"project folder"，執行以下的指令。
```
git init #起始此資料夾為一個git資料夾
git config --global push.default simple #設定，每台電腦第一次設定就好
git add * #把此資料夾所有的東西都傳到預備上傳區
git add .gitignore #把.gitignote也放到預備上傳區，此檔案一般不會跟著上傳
git status #查看現在的狀態
git config --global user.email "youremail@abcd.com" #設定，每台電腦第一次設定就好
git config --global user.name "Your Name" #設定，每台電腦第一次設定就好
git config --global credential.helper cache   # Optional but convienent #設定，每台電腦第一次設定就好
git config --global credential.helper 'cache --timeout=604800'  # Optional but convienent #設定，每台電腦第一次設定就好
git commit -m "first commit" #此次上傳的附註
git remote add origin https://github.com/--your-github-acct--/django_projects.git #連到GitHub上的指定路徑
git push -u origin master #把檔案上傳到gitHub
(enter id and password for git) #若是第一次需要輸入帳號密碼
```
### 更新GitHub上的資料夾
目前的資料夾若有變更且想更新到GitHub上。      
```
git status #確認狀態
git add * #把所有變更的檔案都放到預備上傳區
git commit -a -m "Skeleton tutorial complete" #此次上傳的附註
git push #把檔案上傳到gitHub
```

### 一些參考指令
確認目前資料夾和GitHub上的相差狀態。    
```
git status
git diff
```

### 當你要上傳到其他GitHub帳號時
當自己的電腦已設定好自己的GitHub帳號後，若想傳檔案到其他的GitHub帳號時，需要做以下設定。  
```
cd .git/ #在專案資料夾內切換目錄到.git/
nano config #在.git/資料夾內編輯config
```
在config檔案裡，做以下變更。("git的用戶名"指的都不是你的GitHub帳號)  
```
把以下的url
[remote "origin"]
url = https://github.com/git的用戶名/項目名稱
改寫成以下的url
url = https://git的用戶名@github.com/git的用戶名/項目名稱
```
# References
[1] https://www.dj4e.com/assn/dj4e_github.md  
