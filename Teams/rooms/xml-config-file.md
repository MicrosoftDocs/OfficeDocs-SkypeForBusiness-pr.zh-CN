---
title: 远程管理Microsoft Teams 会议室设备设置
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
- Teams_ITAdmin_Rooms
ms.custom:
- seo-marvel-mar2020
description: 远程管理Microsoft Teams 会议室设备使用的默认设置，包括应用自定义主题和创建主设置文件。
ms.openlocfilehash: 74ae005ceae3c17d64403990eda067e3d8bd7cfc
ms.sourcegitcommit: 9a9168d5c40bbb0cceaf3ffd11eb104c137f26b3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/03/2022
ms.locfileid: "67590159"
---
# <a name="manage-a-microsoft-teams-rooms-console-settings-remotely-with-an-xml-configuration-file"></a>使用 XML 配置文件远程管理Microsoft Teams 会议室控制台设置

本文介绍对Microsoft Teams 会议室设备使用的默认设置的远程管理，包括应用自定义主题。 它讨论如何创建主设置文件，以及有关如何根据需要将其放置在Teams 会议室的讨论链接。
  
可以通过更新主 XML 文件并将副本发送到远程Teams 会议室设备来更改Teams 会议室的默认设置。 
  
## <a name="create-an-xml-configuration-file"></a>创建 XML 配置文件

任何文本编辑器都可用于创建设置文件。 **XML Elements** 表说明了此示例中显示的元素SkypeSettings.xml (配置文件) 所需的文件名。
  
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
  <SingleFoRDefaultContentLayout>1</SingleFoRDefaultContentLayout>
  <DefaultFoRExperience>0</DefaultFoRExperience>
  <EnablePublicPreview>false</EnablePublicPreview>
  <NoiseSuppressionDefault>1</NoiseSuppressionDefault>
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
  <EnableResolutionAndScalingSetting>true</EnableResolutionAndScalingSetting> 
  <MainFoRDisplay> 
      <MainFoRDisplayResolution>1920,1080</MainFoRDisplayResolution> 
      <MainFoRDisplayScaling>100</MainFoRDisplayScaling> 
  </MainFoRDisplay> 
  <ExtendedFoRDisplay> 
      <ExtendedFoRDisplayResolution>1920,1080</ExtendedFoRDisplayResolution> 
      <ExtendedFoRDisplayScaling>100</ExtendedFoRDisplayScaling> 
  </ExtendedFoRDisplay>  
  <EnableDeviceEndToEndEncryption>false</EnableDeviceEndToEndEncryption>
  <SplitVideoLayoutsDisabled>false</SplitVideoLayoutsDisabled>
