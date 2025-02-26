# [Sample Demo](https://github.com/AgoraIO-Usecase/AgoraChat-UIKit-Chatroom-iOS#sample-demo)

In this project, there is a best practice demonstration project in the `Example` folder for you to build your own business capabilities.

To experience functions of the AgoraChatroomUIKit, you can scan the following QR code to try a demo.

[![SampleDemo](./Documentation/demo.png).

# [AgoraChatroomUIKit Guide](https://github.com/AgoraIO-Usecase/AgoraChat-UIKit-Chatroom-iOS#chatroomuikit-guide)

## [Introduction](https://github.com/AgoraIO-Usecase/AgoraChat-UIKit-Chatroom-iOS#introduction)

This guide presents an overview and usage examples of the AgoraChatroomUIKit framework in iOS development, and describes various components and features of this UIKit, enabling developers to have a good understanding of the UIKit and make effective use of it.

## [Table of Contents](https://github.com/AgoraIO-Usecase/AgoraChat-UIKit-Chatroom-iOS#table-of-contents)

- [Requirements](https://github.com/AgoraIO-Usecase/AgoraChat-UIKit-Chatroom-iOS#requirements)
- [Installation](https://github.com/AgoraIO-Usecase/AgoraChat-UIKit-Chatroom-iOS#installation)
- [Documentation](https://github.com/AgoraIO-Usecase/AgoraChat-UIKit-Chatroom-iOS#documentation)
- [Structure](https://github.com/AgoraIO-Usecase/AgoraChat-UIKit-Chatroom-iOS#structure)
- [Quick Start](https://github.com/AgoraIO-Usecase/AgoraChat-UIKit-Chatroom-iOS#quick-start)
- [Precautions](https://github.com/AgoraIO-Usecase/AgoraChat-UIKit-Chatroom-iOS#precautions)
- [Advanced Usage](https://github.com/AgoraIO-Usecase/AgoraChat-UIKit-Chatroom-iOS#advanced-usage)
- [Customization](https://github.com/AgoraIO-Usecase/AgoraChat-UIKit-Chatroom-iOS#customization)
- [BusinessFlowchart](https://github.com/AgoraIO-Usecase/AgoraChat-UIKit-Chatroom-iOS#business-flowchart)
- [API Sequence Diagram](https://github.com/AgoraIO-Usecase/AgoraChat-UIKit-Chatroom-iOS#api-sequence-diagram)
- [DesignGuidelines](https://github.com/AgoraIO-Usecase/AgoraChat-UIKit-Chatroom-iOS#design-guidelines)
- [Contributing](https://github.com/AgoraIO-Usecase/AgoraChat-UIKit-Chatroom-iOS#contributing)
- [License](https://github.com/AgoraIO-Usecase/AgoraChat-UIKit-Chatroom-iOS#license)

# [Requirements](https://github.com/AgoraIO-Usecase/AgoraChat-UIKit-Chatroom-iOS#requirements)

- iOS 13.0+
- Xcode 13.0+
- Swift 5.0+

# [Installation](https://github.com/AgoraIO-Usecase/AgoraChat-UIKit-Chatroom-iOS#installation)

You can install AgoraChatroomUIKit with CocoaPods as a dependency of your Xcode project.

## [CocoaPods](https://github.com/AgoraIO-Usecase/AgoraChat-UIKit-Chatroom-iOS#cocoapods)

```ruby
pod 'AgoraChatroomUIKit'
```

# [Structure](https://github.com/AgoraIO-Usecase/AgoraChat-UIKit-Chatroom-iOS#structure)

### [Basic Components of AgoraChatroomUIKit](https://github.com/AgoraIO-Usecase/AgoraChat-UIKit-Chatroom-iOS#basic-components-of-chatroomuikit)

```
ChatroomUIKit
├─ Service                           // Basic service components.
│  ├─ Protocol                       // Business protocol component.
│  │  ├─ GiftService                 // Gift sending and receiving channel.
│  │  ├─ UserService                 // Component for user login and user attribute update.
│  │  └─ ChatroomService             // Component for implementing the protocol for chat room management, including joining and leaving the chat room and sending and receiving messages.
│  ├─ Implement                      // Protocol implementation component.
│  └─ Client                         // ChatroomUIKit initialization class.
│
└─ UI                                // Basic UI components without business.
   ├─ Resource                       // Image or localize file.
   ├─ Component                      // UI module containing specific business. Some functional UI components in chat room UIKit.
   │  ├─ Room                        // Container of all chat room subviews.
   │  ├─ Chat                        // The chat component and bottom functional area in the chat room.
   │  ├─ Gift                        // Components such as the gift area and gift container in the chat room.
   │  └─ Input                       // Input components in chat rooms such as emoticons.
   └─ Core
      ├─ UIKit                       // Some common UIKit components and custom components.
      ├─ Theme                       // Theme-related components, including colors, fonts, skinning protocols and their components.
      └─ Extension                   // Some convenient system class extensions.
```

# [Documentation](https://github.com/AgoraIO-Usecase/AgoraChat-UIKit-Chatroom-iOS#documentation)

## [Document](https://github.com/AgoraIO-Usecase/AgoraChat-UIKit-Chatroom-iOS/tree/main/Documentation/ChatroomUIKit.doccarchive)

You can open the `ChatroomUIKit.doccarchive` file in Xcode to view files in it or deploy this file to your homepage.

Also, you can right-click the file to show the package contents and copy all files inside to a folder. Then drag this folder to the `terminal` app and run the following command to deploy it on the local IP address.

```bash
python3 -m http.server 8080
```

After deployment, you can visit `http://yourlocalhost:8080/documentation/chatroomuikit` in your browser, where `yourlocalhost` is your local IP address. Alternatively, you can deploy this folder on an external network address.

## [Appearance](https://github.com/AgoraIO-Usecase/AgoraChat-UIKit-Chatroom-iOS/tree/main/Documentation/Appearance.md).

Detailed descriptions of available items in the `UI` component.

## [ComponentRegister](https://github.com/AgoraIO-Usecase/AgoraChat-UIKit-Chatroom-iOS/tree/main/Documentation/ComponentRegister.md).

UI components that can be inherited for customization.

## [GiftsViewController](https://github.com/AgoraIO-Usecase/AgoraChat-UIKit-Chatroom-iOS/blob/main/Documentation/GiftsViewController.md)

A container that contains a gift list. You can inherit this class to implement additional UI definitions and business processing. After you click the **Send** button to deliver a gift, you can decide whether to close the gift pop-up window and call the gift API in your business on your server to send the gift message to the chat room.

# [Quick Start](https://github.com/AgoraIO-Usecase/AgoraChat-UIKit-Chatroom-iOS#quick-start)


This guide provides several usage examples for different AgoraChatroomUIKit components. Refer to the `Examples` folder for detailed code snippets and projects showing various use cases.

Refer to the following steps to create an iOS platform App in Xcode. The creation settings are as follows:

- Product Name: Fill in **ChatroomUIKitQuickStart**.
- Organization Identifier: Fill in your identifier.
- User Interface: Select **Storyboard**.
- Language: You common development language.

### [Step 1: Initialize AgoraChatroomUIKit](https://github.com/AgoraIO-Usecase/AgoraChat-UIKit-Chatroom-iOS#step-1-initialize-chatroomuikit)

```swift
import UIKit
import AgoraChatroomUIKit 

@UIApplicationMain
class AppDelegate: UIResponder, UIApplicationDelegate {

    var window: UIWindow?


    func application(_ application: UIApplication, didFinishLaunchingWithOptions launchOptions: [UIApplicationLaunchOptionsKey: Any]?) -> Bool {
        // You can initialize the AgoraChatroomUIKit when the app loads or before you use it.
        // You need to pass in the App Key.
        // To get the App Key, visit https://docs.agora.io/en/agora-chat/get-started/enable?platform=android#get-chat-project-information.
        ChatroomUIKitClient.shared.setup(appKey: "Appkey")
        return true
    }
}
```

### [Step 2: Log in to the AgoraChatroomUIKit](https://github.com/AgoraIO-Usecase/AgoraChat-UIKit-Chatroom-iOS#step-2-log-in-to-the-chatroomuikit)

```swift
// Log in to the AgoraChatroomUIKit with the user information of the current user object that conforms to the `UserInfoProtocol` protocol.
// The token needs to be obtained from your app server. You can also log in with a temporary token generated on the Agora Console.
// To generate a user and a temporary user token on the Agora Console, see https://docs.agora.io/en/agora-chat/get-started/enable?platform=ios#manage-users-and-generate-tokens.
ChatroomUIKitClient.shared.login(
    userId: "user id",
    token: "token",
    completion: <#T##(ChatError?) -> Void#>
)
```


### [Step 3: Create a chat room view](https://github.com/AgoraIO-Usecase/AgoraChat-UIKit-Chatroom-iOS#step-3-create-a-chat-room-view)


```swift
// 1. Get a chat room list and join a chat room. Alternatively, create a chat room on the Agora Console.
// Choose Project Management > Operation Management > Chat Room and click Create Chat Room and set parameters in the displayed dialog box to create a chat room. Get the chat room ID to pass it to the following `launchRoomView` method.
// 2. Create a chat room view with `ChatroomView` by passing in parameters such as layout parameters and the array of extension button model protocols of the bottom toolbar.
// It is recommended that the width of ChatroomView should be initialized as the width of the screen and the height should be no less than the height of the screen minus the height of the navigation.
let roomView = ChatroomUIKitClient.shared.launchRoomViewWithOptions(
    roomId: self.room?.chatroomId ?? "",
    frame: CGRect(x: 0, y: self.playView.frame.maxY, width: self.view.frame.width, height: 336+BottomBarHeight),
    ownerId: "Chatroom's owner user id"
)
// 3. Add to the destination frame.
// 4. Add users to the chat room on the Console.
// Choose ProjectManager > Operation Manager > Chat Room. Select View Chat Room Members in the Action column of a chat room and add users to the chat room in the displayed dialog box.
```

Please refer to the next chapter for transparent transmission of events.

# [Precautions](https://github.com/AgoraIO-Usecase/AgoraChat-UIKit-Chatroom-iOS#precautions)


When calling `ChatroomUIKitClient.shared.launchRoomView(roomId: String, frame: CGRect, isOwner: Bool)`, remember to add ChatroomView above your existing view to facilitate interception and transparent transmission of click events.

For example, if you have a view that plays video streams, be sure to add ChatroomView above this view.

![UI Hierarchy](./Documentation/hierarchy.png)

# [Advanced Usage](https://github.com/AgoraIO-Usecase/AgoraChat-UIKit-Chatroom-iOS#advanced-usage)

Here are three examples of advanced usage.

### [1.Log in to AgoraChatroomUIKit](https://github.com/AgoraIO-Usecase/AgoraChat-UIKit-Chatroom-iOS#1log-in-to-chatroomuikit)


```swift
class YourAppUser: UserInfoProtocol {

    public func toJsonObject() -> Dictionary<String, Any>? {
        ["userId":self.userId,"nickname":self.nickname,"avatarURL":self.avatarURL,"identity":self.identity,"gender":self.gender]
    }

    var userId: String = "your application user id"

    var nickname: String = "Your user nick name"

    var avatarURL: String = "Your user avatar url"

    var gender: Int = 1

    var identity: String =  "Your user level symbol url"

}
// Use the user information of the current user object that conforms to the UserInfoProtocol protocol to log in to AgoraChatroomUIKit.
// You need to get a user token from your app server. Alternatively, you can use a temporary token. To generate a temporary token, visit https://docs.agora.io/en/agora-chat/get-started/enable?platform=ios#generate-a-user-token.
ChatroomUIKitClient.shared.login(
    user: YourAppUser(),
    token: "token",
    completion: <#T##(ChatError?) -> Void#>)
```

### [2.Initialize the chat room view](https://github.com/AgoraIO-Usecase/AgoraChat-UIKit-Chatroom-iOS#2initialize-the-chat-room-view)


```swift
//1. Get a chat room list and join a chat room. Alternatively, create a chat room on the Agora Console.
// 2. Create a chat room view with `ChatroomView` by passing in parameters such as layout parameters and the array of extension button model protocols of the bottom toolbar.
let options  = ChatroomUIKitInitialOptions.UIOptions()
options.bottomDataSource = self.bottomBarDatas()
options.showGiftMessageArea = true
options.chatAreaShowGift = false
ChatroomUIKitClient.shared.launchRoomView(
    roomId: self.room?.chatroomId ?? "",
    frame: CGRect(x: 0, y: self.playView.frame.maxY, width: self.view.frame.width, height: 336+BottomBarHeight),
    ownerId: self.room?.owner ?? "",
    options: options
)
//3. Add to the destination frame.
```

### [3.Listen for AgoraChatroomUIKit events and errors](https://github.com/AgoraIO-Usecase/AgoraChat-UIKit-Chatroom-iOS#3listen-for-chatroomuikit-events-and-errors)


You can call the `registerRoomEventsListener` method to listen for ChatroomUIKit events and errors.

```swift
ChatroomUIKitClient.shared.registerRoomEventsListener( self)
```

# [Customization](https://github.com/AgoraIO-Usecase/AgoraChat-UIKit-Chatroom-iOS#customization)

### [1.Modify configurable items](https://github.com/AgoraIO-Usecase/AgoraChat-UIKit-Chatroom-iOS#1modify-configurable-items)


The following shows how to change the overall cell layout style of the chat area and how to create the ChatroomView.

```swift
// You can change the overall cell layout style of the chat area by setting the properties.
Appearance.ChatMessageDisplayContentStyle = .all
// Create the ChatroomView by passing in parameters like layout parameters and the bottom toolbar extension button model protocol array.
let roomView = ChatroomUIKitClient.shared.launchRoomView(
    roomId: self.room?.chatroomId ?? "",
    frame: CGRect(x: 0, y: self.playView.frame.maxY, width: self.view.frame.width, height: 336+BottomBarHeight),
    ownerId: self.room?.owner ?? ""
)
self.view.addSubView(roomView)
```

For details, see [Appearance](https://github.com/AgoraIO-Usecase/AgoraChat-UIKit-Chatroom-iOS/blob/main/Documentation/Appearance.md).

### [2.Customize components](https://github.com/AgoraIO-Usecase/AgoraChat-UIKit-Chatroom-iOS#2customize-components)


The following shows how to customize the gift message cell.

```swift
class CustomGiftMessageCell: GiftMessageCell {
    lazy var redDot: UIView = {
        UIView().backgroundColor(.red).cornerRadius(.large)
    }()

    override init(style: UITableViewCell.CellStyle, reuseIdentifier: String?) {
        super.init(style: style, reuseIdentifier: reuseIdentifier)
        self.addSubview(redDot)
    }

    override func refresh(item: GiftEntityProtocol) {
        super.refresh(item: item)
        self.redDot.isHidden = item.selected
    }
}
//Register the custom class that inherits the original class in AgoraChatroomUIKit to replace the original one.
//Call this method before creating a ChatroomView or using other UI components.
ComponentsRegister.shared.GiftMessagesViewCell = CustomGiftMessageCell.self
```

For details, see [ComponentsRegister](https://github.com/AgoraIO-Usecase/AgoraChat-UIKit-Chatroom-iOS/blob/main/Documentation/ComponentsRegister.md).

### [3.Switch to the original or custom theme](https://github.com/AgoraIO-Usecase/AgoraChat-UIKit-Chatroom-iOS#3switch-to-the-original-or-custom-theme)

- Switch to the light or dark theme that comes with the AgoraChatroomUIKit.

```swift
Theme.switchTheme(style: .dark)` or `Theme.switchTheme(style: .light)
```

- Switch to a custom theme.

```swift
/**
How to customize a theme?

To customize a theme, you need to define the hue values of the following five theme colors by reference to the theme color of the design document.

All colors in AgoraChatroomUIKit are defined with the HSLA color model that is a way of representing colors using hue, saturation, lightness, and alpha.

H (Hue): Hue, the basic attribute of color, is a degree on the color wheel from 0 to 360. 0 is red, 120 is green, and 240 is blue.

S (Saturation): Saturation is the intensity and purity of a color. The higher the saturation is, the brighter the color is; the lower the saturation is, the closer the color gets to gray. Saturation is represented by a percentage value, ranging from 0% to 100%. 0% means a shade of gray, and 100% is the full color.

L (Lightness): Lightness is the brightness or darkness of a color. The higher the brightness is, the brighter the color is; the lower the brightness is, the darker the color is. Lightness is represented by a percentage value, ranging from 0% to 100%. 0% indicates a black color and 100% will result in a white color.

A (Alpha): Alpha is the transparency of a color. The value 1 means fully opaque and 0 is fully transparent.

By adjusting the values of individual components of the HSLA model, you can achieve precise color control.
 */
Appearance.primaryHue = 191/360.0
Appearance.secondaryHue = 210/360.0
Appearance.errorHue = 189/360.0
Appearance.neutralHue = 191/360.0
Appearance.neutralSpecialHue = 199/360.0
Theme.switchTheme(style: .custom)
```

Note that custom themes and built-in themes are mutually exclusive.

# [Business Flowchart]

The following figure presents the entire logic of business requests and callbacks.

![Overall flow diagram of business logic](./Documentation/BusinessFlowchart.png)

# [API Sequence Diagram]

The following figure is the best-practice API calling sequence diagram in the `Example` project.

![APIUML](./Documentation/Api.png)

# [Design Guidelines](https://github.com/AgoraIO-Usecase/AgoraChat-UIKit-Chatroom-iOS#design-guidelines)

For any questions about design guidelines and details, you can add comments to the Figma design draft and mention our designer Stevie Jiang.

See the [UI design drawing](https://www.figma.com/community/file/1322495388317476706/chatroom-uikit).

See the [UI design guidelines](https://github.com/StevieJiang/Chat-UIkit-Design-Guide/blob/main/README.md)

# [Contributing](https://github.com/AgoraIO-Usecase/AgoraChat-UIKit-Chatroom-iOS#contributing)

Contributions and feedback are welcome! For any issues or improvement suggestions, you can open an issue or submit a pull request.

## [Author](https://github.com/AgoraIO-Usecase/AgoraChat-UIKit-Chatroom-iOS#author)


zjc19891106, [984065974@qq.com](mailto:984065974@qq.com)

## [License](https://github.com/AgoraIO-Usecase/AgoraChat-UIKit-Chatroom-iOS#license)

AgoraChatroomUIKit is available under the MIT license. See the LICENSE file for more information.
