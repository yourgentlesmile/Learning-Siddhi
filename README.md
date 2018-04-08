# Install Siddhi

## run siddhi with git
You can choose two different way to install and run you siddhi application

* Get WSO2 Stream Processor -> [Download it](https://wso2.com/analytics)
* Using siddhi-plugin-idea -> [Download it](http://plugins.jetbrains.com/plugin/10212-siddhi)

Tips:

* 如果你使用WSO2 Stream Processor进行siddhi开发，如果要使用mysql，kafka这类io扩展性功能时，你需要自主下载jar包，并进行jar包转换,详情如下
* - Convert and copy the Kafka client jars from the `/libs` directory to the /libs directory as follows. - `Create a directory (SOURCE_DIRECTORY) `in a preferred location in your machine and copy the following JARs to it from the `/libs` directory. `kafka_2.11-0.9.0.1.jar`  `kafka-clients-0.9.0.1.jar``metrics-core-2.2.0.jar`  `scala-library-2.11.7.jar`  `scala-parser-combinators_2.11-1.0.4.jar`  `zkclient-0.7.jar` `zookeeper-3.4.6.jar`Create another directory (DESTINATION_DIRECTORY) in a preferred location in your machine. - To convert all the Kafka jars you copied into the , issue the following command. For Windows: `/bin/jartobundle.bat` For Linux: /bin/jartobundle.sh - Copy the converted files from the to the /libs directory.
* 如果你是用的siddhi-sdk，则所有的依赖项都已经包含在了libs文件夹中，因此推荐使用siddhi-sdk

# Siddhi 基本注解
## @source
此注解表示数据的来源，目前数据来源可以有一下几种：
> * HTTP
> * Kafka
> * TCP
> * In-memory
> * WSO2Event
> * Email
> * JMS
> * File
> * RabbitMQ
> * MQTT
> * WebSocket
不同的数据来源在source标签中有着不同的属性配置
### source Mapper
在source标签中使用@map标签可以将数据转换成预期的数据格式，目前支持转换成如下几种：
> * WSO2Event
> * XML
> * TEXT
> * JSON
> * Binary
> * Key Value
> * CSV
## @sink
此注解表示数据的去向，目前有如下几种数据的去向选择：
> * HTTP
> * Kafka
> * TCP
> * In-memory
> * WSO2Event
> * Email
> * JMS
> * File
> * RabbitMQ
> * MQTT
> * WebSocket

@sink标签依然可以使用map标签进行内容的格式化输
