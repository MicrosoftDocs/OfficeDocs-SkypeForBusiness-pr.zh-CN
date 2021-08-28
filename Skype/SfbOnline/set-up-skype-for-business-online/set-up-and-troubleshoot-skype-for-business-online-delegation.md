---
title: Skype for Business Online 委派设置和疑难解答
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: e676b911-5f82-41d8-b4ce-3d0d45c3cd04
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Setup
description: 本文介绍如何设置和排查联机Skype for Business问题。 本文提供设置建议、最佳做法和故障排除步骤的指导。
ms.openlocfilehash: c461b54bba68cf6570eae6a6b4dc18ab99a63b89
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58587844"
---
# <a name="set-up-and-troubleshoot-skype-for-business-online-delegation"></a>Skype for Business Online 委派设置和疑难解答

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

本文介绍如何设置和排查联机Skype for Business问题。 本文提供设置建议、最佳做法和故障排除步骤的指导。
  
## <a name="guidelines-and-requirements"></a>指南和要求

### <a name="guidelines-for-delegation"></a>委派指南

设置和让委派正常工作取决于你遵循以下准则：
  
- 必须使用具有最新更新的 Skype for Business 2015 完整客户端或 Skype for Business 2016 完整客户端。
    
- 必须使用具有最新更新的 Outlook 2013 客户端或 Outlook 2016 客户端。
    
- 确保委派和委派计算机具有一个Outlook配置文件是主要配置文件或默认配置文件。 该邮件配置文件应仅包含一个帐户。
    
- Skype for Business代理人和代理人的用户应为"联机用户"。 此外，Exchange Server帐户的邮箱必须同时为"联机"或两者均位于本地。
    
- 委派方和代理人应该使用相同的主要版本Outlook。
    
- 在 **客户端策略中，EnableExchangeDelegateSync** 属性值应设置为 true。 可以通过在 Skype for Business Online PowerShell 模块中运行 **Get-CSClientPolicy** cmdlet 来验证此设置。
    
- 委托方和代理人必须同时Skype for Business Outlook登录到不同的工作站。
    
- 联机委派不支持Skype for Business邮箱。 这是因为共享邮箱没有 ACL 中的 **sendonbehalf** 访问控制列表 (ACL) 。
    
### <a name="skype-for-business-client-version-support"></a>Skype for Business客户端版本支持

||**Outlook 2013**|**Outlook 2016**|
|:-----|:-----|:-----|
|**Lync/Skype for Business基本客户端**| 不支持 |不支持
|**Skype for Business 2015**|支持| 支持|
|**2016 Skype for Business 2016 年 1 月**|支持| 支持|

   
### <a name="licensing-requirements"></a>许可要求

**EnterpriseE3 许可方案**

|**许可证**|**客户端**|**注释**|
|:-----|:-----|:-----|
|企业版 E3  <br/> |Lync 2013 (Skype for Business 2015) 2013 Outlook 2013 或 Outlook 2016  <br/> Skype for Business 2016 Outlook 2013 或 Outlook 2016  <br/> |Skype for Business基本客户端不支持委派。  <br/> 对于 Mac 客户端，您可以委派呼叫，但不能委派会议。  <br/> |
|Enterprise具有 Office 365 电话系统 + Office 365 xCalling 计划的 E3  <br/> |Lync 2013 (Skype for Business 2015) 2013 Outlook 2013 或 Outlook 2016  <br/> Skype for Business 2016 Outlook 2013 或 Outlook 2016  <br/> Lync for Mac 2011  <br/> |Skype for Business基本客户端不支持委派。  <br/> 对于 Mac 客户端，您可以委派呼叫，但不能委派会议。  <br/> |
   
**EnterpriseE5 许可方案**