</SkypeSettings>
```

如果变量值类型错误、元素无序、元素未封闭或发现另一个错误，则 XML 文件 *格式不正确*。 在处理格式错误的 XML 文件时，将应用到发生错误的点的设置，然后忽略该文件的其余部分。 XML 中的任何未知元素都将忽略。 如果忽略某个参数，它在设备上将保持不变。 如果参数值无效，则其以前的值保持不变。
  
**XML 元素**

| 元素                                     | 类型                        | 等级          | 用法                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
|:--------------------------------------------|:----------------------------|:---------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `<SkypeSettings>`                           | 所有元素的容器。 |                | 必需。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| `<AutoScreenShare>`                         | 布尔&#x2777;            | 第一&#x2776; | 如果为 true，则启用自动屏幕共享。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| `<HideMeetingName>`                         | 布尔&#x2777;            | 第一&#x2776; | 如果为 true，则隐藏会议名称。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| `<UserAccount>`                             | 容器                   | 第一&#x2776; | 凭据参数的容器。 登录地址、Exchange 地址或电子邮件地址通常相同，例如 RainierConf<span></span>@contoso.com。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| `<SkypeSignInAddress>`                      | 字符串&#x2777;             |                | 控制台的 SfB 或 Teams 设备帐户的登录名称。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| `<ExchangeAddress>`                         | 字符串&#x2778;            |                | 控制台 Exchange 设备帐户的登录名称。 如果省略 ExchangeAddress，则不会自动重复使用 SkypeSignInAddress。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| `<DomainUsername>`                          | 字符串&#x2777;            |                | 控制台设备的域和用户名，例如 Seattle\RainierConf。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| `<Password>`                                | 字符串&#x2778;            |                | 密码参数是用于 Skype for Business 设备帐户登录的相同密码。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| `<ConfigureDomain>`                         | 字符串&#x2777;            |                | 你可以列出多个域，以逗号分隔。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| `<ModernAuthEnabled>`                        | 布尔&#x2777;            |                | 默认情况下处于禁用状态。 <br/> <br/>设置为 true 时，Microsoft Teams 会议室应用程序仅使用新式身份验证连接到资源，不会回退到基本身份验证。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| `<TeamsMeetingsEnabled>`                    | 布尔&#x2777;            | 第一&#x2776; | 默认情况下处于禁用状态。 <br/> <br/> 如果 `<SkypeMeetingsEnabled>` 同时禁用 XML 文件，`<TeamsMeetingsEnabled>` 则 XML 文件的格式不正确，但同时启用这两个设置是可以接受的。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| `<SfbMeetingEnabled>`                       | 布尔&#x2778;            | 第一&#x2776; | 默认情况下处于禁用状态。
| `<IsTeamsDefaultClient>`                     | 布尔&#x2777;            | 第一&#x2776; | 默认为启用。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| `<WebexMeetingsEnabled>`                    | 布尔&#x2777;            | 第一&#x2776; | 默认情况下处于禁用状态。 <br/> <br/> 如果为 true，则为 Cisco Webex 会议启用直接来宾加入体验。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| `<ZoomMeetingsEnabled>`                     | 布尔&#x2777;            | 第一&#x2776; | 默认情况下处于禁用状态。 <br/> <br/> 如果为 true，则为 Zoom 会议启用了直接来宾加入体验。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| `<UseCustomInfoForThirdPartyMeetings>`      | 布尔&#x2777;            | 第一&#x2776; | 默认禁用并使用会议室帐户信息加入第三方会议。 <br/> <br/> 如果此值设置为 true，则必须指定这两个 `<CustomDisplayNameForThirdPartyMeetings>`值， `<CustomDisplayEmailForThirdPartyMeetings>` 必须指定。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| `<CustomDisplayNameForThirdPartyMeetings>`  | 字符串&#x2778;            | 第一&#x2776; | 指定用于加入第三方会议的来宾名称。 第三方服务会在其体验中显示此数据，并可能存储在其服务中。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| `<CustomDisplayEmailForThirdPartyMeetings>` | 字符串&#x2778;            | 第一&#x2776; | 指定用于加入第三方会议的来宾电子邮件。 第三方服务会在其体验中显示此数据，并可能存储在其服务中。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| `<BluetoothAdvertisementEnabled>`            | 布尔&#x2777;            | 第一&#x2776; | 默认为启用。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| `<AutoAcceptProximateMeetingInvitations>`    | 布尔&#x2777;            | 第一&#x2776; | 如果为 true，则会自动接受基于邻近的会议。 默认情况下处于禁用状态。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| `<AutoExitMeetingEnabled>`                   | 布尔&#x2777;            | 第一&#x2776; | 如果为 true，则设备将自动退出会议（如果它是会议中最后一位参与者）。  默认情况下处于禁用状态。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| `<DualScreenMode>`                          | 布尔&#x2777;            | 第一&#x2776; | 如果为 true，则启用双屏模式。 否则，设备将使用单屏模式。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| `<DuplicateIngestDefault>`                  | 布尔&#x2777;            | 第一&#x2776; | 如果为 true，则在会议结束时，内容以双屏模式显示在两个屏幕上。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| `<DisableTeamsAudioSharing>`                | 布尔&#x2777;            | 第一&#x2776; | 设置为 true 以禁用 Teams 会议中会议参与者的 HDMI 音频共享。 默认为 false。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| `<FrontRowEnabled>`                          | 布尔&#x2777;            | 第一&#x2776; | 默认为启用。 如果为 false，则禁用前行。
| `<DefaultFoRExperience>`                     | 布尔&#x2777;            | 第一&#x2776; | 默认情况下，库视图。 放置 1 以将默认布局从库视图更改为前行。
| `<SingleFoRDefaultContentLayout>`           | String                      |                 | 在单一显示模式下，只能在 Content+people 和 Content 之间设置默认布局：<br><ul><li><b>0</b> 仅限内容</li><li><b>1</b> 个 Content+人员 (默认) </li></ul>|
| `<EnablePublicPreview>`                     | 布尔&#x2777;            | 第一&#x2776; | 默认情况下处于禁用状态。 如果为 true，则启用公共预览，最终用户可以在启用Teams 会议室时访问公共预览版中的功能。 有关详细信息，请参阅 [Windows 上Microsoft Teams 会议室的公共预览](../public-preview-doc-updates.md#public-preview-for-microsoft-teams-rooms-on-windows)版。 |
| `<NoiseSuppressionDefault>`                 | String                      | 第一&#x2776; | 控制 Teams 中的干扰抑制级别。<br><ul><li><b>0</b> 关闭。 仅使用 OEM 提供的干扰抑制。</li><li><b>1</b> 自动 (默认) 。 Teams 根据本地噪音决定最佳降噪级别。</li><li><b>2</b> 低。 抑制低水平的持久性背景噪音，如计算机风扇或空调。</li><li><b>3</b> 高。 抑制所有不是语音的背景声音。</li></ul>
| `<CortanaWakewordEnabled>`                  | 布尔&#x2777;            | 第一&#x2776; | 设置为 true 以启用 Cortana 唤醒词“Hey Cortana”。 除非你的国家或地区支持 Cortana 服务，并且连接的音频外围设备支持 Cortana，否则此设置没有任何效果。 默认为 false。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| `<SendLogs>`                                | 容器                   | 第一&#x2776; |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| `<EmailAddressForLogsAndFeedback>`          | 字符串&#x2778;            |                | 设置一个可选的电子邮件地址，当“提供反馈”窗口出现时，可以将日志发送到该地址。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| `<SendLogsAndFeedback>`                     | 布尔&#x2777;            |                | 如果为 true，将日志发送到域。如果为 false，仅将反馈发送给管理员（不发送日志）。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| `<Devices>`                                 | 容器                   | 第一&#x2776; | 子元素中的已连接音频设备名称与设备管理器应用中列出的值相同。 配置可能包含目前系统中不存在的设备，例如当前未连接到控制台的 A/V 设备。 可能会为各个设备保留配置。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| `<MicrophoneForCommunication>`              | 字符串&#x2778;            |                | 设置会议中用作录制设备的麦克风。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| `<SpeakerForCommunication>`                 | 字符串&#x2778;            |                | 用作会议扬声器的设备。 此设置用于设置呼叫中使用的扬声器设备。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| `<DefaultSpeaker>`                          | 字符串&#x2778;            |                | 用于播放来自 HDMI 摄入源的音频的设备。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| `<ContentCameraId>`                          | 字符串&#x2778;            |                | 定义在会议室中配置的用于在会议中共享模拟白板内容的相机的实例路径。 请参阅 [“查找内容相机 USB 实例”路径](#locate-the-content-camera-usb-instance-path)。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| `<ContentCameraInverted>`                    | 布尔&#x2777;            |                | 指定是否对内容相机进行物理倒置安装。 对于支持自动旋转的内容相机，请指定 false。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| `<ContentCameraEnhancement>`                 | 布尔&#x2777;            |                | 在默认)  (设置为 true 时，内容相机图像会以数字方式增强：检测到白板边缘并选择适当的缩放，增强墨迹线条，并使白板上写入的人员变得透明。  <br><br> 如果打算将原始视频源发送给会议参与者，以获取空格，其中不使用笔绘制白板，而是使用相机显示便笺、海报或其他媒体，则设置为 false。                                                                                                                                                                                                                                                                                                                                                                                             |
| `<Theming>`                                 | 容器                   | 第一&#x2776; | 可与 XML 文件一起应用的功能之一是组织的自定义主题。 可以指定主题名称、背景图像和颜色。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| `<ThemeName>`                               | 字符串&#x2778;            |                | 用于识别客户端上的主题。 主题名称选项包括“默认”、提供的预设主题之一或“自定义”。 <br/>  自定义主题名称始终使用自 *定义* 名称。 可以在控制台上将客户端 UI 设置为默认设置或预设之一，但管理员必须远程设置自定义主题的使用。 <br/>  预设主题包括： <br/>  默认 <br/>  蓝色波浪 <br/>  数字丛林 <br/>  追梦人 <br/>  莱姆汁 <br/>  完美像素 <br/>  路线图 <br/>  夕阳 <br/>  若要禁用当前主题，请对 ThemeName 使用“无主题”。                                                                                                                                                                                                                                                                               |
| `<CustomThemeImageUrl>`                     | 字符串&#x2778;            |                | 自定义主题是必需的，否则为可选。 仅输入文件名。   有关自定义主题图像的详细信息，请参阅 [“自定义主题图像](xml-config-file.md#Themes) ”部分。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| `<CustomThemeColor>`                        | 容器                   |                | 用于和`<GreenComponent>``<BlueComponent>`值的`<RedComponent>`容器。 这些值是必需的，但不会影响主题颜色。 请指定介于 0-255 之间的任何值。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| `<RedComponent>`                            | 字节 (0-255)                |                | 代表红色组件。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| `<GreenComponent>`                          | 字节 (0-255)                |                | 代表绿色组件。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| `<BlueComponent>`                           | 字节 (0-255)                |                | 代表蓝色组件。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| `<CoordinatedMeetings>`                     | 布尔&#x2777;            | 第一&#x2776; | 协调会议的配置元素的容器。 此元素具有一个属性：<ul><li><b>启用</b> 确定 Teams 是否配置为与其他设备一起参加协调会议。</li></ul>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| `<TrustedAccounts>`                         | String                      |                | 这是设备应接受会议加入请求的每个Teams 会议室设备或 Surface Hub 的逗号分隔的 UPN 列表，或者应向其发送会议加入请求。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| `<Settings>`                                | 容器                   |                | 协调会议的配置音频和视频配置元素的容器。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| `<Audio>`                                   | 布尔&#x2777;            |                | 控制Teams 会议室设备上的音频配置。 此元素具有两个属性：<br><ul><li><b>默认</b> 确定会议开始时麦克风将处于活动状态的设备。 只有一个设备 (通常Teams 会议室设备) 可以设置`true`此字段，而其余设备必须设置此字段以避免`false`音频回显和反馈。</li><li><b>启用</b> 确定会议中的参与者是否可以打开或关闭麦克风。 **将音频默认** 设置为`false`的设备应设置`false`此设置，以便参与者不能意外打开麦克风并引起音频回显或反馈。<p>如果 **音频默认** 设置为 `true`“音频”，则忽略 **已启用音频** 的设置，参与者可以静音或取消静音麦克风。</li></ul>                        |
| `<Video>`                                   | 布尔&#x2777;            |                | 控制Teams 会议室设备上的视频配置。 此元素具有两个属性：<br><ul><li><b>默认</b> 确定在会议开始时相机将处于活动状态的设备。 为了获得最佳体验，我们建议仅将Teams 会议室设备设置为`true``false`所有其他设备。</li><li><b>启用</b> 确定会议中的参与者是否可以打开或关闭相机。 可以在事件参与者希望共享不同视频透视的任何其他设备上将其设置 `true` 为 (例如参与者使用 Surface Hub 白板) 。 如果不希望参与者在设备上打开或关闭相机，请将其设置为 `false`。<p> 如果 **视频默认** 设置为 `true`“视频”，则忽略 **启用视频** 的设置，参与者可以打开或关闭相机。</li></ul> |
| `<Whiteboard>`                              | 布尔&#x2777;            |                | 控制Teams 会议室设备上的白板配置。 此元素具有两个属性：<br><ul><li><b>默认</b> 确定会议开始时白板将处于活动状态的设备。 为了获得最佳体验，我们建议将Teams 会议室设备设置为`false`，并在 Surface Hub 上使用白板。</li><li><b>启用</b> 确定会议中的参与者是否可以打开或关闭白板。 如果不希望参与者在设备上打开或关闭白板，请将其设置为 `false`。<p> 如果 **将 Whiteboard 默认** 设置为 `true`，则将忽略 **启用 Whiteboard** 的设置，并且参与者可以打开或关闭白板。</li></ul>                                                                                                                                                   |
| `<EnableResolutionAndScalingSetting>` | 布尔&#x2777; | 第一&#x2776; | 默认情况下，它将被禁用。 如果要更改会议室前面的分辨率和缩放，请将其设置为 true。 如果为 true，则将应用显示分辨率和缩放设置。 启用此设置后，此设置将影响 Main FoR 和扩展 FoR。 |
| `<MainFoRDisplay>` | 容器 |第一&#x2776; | 如果设备使用单一显示模式，请使用此容器。<br><br>在双显示模式下，会议室主前 (FoR) 是一个屏幕，其中时钟 (会议) 和会议) 中的自预览视频 (。 `<MainFoRDisplayResolution>` 并且 `<MainFoRDisplayScaling>` 必须一次一起设置。 如果只使用任一 `<MainFoRDisplayResolution>` 或 `<MainFoRDisplayScaling>`，则会忽略它。 |
| `<MainFoRDisplayResolution>` | String | | Width、Height (的输入数值，例如 1920，1080) 。 如果 FoR 不支持它，则会忽略它。|
| `<MainFoRDisplayScaling>` | 数字 | | 缩放的输入数值。 有效值为 100 (建议) 、125、150、175、200、225、250、300、350、400、450 和 500。 如果输入 500 且 FoR 最多支持 300，则会将其设置为 300。|
| `<ExtendedFoRDisplay>` | 容器 |第一&#x2776;| 在双显示模式下，会议室 (FoR) 扩展前部是一个屏幕，可在会议) 中看到共享内容 (。  `<ExtendedFoRDisplayResolution>` 并且 `<ExtendedFoRDisplayScaling>` 必须一次一起设置。 如果只使用任一 `<ExtendedFoRDisplayResolution>` 或 `<ExtendedFoRDisplayScaling>`，则会忽略它。 |
| `<ExtendedFoRDisplayResolution>` | String | |Width、Height (的输入数值，例如：1920，1080) 。 如果 FoR 不支持值，则将忽略该值。 |
| `<ExtendedFoRDisplayScaling>` | 数字 | | 缩放的输入数值。 有效值为 100 (建议) 、125、150、175、200、225、250、300、350、400、450 和 500。 如果输入 500 且 FoR 最多支持 300，则会将其设置为 300。 |
| `<EnableDeviceEndToEndEncryption>` | 布尔&#x2777; | | 默认值为 `false`. 指定 `true` 为一对一 Teams 调用启用端到端加密。 调用方和收件人都需要启用端到端加密才能正常工作。 |
| `<SplitVideoLayoutsDisabled>` |  布尔&#x2777; | | 默认值为 `false`. 此设置仅适用于双显示室。 指定 `true` 在两个屏幕上禁用拆分视频库。 这还会禁用前行布局以及与前行布局关联的任何设置。 |

&#x2776;所有一级元素都是可选的。 如果省略第一级元素，则其所有子参数在设备上保持不变。
  
&#x2777;布尔标志可以是：true、false、0 或 1。 将布尔值或数值留空可能会使 XML 格式不正确，并阻止对设置进行更改。
  
&#x2778;如果存在字符串参数且为空且为空是有效值，则在设备上清除该参数。
  
## <a name="manage-console-settings-with-an-xml-configuration-file"></a>使用 XML 配置文件管理控制台设置

启动时，如果Microsoft Teams 会议室控制台找到名为 SkypeSettings.xml `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState`的 XML 文件，则应用 XML 文件指示的配置设置，然后删除 XML 文件。
  
根据企业拥有的Microsoft Teams 会议室设备数量以及如何选择如何对其进行配置，可通过多种方式放置 XML 配置文件。 文件推送到控制台之后，重启以处理配置更改。 成功处理 XML 配置文件后会将其删除。 建议用于Microsoft Teams 会议室设备的管理方法在以下内容中进行讨论：
  
- [为Microsoft Teams 会议室配置组策略](rooms-operations.md#GroupPolicy)
- [使用 PowerShell 进行远程管理](rooms-operations.md#RemotePS) 并 [配置文件项](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc772536(v=ws.11))

你可以使用你喜欢的任何方法，只要你能传输文件并在控制台设备上触发重启即可。 该文件必须可读、可写且可由设备的本地用户帐户删除。 最好是它由该用户拥有并具有授予该用户的完整权限。 如果文件权限未正确设置，软件可能无法应用设置，在成功处理后可能无法删除文件，甚至可能会崩溃。
  
## <a name="supported-meeting-modes-app-version-49"></a>支持的会议模式应用版本 4.9

**Skype for Business (默认) 和 Microsoft Teams**

| XML 表示法                | XML 值      |
|----------------------------|---------------|
| `<TeamsMeetingsEnabled>`     |   True         |
| `<SfbMeetingEnabled>`        |   True         |
| `<IsTeamsDefaultClient>`     |   False        |

**Skype for Business和 Microsoft Teams (默认)**

| XML 表示法                | XML 值      |
|----------------------------|---------------|
| `<TeamsMeetingsEnabled>`    |   True         |
| `<SfbMeetingEnabled>`        |   True         |
| `<IsTeamsDefaultClient>`     |   True        |

**仅 Skype for Business**

| XML 表示法                | XML 值      |
|----------------------------|---------------|
| `<TeamsMeetingsEnabled>`    |   False         |
| `<SfbMeetingEnabled>`        |   True         |
| `<IsTeamsDefaultClient>`     |   False        |

**仅 Microsoft Teams**

| XML 表示法                | XML 值      |
|----------------------------|---------------|
| `<TeamsMeetingsEnabled>`    |   True         |
| `<SfbMeetingEnabled>`        |   False         |
| `<IsTeamsDefaultClient>`     |   True        |


## <a name="supported-meeting-modes-app-version-48-or-lower"></a>支持的会议模式应用版本 4.8 或更低

**Skype for Business (默认) 和 Microsoft Teams**

| XML 表示法                | XML 值      |
|----------------------------|---------------|
|  `<TeamsMeetingsEnabled>`     |   True         |
|  `<IsTeamsDefaultClient>`     |   False        |

**Skype for Business和 Microsoft Teams (默认)**

| XML 表示法                | XML 值      |
|----------------------------|---------------|
|  `<TeamsMeetingsEnabled>`     |   True         |
|  `<IsTeamsDefaultClient>`     |   True         |

**仅 Skype for Business**

| XML 表示法                | XML 值      |
|----------------------------|---------------|
|  `<TeamsMeetingsEnabled>`     |   False         |
|  `<IsTeamsDefaultClient>`     |   False         |

## <a name="custom-theme-images"></a>自定义主题图像

<a name="Themes"> </a>

自定义主题图像文件必须放置在文件夹中`C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState` 。 在变量中 `<CustomThemeImageUrl>` 输入文件名和扩展名。
  
图像文件应完全为 3840X1080 像素，并且必须是以下文件格式之一：jpg、jpeg、png 和 bmp。 如果你的组织想要自定义映像，图形设计器可以使用 [自定义主题 Photoshop 模板](../downloads/ThemingTemplateMicrosoftTeamsRooms_v2.1.psd)。 它包含有关各种用户界面元素相对于主题图像其余部分的位置以及主机和显示中显示的区域的更多详细信息。
  
XML 配置文件必须在设备启动时更新以识别主题图像。 处理并删除新 XML 文件后，主题图形文件将从目录中删除。

## <a name="locate-the-content-camera-usb-instance-path"></a>找到内容相机 USB 实例路径

若要查找实例路径，请执行以下操作：

1. 转到Microsoft Teams 会议室控制台上的 Windows 设置。
2. 输入管理员密码。
3. 在命令提示符下，键`devmgmt.msc`入以显示设备管理器。
4. 在 **设备管理器** 中，查看 **成像设备** 节点并找到内容相机。
5. 右键单击相机，然后打开 **“属性**”。
6. 选择“ **详细信息”** 选项卡，然后在下拉列表中找到 **设备实例路径** 属性。
7. 显示的值是要在 XML 配置文件中设置的设备实例路径。 在 XML 中指定路径时，请将 ampersand (&) 替换为 `&amp;`。

## <a name="set-front-row-as-the-default-layout"></a>将 Front 行设置为默认布局

如果未在 XML 配置中为会议室设置默认显示布局，默认布局将设置为库。 若要将 Front 行视为默认布局，请添加 `<DefaultFoRExperience>1</DefaultFoRExperience>` 到 XML 配置文件。

最终用户可以在会议期间使用布局选取器从默认显示布局切换。

## <a name="turn-off-front-row"></a>关闭前行

默认情况下，前排已启用。 如果不想允许最终用户在特定的会议室中使用 Front 行，请关闭 Front 行。 为此，请添加 `<FrontRowEnabled>false</FrontRowEnabled>` 到 XML 配置文件。

## <a name="set-front-of-room-scale-and-resolution"></a>设置会议室前刻度和分辨率

若要设置会议室前显示器的规模和分辨率，请使用容器添加 `<EnableResolutionAndScalingSetting>true</EnableResolutionAndScalingSetting>` 到 XML 配置文件 `<MainFoRDisplay>` 。 如果设备使用双显示器，请也包括 `<ExtendedFoRDisplay>` 容器。 

`<MainFoRDisplay>`如果使用单个显示器将两者和`<ExtendedFoRDisplay>`容器一起用于Teams 会议室，`<ExtendedFoRDisplay>`则将忽略该容器。 有关详细信息，请参阅上面的示例 XML 和元素表。

## <a name="see-also"></a>另请参阅

[内容照相机](content-camera.md)

[管理 Microsoft Teams 会议室](rooms-manage.md)

[配置文件项](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc772536(v=ws.11))
