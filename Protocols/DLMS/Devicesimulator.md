### 5.2.1 DLMS device simulator

The library that is used to connect to DLMS devices contains functionality to build a simulator for a device. The library offers the following core functionality.

- zero or more servers can be started on a host (different ports)
- zero or more logical devices can be registered with a server (different device id)
- zero or more annotated objects can be registered with a logical device
- these objects define available dlms classes, ObisCodes, attributeIds and methods for the device and can contain any logic
- authentication and encryption are supported

If you want to simulate a certain device you will prepare annotated classes and register instances of these with a logical device. Because you create plain Java you can make use of all functionality Java offers, for example databases. To try and make the simulation more realistic you may build in connection timeouts etc.

#### Usage

For each combination of a cosem class and obiscode you create a java class that you annotate with @CosemClass(id = ..., obis = "x.x.x.x.x.255")

In these java classes you can add fields of type DataObject that you annotate with @CosemAttribute(id = ..., type = Type.x)

Also you can create getXXX and setXXX methods to intercept getting and setting data on a logical device. XXX will be the name of the corresponding field starting with a capital letter.

For example:

```
@CosemClass(id = 3, obis = "1.0.1.8.0.255")
public class ImportValue {

    @CosemAttribute(id = 2, type = Type.DOUBLE_LONG_UNSIGNED)
    private DataObject d1 = DataObject.newUInteger32Data(10001);

    @CosemAttribute(id = 3, type = Type.STRUCTURE)
    private DataObject d2 = DataObject.newStructureData(DataObject.newInteger8Data((byte) -2),
            DataObject.newInteger8Data((byte) 30));
            
    public void setD1(DataObject newData) throws IllegalAttributeAccessException {
      // ....
    }
    public DataObject getD1() throws IllegalAttributeAccessException {
      return d1;
    }
}
```

The value of the field will be the response to get(AttributeAddress...) that is fired from osgp CommandExecutors. NOTE that these values can also be set! For example using the ClientConsole.

You can also annotate methods with or without a DataObject return value and with or without a DataObject parameter: @CosemMethod(id = ..., consumes = Type.x)

For example:

```
    @CosemMethod(id = 1)
    public void hello() throws IllegalMethodAccessException {
        System.out.println("Has been called");
        return;
    }

    @CosemMethod(id = 2, consumes = Type.OCTET_STRING)
    public DataObject hello2(DataObject datO) throws IllegalMethodAccessException {
        throw new IllegalMethodAccessException(MethodResultCode.OTHER_REASON);
    }

```
Such a method will be called when osgp fires ClientConnection.action, the DataObject that may be returned will become available in osgp on the MethodResult object.

####Per command design
The way to implement request/response for a command in the simulator is as follows.
- create a separate package per command
- create a java class for each combination of classid and obiscode
- in this class implement the attribute id's and the methods that will be requested as explained above
