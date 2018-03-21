---
title: "设置和疑难解答 Skype 的在线业务委派"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 01/22/2018
ms.topic: article
ms.assetid: e676b911-5f82-41d8-b4ce-3d0d45c3cd04
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
description: "本文介绍如何设置和疑难解答 Skype 的在线业务委派。 这篇文章为您提供了安装程序的建议、 最佳做法以及故障排除步骤的指南。"
ms.openlocfilehash: b69f6712f78906bc955d3ce014fe8ccd6ab252c1
ms.sourcegitcommit: 94e32f776364b0aaefe2d2d72062ec1c249eaef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2018
---
# <a name="set-up-and-troubleshoot-skype-for-business-online-delegation"></a>设置和疑难解答 Skype 的在线业务委派

本文介绍如何设置和疑难解答 Skype 的在线业务委派。 这篇文章为您提供了安装程序的建议、 最佳做法以及故障排除步骤的指南。
  
## <a name="guidelines-and-requirements"></a>一些原则和要求

### <a name="guidelines-for-delegation"></a>委派的准则

设置和获取委派正常工作取决于您遵循以下准则：
  
- 您必须使用与最新的更新业务 2015年完整客户端为 Skype 或 Skype 业务 2016年完整客户端。
    
- 您必须使用最新的更新的 Outlook 2013 客户机或 Outlook 2016 客户端。
    
- 请确保代理者和代理的计算机具有一个 Outlook 邮件配置文件的主或默认的配置文件。 该邮件配置文件应该包含一个帐户。
    
- Skype 的代理者和代理的业务应该是在线用户。 此外，每个帐户必须同时联机或同时为内部部署的 Exchange Server 邮箱。
    
- 代理者和委托应使用 Outlook 的相同主要版本号。
    
- **EnableExchangeDelegateSync**属性值应设置为**true**的客户端策略中。 您可以通过 Skype 业务在线 PowerShell 模块中运行**Get CSClientPolicy** cmdlet 验证此设置。
    
- 代理者和委托必须登录到 Skype 业务和 Outlook 在同一时间在不同的工作站上。
    
- 共享的邮箱不支持 Skype 的在线业务委派。 这是因为共享的邮箱没有**sendonbehalf**的访问控制列表 (ACL)。
    
### <a name="skype-for-business-client-version-support"></a>Skype 业务客户端版本支持

||**Outlook 的 2013 年**|**Outlook 的 2016 年**|
|:-----|:-----|:-----|
|**Lync/Skype 业务基本客户端**| 不受支持 |不受支持
|**Skype 的业务 2015**|支持| 支持|
|**Skype 业务 2016 年**|支持| 支持|

   
### <a name="licensing-requirements"></a>授权要求

**企业 E3 授权方案**

|**许可证**|**客户端**|**说明**|
|:-----|:-----|:-----|
|企业版 E3  <br/> |Lync 2013 年 (Skype 的业务 2015年) 使用 Outlook 2013 或 Outlook 2016  <br/> Skype 业务 2016 年使用 Outlook 2013 或 Outlook 2016  <br/> |Skype 的业务基本客户端不支持委派。  <br/> 对于 Mac 客户端，可以委托调用，但没有会议。  <br/> |
|企业 E3 Office 365 电话系统 + Office 365 xCalling 计划  <br/> |Lync 2013 年 (Skype 的业务 2015年) 使用 Outlook 2013 或 Outlook 2016  <br/> Skype 业务 2016 年使用 Outlook 2013 或 Outlook 2016  <br/> Lync for Mac 2011  <br/> |Skype 的业务基本客户端不支持委派。  <br/> 对于 Mac 客户端，可以委托调用，但没有会议。  <br/> |
   
**企业 E5 授权方案**

