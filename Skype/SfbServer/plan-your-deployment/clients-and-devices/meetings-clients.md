---
title: 规划会议客户端（Web 应用程序和会议应用程序）
ms.author: v-lanac
author: lanachin
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 2/16/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 31e95e16-f79f-46c6-b123-973fa56a824e
description: 摘要：在规划 Skype for business Server 时，IT 专业人员应查看 Skype for business Web 应用和 Skype 会议应用的支持要求。 本文不适合这些应用程序的用户。
ms.openlocfilehash: 77633b53c44e28301b21cc2f37240a4a1e459938
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42013445"
---
# <a name="plan-for-meetings-clients-web-app-and-meetings-app"></a>规划会议客户端（Web 应用程序和会议应用程序）
 
**摘要：** 在规划 Skype for business Server 时，IT 专业人员应查看 Skype for business Web 应用和 Skype 会议应用的支持要求。 本文不适合这些应用程序的用户。
  
实施 Skype for Business Server 后，组织的用户可能会在部署过程中安装 Skype for Business 客户端。 
  
稍后，这些用户可能会创建会议并邀请来自组织外部的用户，并且这些会议被邀请者可能没有任何版本的 Skype for Business 客户端。 当这些用户单击会议邀请的 URL 时，将会检测到缺少客户端，且没有 Skype for Business 客户端的被邀请者将被要求下载并安装一个轻型的、仅会议的客户端，以便他们可以加入会议。
  