|**许可证**|**客户端**|**注释**|
|:-----|:-----|:-----|
|EnterpriseE5  <br/> |Lync 2013 (Skype for Business 2015) Outlook 2013 或 Outlook 2016。  <br/> Skype for Business 2016 Outlook 2013 或 Outlook 2016  <br/> |Skype for Business基本客户端不支持委派。  <br/> 对于 Mac 客户端，您可以委派呼叫，但不能委派会议。  <br/> |
|EnterpriseE5 加Office 365呼叫计划  <br/> |2016 Mac版Skype for Business 2016 年 1 月  <br/> Lync 2013 (Skype for Business 2015) 2013 Outlook 2013 或 Outlook 2016  <br/> Skype for Business 2016 Outlook 2013 或 Outlook 2016  <br/> Lync for Mac 2011  <br/> |Skype for Business基本客户端不支持委派。  <br/> 对于 Mac 客户端，您可以委派呼叫，但不能委派会议。  <br/> |
   
## <a name="set-up-and-verify-delegation"></a>设置并验证委派

若要设置 Skype for Business Online 委派，请执行以下步骤：
  
### <a name="for-windows-clients"></a>对于 Windows 客户端

 **"呼叫转发"选项卡**
  
1. 选择 **"工具**  >  **选项**  >  **""呼叫设置"。**
    
2. 选择 **"编辑我的代理人成员"。**
    
3. 选择 **"添加**"，选择要添加的代理人，然后选择"确定 **"。**
    
 **"无呼叫转发"选项卡**
  
1. 在Outlook，选择 **"文件**  >  **帐户"设置"**  >  **代理访问添加**  >  **"。**
    
2. 找到并添加要成为代理人的人的姓名。
    
3. 选择" **日历"** 菜单，然后选择"编辑器 **(，** 然后即可读取、创建和修改) 。
    
### <a name="for-mac-clients---lync"></a>对于 Mac 客户端 - Lync

 **"呼叫转发"选项卡**
  
- 如果客户端没有包含"编辑我的代理人成员"链接的"呼叫转发"选项卡，并且代理人位于 Mac 计算机上，则代理人必须登录到基于 Windows 的计算机才能设置委派。 这是因为 Mac 客户端无法建立 MAPI 连接，这是建立从 Skype for Business 委派Outlook。
    
### <a name="verify-success"></a>验证成功

如果设置成功，代理人应看到"你已添加为<">"消息，并且"我管理呼叫的人 **"** 组已创建。  委派者应会看到"代理人 **"** 组已创建。
  
> [!NOTE]
> 委派权限通常在设置过程的 30 分钟内显示。 但是，此过程可能需要 24 小时才能完成。 
  
## <a name="troubleshooting"></a>疑难解答

### <a name="common-issues"></a>常见问题

- > **问题 1** 委派者从客户中删除代理人后，代理人条目将继续显示在"我管理呼叫人员"Outlook组中。
    
  - > **解决方法 1** 在Skype for Business，右键单击"代理人"组中代理人，然后选择"**从组中删除"。** 
    
- > **问题 2** 通过代理客户端授予代理Outlook，确认消息和"我管理呼叫的人"组不会显示给代理人。
    
  - > **解决方法 2** 从客户端中删除Outlook，等待大约 15 分钟进行复制，然后再次添加委托。
    
### <a name="other-common-issues"></a>其他常见问题

- 如果超过 25 个委派者与 25 个代理人的阈值，则委派不起作用。
    
- 不支持Skype for Business基本客户端。
    
    > [!NOTE]
    > 如果安装基本Skype for Business，它将删除并中断委派。 
  
- 如果 **MAPI 状态** 值不正常 **，** 请确保 SIP 和 **SMTP** 值匹配。
    
    > [!NOTE]
    > 首次启动"映射"和"映射"后，可能需要几分钟才能将 MAPI 状态Skype for Business Outlook。
  
- 不支持创建安全组并添加该安全组的委派权限。
    
- MAPI 不可用。 请参阅[2016 客户端中的Skype for Business MAPI 不可用"错误](https://support.microsoft.com/help/3147130)。
    
- 无法Exchange Online客户端访问Skype for Business邮箱。 如果发生这种情况，请[运行Outlook测试](https://testconnectivity.microsoft.com/)以确保它通过。
    
## <a name="related-topics"></a>相关主题
[设置 Skype for Business Online](set-up-skype-for-business-online.md)

[允许 Skype for Business 用户添加 Skype 联系人](let-skype-for-business-users-add-skype-contacts.md)

  
 
