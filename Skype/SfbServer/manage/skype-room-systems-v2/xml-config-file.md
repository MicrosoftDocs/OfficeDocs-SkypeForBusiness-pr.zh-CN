---
title: 使用 XML 配置文件远程管理 Skype 会议室系统 v2 控制台设置
ms.author: jambirk
author: jambirk
ms.reviewer: davgroom
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: df418e25-81fd-474d-be16-5cd1ac8145cc
description: 本文讨论远程管理的 Skype 会议室系统 v2 设备，包括应用自定义主题使用的默认设置。
ms.openlocfilehash: 55a2dc3de11c4fbe8540740a52fe29a377264545
ms.sourcegitcommit: b265545216ff36772d5dc2df381a9046bc71098e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/13/2018
ms.locfileid: "23965973"
---
# <a name="manage-a-skype-room-systems-v2-console-settings-remotely-with-an-xml-configuration-file"></a>使用 XML 配置文件远程管理 Skype 会议室系统 v2 控制台设置
 
本文讨论远程管理的 Skype 会议室系统 v2 设备，包括应用自定义主题使用的默认设置。
  
通过更新主 XML 文件并将副本发送到你管理的控制台，你可以更改远程管理的设备的默认设置。 本文讨论如何创建此文件，并关联到有关如何将其按需放置在远程管理的设备上的讨论。 使用此方法，您还可以实现自定义主题上您 Skype 会议室系统 v2 控制台。 
  
## <a name="creating-an-xml-configuration-file"></a>创建 XML 配置文件

下表介绍此示例 SkypeSettings.xml （这是所需的文件名称） 中所示的元素配置文件。 
  
```
<SkypeSettings>
  <AutoScreenShare>true</AutoScreenShare>
  <HideMeetingName>true</HideMeetingName>
  <UserAccount>
             <SkypeSignInAddress>RanierConf@contoso.com</SkypeSignInAddress>
             <ExchangeAddress>RanierConf@contoso.com</ExchangeAddress>
             <DomainUsername>Seattle\RanierConf</DomainUsername>
             <Password>password</Password>
             <ConfigureDomain>domain1, domain2</ConfigureDomain>
  </UserAccount>    
  <IsTeamsDefaultClient>false</IsTeamsDefaultClient>
  <BluetoothAdvertisementEnabled>true</BluetoothAdvertisementEnabled>
  <SkypeMeetingsEnabled>false</SkypeMeetingsEnabled> 
  <TeamsMeetingsEnabled>true</TeamsMeetingsEnabled> 
  <DualScreenMode>true</DualScreenMode>
  <SendLogs>                           
             <EmailAddressForLogsAndFeedback>RanierConf@contoso.com</EmailAddressForLogsAndFeedback>
                <SendLogsAndFeedback>true</SendLogsAndFeedback>
  </SendLogs>
  <Devices>
              <MicrophoneForCommunication>Microsoft LifeChat LX-6000</MicrophoneForCommunication>
              <SpeakerForCommunication>Realtek High Definition Audio</SpeakerForCommunication>
              <DefaultSpeaker>Polycom CX5100</DefaultSpeaker>
  </Devices>
  <Theming> 
    <ThemeName>Custom</ThemeName>
       <CustomThemeImageUrl>folder path</CustomThemeImageUrl>
      <CustomThemeColor>
           <RedComponent>100</RedComponent>
           <GreenComponent>100</GreenComponent>
           <BlueComponent>100</BlueComponent>
         </CustomThemeColor>
  </Theming>
</SkypeSettings>
```

如果 XML 文件格式错误（即变量值类型错误、元素无序、元素未闭合，等等），则在处理过程中将应用到发现错误时为止的设置，并忽略文件的其余部分。 XML 中的任何未知元素都将忽略。 如果忽略某个参数，它在设备上将保持不变。 如果参数的值无效，则以前的值保持不变。
  
**XML 元素**
 
