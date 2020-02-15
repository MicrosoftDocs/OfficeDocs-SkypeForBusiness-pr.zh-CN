---
title: 重置外部用户访问的全局策略
ms.reviewer: ''
ms:assetid: 8207e1b1-de9e-461f-975f-fcc5c526849a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182545(v=OCS.15)
ms:contentKeyID: 48184675
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
description: 无法完全删除全局策略。使用全局策略的“删除”**** 选项只能将全局策略重置为默认设置，不包括对任何外部用户访问选项的支持。
ms.openlocfilehash: acb275ac924dbb5b7e9ad377ab4d287a0734f752
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043654"
---
# <a name="reset-the-global-policy-for-external-user-access-in-skype-for-business-server"></a>在 Skype for Business Server 中重置外部用户访问的全局策略 

如果创建或配置了不想再使用的外部用户访问策略，可以执行以下操作：

  - 删除已创建的任何站点策略或用户策略。

  - 将全局策略重置为默认设置。默认的全局策略设置拒绝任何外部用户访问。无法删除全局策略。

无法完全删除全局策略。使用全局策略的“删除”**** 选项只能将全局策略重置为默认设置，不包括对任何外部用户访问选项的支持。

## <a name="to-reset-the-global-policy-to-the-default-settings"></a>将全局策略重置为默认设置

1.  从作为 RTCUniversalServerAdmins 组成员的用户帐户（或具有等效的用户权限）或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理员 URL 以打开 Skype for Business Server 控制面板。

3.  在左侧导航栏中，单击“外部用户访问”****，然后单击“外部访问策略”****。

4.  在“外部访问策略”**** 选项卡上，单击全局策略，再单击“编辑”****，然后单击“删除”****。

5.  当系统提示您确认删除时，单击“确定”****。此时会在页面顶部显示一条消息，通知您已重置全局策略。


## <a name="resetting-the-global-external-access-policy-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 重置全局外部访问策略

可以使用 Windows PowerShell 和 Set-csexternalaccesspolicy cmdlet 重置全局外部访问策略。 此 cmdlet 可从 Skype for Business Server 命令行管理程序或远程会话 Windows PowerShell 中运行。 

## <a name="to-reset-the-global-external-access-policy"></a>重置全局外部访问策略

  - 此命令重置全局外部访问策略：
    
        Remove-CsExternalAccessPolicy -Identity "global"

有关详细信息，请参阅[set-csexternalaccesspolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy) cmdlet 的帮助主题。


