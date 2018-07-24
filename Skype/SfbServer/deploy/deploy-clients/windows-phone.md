---
title: 安装和测试 Windows Phone 版 Skype for Business
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 54289bbe-97e7-44bf-8611-4e740fc5b998
description: 摘要： 了解如何安装和测试 for Business Windows Phone 上的 Skype。
ms.openlocfilehash: 90e8b99532e51399f9f76e5e12d60a3eeab84481
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "20978045"
---
# <a name="install-and-test-skype-for-business-for-windows-phone"></a>Skype for Business Server 2015：安装和测试 Windows Phone 版 Skype for Business
 
**摘要：** 了解如何安装和测试 for Business Windows Phone 上的 Skype。
  
Windows Phone 的业务应用程序 Skype 延伸 Skype 业务状态、 即时消息 (IM) 和语音和视频呼叫到 Windows mobile 设备。 使用 Lync 2013 的用户将自动获得升级的应用程序或接收到手动更新的提示，具体视其用户设置而定。 新的用户可以从下载[Windows Phone Marketplace](https://go.microsoft.com/fwlink/p/?linkid=231901)。 在 Windows Phone 8.1 和更高版本，业务的 Windows Phone 应用程序 Skype 才可用。
  
之前将用户定向组织下载应用程序中，您需要运行以下测试以确保它已正确集成到您的环境。 
  
## <a name="install-skype-for-business-windows-phone-81"></a>安装 Business Windows Phone 8.1 Skype

1. 浏览到[Windows Phone 8 更新管理中心](https://www.windowsphone.com/en-us/how-to/wp8/update-central)更新您的电话至 Windows Phone 8.1。
    
2. 从您的电话，转到**存储**和**Skype for Business**搜索。
    
3. 点击“**安装**”。 
    
## <a name="sign-in-to-skype-for-business-for-the-first-time"></a>首次登录 Skype for Business

1. 在**开始**屏幕中，向内轻扫保留以查看您已安装的应用程序和搜索的 Skype 业务的 Windows Phone，然后点击图标以打开应用程序。
    
2. 输入您的登录地址 (例如，user@domain.com) 和密码，，，然后点击**完成**。
    
     系统可能会要求您同时提供用户名和登录地址。 User name 是您用于登录到贵组织的网络 user@domain.com 或域 \ 用户名。
    
3. 在“**客户体验改善计划**”屏幕上，点击“**加入**”将有关应用问题和使用情况的匿名数据发送给 Microsoft，或者，如果不想参与，请点击“**不，谢谢**”。
    
4. 在“**从不错过您的工作呼叫**”屏幕上，输入手机号码（包括国家和地区代码）。 当业务的 Windows Phone 的 Skype 不能使用 Wi-fi 或移动电话数据网络进行音频或视频呼叫时，您将自动在此号码调用它们并将其连接到呼叫的音频部分中。
    
5. 点击**下一页**并查看通知和电话簿访问设置：
    
  - **推送通知**当您收到新的 IM 或呼叫时获得通知。 通常**在**（推荐）。
    
    > [!IMPORTANT]
    > 如果关闭此设置，您将不会通知的 Im、 呼叫或业务的 Windows Phone 通知其他 Skype 这是除非应用程序处于活动状态。 
  
  - **允许通讯簿访问**业务的 Windows Phone 中 Skype 联系人搜索时搜索您的移动电话上的联系人。
    
6. 点击**下一步**开始使用 Skype 的业务的 Windows Phone。
    
    [登录时需要帮助？](https://support.office.com/article/6b827683-ad55-471a-bd4b-3d4ec098bf75)
    
## <a name="verify-mobile-client-installation"></a>验证移动客户端安装

配置客户端并成功登录后，使用以下测试验证您安装 Skype for Business 的 Windows Phone 移动设备上正常工作。
  
### <a name="search-for-a-contact-in-the-corporate-directory"></a>搜索企业目录中的联系人

1. 在“联系人”列表中，点击“**搜索**”。
    
2. 搜索仅存在于全局地址列表中的联系人。
    
3. 确认联系人姓名出现在搜索结果中。
    
### <a name="test-instant-messaging-and-presence"></a>测试即时消息和状态

1. 在“联系人”列表中，点击一个联系人。
    
2. 在联系人卡片中，点击即时消息 (IM) ![Skype for Business 中即时消息的图标](../../media/90f8d5fa-7968-4ef7-bf5b-dddf9b893905.png)图标。
    
3. 确认显示了 IM 窗口，并且您可键入和发送 IM。
    
### <a name="test-dial-out-conferencing"></a>测试电话拨出式会议

1. 在 Outlook 中安排业务会议 Skype。
    
2. 在 Windows Phone 上，打开会议邀请。
    
3. 单击会议中的链接以加入会议。
    
4. 应答来自会议服务的呼叫，并确认您已连接到会议音频。
    
### <a name="test-push-notifications"></a>测试推送通知

1. 选择两个不同的用户帐户进行此测试。 
    
2. 在用户 A 的 Windows Phone 上登录到 Skype 的业务的 Windows Phone 用户 A 的帐户。
    
3. 在设备上打开其他应用程序。
    
4. 在不同的客户端，如桌面客户端，登录到 Skype for Business 使用用户 B 的帐户。
    
5. 将 IM 从用户 B 发送到用户 A。
    
6. 确认用户 A 的移动设备上显示 IM 通知。
    
## <a name="remove-skype-for-business-from-your-windows-phone"></a>删除 Windows Phone Skype for Business

从移动设备中删除 Skype 业务的 Windows Phone 应用程序： 
  
1. 在开始屏幕上滑动手指，查看应用程序列表。 
    
2. 点击并按住业务的 Windows Phone 应用程序 Skype 然后选择**卸载**。
    


