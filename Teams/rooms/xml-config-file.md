---
title: 远程管理Microsoft Teams 会议室设置
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: df418e25-81fd-474d-be16-5cd1ac8145cc
ms.collection:
- M365-collaboration
ms.custom:
- seo-marvel-mar2020
description: 远程管理设备使用的默认设置Microsoft Teams 会议室，包括应用自定义主题和创建主设置文件。
ms.openlocfilehash: 01ecdd5a960978e15e7c21d5f5e7fe6707437a42
ms.sourcegitcommit: e0e3c83cea2662057ee2f3f2a429c7831c3d917a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2022
ms.locfileid: "62213491"
---
# <a name="manage-a-microsoft-teams-rooms-console-settings-remotely-with-an-xml-configuration-file"></a>使用 XML Microsoft Teams 会议室远程管理主机设置

本文讨论远程管理设备使用的默认设置Microsoft Teams 会议室，包括应用自定义主题。 本文讨论如何创建主设置文件，并链接到讨论如何根据需要将它们放在Teams 会议室。
  
通过更新主 XML 文件Teams 会议室将副本发送到远程设备，可以更改 Teams 会议室设置。
  
## <a name="create-an-xml-configuration-file"></a>创建 XML 配置文件

任何文本编辑器都可用于创建设置文件。 XML **Elements** 表说明了此示例中显示的元素SkypeSettings.xml (配置文件) 文件名。
  
```XML
<SkypeSettings>
  <AutoScreenShare>1</AutoScreenShare>
  <HideMeetingName>1</HideMeetingName>
  <AutoExitMeetingEnabled>true</AutoExitMeetingEnabled>
  <AudioRenderDefaultDeviceVolume>70</AudioRenderDefaultDeviceVolume>
  <AudioRenderCommunicationDeviceVolume>30</AudioRenderCommunicationDeviceVolume>
  <UserAccount>
    <SkypeSignInAddress>username@microsoft.com</SkypeSignInAddress>
    <ExchangeAddress>username@microsoft.com</ExchangeAddress>
    <DomainUsername>domain\username</DomainUsername>
    <Password>Password!</Password>
    <ConfigureDomain>domain1, domain2</ConfigureDomain>
    <ModernAuthEnabled>true</ModernAuthEnabled>
  </UserAccount>
  <TeamsMeetingsEnabled>true</TeamsMeetingsEnabled>
  <SfbMeetingEnabled>true</SfbMeetingEnabled>
  <IsTeamsDefaultClient>true</IsTeamsDefaultClient>
  <WebExMeetingsEnabled>true</WebExMeetingsEnabled>
  <ZoomMeetingsEnabled>true</ZoomMeetingsEnabled>
  <UseCustomInfoForThirdPartyMeetings>true</UseCustomInfoForThirdPartyMeetings>
  <CustomDisplayNameForThirdPartyMeetings>guestname</CustomDisplayNameForThirdPartyMeetings>
  <CustomDisplayEmailForThirdPartyMeetings>guest@microsoft.com</CustomDisplayEmailForThirdPartyMeetings>
  <BluetoothAdvertisementEnabled>false</BluetoothAdvertisementEnabled>
  <AutoAcceptProximateMeetingInvitations>true</AutoAcceptProximateMeetingInvitations>
  <CortanaWakewordEnabled>true</CortanaWakewordEnabled>
  <DualScreenMode>0</DualScreenMode>
  <DuplicateIngestDefault>true</DuplicateIngestDefault>
  <DisableTeamsAudioSharing>true</DisableTeamsAudioSharing>
  <FrontRowEnabled>true</FrontRowEnabled>
  <DefaultFoRExperience>0</DefaultFoRExperience>
  <SendLogs>
    <EmailAddressForLogsAndFeedback>username@microsoft.com</EmailAddressForLogsAndFeedback>
    <SendLogsAndFeedback>True</SendLogsAndFeedback>
  </SendLogs>
  <Devices>
    <MicrophoneForCommunication>Device1</MicrophoneForCommunication>
    <SpeakerForCommunication>DeviceX</SpeakerForCommunication>
    <DefaultSpeaker>DeviceX</DefaultSpeaker>
    <ContentCameraId>Camera1</ContentCameraId>
    <ContentCameraEnhancement>true</ContentCameraEnhancement>
    <ContentCameraInverted>false</ContentCameraInverted>
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
  <CoordinatedMeetings enabled="true">
    <TrustedAccounts>username1@microsoft.com,username2@contoso.com</TrustedAccounts>
    <Settings>
      <Audio default="true" enabled="true"/>
      <Video default="true" enabled="true"/>
      <Whiteboard default="true" enabled="true"/>
    </Settings>
  </CoordinatedMeetings>
</SkypeSettings>
```

