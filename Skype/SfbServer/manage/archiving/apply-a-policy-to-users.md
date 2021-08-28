---
title: 将存档策略应用于用户Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: bebd45d1-93c3-4e80-8933-755b699b2209
description: 摘要：了解如何将存档策略分配给用户Skype for Business Server。
ms.openlocfilehash: e9bd351b30ed31092420722a956e57578e100642
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58632986"
---
# <a name="apply-an-archiving-policy-to-users-in-skype-for-business-server"></a>将存档策略应用于用户Skype for Business Server

**摘要：** 了解如何向用户分配存档策略Skype for Business Server。
  
如果为位于 Skype for Business Server 上的用户创建了一个或多个用户存档策略，则可以通过向特定用户或用户组应用相应的策略来实现对特定用户的存档支持。 例如，如果创建支持内部通信存档的策略，可以至少将策略应用于一个用户或用户组，以支持存档用户的 Skype for Business Server 通信。
  
> [!NOTE]
> 如果为部署启用了 Microsoft Exchange集成，Exchange In-Place 保留策略将控制是否对位于 Exchange 上且其邮箱置于"保留"状态In-Place存档。 有关详细信息，请参阅 Plan [for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md)和 Configure integration with Exchange storage for [Skype for Business Server](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md)。 
  
## <a name="apply-a-user-policy-by-using-the-control-panel"></a>使用控制面板应用用户策略

若要使用控制面板应用用户策略：
  
1. 使用分配给 CsArchivingAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。 
    
2. 打开浏览器窗口，然后输入管理 URL 以打开Skype for Business Server控制面板。 
    
3. 在左侧导航栏中，单击“用户”，然后搜索要配置的用户帐户。 
    
4. 在列出搜索结果的表中，单击相应的用户帐户，再单击“编辑”，然后单击“显示详细信息”。
    
5. 在 **"编辑 Lync Server 用户"** 中的" **存档策略"** 下，选择要应用存档用户策略。
    
    > [!NOTE]
    > 这些设置 **\<Automatic\>** 将应用默认服务器安装设置。 服务器将自动应用这些设置。
  
6. 单击“提交”。
    
## <a name="apply-a-user-policy-by-using-windows-powershell"></a>使用策略应用用户Windows PowerShell

您还可以使用 **Grant-CsArchivingPolicy** cmdlet Windows PowerShell用户策略。
  
以下命令向用户 Ken Myer 分配每用户存档策略 RedmondArchivingPolicy。
  
```PowerShell
Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName "RedmondArchivingPolicy"
```

此命令将每用户存档策略 RedmondArchivingPolicy 分配给在注册器池上拥有帐户的 atl-cs-001.contoso.com。 有关此命令中使用的 Filter 参数的详细信息，请参阅 [Get-CsUser](/powershell/module/skype/get-csuser?view=skype-ps) cmdlet 文档。
  
```PowerShell
Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.contoso.com"} | Grant-CsArchivingPolicy -PolicyName "RedmondArchivingPolicy"
```

以下命令删除之前分配给 Ken Myer 的任何每用户存档策略。 删除每用户策略后，将自动使用全局策略或本地站点策略（如果存在）管理 Ken Myer。 站点策略优先于全局策略。
  
```PowerShell
Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName $Null
```

有关详细信息，请参阅 [Grant-CsArchivingPolicy](/powershell/module/skype/grant-csarchivingpolicy?view=skype-ps) cmdlet 文档。
