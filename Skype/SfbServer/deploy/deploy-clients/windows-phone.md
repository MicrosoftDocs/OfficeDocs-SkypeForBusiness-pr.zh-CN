---
title: 安装和测试 Windows Phone 版 Skype for Business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 54289bbe-97e7-44bf-8611-4e740fc5b998
description: '摘要: 了解如何在 Windows Phone 上安装和测试 Skype for Business。'
ms.openlocfilehash: 80b7f208153474380e5fae1b1c8a95b3fdb06e39
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2019
ms.locfileid: "36234856"
---
# <a name="install-and-test-skype-for-business-for-windows-phone"></a>Install and test Skype for Business for Windows Phone
 
**摘要:** 了解如何在 Windows Phone 上安装和测试 Skype for Business。
  
Windows Phone 版 Skype for business 应用将 Skype for business 联机状态、即时消息 (IM) 以及语音和视频呼叫带入 Windows mobile 设备。 使用 Lync 2013 的用户将自动获得升级的应用程序或接收到手动更新的提示，具体视其用户设置而定。 新用户可以从[Windows Phone Marketplace](https://go.microsoft.com/fwlink/p/?linkid=231901)下载它。 Windows Phone 版 Skype for Business 应用仅适用于 Windows Phone 8.1 及更高版本。
  
在你的组织中的用户引导下载应用之前, 你需要运行以下测试以确保它已正确集成到你的环境中。 
  
## <a name="install-skype-for-business-windows-phone-81"></a>安装 Skype for Business Windows Phone 8。1

1. 浏览到[Windows phone 8 更新中心](https://www.windowsphone.com/en-us/how-to/wp8/update-central)以将您的电话更新到 windows phone 8.1。
    
2. 在手机上, 转到**应用商店**, 然后搜索**Skype for business**。
    
3. 点击“**安装**”。 
    
## <a name="sign-in-to-skype-for-business-for-the-first-time"></a>首次登录 Skype for Business

1. 在 "**开始**" 屏幕上, 向左轻扫以查看已安装的应用, 搜索 Windows Phone 版 Skype for business, 然后点击该图标以打开该应用。
    
2. 输入你的登录地址 (例如, user@domain.com) 和密码, 然后点击 "**完成**"。
    
     系统可能会要求您同时提供用户名和登录地址。 用户名用于登录组织的网络, 无论是 user@domain.com 还是域 \ 用户名。
    
3. 在“**客户体验改善计划**”屏幕上，点击“**加入**”将有关应用问题和使用情况的匿名数据发送给 Microsoft，或者，如果不想参与，请点击“**不，谢谢**”。
    
4. 在“**从不错过您的工作呼叫**”屏幕上，输入手机号码（包括国家和地区代码）。 当 Windows Phone 版 Skype for Business 无法使用 Wi-fi 或手机网络数据进行音频或视频呼叫时, 将在此号码处自动呼叫, 并连接到呼叫的音频部分。
    
5. 点击 "**下一步**" 并查看通知和电话簿访问设置:
    
   - **推送通知**收到新的即时消息或呼叫时收到通知。 正常**** (推荐)。
    
     > [!IMPORTANT]
     > 如果关闭此设置, 则不会通知 Im、呼叫或其他 Skype for business for Windows Phone 警报, 除非应用处于活动状态。 
  
   - **允许访问电话簿**在 Windows Phone 版 Skype for Business 中搜索联系人时, 搜索手机上的联系人。
    
6. 点击 "**下一步**" 开始使用 Windows Phone 版 Skype for business。
    
    [需要帮助登录？](https://support.office.com/article/6b827683-ad55-471a-bd4b-3d4ec098bf75)
    
## <a name="verify-mobile-client-installation"></a>验证移动客户端安装

配置客户端并成功登录后, 请使用以下测试验证 Windows Phone 版 Skype for Business 的安装是否在移动设备上正常工作。
  
### <a name="search-for-a-contact-in-the-corporate-directory"></a>搜索企业目录中的联系人

1. 在“联系人”列表中，点击“**搜索**”。
    
2. 搜索仅存在于全局地址列表中的联系人。
    
3. 确认联系人姓名出现在搜索结果中。
    
### <a name="test-instant-messaging-and-presence"></a>测试即时消息和状态

1. 在“联系人”列表中，点击一个联系人。
    
2. 在联系人卡片中, 点击即时消息 (IM) ![Skype for Business 中即时消息的图标](../../media/90f8d5fa-7968-4ef7-bf5b-dddf9b893905.png)按钮.
    
3. 确认显示了 IM 窗口，并且您可键入和发送 IM。
    
### <a name="test-dial-out-conferencing"></a>测试电话拨出式会议

1. 在 Outlook 中, 安排 Skype for Business 会议。
    
2. 在 Windows Phone 上，打开会议邀请。
    
3. 单击会议中的链接以加入会议。
    
4. 应答来自会议服务的呼叫，并确认您已连接到会议音频。
    
### <a name="test-push-notifications"></a>测试推送通知

1. 选择两个不同的用户帐户进行此测试。 
    
2. 在用户 A 的 Windows Phone 上, 使用用户 A 的帐户登录 Windows Phone 版 Skype for Business。
    
3. 在设备上打开其他应用程序。
    
4. 在其他客户端 (如桌面客户端) 上, 使用用户 B 的帐户登录 Skype for business。
    
5. 将 IM 从用户 B 发送到用户 A。
    
6. 验证即时消息通知是否显示在用户 A 的移动设备上。
    
## <a name="remove-skype-for-business-from-your-windows-phone"></a>从 Windows Phone 中删除 Skype for Business

要从移动设备删除 Windows Phone 版 Skype for Business 应用, 请执行以下操作: 
  
1. 在开始屏幕上滑动手指，查看应用程序列表。 
    
2. 点击并按住 Windows Phone 版 Skype for Business 应用程序, 然后选择 "**卸载**"。
    