|元素|类型|等级|用法|
|:--- |:--- |:--- |:--- |
|\<SkypeSettings\>   |所有元素的容器。   ||必需。   |
| \<AutoScreenShare\>  |布尔值和 #x 2777;  |第一个链接 #x 2776;  | 如果为 true，则启用自动屏幕共享。  |
|\<HideMeetingName\>   |布尔值和 #x 2777;  |第一个链接 #x 2776;  |如果为 true，则隐藏会议名称。   |
|\<用户帐户\>   |容器   |第一个链接 #x 2776;  |凭据参数的容器。   登录地址、 Exchange 地址或电子邮件地址通常是相同的如 RanierConf<span></span>@contoso.com。   |
|\<SkypeMeetingsEnabled\>  |布尔值和 #x 2777;  |第一个链接 #x 2776;  |默认为启用。   |
|\<SkypeSignInAddress\>   |字符串和 #x 2778;  ||控制台的 Skype for Business 设备帐户的登录名。   |
|\<ExchangeAddress\>   |字符串和 #x 2778;  ||控制台的 Exchange 设备帐户的登录名。   如果忽略 ExchangeAddress，则不会自动重用 SkypeSignInAddress。   |
|\<DomainUsername\>   |字符串和 #x 2778;  ||控制台设备的域和用户名，例如 Seattle\RanierConf。   |
|\<密码\>   |String 3  || 密码参数是用于 Skype for Business 设备帐户登录的相同密码。  |
| \<ConfigureDomain\>  |字符串和 #x 2778;  ||你可以列出多个域，以逗号分隔。   |
|\<TeamsMeetingsEnabled\>   |布尔值和 #x 2777;  |第一个链接 #x 2776;  |默认为禁用。 <br/> <br/> XML 文件被视为格式不正确，如果两个\<SkypeMeetingsEnabled\>和\<TeamsMeetingsEnabled\>被禁用，但它并可接受已启用同时这两个设置。   |
|\<IsTeamsDefaultClient > |布尔值和 #x 2777;  |第一个链接 #x 2776;  |默认为禁用。 |
|\<BluetoothAdvertisementEnabled > |布尔值和 #x 2777;  |第一个链接 #x 2776;  |默认为启用。 |
|\<DualScreenMode\>  |布尔值和 #x 2777;  |第一个链接 #x 2776;  |如果为 true，则启用双屏幕模式。 否则设备将使用单屏模式。   |
|\<SendLogs\>   |容器   |第一个链接 #x 2776;  ||
|\<EmailAddressForLogsAndFeedback\>   |字符串和 #x 2778;  ||这会设置一个可选的电子邮件地址，当“提供反馈”窗口出现时，日志可发送到此地址。   |
|\<SendLogsAndFeedback\>   |布尔值和 #x 2777;  || 如果为 true，将日志发送到域。如果为 false，仅将反馈发送给管理员（不发送日志）。  |
| \<设备\>  |容器   |第一个链接 #x 2776;  | 子元素中的已连接音频设备名称与设备管理器应用中列出的值相同。 配置可能包含目前系统中不存在的设备，例如当前未连接到控制台的 A/V 设备。 可能会为各个设备保留配置。  |
|\<MicrophoneForCommunication\>   |字符串和 #x 2778;  ||设置将在会议中用作录音设备的麦克风。   |
|\<SpeakerForCommunication\>   |字符串和 #x 2778;  ||用作会议扬声器的设备。 此设置用于设置将在通话中用于接收音频的扬声器设备。   |
|\<DefaultSpeaker\>   |字符串和 #x 2778;  ||用于播放来自 HDMI 摄入源的音频的设备。   |
| \<主题设置\>  |容器   |第一个链接 #x 2776;  |可以使用 XML 文件应用的一项功能是为组织设置自定义主题。 您将能够指定主题名称、 背景图像和颜色。   |
|\<ThemeName\>   |字符串和 #x 2778;  || 用于识别客户端上的主题。 主题名称选项包括“默认”、提供的预设主题之一或“自定义”。 <br/>  自定义主题名称应该始终使用*自定义*的名称。 可以在控制台上将客户端 UI 设置为“默认”或预设主题之一，但应用自定义主题只能由管理员远程设置。 <br/>  预设主题包括： <br/>  默认 <br/>  蓝色波浪 <br/>  数字丛林 <br/>  追梦人 <br/>  莱姆汁 <br/>  完美像素 <br/>  路线图 <br/>  夕阳 <br/>  若要禁用当前主题，用于 ThemeName 中的"无主题"。  |
|\<CustomThemeImageUrl\>   |字符串和 #x 2778;  ||使用自定义主题时为必填，否则为可选。 自定义主题图像，请参阅下面的详细信息的[自定义主题图像](xml-config-file.md#Themes)部分。  |
|\<CustomThemeColor\>   |容器   ||容器\<RedComponent\>， \<GreenComponent\>，和\<BlueComponent\>值。 如果使用自定义主题，这些值为必填。   |
|\<RedComponent\>   |字节 (0-255)   ||代表红色组件。   |
|\<GreenComponent\>   |字节 (0-255)   ||代表绿色组件。   |
|\<BlueComponent\>   |字节 (0-255)   ||代表蓝色组件。   |
| | | |
   
