---
title: 远程管理 Microsoft 团队聊天室设备设置
ms.author: v-lanac
author: lanachin
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: df418e25-81fd-474d-be16-5cd1ac8145cc
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-mar2020
description: Microsoft 团队聊天室设备使用的默认设置的远程管理，包括应用自定义主题和创建主设置文件。
ms.openlocfilehash: 8d723423cc8e93429d193f4340eceddcc55ca10d
ms.sourcegitcommit: 1c2359f10ad5f5ec10dc52508ef4774c04b631ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2020
ms.locfileid: "44230500"
---
# <a name="manage-a-microsoft-teams-rooms-console-settings-remotely-with-an-xml-configuration-file"></a>使用 XML 配置文件远程管理 Microsoft 团队聊天室控制台设置

本文介绍 Microsoft 团队聊天室设备使用的默认设置的远程管理，包括应用自定义主题。 它介绍了如何创建主设置文件，并提供了有关如何在远程托管设备上根据需要放置它们的讨论的链接。
  
你可以通过更新主 XML 文件并将副本发送到托管控制台来更改远程托管设备的默认设置。 你还可以在具有 XML 配置文件的 Microsoft 团队聊天室控制台上实现自定义主题。
  
## <a name="create-an-xml-configuration-file"></a>创建 XML 配置文件

任何文本编辑器都可用于创建设置文件。 **XML 元素**表说明了此示例 SkypeSettings （必需文件名）配置文件中所示的元素。
  
```XML
<SkypeSettings>
    <AutoScreenShare>true</AutoScreenShare>
    <HideMeetingName>true</HideMeetingName>
    <UserAccount>
        <SkypeSignInAddress>RanierConf@contoso.com</SkypeSignInAddress>
        <ExchangeAddress>RanierConf@contoso.com</ExchangeAddress>
        <ModernAuthEnabled>false</ModernAuthEnabled>
        <DomainUsername>Seattle\RanierConf</DomainUsername>
        <Password>password</Password>
        <ConfigureDomain>domain1, domain2</ConfigureDomain>
    </UserAccount>
    <IsTeamsDefaultClient>false</IsTeamsDefaultClient>
    <BluetoothAdvertisementEnabled>true</BluetoothAdvertisementEnabled>
    <AutoAcceptProximateMeetingInvitations>false</AutoAcceptProximateMeetingInvitations>
    <SkypeMeetingsEnabled>false</SkypeMeetingsEnabled>
    <TeamsMeetingsEnabled>true</TeamsMeetingsEnabled>
    <DualScreenMode>true</DualScreenMode>
    <DuplicateIngestDefault>false</DuplicateIngestDefault>
    <SendLogs>
        <EmailAddressForLogsAndFeedback>RanierConf@contoso.com</EmailAddressForLogsAndFeedback>
        <SendLogsAndFeedback>true</SendLogsAndFeedback>
    </SendLogs>
    <Devices>
        <MicrophoneForCommunication>Microsoft LifeChat LX-6000</MicrophoneForCommunication>
        <SpeakerForCommunication>Realtek High Definition Audio</SpeakerForCommunication>
        <DefaultSpeaker>Polycom CX5100</DefaultSpeaker>
        <ContentCameraId>USB\VID_046D&amp;PID_0843&amp;MI_00\7&amp;17446CF2&amp;0&amp;0000</ContentCameraId>
        <ContentCameraInverted>false</ContentCameraInverted>
        <ContentCameraEnhancement>true</ContentCameraEnhancement>
    </Devices>
    <Theming>
        <ThemeName>Custom</ThemeName>
        <CustomThemeImageUrl>file name</CustomThemeImageUrl>
        <CustomThemeColor>
            <RedComponent>100</RedComponent>
            <GreenComponent>100</GreenComponent>
            <BlueComponent>100</BlueComponent>
        </CustomThemeColor>
    </Theming>
</SkypeSettings>
```

如果变量值的类型不正确，元素的顺序不正确，元素未闭合，或者发现了其他错误，则 XML 文件的*格式*不正确。 在处理格式不正确的 XML 文件时，将应用出现错误的位置所找到的设置，然后忽略文件的其余部分。 XML 中的任何未知元素都将忽略。 如果忽略某个参数，它在设备上将保持不变。 如果参数值无效，则它的前一个值保持不变。
  
**XML 元素**

