---
title: 规划会议客户端 （Web 应用程序和会议应用程序）
ms.author: jambirk
author: jambirk
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 2/16/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 31e95e16-f79f-46c6-b123-973fa56a824e
description: 摘要： IT 专业人员应规划的 Skype 业务 Server 时查看 Skype 企业 Web 应用程序和 Skype 会议应用程序的支持的要求。 这篇文章不适合于这些应用程序的用户。
ms.openlocfilehash: 6006bf1ca4b8ce63a662a1c55c79865097c86b18
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32207361"
---
# <a name="plan-for-meetings-clients-web-app-and-meetings-app"></a>规划会议客户端 （Web 应用程序和会议应用程序）
 
**摘要：** IT 专业人员应规划的 Skype 业务 Server 时查看 Skype 企业 Web 应用程序和 Skype 会议应用程序的支持要求。 这篇文章不适合于这些应用程序的用户。
  
您已实现后 Skype 业务服务器，贵组织的用户可能会业务客户端部署过程的一部分安装 Skype。 
  
更高版本上，这些用户可以创建会议并邀请组织外部的用户，这些会议的被邀请者可能没有任何版本的业务客户端 Skype。 当这些用户单击会议邀请的 URL 时，将检测到缺少的客户端，并且不业务客户端 Skype 被邀请者将需要下载并安装轻型、 仅会议客户端，以便他们可以加入会议。
  
