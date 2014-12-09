dockerfile-selenium
===================

采用Selenium的Grid和WebDriver架设测试服务器

### 启动`selenium-hub`

```
docker run --name selenium-hub \
    -p 4444:4444 \
    -d pihizi/selenium-hub:2.44.0
```

### 启动`selenium-node-chrome`浏览器服务器

```
docker run -d \
           --name selenium-node-chrome \
           --env "HUB_PORT_4444_TCP_ADDR=ip.ip.ip.ip" \
           --env "HUB_PORT_4444_TCP_PORT=port" \
           pihizi/selenium-node-chrome
```

### 启动`seleniu-node-firefox`浏览器服务器

```
docker run -d \
           --name selenium-node-firefox \
           --env "HUB_PORT_4444_TCP_ADDR=ip.ip.ip.ip" \
           --env "HUB_PORT_4444_TCP_PORT=port" \
           pihizi/selenium-node-firefox
```

### [可选] 在其他电脑直接运行命令，将该电脑的浏览器注册到`selenium-hub`

```
java -jar selenium-server-standalone-2.44.0.jar \
    -role webdriver \
    -browser "browserName=macfirefox /Applications/Firefox.app/Contents/MacOS/firefox,maxinstance=1" \
    -hubHost ip.ip.ip.ip \
    -port port

```
