# 下行消息

下行消息包含 **actorcloud** 对账户下设备 Publish 的消息列表，包含消息主题（仅限指定主题发送）、消息内容、发布时间、指令状态字段。

"指令状态"包含已下发/已到达状态，通过查询该状态可以确认指令是否抵达设备。


### 应用场景

- 某些应用中，业务逻辑对指令收发确认和 QoS 保证有很强依赖，需要 QoS2（准确一次送达）级别的消息，此时需要通过查询下行消息来确认指令状态以便进行后续业务；

- 用于控制指令备案记录，记录设备是否完成某些指令。


### 注意事项

- 下行消息指令状态是异步更新的，即消息下发后立即产生下发记录，此时指令状态为"已下发"，消息成功到达后（取决于网络时间）才更新为"已到达"；

- 分组下发默认没有下发回执，如需下发回执，请选择"需要回执"进行操作。

![](/assets/device_downstream.png)