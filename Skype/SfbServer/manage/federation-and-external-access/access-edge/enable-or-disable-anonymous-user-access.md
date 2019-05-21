---
title: 启用或禁用匿名用户访问
ms.reviewer: ''
ms:assetid: f10c19e6-b6f9-4d26-9923-0165f36e4af8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619192(v=OCS.15)
ms:contentKeyID: 49733872
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: ''
ms.openlocfilehash: a368a364f39fe8178e9ce4f17a17bea96fea7b23
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280269"
---
# <a name="enable-or-disable-anonymous-user-access-in-skype-for-business-server"></a>在 Skype for Business 服务器中启用或禁用匿名用户访问

匿名用户是在组织的 Active Directory 域服务或受支持的联盟域中没有用户帐户的用户, 但可以邀请他们在本地会议中进行远程参与。 通过允许匿名参与会议, 你可以启用匿名用户 (即仅通过会议或会议密钥验证身份的用户) 来加入会议。 允许匿名参与需要为你的组织启用它。

如果稍后想要临时或永久阻止匿名用户的访问, 则可以为你的组织禁用它。 使用此部分中的过程可为你的组织启用或禁用匿名用户访问权限。

> [!NOTE]  
> 通过为你的组织启用匿名用户访问, 仅指定运行 Access Edge 服务的服务器支持匿名用户的访问。 匿名用户不能参与您的组织中的任何会议, 除非您还配置了至少一个会议策略并将其应用于一个或多个用户或用户组。 只有分配了会议策略 (配置为支持匿名用户) 的用户才可以邀请匿名用户加入会议。 有关配置会议策略以支持邀请匿名用户的详细信息, 请参阅[管理会议策略](../../conferencing/conferencing-policies.md)。

## <a name="to-enable-or-disable-anonymous-user-access-for-your-organization"></a>为你的组织启用或禁用匿名用户访问

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口, 然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。 

3.  在左侧导航栏中, 单击 "**外部用户访问**", 然后单击 "**访问边缘配置**"。

4.  在 "**访问边缘配置**" 页面上, 单击 "**全局**", 单击 "**编辑**", 然后单击 "**显示详细信息**"。

5.  在 "**编辑访问边缘配置**" 中, 执行下列操作之一:
    
      - 若要为你的组织启用匿名用户访问, 请选中 "**启用与匿名用户的通信**" 复选框。
    
      - 若要为你的组织禁用匿名用户访问, 请清除 "**启用与匿名用户的通信**" 复选框。

6.  单击“**提交**”。


## <a name="enabling-or-disabling-anonymous-user-access-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell cmdlet 启用或禁用匿名用户访问

你可以使用 Windows PowerShell 和**CsAccessEdgeConfiguration** cmdlet 管理匿名用户访问。 你可以从 Skype for Business Server Management Shell 或 Windows PowerShell 的远程会话中运行此 cmdlet。 

## <a name="to-enable-anonymous-user-access"></a>启用匿名用户访问

  - 若要启用匿名用户访问, 请将**AllowAnonymousUsers**属性的值设置为 True ($True):
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $True

## <a name="to-disable-anonymous-user-access"></a>禁用匿名用户访问

  - 若要禁用匿名用户访问, 请将**AllowAnonymousUsers**属性的值设置为 False ($False):
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $False


## <a name="see-also"></a>另请参阅

[Set-CsClientPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsClientPolicy?view=skype-ps)  
  