|元素|类型|等级|用法|
|:--- |:--- |:--- |:--- |
|\<SkypeSettings\> |所有元素的容器。 ||必需。 |
| \<AutoScreenShare\>  |布尔 &#x2777;  |第一 &#x2776;  | 如果为 true，则启用自动屏幕共享。  |
|\<HideMeetingName\> |布尔 &#x2777;  |第一 &#x2776;  |如果为 true，则隐藏会议名称。 |
|\<UserAccount\> |容器 |第一 &#x2776;  |凭据参数的容器。 登录地址、Exchange 地址或电子邮件地址通常相同，例如 RanierConf <span></span> @contoso .com。 |
|\<SkypeMeetingsEnabled\>  |布尔 &#x2777;  |第一 &#x2776;  |默认为启用。 |
|\<SkypeSignInAddress\> |字符串 &#x2778;  ||控制台的 SfB 或团队设备帐户的登录名。 |
|\<ExchangeAddress\> |字符串 &#x2778;  ||控制台的 Exchange 设备帐户的登录名。 如果省略 ExchangeAddress，则不会自动重复使用 SkypeSignInAddress。 |
|\<ModernAuthEnabled> |布尔 &#x2777;  |  |默认情况下处于禁用状态。 <br/> <br/>当设置为 true 时，Microsoft 团队聊天室应用程序仅使用新式身份验证连接到资源，不会回退到基本身份验证。|
|\<DomainUsername\> |字符串 &#x2778;  ||控制台设备的域和用户名，例如 Seattle\RanierConf。 |
|\<口令\> |String 3  || 密码参数是用于 Skype for Business 设备帐户登录的相同密码。  |
| \<ConfigureDomain\>  |字符串 &#x2778;  ||你可以列出多个域，以逗号分隔。 |
|\<TeamsMeetingsEnabled\> |布尔 &#x2777;  |第一 &#x2776;  |默认情况下处于禁用状态。 <br/> <br/> 如果 \< SkypeMeetingsEnabled \> 和 TeamsMeetingsEnabled 都被禁用，XML 文件的格式不正确 \< \> ，但可接受同时启用这两个设置。 |
|\<IsTeamsDefaultClient> |布尔 &#x2777;  |第一 &#x2776;  |默认情况下处于禁用状态。 |
|\<BluetoothAdvertisementEnabled> |布尔 &#x2777;  |第一 &#x2776;  |默认为启用。 |
|\<AutoAcceptProximateMeetingInvitations> |布尔 &#x2777;  |第一 &#x2776;  |如果为 true，则自动接受基于邻近感应的会议。 默认情况下处于禁用状态。 |
|\<DualScreenMode\>  |布尔 &#x2777;  |第一 &#x2776;  |如果为 true，则启用双屏幕模式。 否则，设备使用单一屏幕模式。 |
| \<DuplicateIngestDefault\> |布尔 &#x2777;  |第一 &#x2776; |如果为 true，则在双屏幕模式下，在两个屏幕上显示的内容在离开会议时显示。 | 
|\<SendLogs\> |容器 |第一 &#x2776;  |  |
|\<EmailAddressForLogsAndFeedback\> |字符串 &#x2778;  | | 设置可在出现 "提供反馈" 窗口时向其发送日志的可选电子邮件地址。 |
|\<SendLogsAndFeedback\> |布尔 &#x2777;  | | 如果为 true，将日志发送到域。如果为 false，仅将反馈发送给管理员（不发送日志）。  |
| \<设备\>  |容器 |第一 &#x2776;  | 子元素中的已连接音频设备名称与设备管理器应用中列出的值相同。 配置可能包含目前系统中不存在的设备，例如当前未连接到控制台的 A/V 设备。 可能会为各个设备保留配置。  |
|\<MicrophoneForCommunication\> |字符串 &#x2778;  ||设置在会议中用作录制设备的麦克风。 |
|\<SpeakerForCommunication\> |字符串 &#x2778;  ||用作会议扬声器的设备。 此设置用于设置通话中使用的扬声器设备。 |
|\<DefaultSpeaker\> |字符串 &#x2778;  ||用于播放来自 HDMI 摄入源的音频的设备。 |
|\<ContentCameraId>  | 字符串 &#x2778;  | | 定义在会议室中配置的相机的实例路径，以便在会议中共享模拟白板内容。 请参阅[查找内容照相机 USB 实例路径](#locate-the-content-camera-usb-instance-path)。|
|\<ContentCameraInverted>  | 布尔 &#x2777; | | 指定是否将内容摄像头的物理安装倒置。 对于支持自动旋转的内容照相机，请指定 false。 |
|\<ContentCameraEnhancement>  | 布尔 &#x2777; | |当设置为 true （默认值）时，将对内容相机图像进行数字增强：检测白板边缘并选择相应的缩放，墨迹线条将得到增强，并且在白板上书写的人员将变为透明。  <br><br> 如果你打算向会议参与者发送不使用笔绘制白板的空间，而是使用摄像头来显示粘滞便笺、海报或其他媒体，则设置为 false。  |
| \<主题\>  |容器 |第一 &#x2776;  |可与 XML 文件一起应用的功能之一是组织的自定义主题。 你可以指定主题名称、背景图像和颜色。 |
|\<ThemeName\> |字符串 &#x2778;  || 用于识别客户端上的主题。 主题名称选项包括“默认”、提供的预设主题之一或“自定义”。 <br/>  自定义主题名称始终使用 "*自定义*" 名称。 客户端 UI 可在控制台上设置为默认值或其中一个预设，但是使用自定义主题必须由管理员进行远程设置。 <br/>  预设主题包括： <br/>  默认 <br/>  蓝色波浪 <br/>  数字丛林 <br/>  追梦人 <br/>  莱姆汁 <br/>  完美像素 <br/>  路线图 <br/>  夕阳 <br/>  若要禁用当前主题，请对 ThemeName 使用 "无主题"。  |
|\<CustomThemeImageUrl\> |字符串 &#x2778;  ||对于自定义主题是必需的，否则为可选。 仅输入文件名。   |有关自定义主题图像的详细信息，请参阅[自定义主题图像](xml-config-file.md#Themes)部分。
|\<CustomThemeColor\> |容器 ||\<RedComponent \> 、 \< GreenComponent \> 和 \< BlueComponent \> 值的容器。 这些值是自定义主题所必需的。 |
|\<RedComponent\> |字节 (0-255) ||代表红色组件。 |
|\<GreenComponent\> |字节 (0-255) ||代表绿色组件。 |
|\<BlueComponent\> |字节 (0-255) ||代表蓝色组件。 | 
| | | |