& #x 2776;所有第一级元素都是可选的。 如果省略第一级元素，则它的所有子参数保持不变的设备上。
  
& #x 2777;一个布尔型标志可以是以下任一： true、 false，0 或 1。 Boolean 或留空的数值可能表示 XML 格式不正确，因此这些设置没有变化。
  
 & #x 2778;如果字符串参数，显示为空，和空是有效的值是在设备上清除该参数。
  
## <a name="manage-console-settings-using-an-xml-configuration-file"></a>使用 XML 配置文件管理控制台设置

在启动时，如果找到了一个名为 SkypeSettings.xml **C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState**，位置的 XML 文件的 Skype 会议室系统 v2 控制台它将应用配置设置由 XML 文件，然后删除 XML 文件。
  
您的企业具有根据多少 Skype 会议室系统 v2 设备和如何选择管理对它们进行配置，有多种方法来将 XML 配置文件。 文件推送到控制台之后，重启以处理配置更改。 成功处理 XML 配置文件后会将其删除。 建议的 Skype 会议室系统 v2 设备管理方法如下所述：
  
- [为 Skype 会议室系统 v2 配置组策略](room-systems-v2-operations.md#GroupPolicy)
    
- [远程管理使用 PowerShell](room-systems-v2-operations.md#RemotePS)和[配置文件项](https://technet.microsoft.com/library/cc772536%28v=ws.11%29.aspx)
    
你可以使用你喜欢的任何方法，只要你能传输文件并在控制台设备上触发重启即可。 该文件必须可读取、 写入和删除无法由设备的本地用户帐户 （最好应由拥有并向用户授予了完全权限）。 如果文件权限设置不正确，软件可能无法应用设置，成功处理后无法删除文件，甚至可能崩溃。
  
## <a name="custom-theme-images"></a>自定义主题图像
<a name="Themes"> </a>

必须将自定义主题图像文件放在**C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState**，只需输入文件名和扩展名在\<CustomThemeImageUrl\>变量。
  
图像文件应为 3840X1080 像素，且必须为下列文件格式之一：jpg、jpeg、png 和 bmp。 如果您的组织的自定义图像，图形设计器将查找我们的[自定义主题 Photoshop 模板](https://go.microsoft.com/fwlink/?linkid=870441)有用。 它上放置主题图像中的各种元素的位置和控制台和显示上显示哪些区域包含更多详细信息。
  
XML 配置文件必须在设备启动时更新以识别主题图像。处理和删除新 XML 文件后，将从目录中删除主题图形文件。
  
## <a name="see-also"></a>另请参阅


[管理 Skype 会议室系统 v2](skype-room-systems-v2.md)

[配置文件项](https://technet.microsoft.com/library/cc772536%28v=ws.11%29.aspx)