如果变量值的类型不正确、元素顺序不正确、元素未取消排序或找到另一个错误，则 XML 文件 *格式不正确*。 在处理格式错误的 XML 文件时，将应用到发生错误时所找到的设置，然后忽略该文件的其余部分。 XML 中的任何未知元素都将忽略。 如果忽略某个参数，它在设备上将保持不变。 如果参数值无效，其以前的值将保持不变。
  
**XML 元素**

| 元素                                     | 类型                        | 等级          | 用法                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
|:--------------------------------------------|:----------------------------|:---------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| \<SkypeSettings\>                           | 所有元素的容器。 |                | 必需。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| \<AutoScreenShare\>                         | 布尔值&#x2777;            | 第一&#x2776; | 如果为 true，则启用自动屏幕共享。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| \<HideMeetingName\>                         | 布尔值&#x2777;            | 第一&#x2776; | 如果为 true，则隐藏会议名称。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| \<UserAccount\>                             | 容器                   | 第一&#x2776; | 凭据参数的容器。 登录地址、Exchange地址或电子邮件地址通常相同，例如 RainierConf <span></span> @contoso.com。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| \<SkypeSignInAddress\>                      | 字符串&#x2777;             |                | 主机 SfB 或设备帐户的Teams名称。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| \<ExchangeAddress\>                         | 字符串&#x2778;            |                | 主机的设备帐户的登录Exchange名称。 如果省略 ExchangeAddress，则 SkypeSignInAddress 不会自动重复使用。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| \<DomainUsername\>                          | 字符串&#x2777;            |                | 控制台设备的域和用户名，例如 Seattle\RanierConf。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| \<Password\>                                | 字符串&#x2778;            |                | 密码参数是用于 Skype for Business 设备帐户登录的相同密码。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| \<ConfigureDomain\>                         | 字符串&#x2777;            |                | 你可以列出多个域，以逗号分隔。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| \<ModernAuthEnabled>                        | 布尔值&#x2777;            |                | 默认情况下处于禁用状态。 <br/> <br/>设置为 true 时，Microsoft Teams 会议室应用程序仅使用新式身份验证连接到资源，不会回退到基本身份验证。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| \<TeamsMeetingsEnabled\>                    | 布尔值&#x2777;            | 第一&#x2776; | 默认情况下处于禁用状态。 <br/> <br/> 如果同时禁用 和 ，则 XML 文件被视为格式不正确，但可以同时启用这两 \<SkypeMeetingsEnabled\> \<TeamsMeetingsEnabled\> 个设置。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| \<SfbMeetingEnabled\>                       | 布尔值&#x2778;            | 第一&#x2776; | 默认情况下处于禁用状态。
| \<IsTeamsDefaultClient>                     | 布尔值&#x2777;            | 第一&#x2776; | 默认为启用。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| \<WebExMeetingsEnabled\>                    | 布尔值&#x2777;            | 第一&#x2776; | 默认情况下处于禁用状态。 <br/> <br/> 如果为 true，则为 Cisco Webex 会议启用直接来宾加入体验。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| \<ZoomMeetingsEnabled\>                     | 布尔值&#x2777;            | 第一&#x2776; | 默认情况下处于禁用状态。 <br/> <br/> 如果为 true，则为 Zoom 会议启用直接来宾加入体验。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| \<UseCustomInfoForThirdPartyMeetings\>      | 布尔值&#x2777;            | 第一&#x2776; | 默认情况下禁用，并使用会议室帐户信息加入第三方会议。 <br/> <br/> 如果此值设置为 true，则必须指定 \<CustomDisplayNameForThirdPartyMeetings\> 两个 ， \<CustomDisplayEmailForThirdPartyMeetings\> 必须指定 。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| \<CustomDisplayNameForThirdPartyMeetings\>  | 字符串&#x2778;            | 第一&#x2776; | 指定用于加入第三方会议的来宾名称。 第三方服务将在其体验中显示此数据，并可能存储在其服务中。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| \<CustomDisplayEmailForThirdPartyMeetings\> | 字符串&#x2778;            | 第一&#x2776; | 指定用于加入第三方会议的来宾电子邮件。 第三方服务将在其体验中显示此数据，并可能存储在其服务中。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| \<BluetoothAdvertisementEnabled>            | 布尔值&#x2777;            | 第一&#x2776; | 默认为启用。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| \<AutoAcceptProximateMeetingInvitations>    | 布尔值&#x2777;            | 第一&#x2776; | 如果为 true，则自动接受基于邻近感应的会议。 默认情况下处于禁用状态。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| \<AutoExitMeetingEnabled>                   | 布尔值&#x2777;            | 第一&#x2776; | 如果为 true，则设备将自动离开会议（如果它是会议剩余的最后一个参与者）。  默认情况下处于禁用状态。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| \<DualScreenMode\>                          | 布尔值&#x2777;            | 第一&#x2776; | 如果为 true，则启用双屏幕模式。 否则，设备使用单屏幕模式。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| \<DuplicateIngestDefault\>                  | 布尔值&#x2777;            | 第一&#x2776; | 如果为 true，则当会议外时，两个屏幕均以双屏幕模式显示内容。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| \<DisableTeamsAudioSharing\>                | 布尔值&#x2777;            | 第一&#x2776; | 设置为 true 以禁用与会议参与者在会议Teams音频共享。 默认为 false。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| \<FrontRowEnabled>                          | 布尔值&#x2777;            | 第一&#x2776; | 默认为启用。 如果为 false，则禁用 Front Row。
| \<DefaultFoRExperience>                     | 布尔值&#x2777;            | 第一&#x2776; | 库视图默认。 Put 1 将默认布局从"库视图"更改为"前行"。
| \<CortanaWakewordEnabled\>                  | 布尔值&#x2777;            | 第一&#x2776; | 设置为 true 以启用Cortana"你好，Cortana"。 此设置没有任何影响，除非Cortana区域支持此服务，并且连接的音频外围设备支持Cortana。 默认为 false。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| \<SendLogs\>                                | 容器                   | 第一&#x2776; |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| \<EmailAddressForLogsAndFeedback\>          | 字符串&#x2778;            |                | 设置一个可选电子邮件地址，当出现"提供反馈"窗口时，日志可以发送到该地址。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| \<SendLogsAndFeedback\>                     | 布尔值&#x2777;            |                | 如果为 true，将日志发送到域。如果为 false，仅将反馈发送给管理员（不发送日志）。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| \<Devices\>                                 | 容器                   | 第一&#x2776; | 子元素中的已连接音频设备名称与设备管理器应用中列出的值相同。 配置可能包含目前系统中不存在的设备，例如当前未连接到控制台的 A/V 设备。 可能会为各个设备保留配置。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| \<MicrophoneForCommunication\>              | 字符串&#x2778;            |                | 设置用作会议录制设备的麦克风。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| \<SpeakerForCommunication\>                 | 字符串&#x2778;            |                | 用作会议扬声器的设备。 此设置用于设置呼叫中使用的扬声器设备。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| \<DefaultSpeaker\>                          | 字符串&#x2778;            |                | 用于播放来自 HDMI 摄入源的音频的设备。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| \<ContentCameraId>                          | 字符串&#x2778;            |                | 定义在会议室中配置的相机的实例路径，以共享会议中的模拟白板内容。 请参阅 [查找内容相机 USB 实例路径](#locate-the-content-camera-usb-instance-path)。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| \<ContentCameraInverted>                    | 布尔值&#x2777;            |                | 指定内容相机是倒置安装的。 对于支持自动旋转的内容摄像头，请指定 false。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| \<ContentCameraEnhancement>                 | 布尔值&#x2777;            |                | 当设置为 true (默认) 时，内容相机图像会以数字方式增强：检测到白板边缘，选择适当的缩放，墨迹线条得到增强，白板上书写的人将透明。  <br><br> 如果打算向会议参与者发送原始视频源（对于没有用笔绘制白板的空间）设置为 false，则摄像机用于显示便笺、海报或其他媒体。                                                                                                                                                                                                                                                                                                                                                                                             |
| \<Theming\>                                 | 容器                   | 第一&#x2776; | 可以使用 XML 文件应用的功能之一是组织的自定义主题。 你可以指定主题名称、背景图像和颜色。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| \<ThemeName\>                               | 字符串&#x2778;            |                | 用于识别客户端上的主题。 主题名称选项包括“默认”、提供的预设主题之一或“自定义”。 <br/>  自定义主题名称始终使用名称"自定义 *"。* 客户端 UI 可以在主机上设置为"默认"或其中一个预设，但自定义主题的使用必须由管理员远程设置。 <br/>  预设主题包括： <br/>  默认 <br/>  蓝色波浪 <br/>  数字丛林 <br/>  追梦人 <br/>  莱姆汁 <br/>  完美像素 <br/>  路线图 <br/>  夕阳 <br/>  若要禁用当前主题，请使用 ThemeName 的"无主题"。                                                                                                                                                                                                                                                                               |
| \<CustomThemeImageUrl\>                     | 字符串&#x2778;            |                | 对于自定义主题是必需的，否则是可选的。 仅输入文件名。   有关自定义主题图像的信息，请参阅自定义 [主题图像](xml-config-file.md#Themes) 部分。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| \<CustomThemeColor\>                        | 容器                   |                | 、 \<RedComponent\> 和 \<GreenComponent\> 值的 \<BlueComponent\> 容器。 这些值是必需的，但不会影响主题颜色。 请指定介于 0-255 之间的任何值。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| \<RedComponent\>                            | 字节 (0-255)                |                | 代表红色组件。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| \<GreenComponent\>                          | 字节 (0-255)                |                | 代表绿色组件。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| \<BlueComponent\>                           | 字节 (0-255)                |                | 代表蓝色组件。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| \<CoordinatedMeetings\>                     | 布尔值&#x2777;            | 第一&#x2776; | 用于协调会议的配置元素的容器。 此元素有一个属性：<ul><li><b>enabled</b>确定是否Teams配置为与其他设备一起参与协调会议。</li></ul>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| \<TrustedAccounts\>                         | String                      |                | 这是每个 Teams 会议室设备或 Surface Hub 设备应接受会议加入请求或者应发送到哪些会议加入请求的 UPN 的逗号分隔列表。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| \<Settings\>                                | 容器                   |                | 用于协调会议的配置音频和视频配置元素的容器。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| \<Audio\>                                   | 布尔值&#x2777;            |                | 控制设备上Teams 会议室配置。 此元素具有两个属性：<br><ul><li><b>default</b> 确定在会议开始时麦克风将处于活动状态的设备。 只有一 (设备Teams 会议室设备) 可以将此字段设置为 ，而其余设备必须将此字段设置为 以避免音频回声和 `true` `false` 反馈。</li><li><b>enabled</b> 确定会议参与者是否可以打开或关闭麦克风。 将 **"音频默认值** "设置为 的设备应将此设置设置为 ，以便参与者不会意外打开麦克风并 `false` `false` 引发音频回声或反馈。<p>如果 **"音频** 默认值"设置为 ，则忽略"启用音频"设置，参与者可以将麦克风设为静音 `true` 或取消静音。 </li></ul>                        |
| \<Video\>                                   | 布尔值&#x2777;            |                | 控制设备上Teams 会议室配置。 此元素具有两个属性：<br><ul><li><b>default</b> 确定在会议开始时相机将在哪个设备上处于活动状态。 为获得最佳体验，建议仅将Teams 会议室设置为 ，而所有其他 `true` 设备都设置为 `false` 。</li><li><b>enabled</b> 确定会议参与者是否可以打开或关闭摄像机。 可以在事件参与者想要共享不同视频透视图的其他任何设备上将 (设置为 ，例如，如果参与者正在使用 Surface Hub `true` 白板) 。 如果不希望参与者在设备上打开或关闭摄像机，请将其设置为 `false` 。<p> 如果 **"视频** 默认值"设置为 ，则忽略"启用视频"设置，参与者 `true` 可以打开或关闭摄像机。 </li></ul> |
| \<Whiteboard\>                              | 布尔值&#x2777;            |                | 控制设备上白板Teams 会议室配置。 此元素具有两个属性：<br><ul><li><b>default</b> 确定启动会议时白板将在哪个设备上处于活动状态。 为获得最佳体验，我们建议将Teams 会议室设置为 ，并使用白板 `false` 上的Surface Hub。</li><li><b>enabled</b> 确定会议参与者是否可以打开或关闭白板。 如果不希望参与者在设备上打开或关闭白板，请将其设置为 `false` 。<p> 如果 **Whiteboard 默认值** 设置为 `true` ，则忽略 **启用白板** 的设置，参与者可以打开或关闭白板。</li></ul>                                                                                                                                                   |

