---
title: 规划会议客户端（Web 应用和会议应用）
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
description: 摘要：在规划 Skype for business 服务器时，IT 专业人员应查看 Skype for business Web 应用和 Skype 会议应用的支持要求。 本文不适合这些应用的用户。
ms.openlocfilehash: 126d8ffc71a2ff1a0bcbf26c744301736d2b47b2
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803552"
---
# <a name="plan-for-meetings-clients-web-app-and-meetings-app"></a>规划会议客户端（Web 应用和会议应用）
 
**摘要：** 在规划 Skype for business 服务器时，IT 专业人员应查看 skype for business Web 应用和 Skype 会议应用的支持要求。 本文不适合这些应用的用户。
  
一旦你实施了 Skype for Business 服务器，你的组织的用户可能会在部署过程中安装 Skype for business 客户端。 
  
稍后，这些用户可能会创建会议并邀请来自组织外部的用户，并且这些会议被邀请者可能没有任何版本的 Skype for Business 客户端。 当这些用户单击会议邀请的 URL 时，将检测到缺少客户端，并且不需要 Skype for business 客户端的被邀请者将被要求下载并安装一个轻型的会议客户端，以便他们可以加入会议。
  
> [!NOTE]
> Skype for business Web 应用和 Skype 会议应用仅在尝试登录会议而没有 Skype for business 时才可用。 这些应用的用户帮助是[https://aka.ms/smahelp](https://aka.ms/smahelp)。 
  
> [!NOTE]
> 不能预安装 Skype for business Web 应用或 Skype 会议应用，但[智能手机](https://products.office.com/en-us/skype-for-business/download-app?tab=tabs-1)和[平板电脑](https://products.office.com/en-us/skype-for-business/download-app?tab=tabs-2)用户可能能够安装可用于出席会议的廉价移动客户端。
  
默认情况下，主持会议的服务器将引导用户下载并安装 Skype for Business Web 应用以加入会议。 Skype for Business Web 应用存储在前端服务器上，并发送给会议与会者。 
  
对于 Skype for Business 服务器，Skype 会议应用（Windows 上）和 Mac 版 Skype for business （Mac）可作为从 CU5 开始的 Skype for business Web 应用的替代项，但提供替换应用需要 "启用 Skype 会议应用" 中所述的其他配置，[以替换 skype For Business Web 应用（可选）](../../deploy/deploy-clients/deploy-web-downloadable-clients.md#SMA_Enable)。  如果启用 Skype 会议应用和 Mac 版 Skype for business，用户将从 Office 365 内容交付网络（CDN）下载最新版本的应用，而不是从 Skype for business 服务器下载。 对于 Skype for Business Server 2019，使用 Skype 会议应用和 Mac 版 Skype for business 是唯一的选择。
  
Skype 会议应用提供简化的浏览器体验，可用于下载和安装应用和加入会议，包括针对 Internet Explorer 用户的一键式加入。 Skype 会议应用在可靠性和会议体验方面还具有许多对 Skype for Business Web 应用的改进。 
  
> [!NOTE]
> 从 Skype for Business Server 2015 CU5 或更高版本，使用 Skype for Business Online 保留的会议将不再向 clientless 用户发送 Skype for business Web 应用，他们将改为发送 Skype 会议应用（Windows）或 Mac 版 Skype for business （Mac 版）。 从 Skype for Business Server 2015 CU5 或更高版本，如果你[启用 Skype 会议应用来替换 skype For Business Web 应用（可选）](../../deploy/deploy-clients/deploy-web-downloadable-clients.md#SMA_Enable)，clientless 用户将收到 Skype 会议应用或 Mac 版 skype for business，而不是 skype For Business web 应用。 
  
## <a name="software-requirements"></a>软件要求
<a name="OS-Browser"> </a>

若要使用 Skype for Business Web 应用，用户必须具有以下受支持的操作系统和浏览器组合之一。 
  
**适用于 Skype for Business Web 应用的操作系统和最低浏览器支持**

| 操作系统 | Edge | 32-和64位 Internet Explorer 11 或更高版本 | 32-和64位 Internet Explorer 10 或更高版本 | 32-和64位 Internet Explorer 9 或更高版本 | 32和64位的 Safari 6.2.8 版本-11. X | 32-和64位版本的 Chrome 18. X 或更高版本 |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Windows 10  <br/> |必需  <br/> |是  <br/> |不适用  <br/> |不适用  <br/> |不适用  <br/> |是 &#x2778; <br/> |
|Windows 8.1 &#x2776; <br/> |不适用  <br/> |是  <br/> |不适用  <br/> |不适用  <br/> |不适用 <br/> |是 &#x2778; <br/> |
|Windows 8 （基于 Intel） &#x2776; <br/> |不适用  <br/> |不适用  <br/> |是  <br/> |不适用 <br/> |不适用  <br/> |是 &#x2778; <br/> |
|带有 SP1 的 Windows 7 &#x2777; <br/> |不适用  <br/> |是  <br/> |否  <br/> |否  <br/> |不适用 <br/>|是 &#x2778; <br/> |
|Windows Server 2008 R2 SP1 &#x2777; <br/> |不适用  <br/> |是  <br/> |是   <br/> |是  <br/> |不适用 <br/>|是 &#x2778; <br/> |
|macOS 10.8 及更高版本（基于 Intel） &#x2777; <br/> |不适用  <br/> |不适用  <br/> |不适用  <br/> |不适用  <br/> |是  <br/> |是 <br/> |
   
&#x2776; Skype for Business Web 应用浏览器插件需要特定共享插件才能使用基于计算机的语音、视频、共享和查看正在进行的屏幕共享和其他功能。 会议与会者可以选择在加入会议时安装共享插件，也可以在他们启动其中一个功能时提供安装共享插件。 在 Windows 8 和 Windows 8.1 上，只有在运行桌面版 Internet Explorer 10 或 Internet Explorer 11 时，才可以安装共享插件。 这些功能在非桌面版本的 Internet Explorer 10 和11中不可用。 请注意，不再支持 Firefox 和 Safari 版本12.0 及更高版本。
  
&#x2777; 在支持的 Windows 7、Windows Server 2008 R2 和 Macintosh 操作系统上，所有功能均可用，包括基于计算机的语音、视频、应用程序查看、应用程序共享、桌面查看和桌面共享。 若要使用这些功能，必须在出现提示时安装插件。 请注意，Mac OS X 版本10.7 已不再受支持。
  
从 Windows 上的 Chrome 访问 Web 应用 &#x2778; 将启动一个小程序，该程序将在嵌入式 Internet Explorer 框架中加载 Web 应用。 此程序需要安装支持的 Internet Explorer 版本之一，才能正确加载 Web 应用。
  
> [!NOTE]
> Office 365 用户可以将 Internet Explorer 10 或更高版本与 Skype for Business 配合使用。 
  
### <a name="skype-meetings-app"></a>Skype 会议应用

Skype 会议应用在计算机上以应用运行，使用 Windows 10、Windows 8.1、Windows 8、Windows 7、32-和64位 Internet Explorer 11 或更高版本安装了 Internet Explorer 11 或更高版本。 
  
有关任何其他依赖项，请参阅[Skype 会议应用的受支持平台](https://support.office.com/en-US/client/results?Shownav=true&amp;lcid=1033&amp;ns=SKFBWA&amp;version=15&amp;omkt=en-US&amp;ver=15&amp;HelpID=SfBWebApp4001)
  
### <a name="skype-for-business-for-mac"></a>Mac 版 Skype for Business

Mac 版 Skype for business 在使用 macOS 版本10.8 或更高版本的计算机上运行。 

## <a name="hardware-requirements"></a>硬件要求
<a name="OS-Browser"> </a>

计算机硬件要求由操作系统和浏览器确定。 语音和电话功能需要麦克风和扬声器、带麦克风的耳机或者与计算机的同等设备。 视频功能需要与计算机兼容的视频设备。 有关视频硬件支持和预期视频质量的详细信息，请参阅[Skype For business 客户端视频解决方案](video-resolutions.md)。
  
## <a name="network-requirements"></a>网络要求
<a name="Network"> </a>

如果 Skype for business Web 应用或 Skype 会议应用的用户遇到会议连接问题，则其组织的网络基础结构没有配置为支持 Office 365，如[Office 365 url 和 IP 地址范围](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US)中所述。 如果会议是由 Skype for Business Online 或 Skype for business 服务器的用户创建的，则会出现这种情况。 
  
如果用户在未配置为 "已描述" 的网络上，则许多应用功能可能会也可能不起作用，并且他们可能无法连接到会议。
  
## <a name="supported-meetings-features"></a>支持的会议功能
<a name="BKMK_Conferencing"> </a>

此表比较了 Skype for business 客户端、Skype for business Web 应用、Skype 会议应用和 Lync Web App 的用户可用的会议功能。 出于功能比较目的，列出了 lync Web App：仅当会议托管在 Lync 2013 服务器上时，用户才会下载并使用 Lync Web App。

| 特性/功能 | Skype for Business 2016 或2019客户端 | Mac 版 Skype for business 客户端 | Skype 会议应用 | Skype for Business Web App | Lync Web App |
|:-----|:-----|:-----|:-----|:-----|:-----|
|添加计算机音频  <br/> |&#x2714;|&#x2714;|&#x2714; （需要插件）  <br/> |&#x2714; （需要插件）  <br/> |&#x2714; （需要插件）  <br/> |
|添加视频  <br/> |&#x2714;|&#x2714;|&#x2714; （需要插件）  <br/> |&#x2714; （需要插件）  <br/> |&#x2714; （需要插件）  <br/> |
|为经过身份验证的参与者将音频切换到手机  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|为来宾参与者将音频切换到电话  <br/> |&#x2714;|&#x2714;|&#x2714;|||
|查看多方视频（库视图）  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|基于视频的屏幕共享  <br/> |&#x2714;|&#x2714; <br/> |&#x2714; （仅查看）  <br/> |||
|使用会议中演示者控件  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|访问详细的会议名单  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|参与多方 IM  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|发送高重要性 IM 消息  <br/> |&#x2714;|||||
|共享桌面（如果已启用）  <br/> |&#x2714;|&#x2714;|&#x2714; （需要插件）  <br/> |&#x2714; （需要插件）  <br/> |&#x2714; （需要插件）  <br/> |
|共享程序（如果已启用）  <br/> |&#x2714;||&#x2714; （仅限 Windows，需要插件）  <br/> |&#x2714; （仅限 Windows，需要插件）  <br/> |&#x2714; （仅限 Windows，需要插件）  <br/> |
|控制其他用户的共享桌面或程序  <br/> |&#x2714;||&#x2714; （仅在 Windows 上 &#x2776;; 需要插件）  <br/> |&#x2714; （仅在 Windows 上 &#x2776;; 需要插件）  <br/> |&#x2714; （仅在 Windows 上 &#x2776;; 需要插件）  <br/> |
|让其他用户获得共享桌面或程序的控制权  <br/> |&#x2714;|||||
|添加匿名参与者（如果已启用）  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|按姓名邀请参与者  <br/> |&#x2714;|&#x2714;||||
|通过电话号码邀请参与者  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|通过电子邮件邀请参与者  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|使用电话拨入式音频会议  <br/> |&#x2714; &#x2777; |&#x2714; &#x2777; |&#x2714; &#x2777; |&#x2714; &#x2777; |&#x2714; &#x2777; |
|启动“立即开会”会议  <br/> |&#x2714;|&#x2714;||||
|录制会议  <br/> |&#x2714;|||||
|添加和下载附件  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|添加和演示 Microsoft PowerPoint 文件  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|导航 Microsoft PowerPoint 文件  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|添加和编辑 OneNote 会议笔记  <br/> |&#x2714;||仅编辑（不添加）  <br/> |仅编辑（不添加）  <br/> |仅编辑（不添加）  <br/> |
|使用白板  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|发起投票  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|上载文件以与其他人共享  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|安排会议或电话会议  <br/> |Outlook 或 Skype for business Web 计划程序  <br/> |Outlook 或 Skype for business Web 计划程序  <br/> |Skype for Business Web 计划程序  <br/> |Skype for Business Web 计划程序  <br/> |Skype for Business Web 计划程序  <br/> |
|问&amp;经理  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|禁用与会者视频  <br/> |&#x2714;|||||
|禁用会议 IM  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|将观众设为静音  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|将每个人都设为与会者  <br/> |&#x2714;|||||
|开通 Skype 会议直播  <br/> |&#x2714;|||||
   
 &#x2776; 参与者无法控制由 Skype for Business for Mac、Lync for mac 2011 或适用于 Mac 2011 用户的 Communicator 共享的桌面。 这也不适用于最大 OSX 上的 Skype for business Web 应用。
  
 &#x2777; Skype for business Online，此功能需要 Microsoft PSTN 会议、Exchange 统一消息或第三方音频会议提供商。
  
 &#x2778; Lync for Mac 2011 客户端无法在 Skype for Business Web 应用在会议中共享时查看 Microsoft Office 2013 PowerPoint 演示文稿。
  
## <a name="known-issues-and-troubleshooting"></a>已知问题和疑难解答
<a name="BKMK_Conferencing"> </a>

对于最终用户，这些应用的[联机帮助](https://aka.ms/smahelp)随时可用。 IT 专业人员应注意以下问题：
  
- 如果用户在未配置为满足[网络要求](meetings-clients.md#Network)的网络上，则许多应用功能可能会也可能不起作用，并且他们可能根本无法连接到会议。
    
- 某些用户可能有公司管理的计算机，并且已禁用安装应用的权限。 对于这些用户，这两个应用都是一个选项，但[智能手机](https://products.office.com/en-us/skype-for-business/download-app?tab=tabs-1)和[平板电脑](https://products.office.com/en-us/skype-for-business/download-app?tab=tabs-2)用户可能能够安装可用于出席会议的廉价移动客户端。
    
    其他安装问题也将在 "[帮助" 主题](https://support.office.com/en-us/article/Trouble-installing-the-Skype-for-Business-Web-App-plug-in-958fc5f1-2d6f-42e3-815d-a9516c591274?ui=en-US&amp;rs=en-US&amp;ad=US)中介绍。 
    
- 用户首次运行会议应用时，可能会看到防火墙警告。 系统可能会提示您打开端口以优化体验，这可能需要在他们可能没有的计算机上拥有管理员权限。 该应用仍应正常运行，并且用户可以安全地拒绝打开所请求的端口。 
    
- 必须在 Internet Explorer 中[启用 ActiveX 而不进行筛选](https://support.office.com/en-us/article/Turn-off-ActiveX-filtering-for-Skype-for-Business-Web-App-b6de8ff6-ac7e-4e2f-b18c-2f13db643c41?ui=en-US&amp;rs=en-US&amp;ad=US)，即使 IE 不是默认浏览器也是如此。 在 Skype for Business Web 应用中，ActiveX 控件（将其他功能添加到 Web 应用或其他程序的小模块）是音频、视频和屏幕共享所必需的。
    
- 为了使 Skype for Business Web 应用的某些功能正常工作，你必须允许你的浏览器[将 cookie 保存](https://support.office.com/en-us/article/Allow-cookies-for-Skype-Meetings-App-Skype-for-Business-Web-App-2108276b-b5c3-484b-bf2b-dac6eeba4c93)在计算机或设备上。
    
- 你可能需要在浏览器中[启用 JavaScript](https://support.office.com/en-us/article/Turn-on-JavaScript-for-Skype-Meetings-App-Skype-for-Business-Web-App-3d997bf9-637c-4fe6-8ee3-9e62bfda52cd)支持，以便某些 Skype For Business Web 应用功能能够按预期工作。
    
### <a name="aes-support"></a>AES 支持 

从 Skype for Business Server 2015 CU5 不支持 ASP.NET 4.6 的 AES，这可能会导致 Skype 会议应用无法启动。 [由于 ASP .net 4.5 的加密要求](../security/user-and-client-authentication.md#cryptographic-requirements-due-to-asp-net-45)有更多详细信息。
  
## <a name="see-also"></a>另请参阅
<a name="BKMK_Conferencing"> </a>

[在 Skype for Business 服务器中部署 Web 可下载的客户端](../../deploy/deploy-clients/deploy-web-downloadable-clients.md)

[Skype 会议应用支持的平台](https://support.office.com/en-US/client/results?Shownav=true&amp;lcid=1033&amp;ns=SKFBWA&amp;version=15&amp;omkt=en-US&amp;ver=15&amp;HelpID=SfBWebApp4001)
