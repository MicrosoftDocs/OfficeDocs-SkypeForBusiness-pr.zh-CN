---
title: 删除外部用户访问的站点或用户策略
ms.reviewer: ''
ms:assetid: 6d907507-825b-4354-9c03-337a459f72de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521013(v=OCS.15)
ms:contentKeyID: 48184455
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 您可以删除中列出的 Skype 业务 Server 控制面板的外部访问策略页的任何站点或用户策略。
ms.openlocfilehash: 24d26e8668d04f1c11a3039b4b524d25e209e619
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32197742"
---
# <a name="delete-a-site-or-user-policy-for-external-user-access"></a>删除外部用户访问的站点或用户策略

如果您已创建或配置不再想要使用的外部用户访问策略，您可以执行以下操作：

  - 删除您创建的任何站点或用户策略。

  - 全局策略重置为默认设置。 默认全局策略设置拒绝所有外部用户访问。 无法删除全局策略。


您可以删除中列出的 Skype 业务 Server 控制面板的**外部访问策略**页的任何站点或用户策略。 删除全局策略不会实际删除，但仅将其重置为默认设置，不包括支持外部用户访问的任何选项。 有关重置全局策略的详细信息，请参阅[外部用户访问的全局策略重置](reset-the-global-policy-for-external-user-access.md)。


## <a name="to-delete-a-site-or-user-policy-for-external-user-access"></a>删除外部用户访问的站点或用户策略

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。 

3.  单击**外部用户访问**，单击**外部访问策略**。

4.  在**外部访问策略**选项卡中，单击您想要删除，单击**编辑**，然后单击**删除**站点或用户的策略。

5.  当提示您确认删除操作，请单击**确定**。


## <a name="removing-pin-policies-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 删除 PIN 策略

可以使用 Windows PowerShell 和 Remove-csexternalaccesspolicy cmdlet 删除外部访问策略。 从业务 Server 命令行管理程序 Skype 或 Windows PowerShell 远程会话，则可以运行此 cmdlet。 


## <a name="to-remove-a-specific-external-access-policy"></a>删除特定外部访问策略

  - 此命令删除应用到 Redmond 站点的外部访问策略：
    
        Remove-CsExternalAccessPolicy -Identity "site:Redmond"


## <a name="to-remove-all-the-external-access-policies-applied-to-the-per-user-scope"></a>若要删除所有外部访问策略应用于每用户范围

  - 此命令删除在每用户范围配置的所有外部访问策略：
    
        Get-CsExternalAccessPolicy -Filter "tag:*" | Remove-CsExternalAccessPolicy


## <a name="to-remove-all-the-external-access-policies-where-outside-user-access-is-disabled"></a>若要删除其中禁用外部用户访问的所有外部访问策略

  - 此命令可删除外部用户访问已禁用的所有外部访问策略：
    
        Get-CsExternalAccessPolicy | Where-Object {$_.EnableOutsideAccess -eq $False} | Remove-CsExternalAccessPolicy


有关详细信息，请参阅[Remove-csexternalaccesspolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExternalAccessPolicy) cmdlet 的帮助主题。