&#x2776;所有一级元素都是可选的。 如果省略第一级元素，则其所有子参数在设备上保持不变。
  
&#x2777;布尔标志可以是：true、false、0 或 1。 将布尔值或数值留空会使 XML 格式不正确，并防止更改设置。
  
&#x2778;如果字符串参数存在且为空，且空值有效，则设备上将清除该参数。
  
## <a name="manage-console-settings-with-an-xml-configuration-file"></a>使用 XML 配置文件管理控制台设置

启动时，如果Microsoft Teams 会议室找到名为 SkypeSettings.xml 的 XML 文件，它会应用 XML 文件指示的配置设置，然后删除该 `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState` XML 文件。
  
根据企业Microsoft Teams 会议室设备数以及选择管理方式对其进行配置，有几种方法可以放置 XML 配置文件。 文件推送到控制台之后，重启以处理配置更改。 成功处理 XML 配置文件后会将其删除。 以下部分讨论了Microsoft Teams 会议室设备的建议管理方法：
  
- [为用户配置组Microsoft Teams 会议室](rooms-operations.md#GroupPolicy)
- [使用 PowerShell](rooms-operations.md#RemotePS) 和 [配置文件项进行远程管理](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc772536(v=ws.11))

你可以使用你喜欢的任何方法，只要你能传输文件并在控制台设备上触发重启即可。 该文件必须是设备的本地用户帐户可读、可写和可删除的。 最好是它归该用户所有，并且拥有授予该用户的完整权限。 如果未正确设置文件权限，软件可能无法应用设置，可能无法在成功处理后删除文件，甚至可能会崩溃。
  
## <a name="supported-meeting-modes-app-version-49"></a>支持的会议模式应用版本 4.9

**Skype for Business (默认) Microsoft Teams**

| XML 表示法                | XML 值      |
|----------------------------|---------------|
| \<TeamsMeetingsEnabled>     |   True         |
| \<SfbMeetingEnabled>        |   True         |
| \<IsTeamsDefaultClient>     |   False        |

**Skype for Business和Microsoft Teams (默认)**

| XML 表示法                | XML 值      |
|----------------------------|---------------|
| \<TeamsMeetingsEnabled>    |   True         |
| \<SfbMeetingEnabled>        |   True         |
| \<IsTeamsDefaultClient>     |   True        |

**仅 Skype for Business**

| XML 表示法                | XML 值      |
|----------------------------|---------------|
| \<TeamsMeetingsEnabled>    |   False         |
| \<SfbMeetingEnabled>        |   True         |
| \<IsTeamsDefaultClient>     |   False        |

**Microsoft Teams仅**

| XML 表示法                | XML 值      |
|----------------------------|---------------|
| \<TeamsMeetingsEnabled>    |   True         |
| \<SfbMeetingEnabled>        |   False         |
| \<IsTeamsDefaultClient>     |   True        |


## <a name="supported-meeting-modes-app-version-48-or-lower"></a>支持的会议模式应用版本 4.8 或更低版本

**Skype for Business (默认) Microsoft Teams**

| XML 表示法                | XML 值      |
|----------------------------|---------------|
|  \<TeamsMeetingsEnabled>     |   True         |
|  \<IsTeamsDefaultClient>     |   False        |

**Skype for Business和Microsoft Teams (默认)**

| XML 表示法                | XML 值      |
|----------------------------|---------------|
|  \<TeamsMeetingsEnabled>     |   True         |
|  \<IsTeamsDefaultClient>     |   True         |

**仅 Skype for Business**

| XML 表示法                | XML 值      |
|----------------------------|---------------|
|  \<TeamsMeetingsEnabled>     |   False         |
|  \<IsTeamsDefaultClient>     |   False         |

## <a name="custom-theme-images"></a>自定义主题图像

<a name="Themes"> </a>

自定义主题图像文件必须放置在 `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState` 文件夹中。 在 变量中输入文件名和 \<CustomThemeImageUrl\> 扩展名。
  
图像文件应正好为 3840X1080 像素，并且必须是以下文件格式之一：jpg、jpeg、png 和 bmp。 如果你的组织需要自定义图像，图形设计人员可以使用自定义 [主题 Photoshop 模板](../downloads/ThemingTemplateMicrosoftTeamsRooms_v2.1.psd)。 它包含有关各种用户界面元素相对于主题图像其余部分位置以及主机和显示器上显示哪些区域的详细信息。
  
XML 配置文件必须在设备启动时更新以识别主题图像。 处理并删除新的 XML 文件后，主题图形文件将从 目录中删除。

## <a name="locate-the-content-camera-usb-instance-path"></a>找到内容相机 USB 实例路径

查找实例路径：

1. 转到Windows主机上的Microsoft Teams 会议室设置。
2. 输入管理员密码。
3. 在命令提示符下，键入 `devmgmt.msc` 以启动设备管理器。
4. 在 **"设备管理器**"中，查看" **图像处理设备** "节点并找到内容相机。
5. 右键单击相机，然后打开"属性 **"。**
6. 选择" **详细信息** "选项卡，并找到 **下拉列表** 中的"设备实例路径"属性。
7. 显示的值是在 XML 配置文件中设置的设备实例路径。 在 XML 中指定路径时，请将与号 (&) 替换为 `&amp;` 。

## <a name="see-also"></a>另请参阅

[内容照相机](content-camera.md)

[管理 Microsoft Teams 会议室](rooms-manage.md)

[配置文件项](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc772536(v=ws.11))
