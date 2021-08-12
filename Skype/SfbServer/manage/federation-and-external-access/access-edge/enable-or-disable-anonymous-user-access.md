---
title: 启用或禁用匿名用户访问
ms.reviewer: ''
ms:assetid: f10c19e6-b6f9-4d26-9923-0165f36e4af8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619192(v=OCS.15)
ms:contentKeyID: 49733872
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 如何启用和禁用匿名用户访问Skype for Business Server。
ms.openlocfilehash: c06135c0678309c527ec4bda341c17de2d643ce4d6b947077a3a2d02d71dea55
ms.sourcegitcommit: 2a76435beaac1e5daa647e93f693ea8672ec0135
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/11/2021
ms.locfileid: "57848697"
---
# <a name="enable-or-disable-anonymous-user-access-in-skype-for-business-server"></a>启用或禁用匿名用户访问Skype for Business Server

匿名用户是在你的组织的 Active Directory 域服务或受支持的联盟域中没有用户帐户，但可以受邀远程参加内部部署会议的用户。 通过允许匿名参加会议，匿名用户（即仅通过会议密钥验证其身份的用户）可以加入会议。 允许匿名参与需要为组织启用匿名参与。

如果随后要暂时或永久阻止匿名用户访问，则可为组织禁用它。使用本节中的过程为组织启用或禁用匿名用户访问。

> [!NOTE]  
> 仅为组织启用匿名用户访问，将指定运行访问边缘服务的服务器支持匿名用户访问。 在至少配置一个会议策略并将其应用于一个或多个用户或用户组之前，匿名用户将无法参加组织中的任何会议。 只有分配了配置为支持匿名用户的会议策略的那些用户才能邀请匿名用户参加会议。 有关配置会议策略以支持邀请匿名用户的详细信息，请参阅 [管理会议策略](../../conferencing/conferencing-policies.md)。

## <a name="to-enable-or-disable-anonymous-user-access-for-your-organization"></a>为组织启用或禁用匿名用户访问

1.  从 RTCUniversalServerAdmins 组 (或具有同等用户权限) 或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任意计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开Skype for Business Server控制面板。 

3.  在左侧导航栏中，单击“外部用户访问”，然后单击“访问边缘配置”。

4.  在“访问边缘配置”页上，单击“全局”，再单击“编辑”，然后单击“显示详细信息”。

5.  在“编辑访问边缘配置”中，执行下列操作之一：
    
      - 要为组织启用匿名用户访问，请选中“启用与匿名用户的通信”复选框。
    
      - 要为组织禁用匿名用户访问，请清除“启用与匿名用户的通信”复选框。

6.  单击“提交”。


## <a name="enabling-or-disabling-anonymous-user-access-by-using-windows-powershell-cmdlets"></a>使用 cmdlet 启用或禁用匿名Windows PowerShell访问

可以使用 **Set-CsAccessEdgeConfiguration** cmdlet Windows PowerShell匿名用户访问。 可以从命令行管理程序或 Skype for Business Server远程会话中运行此 cmdlet Windows PowerShell。 

## <a name="to-enable-anonymous-user-access"></a>启用匿名用户访问

  - 要启用匿名用户访问，请将 **AllowAnonymousUsers** 属性的值设置为 True ($True)：<br/><br/>Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $True

## <a name="to-disable-anonymous-user-access"></a>禁用匿名用户访问

  - 要禁用匿名用户访问，请将 **AllowAnonymousUsers** 属性的值设置为 False ($False)：<br/><br/>Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $False


## <a name="see-also"></a>另请参阅

[Set-CsClientPolicy](/powershell/module/skype/Set-CsClientPolicy)  
