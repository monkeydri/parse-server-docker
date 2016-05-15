#parse-server docker

## parse-server architecture with docker containers

![Parse Server Diagram](https://github.com/yongjhih/docker-parse-server/raw/master/art/parse-server-diagram.png)

- parse-server docker + mongodb docker (optionaly with rocksDB storage engine)
- parse-cloudCode

- parse-dashboard to manage one or multiple parse-server instances

## Features:

* Support docker stack with docker-compose
* Support parse-cloud-code volume
* Support parse-dashboard
* Support mongodb with rocksDB storage engine
* Support git deploy parse-cloud-code and auto effect after pushed
* Tested docker image
* LiveQuery support




## run parse-server + mongodb with docker-compose:

```sh
$ wget https://github.com/monkeydri/docker-parse-server/raw/master/docker-compose.yml
$ APP_ID=myAppId MASTER_KEY=myMasterKey docker-compose up -d
```


## run parse-dashboard with docker-compose:


## Configuration with docker-compose.yml

Environment:

```yml
# ...
parse-server:
  # ...
  environment:
    DATABASE_URI: $DATABASE_URI
    APP_ID: $APP_ID
    MASTER_KEY: $MASTER_KEY
    PARSE_MOUNT: $PARSE_MOUNT # /parse
    COLLECTION_PREFIX: $COLLECTION_PREFIX
    CLIENT_KEY: $CLIENT_KEY
    REST_API_KEY: $REST_API_KEY
    DOTNET_KEY: $DOTNET_KEY
    JAVASCRIPT_KEY: $JAVASCRIPT_KEY
    DOTNET_KEY: $DOTNET_KEY
    FILE_KEY: $FILE_KEY
    FACEBOOK_APP_IDS: $FACEBOOK_APP_IDS
    SERVER_URL: $SERVER_URL
    MAX_UPLOAD_SIZE: $MAX_UPLOAD_SIZE # 20mb
    GCM_ID: $GCM_ID
    GCM_KEY: $GCM_KEY
    PRODUCTION_PFX: $PRODUCTION_PFX
    PRODUCTION_BUNDLE_ID: $PRODUCTION_BUNDLE_ID
    PRODUCTION_CERT: $PRODUCTION_CERT # prodCert.pem
    PRODUCTION_KEY: $PRODUCTION_KEY # prodKey.pem
    DEV_PFX: $DEV_PFX
    DEV_BUNDLE_ID: $DEV_BUNDLE_ID
    DEV_CERT: $DEV_CERT # devCert.pem
    DEV_KEY: $DEV_KEY # devKey.pem
    VERIFY_USER_EMAILS: $VERIFY_USER_EMAILS # false
    ENABLE_ANON_USERS: $ENABLE_ANON_USERS # true
    ALLOW_CLIENT_CLASS_CREATION: $ALLOW_CLIENT_CLASS_CREATION # true
    APP_NAME: $APP_NAME
    PUBLIC_SERVER_URL: $PUBLIC_SERVER_URL
    TRUST_PROXY: $TRUST_PROXY # false
# ...
```


## See Also

* https://github.com/ParsePlatform/parse-server
* http://blog.parse.com/announcements/introducing-parse-server-and-the-database-migration-tool/
* https://parse.com/docs/server/guide#migrating
* https://hub.docker.com/r/monkeydri/parse-server/
* https://github.com/yongjhih/parse-cloud-code
* https://hub.docker.com/r/yongjhih/parse-cloud-code/
* https://medium.com/cowbear-coder/migration-of-parse-server-with-docker-part1-87034cc29978
* https://github.com/monkeydri/parse-dashboard-dashboard
