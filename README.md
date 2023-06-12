# MealMaven

## 將專案從GitHub `clone`到本機端
https://github.com/HeimdallrTW/MealMaven<br/>
可以直接在想要存放專案的位置打開`cmd`輸入<br/>
- `SSH`
```shell
git clone git@github.com:HeimdallrTW/MealMaven.git
```
- `Https`
```shell
git clone https://github.com/HeimdallrTW/MealMaven.git
```

## 專案導入
1. 開啟`Eclpise`導入專案<br/>
![Alt text](https://imgur.com/abQuf2g.jpg)
2. 導入已存在的`Maven`專案<br/>
![Alt text](https://imgur.com/mXc6ujI.jpg)<br/>
![Alt text](https://imgur.com/Hc8p0Dk.jpg)<br/>
![Alt text](https://imgur.com/JV4Ifij.jpg)<br/>

## application properties 設定
修改`Spring Boot`設定檔，挑選一種檔案作為設定。<br/>
檔案路徑為：<br/>
`src/main/resources/`
- `application.properties`
```properties
# context-path
# server.servlet.context-path=/my-app

## port
server.port=8080

## jsp config
spring.mvc.view.prefix=/WEB-INF/jsp/
spring.mvc.view.suffix=.jsp

# open put and delete request
spring.mvc.hiddenmethod.filter.enabled=true

# Datasourse Config
spring.datasource.driver-class-name=com.microsoft.sqlserver.jdbc.SQLServerDriver
spring.datasource.url=jdbc:sqlserver://localhost:1433;databaseName=<database-name>;trustServerCertificate=true
spring.datasource.username=username
spring.datasource.password=password

# Hibernate (JPA) Config
spring.jpa.properties.hibernate.dialect=org.hibernate.dialect.SQLServer<yyyy>Dialect
spring.jpa.show-sql=true
spring.jpa.properties.hibernate.format_sql=true

# practice only
# spring.jpa.hibernate.ddl-auto=update

# Naming Config easy
spring.jpa.hibernate.naming.physical-strategy=org.hibernate.boot.model.naming.PhysicalNamingStrategyStandardImpl
```
- `application.yml`
```yml
# context-path
# server:
#     servlet:
#         context-path: /my-app

# server port
server:
    port: 8080

# jsp config
spring:
    mvc:
        view:
            prefix: /WEB-INF/jsp/
            suffix: .jsp
        hiddenmethod:
            filter:
                enabled: true
    # Datasourse Config
    datasource:
        driver-class-name: com.microsoft.sqlserver.jdbc.SQLServerDriver
        url: jdbc:sqlserver://localhost:1433;databaseName=<database-name>;trustServerCertificate=true
        username: username
        password: password
    # Hibernate (JPA) Config
    jpa:
        properties:
            hibernate:
                dialect: org.hibernate.dialect.SQLServerDialect
                format_sql: true
        show-sql: true
        hibernate:
            naming:
                physical-strategy: org.hibernate.boot.model.naming.PhysicalNamingStrategyStandardImpl
```

## `git` 版本控制
進行開發時，先建立自己的分支後再進行程式碼撰寫。<br/>
可以由以下指令在`cmd`建立新分支並查看。

> `git checkout -b <branch name>`

其中`branch name`是自行定義的分支名稱。<br/><br/>
要切換分支可以輸入`git checkout <branch name>`。
開發中，部分程式碼可以先`commit`到自己的分支中，並且撰寫`commit`的內容。<br/>
首行為標題，空一行後為內文。可以記錄下這次`commit`中是完成哪些功能或程式段落。<br/>
`commit`後也可以先將新進度的個人分支`push`上`GitHub`。

```
git add [檔案名稱或是輸入 . 來加入所有檔案]
git commit -m "commit標題"
git commit #說明：若是沒有使用-m，會進入vim編輯器，要離開可以打[:q!]來不儲存離開。
           #如果有撰寫說明，可以使用[:wq]儲存並離開。
git push origin <branch name> # push到Github
```

待功能完成後，先測試程式功能正常後在`merge`回`main`分支，並且`push`上`Github`。<br/>
其他人可以在`pull`下來最新版本後`merge`回自己目前開發中的分支。<br/>
### Branch Name
Git分支命名以`f_[feature name]`，例如`f_login`<br/>

盡量每日都將工作進度`commit`到自己的`branch`，不用等到完成後才`commit`。

> git教學連結<br/>https://gitbook.tw/


## 專案結構
```
com
└── ispan
    └── mealmaven
        ├── Application.java
        ├── ServletInitializer.java
        │
        ├── platformsystem
        ├── restaurantsystem
        └── usersystem
```
"# MealMaven" 
