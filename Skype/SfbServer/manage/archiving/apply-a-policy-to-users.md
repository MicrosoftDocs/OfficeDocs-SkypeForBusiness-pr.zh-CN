---
title: 在 Skype for Business Server 2015 中向用户应用存档策略
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: bebd45d1-93c3-4e80-8933-755b699b2209
description: 摘要： 了解如何为业务服务器 2015年在 Skype 中向用户分配存档策略。
ms.openlocfilehash: 0a9b19f6b02daae09f71b1f9933c90bfc86c5e23
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/05/2018
ms.locfileid: "19569384"
---
# <a name="apply-an-archiving-policy-to-users-in-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 中向用户应用存档策略

**摘要：** 了解如何为业务服务器 2015年在 Skype 中向用户分配存档策略。
  
如果您已创建了一个或多个用户策略的用户的存档的业务服务器 2015年驻留在 Skype，您可以通过将适当的策略应用于这些用户或用户组来实现特定用户的存档支持。 例如，如果您创建策略，以支持的内部通信存档，可将其应用于至少一个用户或用户组，以支持存档的用户的 Skype 业务服务器 2015年通信。
  
> [!NOTE]
> 如果您为您的部署，Exchange 就地保留策略控件上启用 Microsoft Exchange 集成，是否驻留在 Exchange 上的用户启用存档，并且具有其邮箱置于就地保留。 有关详细信息，请参阅[规划存档中的业务服务器 2015 Skype](../../plan-your-deployment/archiving/archiving.md)和[配置与业务服务器 2015年的 Skype 的 Exchange 存储的集成](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md)。 
  
## <a name="apply-a-user-policy-by-using-the-control-panel"></a>使用控制面板应用用户策略

使用控制面板应用用户策略：
  
1. 使用分配给 CsArchivingAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。 
    
2. 打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。 
    
3. 在左侧导航栏中，单击“**用户**”，然后搜索要配置的用户帐户。 
    
4. 在列出搜索结果的表中，单击相应的用户帐户，再单击“**编辑**”，然后单击“**显示详细信息**”。
    
5. 在**编辑 Lync Server 用户****存档策略**下，选择要应用的存档用户策略。
    
    > [!NOTE]
    > **\<自动\>** 设置应用默认服务器安装设置。 服务器将自动应用这些设置。
  
6. 单击“**提交**”。
    
## <a name="apply-a-user-policy-by-using-windows-powershell"></a>使用 Windows PowerShell 将用户策略应用

您还可以使用 Windows PowerShell **Grant-csarchivingpolicy** cmdlet 应用的用户策略。
  
以下命令向用户 Ken Myer 分配每用户存档策略 RedmondArchivingPolicy。
  
```
Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName "RedmondArchivingPolicy"
```

此命令向帐户驻留在注册器池 atl-cs-001.contoso.com 的所有用户分配每用户存档策略 RedmondArchivingPolicy。 有关此命令中同时使用 Filter 参数的详细信息，请参阅[Get-csuser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) cmdlet 文档。
  
```
Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.contoso.com"} | Grant-CsArchivingPolicy -PolicyName "RedmondArchivingPolicy"
```

以下命令可删除之前已分配给 Ken Myer 的所有每用户存档策略。在删除每用户策略后，将自动使用全局策略或本地站点策略（如果有）管理 Ken Myer。站点策略优先于全局策略。
  
```
Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName $Null
```

有关详细信息，请参阅[Grant-csarchivingpolicy](https://docs.microsoft.com/powershell/module/skype/grant-csarchivingpolicy?view=skype-ps) cmdlet 文档。
  