&#x2776; 所有第一级元素都是可选的。 如果省略第一级元素，其所有子参数在设备上保持不变。
  
&#x2777; boolean 标志可以是： true、false、0或1。 将布尔值或数字值保留为空可使 XML 呈现出格式错误，并防止对设置进行更改。
  
&#x2778; 如果字符串参数存在且为空，空值为有效值，则在设备上清除该参数。
  
## <a name="manage-console-settings-with-an-xml-configuration-file"></a>使用 XML 配置文件管理控制台设置

在启动时，如果 Microsoft 团队聊天室控制台发现名为 SkypeSettings 的 XML 文件 `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState` ，则应用由 xml 文件指示的配置设置，然后删除 xml 文件。
  
根据你的企业拥有的 Microsoft 团队会议室设备的数量以及你选择的管理方式来配置它们，有多种方法可以放置 XML 配置文件。 文件推送到控制台之后，重启以处理配置更改。 成功处理 XML 配置文件后会将其删除。 有关 Microsoft 团队聊天室设备的建议的管理方法，请参见：
  
- [为 Microsoft 团队聊天室配置组策略](rooms-operations.md#GroupPolicy)
- [使用 PowerShell 的远程管理](rooms-operations.md#RemotePS)和[配置文件项目](https://technet.microsoft.com/library/cc772536%28v=ws.11%29.aspx)

你可以使用你喜欢的任何方法，只要你能传输文件并在控制台设备上触发重启即可。 该文件必须是可读、可写且可由设备的本地用户帐户删除。 最好是由该用户拥有并授予该用户的完全权限。 如果文件权限设置不正确，则软件可能无法应用设置，也可能无法在成功处理时删除文件，甚至可能会崩溃。
  
## <a name="custom-theme-images"></a>自定义主题图像

<a name="Themes"> </a>

自定义主题图像文件必须放置在文件夹中 `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState` 。 在 CustomThemeImageUrl 变量中输入文件名和扩展名 \< \> 。
  
图像文件应正好3840X1080 像素，并且必须是以下文件格式之一： jpg、jpeg、png 和 bmp。 如果你的组织需要自定义图像，图形设计器可以使用[自定义主题 Photoshop 模板](../downloads/ThemingTemplateMicrosoftTeamsRooms_v2.1.psd)。 它包含有关各种用户界面元素相对于其他主题图像的位置以及哪些区域显示在控制台和显示中的详细信息。
  
XML 配置文件必须在设备启动时更新以识别主题图像。 处理并删除新的 XML 文件后，将从目录中删除主题图形文件。
  
## <a name="locate-the-content-camera-usb-instance-path"></a>找到 "内容照相机" USB 实例路径

要查找实例路径，请执行以下操作：

1. 转到 Microsoft 团队聊天室控制台上的 Windows 设置。
2. 输入管理员密码。
3. 从命令提示符处，键入 `devmgmt.msc` 以调出设备管理器。
4. 在 "**设备管理器**" 中，查看 "**图像设备**" 节点并找到 "内容照相机"。
5. 右键单击相机，然后打开 "**属性**"。
6. 选择 "**详细信息**" 选项卡，然后在下拉列表中找到 "**设备实例路径**" 属性。
7. 显示的值是要在 XML 配置文件中设置的设备实例路径。 在 XML 中指定路径时，请将与号（&）替换为 `&amp;` 。

## <a name="see-also"></a>另请参阅

[内容照相机](content-camera.md)

[管理 Microsoft Teams 会议室](rooms-manage.md)

[配置文件项目](https://technet.microsoft.com/library/cc772536%28v=ws.11%29.aspx)
