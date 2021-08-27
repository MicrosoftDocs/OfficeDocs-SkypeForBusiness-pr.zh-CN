---
title: 安装和测试Windows Phone版Skype for Business
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 54289bbe-97e7-44bf-8611-4e740fc5b998
description: 摘要：了解如何在客户端上Skype for Business和测试Windows Phone。
ms.openlocfilehash: f912c1f5bd3c0bd5f8c3cc553c64ee3b7850f63e
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58618148"
---
# <a name="install-and-test-skype-for-business-for-windows-phone"></a>安装和测试Windows Phone版Skype for Business
 
**摘要：** 了解如何在客户端上Skype for Business和测试Windows Phone。
  
该Windows Phone版Skype for Business应用Skype for Business移动设备提供 (即时消息) 以及语音和视频呼叫Windows功能。 使用 Lync 2013 的用户将自动获得更新的应用，或收到手动更新应用的提示，具体取决于其用户设置。 新用户可以从 Windows Phone [Marketplace 下载它](https://go.microsoft.com/fwlink/p/?linkid=231901)。 Windows Phone版Skype for Business应用仅适用于 Windows Phone 8.1 及更高版本。
  
在引导贵组织的用户下载应用之前，你需要运行以下测试，以确保它正确集成到你的环境中。 
  
## <a name="install-skype-for-business-windows-phone-81"></a>安装 Skype for Business Windows Phone 8.1

1. 浏览到[Windows Phone 8 更新中心](https://www.windowsphone.com/en-us/how-to/wp8/update-central)以将手机更新到 Windows Phone 8.1。
    
2. 从手机中，转到 **应用商店**，**然后搜索** Skype for Business。
    
3. 点击 **"安装"。** 
    
## <a name="sign-in-to-skype-for-business-for-the-first-time"></a>首次Skype for Business登录

1. 在 **"开始**"屏幕上，向左轻扫以查看已安装的应用，Windows Phone版Skype for Business，然后点击图标以打开该应用。
    
2. 输入你的登录地址 (例如，user@domain.com) 和密码， **然后点击完成**。
    
     系统可能会要求你同时提供用户名和登录地址。 用户名是登录到组织网络时使用的名称，user@domain.com 域\用户名。
    
3. 在 **"客户体验改善计划**"屏幕上，点击"**加入**"，将有关应用问题和使用情况的匿名数据发送到Microsoft;如果不想参与，则选择"否"。
    
4. 在" **从不错过你的工作呼叫"** 屏幕上，输入具有国家/地区代码的移动号码。 Windows Phone版Skype for Business使用 Wi-Fi 或手机数据网络进行音频或视频呼叫时，系统将自动通过此号码呼叫你并连接到呼叫的音频部分。
    
5. 点击 **"下** 一步"并查看通知和电话簿访问设置：
    
   - **推送通知** 收到新 IM 或呼叫时收到警报。 正常 **情况下， (** 推荐) 。
    
     > [!IMPORTANT]
     > 如果关闭此设置，将不会收到任何 IMS、呼叫或其他Windows Phone版Skype for Business通知，除非应用处于活动状态。 
  
   - **允许电话簿访问** 在移动电话上搜索联系人时，在移动电话上搜索Windows Phone版Skype for Business。
    
6. 点击 **"下** 一步"以开始使用Windows Phone版Skype for Business。
    
    [需要帮助登录？](https://support.office.com/article/6b827683-ad55-471a-bd4b-3d4ec098bf75)
    
## <a name="verify-mobile-client-installation"></a>验证移动客户端安装

配置客户端并成功登录后，请使用以下测试来验证您的 Windows Phone版Skype for Business安装在移动设备上是否正常工作。
  
### <a name="search-for-a-contact-in-the-corporate-directory"></a>搜索企业目录中的联系人

1. 在联系人列表中，点击"搜索 **"。**
    
2. 搜索仅存在于全局地址列表中的联系人。
    
3. 确认联系人姓名出现在搜索结果中。
    
### <a name="test-instant-messaging-and-presence"></a>测试即时消息和状态

1. 在“联系人”列表中，点击一个联系人。
    
2. 在联系人卡片中，点击即时消息 (IM)  ![即时消息中的图标Skype for Business](../../media/90f8d5fa-7968-4ef7-bf5b-dddf9b893905.png)图标。
    
3. 验证是否显示 IM 窗口，以及能否键入和发送 IM。
    
### <a name="test-dial-out-conferencing"></a>测试电话拨出式会议

1. 在Outlook中，安排Skype for Business会议。
    
2. On your Windows Phone， open the meeting invitation.
    
3. 单击会议中的链接以加入会议。
    
4. 应答来自会议服务的呼叫，并确认您已连接到会议音频。
    
### <a name="test-push-notifications"></a>测试推送通知

1. 为此测试选择两个不同的用户帐户。 
    
2. 在用户 A 的Windows Phone，登录Windows Phone版Skype for Business A 的帐户登录。
    
3. 在设备上打开另一个应用程序。
    
4. 在不同的客户端（如桌面客户端）上，Skype for Business B 的帐户登录登录。
    
5. 将 IM 从用户 B 发送到用户 A。
    
6. 验证 IM 通知是否显示在用户 A 的移动设备上。
    
## <a name="remove-skype-for-business-from-your-windows-phone"></a>从Skype for Business中删除Windows Phone

若要从Windows Phone版Skype for Business删除应用，请运行以下操作： 
  
1. 从开始屏幕中，轻扫以查看应用程序列表。 
    
2. 点击并按住Windows Phone版Skype for Business应用程序，然后选择"卸载 **"。**
    


