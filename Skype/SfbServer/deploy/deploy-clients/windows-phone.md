---
title: 安装和测试 Windows Phone 版 Skype for Business
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 54289bbe-97e7-44bf-8611-4e740fc5b998
description: 摘要： 了解如何安装和测试业务对 Windows Phone 的 Skype。
ms.openlocfilehash: c3f9fcf20726c4fd33dc4de462b64a1397373a0f
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="install-and-test-skype-for-business-for-windows-phone"></a>Skype for Business Server 2015：安装和测试 Windows Phone 版 Skype for Business
 
**摘要：**了解如何安装和测试业务对 Windows Phone 的 Skype。
  
Windows Phone 为业务应用程序为 Skype 带来的业务状态、 即时消息 (IM) 和语音和视频调用 Windows 移动设备到 Skype。 使用 Lync 2013 的用户将自动获得升级的应用程序或接收到手动更新的提示，具体视其用户设置而定。 新用户可以下载它从[Windows Phone 市场](https://go.microsoft.com/fwlink/p/?linkid=231901)。 在 Windows Phone 8.1 或更高版本，Windows Phone 为业务应用程序为 Skype 才可用。
  
之前在您的组织可以下载应用程序引导用户，您需要运行以下测试，以确保它正确地集成到您的环境。 
  
## <a name="install-skype-for-business-windows-phone-81"></a>为业务 Windows Phone 8.1 安装 Skype

1. 浏览到[Windows Phone 8 更新中心](https://www.windowsphone.com/en-us/how-to/wp8/update-central)到 Windows Phone 8.1 更新您的电话。
    
2. 从您的电话转到**存储区**，并搜索**业务的 Skype**。
    
3. 点击“**安装**”。 
    
## <a name="sign-in-to-skype-for-business-for-the-first-time"></a>首次登录 Skype for Business

1. 在**启动**屏幕上，刷左查看您已安装的应用程序、 搜索为 Skype 业务为 Windows Phone，和然后点击该图标以打开该应用程序。
    
2. 输入您的登录地址 (例如，user@domain.com) 和密码，然后点击**完成**。
    
     系统可能会要求您同时提供用户名和登录地址。 用户名是您用于登录到您的组织的网络上，user@domain.com 或域 \ 用户名。
    
3. 在“**客户体验改善计划**”屏幕上，点击“**加入**”将有关应用问题和使用情况的匿名数据发送给 Microsoft，或者，如果不想参与，请点击“**不，谢谢**”。
    
4. 在“**从不错过您的工作呼叫**”屏幕上，输入手机号码（包括国家和地区代码）。 当业务为 Windows Phone 的 Skype 能使用 Wi-fi 或蜂窝数据网络进行音频或视频的通话时，将会自动叫此号码并连接到电话的音频部分。
    
5. 点击**下一页**和检查的通知和通讯簿访问设置：
    
  - **推式通知**当您收到新的即时消息或调用时得到预警。 通常**上**（推荐）。
    
    > [!IMPORTANT]
    > 如果您关闭此设置，将不会通知您 IMs、 呼叫，或其他 Skype 业务为 Windows Phone 通知除非应用程序处于活动状态。 
  
  - **允许通讯簿访问**业务为 Windows Phone 中 Skype 联系人搜索时搜索您的手机上的联系人。
    
6. 点击**下一步**以开始使用 Skype 业务为 Windows Phone。
    
    [登录时需要帮助吗？](https://support.office.com/article/6b827683-ad55-471a-bd4b-3d4ec098bf75)
    
## <a name="verify-mobile-client-installation"></a>验证移动客户端安装

配置客户端并登录成功后，使用以下测试来验证安装 Skype 为 Windows Phone 的业务正常工作，您的移动设备上。
  
### <a name="search-for-a-contact-in-the-corporate-directory"></a>搜索企业目录中的联系人

1. 在“联系人”列表中，点击“**搜索**”。
    
2. 搜索仅存在于全局地址列表中的联系人。
    
3. 确认联系人姓名出现在搜索结果中。
    
### <a name="test-instant-messaging-and-presence"></a>测试即时消息和状态

1. 在“联系人”列表中，点击一个联系人。
    
2. 该联系人的卡片中点击即时消息 (IM) ![Skype for Business 中即时消息的图标](../../media/90f8d5fa-7968-4ef7-bf5b-dddf9b893905.png)图标。
    
3. 确认显示了 IM 窗口，并且您可键入和发送 IM。
    
### <a name="test-dial-out-conferencing"></a>测试电话拨出式会议

1. 在 Outlook 中，安排商务会议 Skype。
    
2. 在 Windows Phone 上，打开会议邀请。
    
3. 单击会议中的链接以加入会议。
    
4. 应答来自会议服务的呼叫，并确认您已连接到会议音频。
    
### <a name="test-push-notifications"></a>测试推送通知

1. 选择两个不同的用户帐户进行此测试。 
    
2. 在用户 A 的 Windows Phone，登录到 Skype 的业务为 Windows Phone 用户 A 的帐户。
    
3. 在设备上打开其他应用程序。
    
4. 在另一个客户机，如台式客户机，登录到 Skype 业务与 B 的用户帐户。
    
5. 将 IM 从用户 B 发送到用户 A。
    
6. 确保即时消息通知用户 A 的移动设备上显示。
    
## <a name="remove-skype-for-business-from-your-windows-phone"></a>删除 Windows Phone Skype 的业务

若要删除从您的移动设备业务为 Windows Phone 应用程序为 Skype: 
  
1. 在开始屏幕上滑动手指，查看应用程序列表。 
    
2. 请点击按住对于 Windows Phone 的业务应用程序中，Skype，然后选择**卸载**。
    
## <a name="see-also"></a>另请参阅

#### 


[开始使用 Skype 为 Windows Phone 8.1 业务]()

