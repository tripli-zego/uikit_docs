To log in to a room, call the [`loginRoom`](https://www.zegocloud.com/article/api?doc=Express_Video_SDK_API~Java_android~class~im-zego-zegoexpress-zego-express-engine#login-room) method. If the roomID does not exist, a new room will be created and you will log in automatically when you call the `loginRoom` method.

```java
/** create a user */
ZegoUser user = new ZegoUser("user1");


ZegoRoomConfig roomConfig = new ZegoRoomConfig();
/** Token is generated by the user's own server. For an easier and convenient debugging, you can get a temporary token from the ZEGOCLOUD Admin Console */
roomConfig.token = "xxxx";
/** onRoomUserUpdate callback can be received only by passing in a ZegoRoomConfig whose "isUserStatusNotify" parameter value is "true".*/
roomConfig.isUserStatusNotify = true;

/** log in to a room */
engine.loginRoom("room1", user, roomConfig, (int error, JSONObject extendedData)->{
    // (Optional callback) The result of logging in to the room. If you only pay attention to the login result, you can use this callback.
});  
```