|**许可证**|**客户端**|**说明**|
|:-----|:-----|:-----|
|企业 E5  <br/> |使用 Outlook 2013 或 Outlook 2016 Lync 2013 (Skype 的业务 2015年)。  <br/> Skype 业务 2016 年使用 Outlook 2013 或 Outlook 2016  <br/> |Skype 的业务基本客户端不支持委派。  <br/> 对于 Mac 客户端，可以委托调用，但没有会议。  <br/> |
|企业 E5 加上 Office 365 电话计划  <br/> |Skype 业务 Mac 2016 年的  <br/> Lync 2013 年 (Skype 的业务 2015年) 使用 Outlook 2013 或 Outlook 2016  <br/> Skype 业务 2016 年使用 Outlook 2013 或 Outlook 2016  <br/> Lync for Mac 2011  <br/> |Skype 的业务基本客户端不支持委派。  <br/> 对于 Mac 客户端，可以委托调用，但没有会议。  <br/> |
   
## <a name="set-up-and-verify-delegation"></a>设置并验证委派

若要设置 Skype 的在线业务委派，请执行以下步骤：
  
### <a name="for-windows-clients"></a>对于 Windows 客户端

 **电话转接选项卡**
  
1. 选择**工具** > **选项** > **来电转接设置**。
    
2. 选择**编辑我的代理成员**。
    
3. 选择**添加**，选择您想添加的委托，然后选择**确定**。
    
 **没有来电转接选项卡**
  
1. 在 Outlook 中，选择**文件** > **帐户设置** > **代理访问** > **添加**。
    
2. 找到并添加要委托的人的名称。
    
3. 选择**日历**菜单，然后选择**编辑器 （可以阅读、 创建和修改项目）**。
    
### <a name="for-mac-clients---lync"></a>对于 Mac 客户-Lync

 **电话转接选项卡**
  
- 如果客户端没有**来电转接**的选项卡的**编辑我的代理成员**链接，并代理者位于 Mac 计算机，代理者必须登录到基于 Windows 的计算机以设置委派。 这是因为 Mac 客户端无法使 MAPI 连接，这是建立从 Outlook 的业务委派的 Skype 的要求。
    
### <a name="verify-success"></a>验证成功

如果安装成功，代理应该看到**已添加为 < 名称 > 的代理人**消息，并显示创建**人我呼叫管理的**组。 代理者应该看到**委托**组已创建。
  
> [!NOTE]
> 委派权限通常显示在安装过程的 30 分钟内。 但是，此过程可能需要 24 小时才能完成。 
  
## <a name="troubleshooting"></a>疑难解答

### <a name="common-issues"></a>常见的问题

- > **问题 1**委托人项继续代理者已从 Outlook 客户端中移除委托后出现的**人我呼叫管理的**组中。
    
  - > **解决方法 1**业务客户端的 Skype，在委托**代理**组中，用鼠标右键单击，然后选择**从组中删除**。
    
- > **问题 2**通过 Outlook 客户端授予代理访问权限后，既没有确认消息，也没有**人我呼叫管理的**组将显示为委托。
    
  - > **解决方案 2**从 Outlook 客户端删除委派、 等待复制，大约 15 分钟，然后再次添加该委托。
    
### <a name="other-common-issues"></a>其他常见问题

- 如果超出 25 日委派人和 25 委托的阈值，委派不起作用。
    
- Skype 的业务基本客户端不支持。
    
    > [!NOTE]
    > 如果您安装 Skype 业务基本客户端，它将移除并中断的委派。 
  
- 如果**MAPI Status**值不**确定**，请确保**SIP**和**SMTP**值匹配。
    
    > [!NOTE]
    > 它可能需要几分钟的 MAPI 状态显示为**确定**后第一次对业务和 Outlook 启动 Skype。
  
- 不支持创建安全组并添加该安全组委派权限。
    
- MAPI 是不可用的。 看到[Skype 业务 2016年客户端在"MAPI 不可用"错误消息](https://support.microsoft.com/en-us/help/3147130)。
    
- 联机 Exchange 邮箱并不是可以通过 Skype 业务客户端的访问。 如果发生这种情况，运行[Outlook 连接测试](https://testconnectivity.microsoft.com/)以确保它可以通过。
    
## <a name="related-topics"></a>相关主题
[设置 Skype for Business Online](set-up-skype-for-business-online.md)

[允许 Skype for Business 用户添加 Skype 联系人](let-skype-for-business-users-add-skype-contacts.md)