> [!NOTE]
> 尝试无 for Business 的 Skype 登录到会议时，业务 Web App 的 Skype 和 Skype 会议应用程序才可用。 这些应用程序的用户帮助位于[https://aka.ms/smahelp](https://aka.ms/smahelp)。 
  
> [!NOTE]
> 不能预安装任一 Skype，企业 Web 应用程序或 Skype 会议应用程序，但[智能手机](https://products.office.com/en-us/skype-for-business/download-app?tab=tabs-1)和[平板电脑](https://products.office.com/en-us/skype-for-business/download-app?tab=tabs-2)用户可能无法安装它们可用于参加会议的便宜移动客户端。
  
默认情况下主持会议的服务器将直接下载并安装 Skype 业务 Web App 加入会议的用户。 企业 Web 应用程序的 Skype 存储在前端服务器上，并获取发送给会议参与者。 
  
对于业务服务器 Skype，（Windows) 上的 Skype 会议应用程序和 Skype for Business for Mac （在 Mac) 是可用作 Skype 替换为 CU5，企业 Web 应用程序从开始，但提供替换应用程序需要其他配置[启用 Skype 会议应用程序替换 Skype 业务 Web 应用程序 （可选）](../../deploy/deploy-clients/deploy-web-downloadable-clients.md#SMA_Enable)中所述。  如果启用了 Skype 会议应用程序和 Skype for Business for Mac，用户将从 Office 365 内容交付网络 (CDN) 而不是从您的业务服务器 Skype 下载最新版本的应用程序。 为业务服务器 2019年的 Skype，for Mac for Business 使用 Skype 会议应用程序和 Skype 是唯一的选项。
  
Skype 会议应用程序提供了有关下载和安装应用程序和加入会议，包括用户的 Internet Explorer 的一次单击加入简化的浏览器体验。 Skype 会议应用程序也有很多改进通过 Skype 业务 Web 应用程序以实现可靠性和会议体验。 
  
> [!NOTE]
> 截止 Skype 的业务服务器 2015 CU5 或更高版本，会议保留业务 online 使用 Skype 将不再无客户端向用户发送 Skype 业务 Web 应用程序，它们将改为发送 Skype 会议应用程序 （在 Windows 中) 或 for Business 的 Skype for Mac （在 Mac)。 截止 Skype 业务服务器 2015 CU5 或更高版本，如果您[启用 Skype 会议应用程序替换为业务 Web 应用程序 （可选） 的 Skype](../../deploy/deploy-clients/deploy-web-downloadable-clients.md#SMA_Enable)，无客户端的用户将发送 Skype 会议应用程序或 Mac 而不是企业 Web 应用程序的 Skype 的业务的 Skype。 
  
## <a name="software-requirements"></a>软件要求
<a name="OS-Browser"> </a>

用于 Skype 企业 Web 应用程序，用户必须有下列选项之一支持的操作系统和浏览器组合。 
  
**操作系统和的 Skype 业务 Web 应用程序的最小的浏览器支持**

| 操作系统 | Edge | 32 位和 64 位 Internet Explorer 11 或更高版本 | 32 位和 64 位 Internet Explorer 10 或更高版本 | 32 位和 64 位 Internet Explorer 9 或更高版本 | 32 位和 64 位版本的 Safari 6.2.8-11.X | 32 位和 64 位版本的 Chrome 18.X 或更高版本 |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Windows 10  <br/> |是   <br/> |是  <br/> |不适用  <br/> |不适用  <br/> |不适用  <br/> |是 & #x 2778; <br/> |
|Windows 8.1 & #x 2776; <br/> |不适用  <br/> |是  <br/> |不适用  <br/> |不适用  <br/> |不适用 <br/> |是 & #x 2778; <br/> |
|Windows 8 (基于 Intel) & #x 2776; <br/> |不适用  <br/> |不适用  <br/> |是  <br/> |不适用 <br/> |不适用  <br/> |是 & #x 2778; <br/> |
|Windows 7 SP1 & #x 2777; <br/> |不适用  <br/> |是  <br/> |否  <br/> |否  <br/> |不适用 <br/>|是 & #x 2778; <br/> |
|Windows Server 2008 R2 SP1 & #x 2777; <br/> |不适用  <br/> |是  <br/> |是   <br/> |是  <br/> |不适用 <br/>|是 & #x 2778; <br/> |
|macOS 10.8 及更高版本 （基于 Intel） & #x 2777; <br/> |不适用  <br/> |不适用  <br/> |不适用  <br/> |不适用  <br/> |是  <br/> |是  <br/> |
   
& #x 2776;企业 Web 应用程序浏览器插件 Skype 需要特定的共享插件，用于基于计算机的语音、 视频、 共享和查看正在进行屏幕共享和其他功能。 会议与会者提供的选项安装时加入会议或时他们启动其中一种功能的共享插件。 在 Windows 8 和 Windows 8.1，共享插件可以安装仅当您正在为台式机运行 Internet Explorer 10 或 Internet Explorer 11。 这些功能不可用与非桌面版本的 Internet Explorer 10 和 11。 请注意 12.0 及更高版本的 Firefox 和 Safari 版本不再受支持。
  
& #x 2777;在支持的 Windows 7、windows、 Windows Server 2008 R2 和 Macintosh 操作系统上，所有功能都均可用，包括基于计算机的语音、 视频、 应用程序查看、 应用程序共享、 桌面查看和桌面共享。 若要使用这些功能，必须安装插件时提示。 请注意 Mac OS X 10.7 版本不再受支持。
  
& #x 2778;从 Windows 上的 Chrome 访问 Web 应用程序将启动此操作将加载嵌入的 Internet Explorer 框架中 Web 应用程序的小程序。 此程序需要支持之一版本的 Internet Explorer 安装的 Web 应用程序以正确加载。
  
> [!NOTE]
> Office 365 用户可以使用 Internet Explorer 10 或更高版本 Skype for Business。 
  
### <a name="skype-meetings-app"></a>Skype 会议应用

Skype 会议应用程序使用 Windows 10、 Windows 8.1、 Windows 8 和 Windows 7，带 32 位和 64 位 Internet Explorer 11 的计算机上运行作为应用程序或更高版本。 
  
有关其他任何依赖项，请参阅[Skype 会议应用程序支持的平台](https://support.office.com/en-US/client/results?Shownav=true&amp;lcid=1033&amp;ns=SKFBWA&amp;version=15&amp;omkt=en-US&amp;ver=15&amp;HelpID=SfBWebApp4001)
  
### <a name="skype-for-business-for-mac"></a>Skype for Business for Mac

用于 Mac 的业务的 Skype 运行使用 macOS 10.8 或更高版本的计算机上。 

## <a name="hardware-requirements"></a>硬件要求
<a name="OS-Browser"> </a>

计算机硬件要求由操作系统和浏览器确定。 语音和电话功能需要麦克风和扬声器、带麦克风的耳机或者与计算机的同等设备。 视频功能需要与计算机兼容的视频设备。 有关视频硬件支持和预期视频质量的详细信息，请参阅[Skype 业务的客户端视频分辨率](video-resolutions.md)。
  
## <a name="network-requirements"></a>网络要求
<a name="Network"> </a>

如果会议的连接问题的企业 Web 应用程序或 Skype 会议应用程序体验 Skype 用户，很可能其组织的网络基础结构不配置为支持 Office 365， [Office 365 Url 和 IP 地址范围](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US)中所述。 会议已由用户创建的 Skype 业务联机或 Skype 业务服务器是否，这种情况。 
  
如果用户是在网络上未配置如下所述，多个应用程序功能可能也可能不起作用，它们可能无法在能够连接到所有会议。
  
## <a name="supported-meetings-features"></a>支持的会议功能
<a name="BKMK_Conferencing"> </a>

下表比较业务 Web 应用程序、 Skype 会议应用程序和 Lync Web App 供业务客户端的 Skype、 Skype 的用户的会议功能。 功能比较目的列出 Lync Web App： 用户将仅下载和使用 Lync Web App，如果 Lync 2013 服务器上已承载会议。

| 特性/功能 | Skype 业务 2016年或 2019年客户端 | Skype for Mac 客户端上的 Business | Skype 会议应用 | Skype for Business Web App | Lync Web App |
|:-----|:-----|:-----|:-----|:-----|:-----|
|添加计算机音频  <br/> |& #x 2714;|& #x 2714;|& #x 2714;（需要插件）  <br/> |& #x 2714;（需要插件）  <br/> |& #x 2714;（需要插件）  <br/> |
|添加视频  <br/> |& #x 2714;|& #x 2714;|& #x 2714;（需要插件）  <br/> |& #x 2714;（需要插件）  <br/> |& #x 2714;（需要插件）  <br/> |
|切换到电话音频，经过身份验证的参与者  <br/> |& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|
|切换到电话音频，为来宾参与者  <br/> |& #x 2714;|& #x 2714;|& #x 2714;|||
|查看多方视频（库视图）  <br/> |& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|
|基于视频的屏幕共享  <br/> |& #x 2714;|& #x 2714; <br/> |&#x2714;(View-only)  <br/> |||
|使用会议中演示者控件  <br/> |& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|
|访问详细的会议名单  <br/> |& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|
|参与多方 IM  <br/> |& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|
|发送高重要性 IM 消息  <br/> |& #x 2714;|||||
|共享桌面（如果已启用）  <br/> |& #x 2714;|& #x 2714;|& #x 2714;（需要插件）  <br/> |& #x 2714;（需要插件）  <br/> |& #x 2714;（需要插件）  <br/> |
|共享程序（如果已启用）  <br/> |& #x 2714;||& #x 2714年; （在仅限需要插件）  <br/> |& #x 2714年; （在仅限需要插件）  <br/> |& #x 2714年; （在仅限需要插件）  <br/> |
|获得另一个用户共享的桌面或程序的控制权  <br/> |& #x 2714;||& #x 2714;(& #x 2776;在仅限需要插件）  <br/> |& #x 2714;(& #x 2776;在仅限需要插件）  <br/> |& #x 2714;(& #x 2776;在仅限需要插件）  <br/> |
|允许控制共享的桌面或程序的另一个用户  <br/> |& #x 2714;|||||
|添加匿名参与者（如果已启用）  <br/> |& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|
|按名称邀请参与者  <br/> |& #x 2714;|& #x 2714;||||
|邀请参与者通过电话号码  <br/> |& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|
|通过电子邮件邀请参与者  <br/> |& #x 2714;||& #x 2714;|& #x 2714;|& #x 2714;|
|使用电话拨入式音频会议  <br/> |& #x 2714;& #x 2777; |& #x 2714;& #x 2777; |& #x 2714;& #x 2777; |& #x 2714;& #x 2777; |& #x 2714;& #x 2777; |
|启动“立即开会”会议  <br/> |& #x 2714;|& #x 2714;||||
|录制会议  <br/> |& #x 2714;|||||
|添加并下载附件  <br/> |& #x 2714;||& #x 2714;|& #x 2714;|& #x 2714;|
|添加和演示 Microsoft PowerPoint 文件  <br/> |& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|
|导航 Microsoft PowerPoint 文件  <br/> |& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|
|添加和编辑 OneNote 会议笔记  <br/> |& #x 2714;||仅编辑（不添加）  <br/> |仅编辑（不添加）  <br/> |仅编辑（不添加）  <br/> |
|使用白板  <br/> |& #x 2714;||& #x 2714;|& #x 2714;|& #x 2714;|
|发起投票  <br/> |& #x 2714;||& #x 2714;|& #x 2714;|& #x 2714;|
|上载文件以与其他人共享  <br/> |& #x 2714;||& #x 2714;|& #x 2714;|& #x 2714;|
|安排会议或电话会议  <br/> |Outlook 或 Skype 业务 Web 计划程序  <br/> |Outlook 或 Skype 业务 Web 计划程序  <br/> |Skype 业务 Web 计划程序  <br/> |Skype 业务 Web 计划程序  <br/> |Skype 业务 Web 计划程序  <br/> |
|问：&amp;是经理  <br/> |& #x 2714;||& #x 2714;|& #x 2714;|& #x 2714;|
|禁用与会者视频  <br/> |& #x 2714;|||||
|禁用会议 IM  <br/> |& #x 2714;||& #x 2714;|& #x 2714;|& #x 2714;|
|受众设置为静音  <br/> |& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|& #x 2714;|
|将每个人都设为与会者  <br/> |& #x 2714;|||||
|开通 Skype 会议直播  <br/> |& #x 2714;|||||
   
 & #x 2776; 参与者无法控制由 for Business 的 Skype Mac、 Lync for Mac 2011 或 Communicator for Mac 2011 用户共享的桌面。 这还不适合 Skype 业务最大 OSX 上的 Web 应用程序。
  
 & #x 2777; 业务 online Skype，此功能需要 Microsoft PSTN 会议、 Exchange 统一消息，或第三方音频会议提供商。
  
 & #x 2778; Lync for Mac 2011 客户端无法查看 Microsoft Office 2013 PowerPoint 演示文稿，当他们具有已共享在会议中的 Skype 的企业 Web 应用程序。
  
## <a name="known-issues-and-troubleshooting"></a>已知的问题和疑难解答
<a name="BKMK_Conferencing"> </a>

面向最终用户，这些应用程序的[联机帮助](https://aka.ms/smahelp)是随时可用。 IT 专业人员应注意以下问题：
  
- 如果用户不是在网络上配置以满足[网络要求](meetings-clients.md#Network)，多个应用程序功能可能也可能不起作用，它们可能无法在能够连接到所有会议。
    
- 某些用户可能具有企业管理被禁用的权限来安装应用程序的计算机。 这些用户，都不应用程序是一个选项，但[智能手机](https://products.office.com/en-us/skype-for-business/download-app?tab=tabs-1)和[平板电脑](https://products.office.com/en-us/skype-for-business/download-app?tab=tabs-2)用户可能无法安装它们可用于参加会议的便宜移动客户端。
    
    中[帮助主题](https://support.office.com/en-us/article/Trouble-installing-the-Skype-for-Business-Web-App-plug-in-958fc5f1-2d6f-42e3-815d-a9516c591274?ui=en-US&amp;rs=en-US&amp;ad=US)，还会涉及其他安装问题。 
    
- 用户可能会看到警告第一次防火墙它们运行会议应用程序。 他们可能提示您以打开端口以优化的体验，并且这可能需要他们可能没有在计算机上的管理员权限。 应用程序应仍正常工作，用户可以安全地拒绝打开请求的端口。 
    
- 您必须具有[ActiveX 启用，但不过滤](https://support.office.com/en-us/article/Turn-off-ActiveX-filtering-for-Skype-for-Business-Web-App-b6de8ff6-ac7e-4e2f-b18c-2f13db643c41?ui=en-US&amp;rs=en-US&amp;ad=US)在 Internet Explorer 中，即使 IE 不是默认浏览器。 在企业 Web 应用程序，ActiveX 控件的 Skype — 向 web 应用程序或其他程序的其他功能的小型模块 — 需要音频、 视频和屏幕共享。
    
- Skype 业务 Web 应用程序，以便它们正确运行一些功能，您必须允许您浏览器到您的计算机或设备上的[cookie 保存](https://support.office.com/en-us/article/Allow-cookies-for-Skype-Meetings-App-Skype-for-Business-Web-App-2108276b-b5c3-484b-bf2b-dac6eeba4c93)。
    
- 您可能需要[打开 JavaScript](https://support.office.com/en-us/article/Turn-on-JavaScript-for-Skype-Meetings-App-Skype-for-Business-Web-App-3d997bf9-637c-4fe6-8ee3-9e62bfda52cd)到支持在浏览器中的企业 Web 应用程序功能的一些 Skype 以按预期方式工作。
    
### <a name="aes-support"></a>AES 支持 

截止业务服务器 2015 CU5 的 Skype，AES 不支持 ASP.NET 4.6，这可能会导致 Skype 会议应用程序无法启动。 [由于 ASP.NET 4.5 加密要求](../security/user-and-client-authentication.md#cryptographic-requirements-due-to-asp-net-45)有更多详细信息。
  
## <a name="see-also"></a>另请参阅
<a name="BKMK_Conferencing"> </a>

[为业务服务器部署中 Skype Web 可下载的客户端](../../deploy/deploy-clients/deploy-web-downloadable-clients.md)

[Skype 会议应用程序所支持的平台](https://support.office.com/en-US/client/results?Shownav=true&amp;lcid=1033&amp;ns=SKFBWA&amp;version=15&amp;omkt=en-US&amp;ver=15&amp;HelpID=SfBWebApp4001)
