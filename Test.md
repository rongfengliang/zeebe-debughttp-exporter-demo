## steps

* deploy workflow

```code
./zbctl.darwin --insecure --address 127.0.0.1:27500  deploy order-process.bpmn
```

* create instance

```code
./zbctl.darwin --insecure --address 127.0.0.1:27500 create instance order-process --variables '{"orderId": "1234", "orderValue":99}'
./zbctl.darwin --insecure create instance order-process --variables '{"orderId": "2345", "orderValue":100}'
```
* create worker

```code
./zbctl.darwin --insecure --address 127.0.0.1:27500 create worker initiate-payment --handler cat
```
* publish message

```code
./zbctl.darwin --insecure publish message "payment-received" --correlationKey="1234"
./zbctl.darwin --insecure publish message "payment-received" --correlationKey="2345"
```

* end worker

```code
./zbctl.darwin --insecure create worker ship-without-insurance --handler cat
./zbctl.darwin --insecure create worker ship-with-insurance --handler cat
```