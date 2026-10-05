# 第2回 Webエンジニアリング演習 レポート
## 学籍番号
4724214
## コンフリクトが発生した理由
README.mdの同じ個所を異なるブランチで編集し、mainに取り込もうとしたらmainブランチがどっちを取り込んでいいかわからず、
コンフリクトが発生した。
## 履歴
```
@4724214 ➜ /workspaces/web_eng_report (main) $ git log --oneline --graph --all
* 5630df5 (HEAD -> main, origin/main, origin/HEAD) Fix README banner
*   d6a91a5 Merge pull request #3 from 4724214/plactice/conflict-b
|\  
| *   46e720c (origin/plactice/conflict-b, plactice/conflict-b) Merge branch 'main' into plactice/conflict-b
| |\  
| |/  
|/|   
* |   f894b24 Merge pull request #2 from 4724214/plactice/conflict-a
|\ \  
| * | 17b3c06 (origin/plactice/conflict-a, plactice/conflict-a) Update README
* | | 880960a Merge pull request #1 from 4724214/feature/add-readme
|\| | 
| | * fddb09b Update README
| |/  
| * 25d9286 (origin/feature/add-readme, feature/add-readme) Add README
|/  
* cbda851 Add(Report/REPORT_01.md)
* 35126f1 Add index.html
* 6a851ca Create devcontainer.json
```