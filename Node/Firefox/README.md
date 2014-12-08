```
$ docker run -d --link selenium-hub:hub pihizi/selenium-node-firefox
```

```
$ docker run -d \
        --name selenium-node-firefox \
        --env "HUB_PORT_4444_TCP_ADDR=ip.ip.ip.ip" \
        --env "HUB_PORT_4444_TCP_PORT=port" \
        pihizi/selenium-node-firefox
```

