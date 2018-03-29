---
title: 规划会议客户端 （Web 应用程序和会议的应用程序）
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/16/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 31e95e16-f79f-46c6-b123-973fa56a824e
description: 摘要： IT 专业人员应检查同时规划为 Skype 业务服务器 2015年 Skype 业务 Web 应用程序和 Skype 会议应用程序的支持要求。 这篇文章不是为这些应用程序的用户。
ms.openlocfilehash: 608a85e36d436bbcee21e4ed86dc9b5c815088ed
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="plan-for-meetings-clients-web-app-and-meetings-app"></a>规划会议客户端 （Web 应用程序和会议的应用程序）
 
**摘要：**IT 专业人员应同时规划为 Skype 业务服务器 2015年检查 Skype 业务 Web 应用程序和 Skype 会议应用程序的支持要求。 这篇文章不是为这些应用程序的用户。
  
一旦已经为业务服务器实现 Skype，贵组织用户大概是将业务客户端作为部署过程的一部分进行安装 Skype。 
  
在以后，这些用户可能会创建会议，并邀请来自组织外部的用户，这些会议受邀者可能没有 Skype 业务客户端的任何版本。 当这些用户单击会议邀请中的 URL 时，将检测到客户端的缺乏和 Skype 业务客户端不受邀请的人将被要求下载并安装轻量级的会议专用客户端，以便它们可以加入会议。
  