> [!NOTE]
> Skype for Business Web 应用和 Skype 会议应用仅在尝试登录会议时没有 Skype for business 时可用。 这些应用程序的用户帮助位于[https://aka.ms/smahelp](https://aka.ms/smahelp)。 
  
> [!NOTE]
> 您不能预安装 Skype for Business Web 应用或 Skype 会议应用程序，但[智能手机](https://products.office.com/skype-for-business/download-app?tab=tabs-1)和[平板电脑](https://products.office.com/skype-for-business/download-app?tab=tabs-2)用户可能能够安装可用于参加会议的廉价移动客户端。
  
默认情况下，主持会议的服务器将引导用户下载并安装 Skype for Business Web 应用以加入会议。 Skype for Business Web 应用程序存储在前端服务器上，并发送给会议与会者。 
  
对于 Skype for Business Server，skype 会议应用（在 Windows 上）和 Skype for Business for Mac （基于 Mac）可作为 Skype for business Web 应用程序的替换功能，以 CU5 开头，但提供替换应用程序需要在[启用 Skype 会议应用程序中描述的其他配置来替换 Skype For Business Web app （可选）](../../deploy/deploy-clients/deploy-web-downloadable-clients.md#SMA_Enable)。  如果启用 Skype 会议应用和 Skype for business for Mac，用户将从 Office 365 内容传送网络（CDN）而不是从 Skype for Business 服务器下载最新版本的应用程序。 对于 Skype for business Server 2019，使用 Skype 会议应用程序和 Skype for business for Mac 是唯一的选择。
  
Skype 会议应用提供简化的浏览器体验，可用于下载和安装应用程序并加入会议，包括 Internet Explorer 用户的点击式加入。 Skype 会议应用程序对 Skype for business Web 应用程序的可靠性和会议体验也有很多改进。 
  
> [!NOTE]
> 从 Skype for Business Server 2015 CU5 或更高版本起，使用 Skype for Business Online 举行的会议将不再向 clientless 用户发送 Skype for Business Web 应用，而是发送 Skype 会议应用程序（在 Windows 中）或 Skype for business for Mac （在 Mac 上）。 从 Skype for Business Server 2015 CU5 或更高版本起，如果您[启用 Skype 会议应用程序以替换 skype For Business Web 应用（可选）](../../deploy/deploy-clients/deploy-web-downloadable-clients.md#SMA_Enable)，则 clientless 用户将发送 Skype 会议应用或 skype for Business for Mac 而不是 skype For Business web 应用。 
  
## <a name="software-requirements"></a>软件要求
<a name="OS-Browser"> </a>

若要使用 Skype for Business Web 应用，用户必须具有以下受支持的操作系统和浏览器组合之一。 
  
**适用于 Skype for Business Web 应用的操作系统和最低浏览器支持**

| 操作系统 | Microsoft Edge | 32-和 64-位 Internet Explorer 11 或更高版本 | 32-和 64-位 Internet Explorer 10 或更高版本 | 32-和 64-位 Internet Explorer 9 或更高版本 | 32-和64位版本的 Safari 6.2.8-11. X | 32-和64位版本的 Chrome 18. X 或更高版本 |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Windows 10  <br/> |是  <br/> |是  <br/> |不适用  <br/> |不适用  <br/> |不适用  <br/> |是 &#x2778; <br/> |
|Windows 8.1 &#x2776; <br/> |不适用  <br/> |是  <br/> |不适用  <br/> |不适用  <br/> |不适用 <br/> |是 &#x2778; <br/> |
|Windows 8 （基于 Intel） &#x2776; <br/> |不适用  <br/> |不适用  <br/> |是  <br/> |不适用 <br/> |不适用  <br/> |是 &#x2778; <br/> |
|Windows 7 SP1 &#x2777; <br/> |不适用  <br/> |是  <br/> |否  <br/> |否  <br/> |不适用 <br/>|是 &#x2778; <br/> |
|Windows Server 2008 R2 SP1 &#x2777; <br/> |不适用  <br/> |是  <br/> |是  <br/> |是  <br/> |不适用 <br/>|是 &#x2778; <br/> |
|macOS 10.8 及更高版本（基于 Intel） &#x2777; <br/> |不适用  <br/> |不适用  <br/> |不适用  <br/> |不适用  <br/> |是  <br/> |是 <br/> |
   
&#x2776; Skype for Business Web App 浏览器插件需要特定的共享插件，才能使用基于计算机的语音、视频、共享和查看正在进行的屏幕共享和其他功能。 会议与会者可以选择在加入会议时或在他们启动这些功能之一时安装共享插件。 在 Windows 8 和 Windows 8.1 中，只有在对桌面运行 Internet Explorer 10 或 Internet Explorer 11 时，才能安装共享插件。 这些功能在非桌面版本的 Internet Explorer 10 和11中不可用。 请注意，已不再支持 Firefox 和 Safari 版本12.0 及更高版本。
  
&#x2777; 受支持的 Windows 7、Windows Server 2008 R2 和 Macintosh 操作系统，所有功能均可用，包括基于计算机的语音、视频、应用程序查看、应用程序共享、桌面查看和桌面共享。 若要使用这些功能，必须在出现提示时安装插件。 请注意，Mac OS X 版本10.7 已不再受支持。
  
从 Windows 上的 Chrome 访问 Web 应用程序 &#x2778; 将启动一个小型程序，该程序将在嵌入式 Internet Explorer 框架中加载 Web 应用程序。 此程序需要安装受支持的 Internet Explorer 版本之一，才能正确加载 Web 应用。
  
> [!NOTE]
> Office 365 用户可以在 Skype for Business 中使用 Internet Explorer 10 或更高版本。 
  
### <a name="skype-meetings-app"></a>Skype 会议应用

Skype 会议应用程序在使用 Windows 10、Windows 8.1、windows 8、Windows 7、32和64位 Internet Explorer 11 或更高版本的计算机上运行的应用程序。 
  
有关任何其他依赖项，请参阅[Skype 会议应用程序支持的平台](https://support.office.com/client/results?Shownav=true&amp;lcid=1033&amp;ns=SKFBWA&amp;version=15&amp;omkt=en-US&amp;ver=15&amp;HelpID=SfBWebApp4001)
  
### <a name="skype-for-business-for-mac"></a>Mac 版 Skype for Business

Skype for business for Mac 在使用 macOS 版本10.8 或更高版本的计算机上运行。 

## <a name="hardware-requirements"></a>硬件要求
<a name="OS-Browser"> </a>

计算机的硬件要求由操作系统和浏览器决定。 语音和电话功能需要麦克风和扬声器、带麦克风的耳机或与计算机兼容的等效设备。 视频功能需要与计算机兼容的视频设备。 有关视频硬件支持和预期的视频质量的详细信息，请参阅[Skype For business 客户端视频解决方案](video-resolutions.md)。
  
## <a name="network-requirements"></a>网络要求
<a name="Network"> </a>

如果 Skype for Business Web 应用或 Skype 会议应用程序的用户遇到会议连接问题，则组织的网络基础结构可能未配置为支持 office 365，如[office 365 url 和 IP 地址范围](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US)中所述。 无论会议是由 Skype for Business Online 用户还是 Skype for business Server 的用户创建的，都是这样的。 
  
如果用户在未配置为所述的网络上，则许多应用程序功能可能会也可能不起作用，并且可能无法连接到会议。
  
## <a name="supported-meetings-features"></a>支持的会议功能
<a name="BKMK_Conferencing"> </a>

此表对 Skype for Business 客户端、Skype for Business Web 应用程序、Skype 会议应用程序和 Lync Web 应用程序的用户可用的会议功能进行比较。 出于功能比较目的列出了 Lync Web App：只有在 Lync 2013 服务器上托管会议时，用户才会下载和使用 Lync Web App。

| 功能/功能 | Skype for Business 2016 或2019客户端 | Mac 客户端上的 Skype for Business | Skype 会议应用 | Skype for Business Web 应用 | Lync Web App |
|:-----|:-----|:-----|:-----|:-----|:-----|
|添加计算机音频  <br/> |&#x2714;|&#x2714;|&#x2714; （需要插件）  <br/> |&#x2714; （需要插件）  <br/> |&#x2714; （需要插件）  <br/> |
|添加视频  <br/> |&#x2714;|&#x2714;|&#x2714; （需要插件）  <br/> |&#x2714; （需要插件）  <br/> |&#x2714; （需要插件）  <br/> |
|为经过身份验证的参与者将音频切换到电话  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|为来宾参与者将音频切换到电话  <br/> |&#x2714;|&#x2714;|&#x2714;|||
|查看多方视频（库视图）  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|基于视频的屏幕共享  <br/> |&#x2714;|&#x2714; <br/> |&#x2714; （仅查看）  <br/> |||
|使用会议中演示者控件  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|访问详细的会议名单  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|参与多方 IM  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|将 IM 邮件设置为高重要性  <br/> |&#x2714;|||||
|共享桌面（如果已启用）  <br/> |&#x2714;|&#x2714;|&#x2714; （需要插件）  <br/> |&#x2714; （需要插件）  <br/> |&#x2714; （需要插件）  <br/> |
|共享程序（如果已启用）  <br/> |&#x2714;||&#x2714; （仅限 Windows; 需要插件）  <br/> |&#x2714; （仅限 Windows; 需要插件）  <br/> |&#x2714; （仅限 Windows; 需要插件）  <br/> |
|控制其他用户的共享桌面或程序  <br/> |&#x2714;||&#x2714; （仅在 Windows 上 &#x2776;; 需要插件）  <br/> |&#x2714; （仅在 Windows 上 &#x2776;; 需要插件）  <br/> |&#x2714; （仅在 Windows 上 &#x2776;; 需要插件）  <br/> |
|让其他用户控制您的共享桌面或程序  <br/> |&#x2714;|||||
|添加匿名参与者（如果已启用）  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|按名称邀请参与者  <br/> |&#x2714;|&#x2714;||||
|通过电话号码邀请参与者  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|通过电子邮件邀请参与者  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|使用电话拨入式音频会议  <br/> |&#x2714; &#x2777; |&#x2714; &#x2777; |&#x2714; &#x2777; |&#x2714; &#x2777; |&#x2714; &#x2777; |
|启动 "立即开会" 会议  <br/> |&#x2714;|&#x2714;||||
|录制会议  <br/> |&#x2714;|||||
|添加和下载附件  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|添加并演示 Microsoft PowerPoint 文件  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|导航 Microsoft PowerPoint 文件  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|添加和编辑 OneNote 会议笔记  <br/> |&#x2714;||仅编辑（不添加）  <br/> |仅编辑（不添加）  <br/> |仅编辑（不添加）  <br/> |
|使用白板  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|发起投票  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|上载文件以与其他人共享  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|安排会议  <br/> |Outlook 或 Skype for Business Web 计划程序  <br/> |Outlook 或 Skype for Business Web 计划程序  <br/> |Skype for Business Web 计划程序  <br/> |Skype for Business Web 计划程序  <br/> |Skype for Business Web 计划程序  <br/> |
|问&amp;：经理  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|禁用与会者视频  <br/> |&#x2714;|||||
|禁用会议即时消息  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|静音受众  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|使所有人成为与会者  <br/> |&#x2714;|||||
|生成 Skype 会议直播  <br/> |&#x2714;|||||
   
 &#x2776; 参与者无法控制由 Skype for Business for Mac、Lync for mac 2011 或 Communicator for Mac 2011 用户共享的桌面。 这也不适用于最大 OSX 上的 Skype for business Web 应用。
  
 &#x2777; 适用于 Skype for Business Online，此功能需要 Microsoft PSTN 会议、Exchange 统一消息或第三方音频会议提供商。
  
 &#x2778; Lync for Mac 2011 客户端在 Skype for Business Web 应用程序在会议中共享时无法查看 Microsoft Office 2013 PowerPoint 演示文稿。
  
## <a name="known-issues-and-troubleshooting"></a>已知问题和疑难解答
<a name="BKMK_Conferencing"> </a>

对于最终用户，这些应用程序的[联机帮助](https://aka.ms/smahelp)随时可用。 IT 专业人员应注意以下问题：
  
- 如果用户在未配置为符合[网络要求](meetings-clients.md#Network)的网络上，则很多应用程序功能可能会或不能正常运行，并且可能无法连接到会议。
    
- 某些用户可能已对公司管理的计算机提供了安装应用程序的禁用权限。 对于这些用户，这两个应用程序都不是一个选项，但[智能手机](https://products.office.com/skype-for-business/download-app?tab=tabs-1)和[平板电脑](https://products.office.com/skype-for-business/download-app?tab=tabs-2)用户可能能够安装可用于参加会议的廉价移动客户端。
    
    其他安装问题也包含在[帮助主题](https://support.office.com/article/Trouble-installing-the-Skype-for-Business-Web-App-plug-in-958fc5f1-2d6f-42e3-815d-a9516c591274?ui=en-US&amp;rs=en-US&amp;ad=US)中。 
    
- 用户在首次运行会议应用程序时，可能会看到防火墙警告。 系统可能会提示他们打开端口以优化体验，这可能需要在可能没有的计算机上具有管理员权限。 应用仍应正常运行，并且用户可以安全地拒绝打开请求的端口。 
    
- 必须在 Internet Explorer 中[启用 ActiveX 且](https://support.office.com/article/Turn-off-ActiveX-filtering-for-Skype-for-Business-Web-App-b6de8ff6-ac7e-4e2f-b18c-2f13db643c41?ui=en-US&amp;rs=en-US&amp;ad=US)不进行筛选，即使 IE 不是默认浏览器也是如此。 在 Skype for Business Web 应用程序中，音频、视频和屏幕共享需要 ActiveX 控件（一个将其他功能添加到 Web 应用程序或其他程序中）的小模块。
    
- 若要使 Skype for Business Web 应用的某些功能正常工作，您必须允许浏览器[将 cookie 保存](https://support.office.com/article/Allow-cookies-for-Skype-Meetings-App-Skype-for-Business-Web-App-2108276b-b5c3-484b-bf2b-dac6eeba4c93)在计算机或设备上。
    
- 您可能需要在浏览器中[启用 JavaScript](https://support.office.com/article/Turn-on-JavaScript-for-Skype-Meetings-App-Skype-for-Business-Web-App-3d997bf9-637c-4fe6-8ee3-9e62bfda52cd)支持，以使某些 Skype For Business Web 应用功能按预期工作。
    
### <a name="aes-support"></a>AES 支持 

从 Skype for business Server 2015 CU5，AES 不支持 ASP.NET 4.6，这可能会导致 Skype 会议应用无法启动。 [由于 ASP .net 4.5 的加密要求](../security/user-and-client-authentication.md#cryptographic-requirements-due-to-asp-net-45)包含更多详细信息。
  
## <a name="see-also"></a>另请参阅
<a name="BKMK_Conferencing"> </a>

[在 Skype for Business Server 中部署 Web 可下载客户端](../../deploy/deploy-clients/deploy-web-downloadable-clients.md)

[Skype 会议应用程序支持的平台](https://support.office.com/client/results?Shownav=true&amp;lcid=1033&amp;ns=SKFBWA&amp;version=15&amp;omkt=en-US&amp;ver=15&amp;HelpID=SfBWebApp4001)
