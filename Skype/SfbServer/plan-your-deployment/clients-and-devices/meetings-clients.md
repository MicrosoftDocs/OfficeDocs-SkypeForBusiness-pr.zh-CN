---
title: 'Plan for Meetings clients (Web App and Meetings App) '
ms.author: v-mahoffman
author: cichur
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 2/16/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 31e95e16-f79f-46c6-b123-973fa56a824e
description: 摘要：IT 专业人员应在规划会议Skype for Business Web应用Skype查看 Skype for Business Server 的支持要求。 本文不适合这些应用的用户。
ms.openlocfilehash: 615fff0be39afd41745087d4dae4ea40385e034b
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60762260"
---
# <a name="plan-for-meetings-clients-web-app-and-meetings-app"></a>Plan for Meetings clients (Web App and Meetings App) 
 
**摘要：** IT 专业人员应在规划会议应用的同时Skype for Business Web应用Skype会议应用的支持Skype for Business Server。 本文不适合这些应用的用户。
  
实施部署Skype for Business Server，组织的用户可能会将 Skype for Business客户端作为部署过程的一部分进行安装。 
  
稍后，这些用户可以创建会议并邀请组织外部的用户，并且这些会议被邀请者可能没有任何版本的 Skype for Business 客户端。 当这些用户单击会议邀请的 URL 时，将检测到缺少客户端，并且将要求没有 Skype for Business 客户端的被邀请者下载并安装轻型仅会议客户端，以便他们可以加入会议。
  
