# Your Plugin Name

nativescript-aws-dynamo

This plugin is limited edition  to use AWS DynamoDB services.
if you want to buy full edition or other AWS services plugins then you can touch us with this url.
www.cerensoftware.co.uk

## (Optional) Prerequisites / Requirements

if you get keychain error in iOS
you have to install [nativescript-custom-entitlements](https://github.com/Essent/nativescript-custom-entitlements) plugin to your project.
you add this lines to app.entitlements file.


```xml
<dict>
    <key>keychain-access-groups</key>
    <array>
        <string>$(AppIdentifierPrefix)org.nativescript.yourprojectname</string>
    </array>
</dict>
```


## Installation

```javascript
tns plugin add nativescript-aws-cognito
```

## Usage 


	
	```javascript
    import { AwsDynamo, DynamoCommonDelegate } from 'nativescript-aws-dynamo';
    ```)

	```javascript
    this.awsDynamo = new AwsDynamo();
    this.awsDynamo.initDdb("AWSRegionUSEast2", "us-east-2:77218a3c-b958-41qw-bf14-984d54adba56");
    ```)

	```javascript
     this.awsDynamo.putItem("Books", [{ key: "ISBN", value: { data: "8", type: "S" } },
    { key: "Author", value: { data: "ali4", type: "S" } },
    { key: "Title", value: { data: "deneme4", type: "S" } },
    { key: "list1", value: { type: "L", data: [{ data: "list1", type: "S" }, { data: "3", type: "N" }] } },
    { key: "boolen", value: { type: "BO", data: true } },
    { key: "set1", value: { type: "SS", data: ["set1", "set2"] } }
    ], this);
    ```)


	```javascript
     this.awsDynamo.getItem("Books",[{"key":"ISBN","value":{data:"10", type:"S"}}], this);
    ```)

	```javascript
     this.awsDynamo.deleteItem("Books",[{"key":"ISBN","value":{data:"4", type:"S"}}], this);
    ```)


	```javascript
     this.awsDynamo.updateItem("Books",[{"key":"ISBN","value":{data:"3", type:"S"}}], [{key:"set2", value:{type:"SS", data:["set1","set2"]},"action":"PUT"}] , this);
    ```)

## API

This plugin uses ObjectiveC AWS SDk and Java AWS Sdk.
    
## License

Apache License Version 2.0, January 2004
