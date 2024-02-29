サブモジュールなので、これでリポジトリからダウンロードする。
git clone --recurse-submodules https://github.com/hackathon2024winter/narra-belle

AWS にデプロイした場合、awskit_replace_these_files のファイルを置き換えること。
docker-compose.yml から MySQL コンテナが消えている。

.env の MYSQL_HOST をこんな感じの RDS id に置き換えること。
MYSQL_HOST=aws-and-infra-rdsa.c8ugutxhhe7a.ap-northeast-1.rds.amazonaws.com

.env のデータベース関連の定数は RDS のデプロイに使用したユーザー名とパスワードと一致させること。

git submodule foreach "git pull orgin develop"

submodule を備える GitHub リポジトリの develop ブランチを更新する場合

1.  todo_front ディレクトリを選択
2.  git checkout develop
3.  git pull origin develop
4.  todo_back ディレクトリを選択
5.  git checkout develop
6.  git pull origin develop
7.  narra-belle ディレクトリを選択
8.  git checkout develop
9.  git pull origin develop
10. git submodule update --init --recursive
