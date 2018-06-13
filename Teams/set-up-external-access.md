---
title: 允许用户与外部团队用户
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
description: '请参阅如何配置团队以使用户可以与其他组织中的用户或外部给他们的联系人 talk 允许。 '
ms.openlocfilehash: af4b6a61117e96fdbdf869b2bf7fc54c286b42f0
ms.sourcegitcommit: c05731b8a757864c0f6620bfeda3ae28a3582011
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/12/2018
ms.locfileid: "19863377"
---
# <a name="allow-users-to-contact-external-teams-users"></a>允许用户与外部团队用户
  
在下列情况下，请按照本文的步骤进行操作：
  
- 你的用户在企业内的不同域中。例如，Rob@ContosoEast.com 和 Ann@ContosoWest.com。
    
- 在您的组织团队用于联系外部组织的特定企业中的人员，您希望他人。
    
- 您希望任何其他人在世界上使用团队能够找到并与您联系，使用您的电子邮件地址。 如果您和它们使用的默认设置，这将自动工作。 如果他们更改了默认设置，他们需要确认其配置没有阻止你的域。
    
## <a name="enable-business-to-business-communications-for-your-users"></a>为你的用户启用企业到企业通信
<a name="bk_preview"> </a>

在这两个组织为此，您必须在 Office 365 中具有[管理员权限](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)。

![](media/teams-logo-30x30.png)**使用 Microsoft 团队和业务管理中心的 Skype**团队-徽标 30x30.png。
1. 在左侧导航窗格中，转到**组织范围的设置** > **外部访问**。 

2. 在**外部访问**页的顶部，启用**外部访问**。 

3. 单击" **保存**"。 

4. 请确保其他组织中的管理遵循相同的步骤，并进入您的业务为允许域的域。
 
5. **测试最长需要等待 24 小时** 。如果你更改了外部通信设置，最长需要等待 24 小时才能让更改传播到所有数据中心。

  
## <a name="test-and-troubleshoot"></a>测试和故障排除
<a name="bk_preview"> </a>

 **人们在设置企业到企业通信时遇到的最常见的问题是正确完成[Office 365 URL 和 IP 地址范围](https://docs.microsoft.com/en-us/microsoftteams/office-365-urls-ip-address-ranges)。**
  
若要测试您的安装程序，您需要在公司防火墙背后处于不是对团队的联系人。
  
1. 后更改您的外部访问设置，**等待达 24 小时到测试**。
    
2. 搜索团队中您联系人并发送一个请求聊天。
    
    如果您收到一条消息，无法将其发送由于公司策略，您需要仔细检查您的[Office 365 Url 和 IP 地址范围](https://docs.microsoft.com/en-us/microsoftteams/office-365-urls-ip-address-ranges)。
    
3. 让您的联系人向您发送请求聊天。 如果你未收到其请求，那么你的防火墙有问题（假设他们已确认其防火墙设置正确）。
    
4. 测试您的防火墙问题是否另一种方法是转到咖啡馆，如在防火墙背后不处于 wifi 位置并使用团队将请求发送到您的联系人聊天。 如果消息顺利传送，但不是在你工作的时候，那么问题出自你的防火墙。
    
## <a name="how-to-find-others-and-be-found-when-connecting-with-another-business"></a>在与其他企业连接时如何查找其他人以及如何被找到
<a name="bk_preview"> </a>

与其他团队用户启用外部访问后，用户可以通过搜索其登录名查找联盟的团队用户： 例如，Rob@contoso.com。 然后他们将需要将此人添加到他们的联系人列表。
  
  
## <a name="tips-on-setting-up-communications-with-federated-businesses"></a>设置联盟企业通信的提示
<a name="bk_preview"> </a>
    
- 当两个团队用户与 Office 365 域与之通信彼此在单独的域时，只能使用两个组织中打开的团队功能 （例如，视频对话或桌面共享）。
    
- 如果您的组织中的团队用户置于就地或诉讼保留，该用户和其他 Skype 业务或 Skype 用户之间的 IM 对话将保存其邮箱中的**可恢复的项目**中。 这些对话将不保存在其邮箱中的" **对话历史记录**"文件夹中。
  
<a name="bk_preview"> </a>
 
