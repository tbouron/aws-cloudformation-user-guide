# AWS::GameLift::Fleet<a name="aws-resource-gamelift-fleet"></a>

The `AWS::GameLift::Fleet` resource creates an Amazon GameLift \(GameLift\) fleet to host game servers\. A fleet is a set of EC2 instances, each of which is a host in the fleet\. For more information, see the [CreateFleet](http://docs.aws.amazon.com/gamelift/latest/apireference/API_CreateFleet.html) action in the *Amazon GameLift API Reference*\.


+ [Syntax](#aws-resource-gamelift-fleet-syntax)
+ [Properties](#w3ab2c21c10d649b9)
+ [Return Value](#w3ab2c21c10d649c11)
+ [Example](#w3ab2c21c10d649c13)

## Syntax<a name="aws-resource-gamelift-fleet-syntax"></a>

To declare this entity in your AWS CloudFormation template, use the following syntax:

### JSON<a name="aws-resource-gamelift-fleet-syntax.json"></a>

```
{
  "Type" : "AWS::GameLift::Fleet",
  "Properties" : {
    "[BuildId](#cfn-gamelift-fleet-buildid)" : String,
    "[Description](#cfn-gamelift-fleet-description)" : String,
    "[DesiredEC2Instances](#cfn-gamelift-fleet-desiredec2instances)" : Integer,
    "[EC2InboundPermissions](#cfn-gamelift-fleet-ec2inboundpermissions)" : [ [EC2InboundPermission](aws-properties-gamelift-fleet-ec2inboundpermission.md), ... ],
    "[EC2InstanceType](#cfn-gamelift-fleet-ec2instancetype)" : String,
    "[LogPaths](#cfn-gamelift-fleet-logpaths)" : [ String, ... ],
    "[MaxSize](#cfn-gamelift-fleet-maxsize)" : Integer,
    "[MinSize](#cfn-gamelift-fleet-minsize)" : Integer,
    "[Name](#cfn-gamelift-fleet-name)" : String,
    "[ServerLaunchParameters](#cfn-gamelift-fleet-serverlaunchparameters)" : String,
    "[ServerLaunchPath](#cfn-gamelift-fleet-serverlaunchpath)" : String
  }
}
```

### YAML<a name="aws-resource-gamelift-fleet-syntax.yaml"></a>

```
Type: "AWS::GameLift::Fleet"
Properties: 
  [BuildId](#cfn-gamelift-fleet-buildid): String
  [Description](#cfn-gamelift-fleet-description): String
  [DesiredEC2Instances](#cfn-gamelift-fleet-desiredec2instances): Integer
  [EC2InboundPermissions](#cfn-gamelift-fleet-ec2inboundpermissions):
    - [EC2InboundPermission](aws-properties-gamelift-fleet-ec2inboundpermission.md)
  [EC2InstanceType](#cfn-gamelift-fleet-ec2instancetype): String
  [LogPaths](#cfn-gamelift-fleet-logpaths):
    [ String, ... ]
  [MaxSize](#cfn-gamelift-fleet-maxsize): Integer
  [MinSize](#cfn-gamelift-fleet-minsize): Integer
  [Name](#cfn-gamelift-fleet-name): String
  [ServerLaunchParameters](#cfn-gamelift-fleet-serverlaunchparameters): String
  [ServerLaunchPath](#cfn-gamelift-fleet-serverlaunchpath): String
```

## Properties<a name="w3ab2c21c10d649b9"></a>

`BuildId`  <a name="cfn-gamelift-fleet-buildid"></a>
The unique identifier for the build that you want to use with this fleet\.  
*Required: *Yes  
*Type*: String  
*Update requires*: [Replacement](using-cfn-updating-stacks-update-behaviors.md#update-replacement)

`Description`  <a name="cfn-gamelift-fleet-description"></a>
Information that helps you identify the purpose of this fleet\.  
*Required: *No  
*Type*: String  
*Update requires*: [No interruption](using-cfn-updating-stacks-update-behaviors.md#update-no-interrupt)

`DesiredEC2Instances`  <a name="cfn-gamelift-fleet-desiredec2instances"></a>
The number of EC2 instances that you want in this fleet\.  
*Required: *Yes  
*Type*: Integer  
*Update requires*: [No interruption](using-cfn-updating-stacks-update-behaviors.md#update-no-interrupt)

`EC2InboundPermissions`  <a name="cfn-gamelift-fleet-ec2inboundpermissions"></a>
The incoming traffic, expressed as IP ranges and port numbers, that is permitted to access the game server\. If you don't specify values, no traffic is permitted to your game servers\.  
*Required: *No  
*Type*: List of [Amazon GameLift Fleet EC2InboundPermission](aws-properties-gamelift-fleet-ec2inboundpermission.md)  
*Update requires*: [No interruption](using-cfn-updating-stacks-update-behaviors.md#update-no-interrupt)

`EC2InstanceType`  <a name="cfn-gamelift-fleet-ec2instancetype"></a>
The type of EC2 instances that the fleet uses\. EC2 instance types define the CPU, memory, storage, and networking capacity of the fleet's hosts\. For more information about the instance types that are supported by GameLift, see the [EC2InstanceType](http://docs.aws.amazon.com/gamelift/latest/apireference/API_CreateFleet.html#gamelift-CreateFleet-request-EC2InstanceType) parameter in the *Amazon GameLift API Reference*\.  
*Required: *Yes  
*Type*: String  
*Update requires*: [Replacement](using-cfn-updating-stacks-update-behaviors.md#update-replacement)

`LogPaths`  <a name="cfn-gamelift-fleet-logpaths"></a>
The path to game\-session log files that are generated by your game server, with the slashes \(`\`\) escaped\. After a game session has been terminated, GameLift captures and stores the logs in an S3 bucket\.  
*Required: *No  
*Type*: List of String values  
*Update requires*: [Replacement](using-cfn-updating-stacks-update-behaviors.md#update-replacement)

`MaxSize`  <a name="cfn-gamelift-fleet-maxsize"></a>
The maximum number of EC2 instances that you want to allow in this fleet\. By default, AWS CloudFormation, sets this property to `1`\.  
*Required: *No  
*Type*: Integer  
*Update requires*: [No interruption](using-cfn-updating-stacks-update-behaviors.md#update-no-interrupt)

`MinSize`  <a name="cfn-gamelift-fleet-minsize"></a>
The minimum number of EC2 instances that you want to allow in this fleet\. By default, AWS CloudFormation, sets this property to `0`\.  
*Required: *No  
*Type*: Integer  
*Update requires*: [No interruption](using-cfn-updating-stacks-update-behaviors.md#update-no-interrupt)

`Name`  <a name="cfn-gamelift-fleet-name"></a>
An identifier to associate with this fleet\. Fleet names don't need to be unique\.  
*Required: *Yes  
*Type*: String  
*Update requires*: [No interruption](using-cfn-updating-stacks-update-behaviors.md#update-no-interrupt)

`ServerLaunchParameters`  <a name="cfn-gamelift-fleet-serverlaunchparameters"></a>
The parameters that are required to launch your game server\. Specify these parameters as a string of command\-line parameters, such as `+sv_port 33435 +start_lobby`\.  
*Required: *No  
*Type*: String  
*Update requires*: [Replacement](using-cfn-updating-stacks-update-behaviors.md#update-replacement)

`ServerLaunchPath`  <a name="cfn-gamelift-fleet-serverlaunchpath"></a>
The location of your game server that GameLift launches\. You must escape the slashes \(`\`\) and use the following pattern: `C:\\game\\launchpath`\. For example, if your game server files are in the `MyGame` folder, the path should be `C:\\game\\MyGame\\server.exe`\.  
*Required: *Yes  
*Type*: String  
*Update requires*: [Replacement](using-cfn-updating-stacks-update-behaviors.md#update-replacement)

## Return Value<a name="w3ab2c21c10d649c11"></a>

### Ref<a name="w3ab2c21c10d649c11b2"></a>

When the logical ID of this resource is provided to the `Ref` intrinsic function, `Ref` returns the fleet ID, such as `myfleet-a01234b56-7890-1de2-f345-g67h8i901j2k`\.

For more information about using the `Ref` function, see [Ref](intrinsic-function-reference-ref.md)\.

## Example<a name="w3ab2c21c10d649c13"></a>

The following example creates a GameLift fleet named `MyGameFleet` with two inbound permissions\. The fleet uses a `Ref` intrinsic function to specify a build, which can be declared elsewhere in the same template\. For the log path and server launch path, the example uses the escape character \(`\`\) to escape the slashes \(`\`\)\.

### JSON<a name="aws-resource-gamelift-fleet-example.json"></a>

```
"FleetResource": {
  "Type": "AWS::GameLift::Fleet",
  "Properties": {
    "Name": "MyGameFleet",
    "Description": "A fleet for my game",
    "BuildId": { "Ref": "BuildResource" },
    "ServerLaunchPath": "c:\\game\\TestApplicationServer.exe",
    "LogPaths": [
      "c:\\game\\testlog.log",
      "c:\\game\\testlog2.log"
    ],
    "EC2InstanceType": "t2.small",
    "DesiredEC2Instances": "2",
    "EC2InboundPermissions": [
      {
        "FromPort": "1234",
        "ToPort": "1324",
        "IpRange": "0.0.0.0/24",
        "Protocol": "TCP"
      },
      {
        "FromPort": "1356",
        "ToPort": "1578",
        "IpRange": "192.168.0.0/24",
        "Protocol": "UDP"
      }
    ]
  } 
}
```

### YAML<a name="aws-resource-gamelift-fleet-example.yaml"></a>

```
FleetResource: 
  Type: "AWS::GameLift::Fleet"
  Properties: 
    Name: "MyGameFleet"
    Description: "A fleet for my game"
    BuildId: 
      Ref: "BuildResource"
    ServerLaunchPath: "c:\\game\\TestApplicationServer.exe"
    LogPaths: 
      - "c:\\game\\testlog.log"
      - "c:\\game\\testlog2.log"
    EC2InstanceType: "t2.small"
    DesiredEC2Instances: "2"
    EC2InboundPermissions: 
      - 
        FromPort: "1234"
        ToPort: "1324"
        IpRange: "0.0.0.0/24"
        Protocol: "TCP"
      - 
        FromPort: "1356"
        ToPort: "1578"
        IpRange: "192.168.0.0/24"
        Protocol: "UDP"
```