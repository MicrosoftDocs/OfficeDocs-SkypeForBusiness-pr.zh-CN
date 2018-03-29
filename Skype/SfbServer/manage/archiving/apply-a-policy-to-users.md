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
description: 摘要： 了解如何为业务服务器 2015年到 Skype 的用户分配的存档策略。
ms.openlocfilehash: fc9811aa57a1ba397dedce325f03ea2d77e4413b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="apply-an-archiving-policy-to-users-in-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 中向用户应用存档策略

**摘要：**了解如何为业务服务器 2015年到 Skype 的用户分配的存档策略。
  
如果您已创建了一个或多个存档的用户的用户策略的业务服务器 2015年驻留在 Skype 上，可以实现通过将合适的策略应用到这些用户或用户组对特定用户存档支持。 例如，如果您创建的策略来支持内部通信存档，可以将其应用到至少一个用户或用户组，以支持用户的 Skype 业务服务器 2015年通信存档。
  
> [!NOTE]
> 如果您启用 Microsoft Exchange 集成您的部署 Exchange 的就地保存策略控制是否驻留在 Exchange 的用户启用存档和保留在原位上放有自己的邮箱。 有关详细信息，请参阅[规划业务服务器 2015年的 Skype 在归档](../../plan-your-deployment/archiving/archiving.md)和[具有的业务服务器 2015 Skype 的 Exchange 存储配置集成](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md)。 
  
## <a name="apply-a-user-policy-by-using-the-control-panel"></a>使用控制面板应用用户策略

使用控制面板应用用户策略：
  
1. 使用分配给 CsArchivingAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。 
    
2. 打开浏览器窗口，然后输入管理员 URL 打开 Skype 业务服务器控件面板。 
    
3. 在左侧导航栏中，单击“**用户**”，然后搜索要配置的用户帐户。 
    
4. 在列出搜索结果的表中，单击相应的用户帐户，再单击“**编辑**”，然后单击“**显示详细信息**”。
    
5. 在**编辑 Lync 服务器用户****存档策略**下，选择您要应用的存档用户策略。
    
    > [!NOTE]
    > **\<自动\>**设置应用默认服务器安装设置。 服务器将自动应用这些设置。
  
6. 单击“**提交**”。
    
## <a name="apply-a-user-policy-by-using-windows-powershell"></a>通过使用 Windows PowerShell 应用用户策略

您还可以通过使用 Windows PowerShell**授予 CsArchivingPolicy** cmdlet 应用用户策略。
  
以下命令向用户 Ken Myer 分配每用户存档策略 RedmondArchivingPolicy。
  
```
Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName "RedmondArchivingPolicy"
```

此命令将每个用户存档策略 RedmondArchivingPolicy 对所有用户谁具有帐户穴上注册池 atl-cs-001.contoso.com。在此命令中使用该筛选器参数的详细信息，请参阅[获取 CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) cmdlet 文档。
  
```
Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.contoso.com"} | Grant-CsArchivingPolicy -PolicyName "RedmondArchivingPolicy"

```

以下命令可删除之前已分配给 Ken Myer 的所有每用户存档策略。在删除每用户策略后，将自动使用全局策略或本地站点策略（如果有）管理 Ken Myer。站点策略优先于全局策略。
  
```
Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName $Null
```

有关详细信息，请参阅[授予 CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csarchivingpolicy?view=skype-ps) cmdlet 文档。
  

