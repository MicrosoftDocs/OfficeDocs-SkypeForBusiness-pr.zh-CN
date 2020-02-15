---
title: 删除用于外部用户访问的站点或用户策略
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
f1.keywords:
- NOCSH
localization_priority: Normal
description: 您可以删除在 "外部访问策略" 页上的 Skype for Business Server 控制面板中列出的任何站点或用户策略。
ms.openlocfilehash: ae0a0499e7497c4d62884860a2730960e5070ac8
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42041231"
---
# <a name="delete-a-site-or-user-policy-for-external-user-access"></a>删除用于外部用户访问的站点或用户策略

如果创建或配置了不想再使用的外部用户访问策略，可以执行以下操作：

  - 删除已创建的任何站点策略或用户策略。

  - 将全局策略重置为默认设置。默认的全局策略设置拒绝任何外部用户访问。无法删除全局策略。


您可以删除在 "**外部访问策略**" 页上的 Skype For Business Server 控制面板中列出的任何站点或用户策略。 删除全局策略时不会真正删除该策略，而只是将其重置为不支持任何外部用户访问选项的默认设置。 有关重置全局策略的详细信息，请参阅[重置外部用户访问的全局策略](reset-the-global-policy-for-external-user-access.md)。


## <a name="to-delete-a-site-or-user-policy-for-external-user-access"></a>删除外部用户访问的站点或用户策略

1.  从作为 RTCUniversalServerAdmins 组成员的用户帐户（或具有等效的用户权限）或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理员 URL 以打开 Skype for Business Server 控制面板。 

3.  单击“外部用户访问”****，再单击“外部访问策略”****。

4.  在“外部访问策略”**** 选项卡上，单击要删除的站点或用户策略，再单击“编辑”****，然后单击“删除”****。

5.  当系统提示您确认删除时，单击“确定”****。


## <a name="removing-pin-policies-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 删除 PIN 策略

可以使用 Windows PowerShell 和 Set-csexternalaccesspolicy cmdlet 删除外部访问策略。 此 cmdlet 可从 Skype for Business Server 命令行管理程序或从 Windows PowerShell 的远程会话中运行。 


## <a name="to-remove-a-specific-external-access-policy"></a>删除特定的外部访问策略

  - 此命令删除适用于 Redmond 站点的外部访问策略：
    
        Remove-CsExternalAccessPolicy -Identity "site:Redmond"


## <a name="to-remove-all-the-external-access-policies-applied-to-the-per-user-scope"></a>删除应用于每用户作用域的所有外部访问策略

  - 此命令删除在每用户范围配置的所有外部访问策略：
    
        Get-CsExternalAccessPolicy -Filter "tag:*" | Remove-CsExternalAccessPolicy


## <a name="to-remove-all-the-external-access-policies-where-outside-user-access-is-disabled"></a>删除在禁用外部用户访问的所有外部访问策略

  - 此命令删除已禁用外部用户访问的所有外部访问策略：
    
        Get-CsExternalAccessPolicy | Where-Object {$_.EnableOutsideAccess -eq $False} | Remove-CsExternalAccessPolicy


有关详细信息，请参阅[set-csexternalaccesspolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy) cmdlet 的帮助主题。
