# rasa_x_install

## rasa x 安裝方式
參考 [Docker Compose Manual Install](https://rasa.com/docs/rasa-x/installation-and-setup/install/docker-compose#docker-compose-manual-install) 的步驟安裝

## 注意事項
* 要先裝 docker & docker-compose
* 下載 [docker-compose.yml](https://storage.googleapis.com/rasa-x-releases/0.32.2/docker-compose.ce.yml) (version: 0.32.2)
* Terms agree.txt 的內容 "${USER} ${date}"
* DB data Permissions 特別注意, linux & windows 設定方式不一樣 (refs: [Postgres Database Storage](https://rasa.com/docs/rasa-x/installation-and-setup/install/docker-compose#postgres-database-storage))
* DB container 啟動的時候帶入的密碼設定沒有生效(可能是 image 問題?), 先不設定密碼來解 `ALLOW_EMPTY_PASSWORD: "yes"`
* 設定 rasa x 預設密碼的方式
    1. 進到 rasa-x container shell
    2. `python /app/scripts/manage_users.py create --update <username> <password> <role>`
        `python /app/scripts/manage_users.py create --update me mypassword123 admin`

        role : 'admin', 'annotator', 'tester'
* rasa-x url : http://localhost 