> [!NOTE]
> 尝试无业务 Skype 登录到会议时，企业 Web 应用程序为 Skype 和 Skype 会议应用程序才可用。 这些应用程序的用户帮助位于[https://aka.ms/smahelp](https://aka.ms/smahelp)。 
  
> [!NOTE]
> 您不能预先安装任一 Skype 业务 Web 应用程序或 Skype 会议应用程序，但[智能手机](https://products.office.com/en-us/skype-for-business/download-app?tab=tabs-1)和[手写板](https://products.office.com/en-us/skype-for-business/download-app?tab=tabs-2)的用户可以安装可用于参加会议的廉价移动客户端。
  
默认情况下，主持会议的服务器将引导用户下载并安装 Skype 业务 Web 应用程序，即可加入会议。 Skype 业务 Web 应用程序的前端服务器上存储和获取发送给与会者。 
  
从 Skype 开始的业务服务器 CU5，Skype 会议应用程序是可以作为替代 Skype 业务 Web 应用程序，但提供 Skype 会议应用程序需要启用 Skype 会议应用程序替换 Skype 为[中所述的其他配置企业 Web 应用程序 （可选）](../../deploy/deploy-clients/deploy-web-downloadable-clients.md#SMA_Enable)。 如果启用了 Skype 会议应用程序，用户将从第 365 办公室内容传递网络 (CDN) 而不是从您 Skype 业务服务器下载最新版本的应用程序。
  
Skype 会议应用程序提供了用于下载和安装应用程序和参加会议，其中包括 Internet Explorer 的用户一单击联接简化浏览器体验。 Skype 会议应用程序还有许多改进通过 theSkype 业务的 Web 应用程序的可靠性和会议体验。 
  
> [!NOTE]
> Skype 的业务服务器 2015 CU5 或更高版本，截至会议举行业务联机使用 Skype 将不再发送无客户端用户 Skype 业务 Web 应用程序，它们将改为发送 Skype 会议应用程序。 截至 Skype 业务服务器 2015 CU5 或更高版本，如果您[启用 Skype 会议应用程序替换 Skype 业务 Web 应用程序 （可选）](../../deploy/deploy-clients/deploy-web-downloadable-clients.md#SMA_Enable)，无客户端的用户将发送业务 Web 应用程序而不是 Skype 的 Skype 会议应用程序。 
  
## <a name="software-requirements"></a>软件要求
<a name="OS-Browser"> </a>

用于 Skype 业务 Web 应用程序，用户必须具有下列任一支持操作系统和浏览器组合。 
  
**操作系统和 Skype 业务 Web 应用程序的最低浏览器支持**


|**操作系统**|**边缘**|**32 位和 64 位 Internet Explorer 11 或更高版本**|**32 位和 64 位 Internet Explorer 10 或更高版本**|**32 位和 64 位 Internet Explorer 9 或更高版本**|**32 位和 64 位版本的 Firefox 12.X 或更高版本**|**32 位和 64 位版本的 Chrome 18.X 或更高版本**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Windows 10  <br/> |是  <br/> |是  <br/> |不适用  <br/> |不适用  <br/> |是  <br/> |是 & #x 2778; <br/> |
| Windows 8.1 和 #x 2776; <br/> |不适用  <br/> |是  <br/> |不适用  <br/> |不适用  <br/> |是  <br/> |是 & #x 2778; <br/> |
| Windows 8 （基于英特尔®） 和 #x 2776; <br/> |不适用  <br/> |不适用  <br/> |是  <br/> |不适用  <br/> |是  <br/> |是 & #x 2778; <br/> |
|Windows 7 SP1 和 #x 2777; 与 <br/> |不适用  <br/> |是  <br/> |否  <br/> |否  <br/> |是  <br/> |是 & #x 2778; <br/> |
|Windows Server 2008 R2 SP1 和 #x 2777; 与 <br/> |不适用  <br/> |是  <br/> |是  <br/> |是  <br/> |是  <br/> |是 & #x 2778; <br/> |
|macOS 10.8 及更高版本 (intel) & #x 2777; <br/> |不适用  <br/> |不适用  <br/> |不适用  <br/> |不适用  <br/> |是  <br/> |是 & #x 2779; <br/> |
   
& #x 2776;企业 Web 应用程序浏览器插件的 Skype 要求特定的共享插件要使用基于计算机的语音、 视频、 共享并查看正在进行屏幕共享和其他功能。 会议与会者提供的选项来安装它们参加会议或当他们启动其中一种功能共享插件。 在 Windows 8，Windows 8.1 共享插件可以安装仅当您在桌面运行 Internet Explorer 10 或 Internet Explorer 11。 这些功能不可用非桌面版本的 Internet Explorer 10 和 11。
  
& #x 2777;在支持的 Windows 7，Windows Server 2008 R2 和 Macintosh 操作系统，所有功能都都可用包括基于计算机的语音、 视频、 应用程序查看、 共享应用程序、 桌面查看和桌面共享。 若要使用这些功能，您必须安装插件的提示时。 请注意，不再支持 Mac OS X 版本 10.7。
  
& #x 2778;从 Windows 上的铬访问 Web 应用程序将启动一个小程序，该程序将加载嵌入式 Internet Explorer 框架中使 Web 应用程序。 此程序需要一种受支持版本的 Internet Explorer 安装 Web 应用程序能够正确加载。
  
& #x 2779;从 Chrome 在 Mac 上访问 Web 应用程序将启动一个小程序，该程序将加载 Web 应用程序中嵌入的 Safari 框架。 该程序需要的支持为使 Web 应用程序能够正确加载安装版本的 Safari。
  
> [!NOTE]
> Office 365 的用户可以使用 Internet Explorer 10 或更高版本使用 Skype 业务。 
  
### <a name="skype-meetings-app"></a>Skype 会议应用

Skype 会议应用程序稍后安装，或作为应用程序运行在具有 32 位和 64 位 Internet Explorer 11 使用 Windows 10、 Windows 8.1、 Windows 8、 Windows 7 计算机上。 
  
该应用程序还在运行 macOS 10.10 或更高版本的操作系统与任何特定的浏览器依赖项。 
  
有关其他任何依赖项，请参阅[支持 Skype 会议应用程序的平台](https://support.office.com/en-US/client/results?Shownav=true&amp;lcid=1033&amp;ns=SKFBWA&amp;version=15&amp;omkt=en-US&amp;ver=15&amp;HelpID=SfBWebApp4001)
  
## <a name="hardware-requirements"></a>硬件要求
<a name="OS-Browser"> </a>

计算机硬件要求由操作系统和浏览器确定。 语音和电话功能需要麦克风和扬声器、带麦克风的耳机或者与计算机的同等设备。 视频功能需要与计算机兼容的视频设备。 有关视频硬件支持和预期的视频质量的详细信息，请参阅[Skype 业务客户端的视频分辨率](video-resolutions.md)。
  
## <a name="network-requirements"></a>网络要求
<a name="Network"> </a>

如果会议的连接问题的业务 Web 应用程序或 Skype 会议应用程序体验 Skype 的用户，很有组织的网络基础结构被配置为不支持 Office 365 提供[Office 365 的 Url 和 IP 地址范围](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US)中所述。 这种情况是否创建会议的 Skype 用户在线业务或 Skype 业务服务器 2015年个。 
  
如果用户是在网络上未配置所述，许多应用程序功能可能会或可能不起作用，它们可能不能连接到所有会议。
  
## <a name="supported-meetings-features"></a>支持的会议功能
<a name="BKMK_Conferencing"> </a>

此表比较企业 Web 应用程序、 Skype 会议应用程序，和 Lync Web 应用程序可用的业务客户端的 Skype，Skype 用户的会议功能。 Lync Web 应用程序列出的功能比较目的： 用户将仅下载和使用 Lync Web 应用程序，如果 Lync 2013 服务器上主持了会议。
  

|**特性/功能**|**Skype 业务 2016年客户端**|**Skype 的 Mac 客户端上的业务**|**Skype 会议应用程序**|**Skype 业务 Web 应用程序**|**Lync Web 应用程序**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|添加计算机音频  <br/> |![核对清单检查](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![核对清单检查](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![核对清单检查](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)（需要插件）  <br/> |![核对清单检查](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)（需要插件）  <br/> |![核对清单检查](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)（需要插件）  <br/> |
|添加视频  <br/> |![核对清单检查](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![核对清单检查](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![核对清单检查](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)（需要插件）  <br/> |![核对清单检查](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)（需要插件）  <br/> |![核对清单检查](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)（需要插件）  <br/> |
|对经过身份验证的参与者切换到电话的音频  <br/> |![核对清单检查](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![核对清单检查](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![核对清单检查](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![核对清单检查](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![核对清单检查](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|
|切换到电话的音频，来宾参与者  <br/> |![核对清单检查](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![核对清单检查](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![核对清单检查](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|||
|查看多方视频（库视图）  <br/> |![核对清单检查](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![核对清单检查](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![核对清单检查](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![核对清单检查](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![核对清单检查](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|
|基于视频的屏幕共享  <br/> |![核对清单检查](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![核对清单检查](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png) （对于仅承载在 Skype 的在线业务的会议） <br/> |![核对清单检查](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)（仅查看）  <br/> |||
|使用会议中演示者控件  <br/> |![核对清单检查](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![核对清单检查](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![核对清单检查](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![核对清单检查](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![核对清单检查](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|
|访问详细的会议名单  <br/> |![核对清单检查](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![核对清单检查](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![核对清单检查](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![核对清单检查](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![核对清单检查](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|
|参与多方 IM  <br/> |![核对清单检查](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![核对清单检查](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![核对清单检查](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![核对清单检查](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![核对清单检查](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|
|发送高重要性 IM 消息  <br/> |![核对清单检查](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|||||
|共享桌面（如果已启用）  <br/> |![核对清单检查](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![核对清单检查](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![核对清单检查](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)![读取脚注 1](../../media/817e529d-a5e1-4969-a195-f3ba3c6a2e7f.png)（需要插件）  <br/> |![核对清单检查](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)![读取脚注 1](../../media/817e529d-a5e1-4969-a195-f3ba3c6a2e7f.png)（需要插件）  <br/> |![核对清单检查](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)![读取脚注 1](../../media/817e529d-a5e1-4969-a195-f3ba3c6a2e7f.png)（需要插件）  <br/> |
|共享程序（如果已启用）  <br/> |![核对清单检查](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)||![核对清单检查](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)（仅限上需要插件）  <br/> |![核对清单检查](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)（仅限上需要插件）  <br/> |![核对清单检查](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)（仅限上需要插件）  <br/> |
|控制其他用户的共享的桌面或程序  <br/> |![核对清单检查](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)||![核对清单检查](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)（仅限上需要插件）  <br/> |![核对清单检查](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)（仅限上需要插件）  <br/> |![核对清单检查](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)（仅限上需要插件）  <br/> |
|允许其他用户共享的桌面或程序的控制  <br/> |![核对清单检查](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|||||
|添加匿名参与者（如果已启用）  <br/> |![核对清单检查](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![核对清单检查](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![核对清单检查](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![核对清单检查](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![核对清单检查](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|
|邀请参与者按名称  <br/> |![核对清单检查](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![核对清单检查](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)||||
|邀请参与者按电话号码  <br/> |![核对清单检查](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![核对清单检查](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![核对清单检查](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![核对清单检查](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![核对清单检查](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|
|通过电子邮件邀请参与者  <br/> |![核对清单检查](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)||![核对清单检查](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![核对清单检查](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![核对清单检查](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|
|使用电话拨入式音频会议  <br/> |![核对清单检查](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)![读取脚注 2](../../media/e366e0ee-8e3f-4e83-8009-2e7eb5674a18.png)|![核对清单检查](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)![读取脚注 2](../../media/e366e0ee-8e3f-4e83-8009-2e7eb5674a18.png)|![核对清单检查](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)![读取脚注 2](../../media/e366e0ee-8e3f-4e83-8009-2e7eb5674a18.png)|![核对清单检查](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)![读取脚注 2](../../media/e366e0ee-8e3f-4e83-8009-2e7eb5674a18.png)|![核对清单检查](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)![读取脚注 2](../../media/e366e0ee-8e3f-4e83-8009-2e7eb5674a18.png)|
|启动“立即开会”会议  <br/> |![核对清单检查](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![核对清单检查](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)||||
|录制会议  <br/> |![核对清单检查](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|||||
|添加和下载附件  <br/> |![核对清单检查](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)||![核对清单检查](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![核对清单检查](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![核对清单检查](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|
|添加和演示 Microsoft PowerPoint 文件  <br/> |![核对清单检查](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![核对清单检查](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![核对清单检查](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![核对清单检查](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![核对清单检查](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|
|导航 Microsoft PowerPoint 文件  <br/> |![核对清单检查](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![核对清单检查](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![核对清单检查](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![核对清单检查](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![核对清单检查](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|
|添加和编辑 OneNote 会议笔记  <br/> |![核对清单检查](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)||仅编辑（不添加）  <br/> |仅编辑（不添加）  <br/> |仅编辑（不添加）  <br/> |
|使用白板  <br/> |![核对清单检查](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)||![核对清单检查](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![核对清单检查](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![核对清单检查](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|
|发起投票  <br/> |![核对清单检查](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)||![核对清单检查](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![核对清单检查](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![核对清单检查](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|
|上载文件以与其他人共享  <br/> |![核对清单检查](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)||![核对清单检查](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![核对清单检查](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![核对清单检查](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|
|安排会议或电话会议  <br/> |Outlook 或 Skype 业务网站计划程序  <br/> |Outlook 或 Skype 业务网站计划程序  <br/> |Skype 业务网站计划程序  <br/> |Skype 业务网站计划程序  <br/> |Skype 业务网站计划程序  <br/> |
|问：&amp;管理器  <br/> |![核对清单检查](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)||![核对清单检查](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![核对清单检查](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![核对清单检查](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|
|禁用与会者视频  <br/> |![核对清单检查](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|||||
|禁用会议 IM  <br/> |![核对清单检查](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)||![核对清单检查](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![核对清单检查](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![核对清单检查](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|
|静音的观众  <br/> |![核对清单检查](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![核对清单检查](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![核对清单检查](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![核对清单检查](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![核对清单检查](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|
|将每个人都设为与会者  <br/> |![核对清单检查](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|||||
|开通 Skype 会议直播  <br/> |![核对清单检查](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|||||
   
![读取脚注 1](../../media/817e529d-a5e1-4969-a195-f3ba3c6a2e7f.png) 参与者不能控制共享通过 Lync 为 Mac 2011 或 Communicator Mac 2011 用户的桌面。 Lync 为 Mac 2011 和 Communicator 的 Mac 2011 用户可以控制桌面由 Windows 用户共享。 这还不适合用于 Skype 业务上最大的 OSX 的 Web 应用程序。
  
![读取脚注 2](../../media/e366e0ee-8e3f-4e83-8009-2e7eb5674a18.png) Skype 的在线业务，这项功能需要 Microsoft PSTN 会议，Exchange 统一消息，或第三方音频会议提供商。
  
![读取脚注 3](../../media/f58a4c2c-e4b3-4954-9eee-1d5f7a89da53.png) Lync 为 Mac 2011 客户端无法查看 Microsoft Office 2013 PowerPoint 演示文稿时共享在会议中通过 Skype 为企业 Web 应用程序。
  
## <a name="known-issues-and-troubleshooting"></a>已知的问题和疑难解答
<a name="BKMK_Conferencing"> </a>

对于最终用户，这些应用程序的[联机帮助](https://aka.ms/smahelp)是随时可供使用。 IT 专业人员应注意以下问题：
  
- 如果不是在网络上的用户配置，以满足[网络需求](meetings-clients.md#Network)，许多应用程序功能可能会或可能不起作用，它们可能不能连接到所有会议。
    
- 某些用户可能有企业管理已禁用权限来安装应用程序的计算机。 对于这些用户，既没有应用程序是一个选项，但[智能手机](https://products.office.com/en-us/skype-for-business/download-app?tab=tabs-1)和[手写板](https://products.office.com/en-us/skype-for-business/download-app?tab=tabs-2)的用户可以安装可用于参加会议的廉价移动客户端。
    
    在[帮助主题](https://support.office.com/en-us/article/Trouble-installing-the-Skype-for-Business-Web-App-plug-in-958fc5f1-2d6f-42e3-815d-a9516c591274?ui=en-US&amp;rs=en-US&amp;ad=US)中，还会涉及其他安装问题。 
    
- 用户可能会看到防火墙警告第一次会议的应用程序运行它们。 他们可能提示您打开端口优化体验，并且这可能要求它们可能没有的计算机上的管理员权限。 应用程序应仍正常工作，用户可以放心地拒绝打开请求的端口。 
    
- 您必须[没有筛选启用 ActiveX](https://support.office.com/en-us/article/Turn-off-ActiveX-filtering-for-Skype-for-Business-Web-App-b6de8ff6-ac7e-4e2f-b18c-2f13db643c41?ui=en-US&amp;rs=en-US&amp;ad=US)在 Internet Explorer 中即使不是 IE 默认浏览器。 在企业 Web 应用程序，一个 ActiveX 控件的 Skype — — 将其他功能添加到 web 应用程序或其他程序的小型模块 — — 是所必需的音频、 视频和屏幕共享。
    
- Skype 业务 Web 应用程序能够正常运行的某些功能，您必须允许计算机或设备上的[cookie 保存](https://support.office.com/en-us/article/Allow-cookies-for-Skype-Meetings-App-Skype-for-Business-Web-App-2108276b-b5c3-484b-bf2b-dac6eeba4c93)到您的浏览器。
    
- 您可能需要[打开 JavaScript](https://support.office.com/en-us/article/Turn-on-JavaScript-for-Skype-Meetings-App-Skype-for-Business-Web-App-3d997bf9-637c-4fe6-8ee3-9e62bfda52cd)支持企业 Web 应用程序功能的某些 Skype，以达到预期效果的浏览器中。
    
### <a name="cryptographic-requirements-due-to-asp-net-45"></a>由于 ASP.NET 4.5 加密需求

自业务服务器 2015 CU5 的 Skype，ASP.NET 4.6 不支持 AES 和这可能会导致 Skype 会议应用程序无法启动。 如果客户端使用 AES 作为您将需要将计算机密钥值重置为 sha-1 或 IIS 上的 Skype 会议应用程序站点级别上的另一种受支持的算法的计算机密钥验证值。 如有必要，请参阅[IIS 8.0 ASP.NET 配置管理](https://docs.microsoft.com/en-us/iis/get-started/whats-new-in-iis-8/iis-80-aspnet-configuration-management)。
  
其他受支持的值是：
  
- HMACSHA256
    
- HMACSHA384
    
- HMACSHA512
    
 AES、 3DES 和 MD5 不再允许，因为过去在 ASP.NET 4 中的值。[在 ASP.NET 4.5，2 磅的加密改进](https://blogs.msdn.microsoft.com/webdev/2012/10/23/cryptographic-improvements-in-asp-net-4-5-pt-2/)有更多详细信息。
  
## <a name="see-also"></a>另请参阅
<a name="BKMK_Conferencing"> </a>

#### 

[为业务服务器 2015年部署在 Skype 的 Web 下载客户端](../../deploy/deploy-clients/deploy-web-downloadable-clients.md)
#### 

[Skype 会议应用程序支持的平台](https://support.office.com/en-US/client/results?Shownav=true&amp;lcid=1033&amp;ns=SKFBWA&amp;version=15&amp;omkt=en-US&amp;ver=15&amp;HelpID=SfBWebApp4001)