> [!NOTE]
> "Skype for Business Web应用 Skype 会议"应用仅在尝试在不登录会议的情况下尝试登录会议Skype for Business。 有关这些应用的用户帮助位于 [https://aka.ms/smahelp](https://aka.ms/smahelp) 。 
  
> [!NOTE]
> 不能预先安装 Skype for Business Web应用 或 Skype 会议应用，但智能手机和平板电脑用户可能会安装他们[](https://products.office.com/skype-for-business/download-app?tab=tabs-1)可用于参加会议的[](https://products.office.com/skype-for-business/download-app?tab=tabs-2)低成本移动客户端。
  
默认情况下，主持会议的服务器将指示用户下载并安装Skype for Business Web应用加入会议。 会议Skype for Business Web应用前端服务器上存储，并发送给与会者。 
  
For Skype for Business Server， Skype Meetings App (on Windows) and Mac版Skype for Business (on Mac) are available as replacements for Skype for Business Web应用 beginning with CU5， but providing the replacement apps requiresEnable Skype [Meetings App to replace Skype for Business Web应用 (Optional) 中所述的其他配置](../../deploy/deploy-clients/deploy-web-downloadable-clients.md#SMA_Enable)。 如果Skype会议应用Mac版Skype for Business，用户将从 Microsoft 365 或 Office 365 内容分发网络 (CDN) 而不是从 Skype for Business 服务器下载应用的最新版本。 对于 Skype for Business Server 2019，Skype会议应用和Mac版Skype for Business是唯一的选项。
  
Skype会议 应用提供了一种简化的浏览器体验，用于下载和安装应用以及加入会议，包括一键加入 Internet Explorer。 Skype会议 应用在可靠性和会议体验Skype for Business Web应用方面进行了许多改进。 
  
> [!NOTE]
> 自 Skype for Business Server 2015 CU5 或更高版本起，使用 Skype for Business Online 召开的会议将不再向无客户端用户发送 Skype for Business Web应用，而是在 Windows) 或 Mac) 上的 Mac版Skype for Business (上发送 Skype 会议应用 (。 从 Skype for Business Server 2015 CU5 或更高版本开始，如果启用 Skype 会议应用以替换[Skype for Business Web应用 (可选) ，](../../deploy/deploy-clients/deploy-web-downloadable-clients.md#SMA_Enable)则无客户端用户Skype会议应用或 Mac版Skype for Business 而不是Skype for Business Web应用。 
  
## <a name="software-requirements"></a>软件要求
<a name="OS-Browser"> </a>

若要使用Skype for Business Web应用，用户必须具有以下支持的操作系统和浏览器组合之一。 
  
**操作系统和最低浏览器支持Skype for Business Web应用**

| 操作系统 | Microsoft Edge | 32 位和 64 位 Internet Explorer 11 或更高版本 | 32 位和 64 位Internet Explorer 10或更高版本 | 32 位和 64 位Internet Explorer 9或更高版本 | Safari 6.2.8 - 11.X 的 32 位和 64 位版本 | 32 位和 64 位版本的 Chrome 18.X 或更高版本 |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Windows 10  <br/> |是  <br/> |是  <br/> |不适用  <br/> |不适用  <br/> |不适用  <br/> |是&#x2778; <br/> |
|Windows 8.1 &#x2776; <br/> |不适用  <br/> |是  <br/> |不适用  <br/> |不适用  <br/> |不适用 <br/> |是&#x2778; <br/> |
|Windows 8 (Intel) &#x2776; <br/> |不适用  <br/> |不适用  <br/> |是  <br/> |不适用 <br/> |不适用  <br/> |是&#x2778; <br/> |
|Windows 7 SP1 &#x2777; <br/> |不适用  <br/> |是  <br/> |否  <br/> |否  <br/> |不适用 <br/>|是&#x2778; <br/> |
|WindowsServer 2008 R2 SP1 &#x2777; <br/> |不适用  <br/> |是  <br/> |是  <br/> |是  <br/> |不适用 <br/>|是&#x2778; <br/> |
|基于 Intel 的 (macOS 10.8) &#x2777; <br/> |不适用  <br/> |不适用  <br/> |不适用  <br/> |不适用  <br/> |是  <br/> |是 <br/> |
   
&#x2776;浏览器Skype for Business Web应用插件需要特定的共享插件，以便使用基于计算机的语音、视频、共享以及查看正在进行的屏幕共享和其他功能。 当与会者加入会议或启动其中一项功能时，可以选择安装共享插件。 在 Windows 8 和 Windows 8.1 上，只有在运行 Internet Explorer 10 或 Internet Explorer 11 桌面版时，才能安装共享插件。 这些功能不适用于非桌面版 Internet Explorer 10 11。 请注意，Firefox 和 Safari 版本 12.0 及更高版本不再受支持。
  
&#x2777; 在受支持的 Windows 7、Windows Server 2008 R2 和 Macintosh 操作系统上，所有功能都可用，包括基于计算机的语音、视频、应用程序查看、应用程序共享、桌面查看和桌面共享。 若要使用这些功能，必须在系统提示时安装插件。 请注意，不再支持 Mac OS X 版本 10.7。  另请注意，Web 应用不会安装在 OS X 10.15 或更高版本上。  我们建议使用最新版本的 Mac版Skype for Business支持匿名加入方案。
  
&#x2778;从 Chrome 访问 Web Windows将启动一个小程序，该程序将在嵌入的 Internet Explorer 框架中加载 Web 应用。 若要正确加载 Web App，此程序Internet Explorer支持的版本之一。
  
> [!NOTE]
> Microsoft 365和Office 365用户可以将Internet Explorer 10或更高版本与Skype for Business。 
  
### <a name="skype-meetings-app"></a>Skype 会议应用

Skype会议应用作为应用在安装了 32 位和 64 位 Internet Explorer 11 或更高版本的 Windows 10、Windows 8.1、Windows 8、Windows 7 的计算机上运行。 
  
有关任何其他依赖项，请参阅支持的平台[Skype会议应用](https://support.office.com/client/results?Shownav=true&amp;lcid=1033&amp;ns=SKFBWA&amp;version=15&amp;omkt=en-US&amp;ver=15&amp;HelpID=SfBWebApp4001)
  
### <a name="skype-for-business-for-mac"></a>Mac 版 Skype for Business

Mac版Skype for Business macOS 版本 10.8 或更高版本的计算机上运行。 

## <a name="hardware-requirements"></a>硬件要求
<a name="OS-Browser"> </a>

计算机硬件要求由操作系统和浏览器决定。 语音和电话功能需要麦克风和扬声器、带麦克风的耳机或与计算机兼容的等效设备。 视频功能需要与计算机兼容的视频设备。 有关视频硬件支持和预期视频质量的详细信息，请参阅Skype for Business[客户端视频分辨率](video-resolutions.md)。
  
## <a name="network-requirements"></a>网络要求
<a name="Network"> </a>

如果 Skype for Business Web应用 或 Skype 会议应用的用户遇到会议连接问题，则其组织的网络基础结构可能未配置为支持[Office 365，](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US)如 Office 365 URL 和 IP 地址范围中所述。 这是会议是由 Skype for Business Online 或 Skype for Business Server。 
  
如果用户处于未如所述配置的网络，则许多应用功能可能工作，也可能不起作用，并且他们可能无法连接到会议。
  
## <a name="supported-meetings-features"></a>支持的会议功能
<a name="BKMK_Conferencing"> </a>

此表比较了 Skype for Business 客户端、Skype for Business Web应用、Skype 会议应用和 Lync Web App 的用户可用的会议功能。 列出了 Lync Web App 以用于功能比较：如果用户在 Lync 2013 服务器上承载会议，则用户将仅下载和使用 Lync Web App。

| 功能 | Skype for Business 2016 或 2019 客户端 | Skype for Business Mac 客户端上 | Skype 会议应用 | Skype for Business Web 应用 | Lync Web App |
|:-----|:-----|:-----|:-----|:-----|:-----|
|添加计算机音频  <br/> |&#x2714;|&#x2714;|&#x2714; (需要插件)   <br/> |&#x2714; (需要插件)   <br/> |&#x2714; (需要插件)   <br/> |
|添加视频  <br/> |&#x2714;|&#x2714;|&#x2714; (需要插件)   <br/> |&#x2714; (需要插件)   <br/> |&#x2714; (需要插件)   <br/> |
|为经过身份验证的参与者将音频切换到电话  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|将音频切换到来宾参与者的电话  <br/> |&#x2714;|&#x2714;|&#x2714;|||
|查看多方视频 (库视图)   <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|基于视频的屏幕共享  <br/> |&#x2714;|&#x2714; <br/> |&#x2714; (仅查看)   <br/> |||
|使用会议中演示者控件  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|访问详细的会议名单  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|参与多方 IM  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|将 IM 消息设置为高重要性  <br/> |&#x2714;|||||
|共享桌面（如果已启用）  <br/> |&#x2714;|&#x2714;|&#x2714; (需要插件)   <br/> |&#x2714; (需要插件)   <br/> |&#x2714; (需要插件)   <br/> |
|共享程序（如果已启用）  <br/> |&#x2714;||&#x2714; (仅在Windows上;需要插件)   <br/> |&#x2714; (仅在Windows上;需要插件)   <br/> |&#x2714; (仅在Windows上;需要插件)   <br/> |
|控制其他用户的共享桌面或程序  <br/> |&#x2714;||&#x2714; (&#x2776; 仅在Windows上;需要插件)   <br/> |&#x2714; (&#x2776; 仅在Windows上;需要插件)   <br/> |&#x2714; (&#x2776; 仅在Windows上;需要插件)   <br/> |
|让其他用户控制你的共享桌面或程序  <br/> |&#x2714;|||||
|添加匿名参与者（如果已启用）  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|按姓名邀请参与者  <br/> |&#x2714;|&#x2714;||||
|按电话号码邀请参与者  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|通过电子邮件邀请参与者  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|使用拨入音频会议  <br/> |&#x2714; &#x2777; |&#x2714; &#x2777; |&#x2714; &#x2777; |&#x2714; &#x2777; |&#x2714; &#x2777; |
|启动"立即开会"会议  <br/> |&#x2714;|&#x2714;||||
|录制会议  <br/> |&#x2714;|||||
|添加和下载附件  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|添加并演示 Microsoft PowerPoint 文件  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|导航 Microsoft PowerPoint文件  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|添加和编辑OneNote会议笔记  <br/> |&#x2714;||仅编辑 (不添加)   <br/> |仅编辑 (不添加)   <br/> |仅编辑 (不添加)   <br/> |
|使用白板  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|发起投票  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Upload与其他人共享的文件  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|安排会议  <br/> |Outlook 或 Skype for Business Web计划程序  <br/> |Outlook 或 Skype for Business Web计划程序  <br/> |Skype for Business Web计划程序  <br/> |Skype for Business Web计划程序  <br/> |Skype for Business Web计划程序  <br/> |
|问答 &amp; 管理器  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|禁用与会者视频  <br/> |&#x2714;|||||
|禁用会议 IM  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|静音受众  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|使每个人都成为与会者  <br/> |&#x2714;|||||
|生成Skype 会议广播  <br/> |&#x2714;|||||
   
 &#x2776;参与者无法控制由 Mac版Skype for Business、Lync for Mac 2011 或 Communicator For Mac 2011 用户共享的桌面。 这同样对在最大 OSX Skype for Business Web应用不起作用。
  
 &#x2777; 对于 Skype for Business Online，此功能需要 Microsoft PSTN 会议、Exchange统一消息或第三方音频会议提供商。
  
 &#x2778; Lync for Mac 2011 客户端在会议Microsoft Office共享 2013 PowerPoint演示文稿时无法查看这些演示文稿Skype for Business Web应用。
  
## <a name="known-issues-and-troubleshooting"></a>已知问题和疑难解答
<a name="BKMK_Conferencing"> </a>

对于最终用户， [这些应用的](https://aka.ms/smahelp) 联机帮助随时可用。 IT 专业人员应注意以下问题：
  
- 如果用户处于未配置为满足网络要求的网络上，则许多应用功能[](meetings-clients.md#Network)可能工作，也可能不起作用，并且他们可能无法连接到会议。
    
- 某些用户可能拥有公司管理的计算机，这些计算机具有安装应用的已禁用权限。 对于这些用户，这两种应用都不是一个选项[](https://products.office.com/skype-for-business/download-app?tab=tabs-1)，但智能手机和[平板电脑](https://products.office.com/skype-for-business/download-app?tab=tabs-2)用户可能无法安装他们可用于参加会议的低成本移动客户端。
    
    其他安装问题也涵盖在帮助 [主题中](https://support.office.com/article/Trouble-installing-the-Skype-for-Business-Web-App-plug-in-958fc5f1-2d6f-42e3-815d-a9516c591274?ui=en-US&amp;rs=en-US&amp;ad=US)。 
    
- 用户首次运行会议应用时可能会看到防火墙警告。 系统可能会提示他们打开端口以优化体验，这可能需要用户可能没有的管理员权限。 应用应仍可运行，用户可以安全地拒绝打开请求的端口。 
    
- 即使 IE[不是ActiveX](https://support.office.com/article/Turn-off-ActiveX-filtering-for-Skype-for-Business-Web-App-b6de8ff6-ac7e-4e2f-b18c-2f13db643c41?ui=en-US&amp;rs=en-US&amp;ad=US)浏览器，Internet Explorer启用 IE。 在Skype for Business Web应用中，ActiveX、视频和屏幕共享需要一个控件（一个向 Web 应用或其他程序添加其他功能的小模块）。
    
- 若要使Skype for Business Web应用某些功能正常工作，必须允许浏览器在计算机或设备上保存 Cookie。 [](https://support.office.com/article/Allow-cookies-for-Skype-Meetings-App-Skype-for-Business-Web-App-2108276b-b5c3-484b-bf2b-dac6eeba4c93)
    
- 你可能需要在[浏览器中启用 JavaScript](https://support.office.com/article/Turn-on-JavaScript-for-Skype-Meetings-App-Skype-for-Business-Web-App-3d997bf9-637c-4fe6-8ee3-9e62bfda52cd)支持，某些Skype for Business Web应用功能可以正常工作。
    
### <a name="aes-support"></a>AES 支持 

自 Skype for Business Server 2015 CU5 起，ASP.NET 4.6 不支持 AES，这可能会导致 Skype 会议应用无法启动。 [由于 4.5 ASP.NET 加密](../security/user-and-client-authentication.md#cryptographic-requirements-due-to-asp-net-45) 要求的详细信息。
  
## <a name="see-also"></a>另请参阅
<a name="BKMK_Conferencing"> </a>

[在客户端部署 Web 可下载Skype for Business Server](../../deploy/deploy-clients/deploy-web-downloadable-clients.md)

[Skype会议应用支持的平台](https://support.office.com/client/results?Shownav=true&amp;lcid=1033&amp;ns=SKFBWA&amp;version=15&amp;omkt=en-US&amp;ver=15&amp;HelpID=SfBWebApp4001)
