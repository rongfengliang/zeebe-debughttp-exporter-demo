# zeebe with http debug config

> with prometheus integration

## how to running

* build

```code
docker-compose up -d
```

* start 

```code
docker-compose up -d
```

* deploy flow
> mac tools

```code
./zbctl.darwin --insecure --address 127.0.0.1:27500 deploy flow.bpmn
```
* create instance
> mac tools

```code
./zbctl.darwin --insecure --address 127.0.0.1:27500 create instance demoProcess
```

* run test shell

```code
sh app.sh
```
* view debug page

open http://localhost:8000

