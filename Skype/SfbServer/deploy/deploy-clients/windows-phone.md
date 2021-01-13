---
title: 安装和测试适用于 Windows Phone 的 Skype for Business
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 54289bbe-97e7-44bf-8611-4e740fc5b998
description: 摘要：了解如何在 Windows Phone 上安装和测试 Skype for Business。
ms.openlocfilehash: 8323231f67e8aca87d3670cfee1a2137f0dd6c21
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812712"
---
# <a name="install-and-test-skype-for-business-for-windows-phone"></a>安装和测试适用于 Windows Phone 的 Skype for Business
 
**摘要：** 了解如何在 Windows Phone 上安装和测试 Skype for Business。
  
Skype for Business for Windows Phone 应用将 Skype for Business 状态、即时消息 (IM) 以及语音和视频呼叫引入 Windows 移动设备。 使用 Lync 2013 的用户将自动获取更新的应用，或根据用户设置提示手动更新它。 新用户可以从 [Windows Phone Marketplace 下载它](https://go.microsoft.com/fwlink/p/?linkid=231901)。 Skype for Business for Windows Phone 应用仅适用于 Windows Phone 8.1 及更高版本。
  
在指示组织中用户下载应用之前，你需要运行以下测试，以确保它正确集成到你的环境中。 
  
## <a name="install-skype-for-business-windows-phone-81"></a>安装 Skype for Business Windows Phone 8.1

1. 浏览到 [Windows Phone 8 更新中心](https://www.windowsphone.com/en-us/how-to/wp8/update-central) ，将手机更新到 Windows Phone 8.1。
    
2. 从你的手机，转到 **应用商店**，并搜索 Skype **for Business。**
    
3. 点击 **"安装"。** 
    
## <a name="sign-in-to-skype-for-business-for-the-first-time"></a>首次登录 Skype for Business

1. 在 **"开始** "屏幕上，向左轻扫以查看已安装的应用，搜索适用于 Windows Phone 的 Skype for Business，然后点击图标以打开该应用。
    
2. 输入你的登录地址 (例如，输入user@domain.com) 密码，然后点击"完成 **"。**
    
     系统可能会要求你同时提供用户名和登录地址。 用户名是登录到组织网络时使用的名称，user@domain.com域\用户名。
    
3. 在 **"客户体验改善** 计划"屏幕上，点击"加入"将有关应用问题和使用情况的匿名数据发送给 Microsoft，如果不想参加，则选择"否"。 
    
4. 在 **"永不错过你的工作呼叫** "屏幕上，输入具有国家/地区代码的移动号码。 当 Skype for Business for Windows Phone 无法使用 Wi-Fi 或手机数据网络进行音频或视频呼叫时，系统将自动拨打此号码并连接到呼叫的音频部分。
    
5. 点击 **"下** 一步"并查看通知和电话簿访问设置：
    
   - **推送通知** 收到新 IM 或呼叫时获取警报。 正常 **情况下， (** 推荐) 。
    
     > [!IMPORTANT]
     > 如果关闭此设置，将不会收到有关 IM、呼叫或其他 Skype for Business for Windows Phone 警报的通知，除非应用处于活动状态。 
  
   - **允许电话簿访问** 在 Skype for Business for Windows Phone 中搜索联系人时，在移动电话上搜索联系人。
    
6. 点击 **"下** 一步"开始使用适用于 Windows Phone 的 Skype for Business。
    
    [需要帮助登录？](https://support.office.com/article/6b827683-ad55-471a-bd4b-3d4ec098bf75)
    
## <a name="verify-mobile-client-installation"></a>验证移动客户端安装

配置客户端并成功登录后，使用以下测试验证 Skype for Business for Windows Phone 的安装在移动设备上是否正常工作。
  
### <a name="search-for-a-contact-in-the-corporate-directory"></a>搜索企业目录中的联系人

1. 在联系人列表中，点击"**搜索"。**
    
2. 搜索仅存在于全局地址列表中的联系人。
    
3. 确认联系人姓名出现在搜索结果中。
    
### <a name="test-instant-messaging-and-presence"></a>测试即时消息和状态

1. 在“联系人”列表中，点击一个联系人。
    
2. 在联系人卡片中，点击即时消息 (IM)  ![Skype for Business 中的即时消息图标](../../media/90f8d5fa-7968-4ef7-bf5b-dddf9b893905.png)图标。
    
3. 验证是否显示 IM 窗口，以及能否键入和发送 IM。
    
### <a name="test-dial-out-conferencing"></a>测试电话拨出式会议

1. 在 Outlook 中，安排 Skype for Business 会议。
    
2. 在 Windows Phone 上，打开会议邀请。
    
3. 单击会议中的链接以加入会议。
    
4. 应答来自会议服务的呼叫，并确认您已连接到会议音频。
    
### <a name="test-push-notifications"></a>测试推送通知

1. 为此测试选择两个不同的用户帐户。 
    
2. 在用户 A 的 Windows Phone 上，使用用户 A 的帐户登录到适用于 Windows Phone 的 Skype for Business。
    
3. 在设备上打开另一个应用程序。
    
4. 在不同的客户端（如桌面客户端）上，使用用户 B 的帐户登录 Skype for Business。
    
5. 将 IM 从用户 B 发送到用户 A。
    
6. 验证 IM 通知是否显示在用户 A 的移动设备上。
    
## <a name="remove-skype-for-business-from-your-windows-phone"></a>从 Windows Phone 中删除 Skype for Business

若要从移动设备中删除 Skype for Business for Windows Phone 应用： 
  
1. 从"开始"屏幕中，轻扫以查看应用程序列表。 
    
2. 点击并按住适用于 Windows Phone 的 Skype for Business 应用程序，然后选择"**卸载"。**
    


