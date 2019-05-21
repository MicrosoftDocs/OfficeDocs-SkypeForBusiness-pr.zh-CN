---
title: 删除外部用户访问的站点或用户策略
ms.reviewer: ''
ms:assetid: 6d907507-825b-4354-9c03-337a459f72de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521013(v=OCS.15)
ms:contentKeyID: 48184455
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 你可以删除 "外部访问策略" 页面上 "Skype for Business 服务器" 控制面板中列出的任何网站或用户策略。
ms.openlocfilehash: 615df309088a329e07f5417dce16e98366a371c7
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280122"
---
# <a name="delete-a-site-or-user-policy-for-external-user-access"></a>删除外部用户访问的站点或用户策略

如果您已创建或配置了不希望再使用的外部用户访问策略, 则可以执行以下操作:

  - 删除您创建的任何网站或用户策略。

  - 将全局策略重置为默认设置。 默认全局策略设置拒绝任何外部用户访问。 无法删除全局策略。


你可以删除 "**外部访问策略**" 页面上 "Skype For business 服务器" 控制面板中列出的任何网站或用户策略。 删除全局策略实际上并不会将其删除, 而只是将其重置为默认设置, 而不包括对任何外部用户访问选项的支持。 有关重置全局策略的详细信息, 请参阅[重置外部用户访问的全局策略](reset-the-global-policy-for-external-user-access.md)。


## <a name="to-delete-a-site-or-user-policy-for-external-user-access"></a>删除用于外部用户访问的网站或用户策略

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口, 然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。 

3.  单击 "**外部用户访问**", 单击 "**外部访问策略**"。

4.  在 "**外部访问策略**" 选项卡上, 单击要删除的网站或用户策略, 单击 "**编辑**", 然后单击 "**删除**"。

5.  当系统提示确认删除时, 单击 **"确定"**。


## <a name="removing-pin-policies-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 删除 PIN 策略

可以使用 Windows PowerShell 和 CsExternalAccessPolicy cmdlet 删除外部访问策略。 此 cmdlet 既可以从 Skype for Business 服务器管理外壳运行, 也可以从 Windows PowerShell 的远程会话运行。 


## <a name="to-remove-a-specific-external-access-policy"></a>删除特定的外部访问策略

  - 此命令将删除应用于 Redmond 网站的外部访问策略:
    
        Remove-CsExternalAccessPolicy -Identity "site:Redmond"


## <a name="to-remove-all-the-external-access-policies-applied-to-the-per-user-scope"></a>删除应用到每用户范围的所有外部访问策略

  - 此命令将删除在每个用户范围内配置的所有外部访问策略:
    
        Get-CsExternalAccessPolicy -Filter "tag:*" | Remove-CsExternalAccessPolicy


## <a name="to-remove-all-the-external-access-policies-where-outside-user-access-is-disabled"></a>删除禁用外部用户访问权限的所有外部访问策略

  - 此命令将删除在禁用外部用户访问权限的所有外部访问策略:
    
        Get-CsExternalAccessPolicy | Where-Object {$_.EnableOutsideAccess -eq $False} | Remove-CsExternalAccessPolicy


有关详细信息, 请参阅[CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExternalAccessPolicy) cmdlet 的帮助主题。
