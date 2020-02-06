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
description: 您不能完全删除全局策略。 使用全局策略中的 "**删除**" 选项仅将全局策略重置为默认设置，不包括对任何外部用户访问选项的支持。
ms.openlocfilehash: e0e59c4de1b7a4bacbef30b4caa3d26c29b81e84
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818263"
---
# <a name="reset-the-global-policy-for-external-user-access-in-skype-for-business-server"></a>在 Skype for Business 服务器中重置外部用户访问的全局策略 

如果您已创建或配置了不希望再使用的外部用户访问策略，则可以执行以下操作：

  - 删除您创建的任何网站或用户策略。

  - 将全局策略重置为默认设置。 默认全局策略设置拒绝任何外部用户访问。 无法删除全局策略。

您不能完全删除全局策略。 使用全局策略中的 "**删除**" 选项仅将全局策略重置为默认设置，不包括对任何外部用户访问选项的支持。

## <a name="to-reset-the-global-policy-to-the-default-settings"></a>将全局策略重置为默认设置

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口，然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。

3.  在左侧导航栏中，单击 "**外部用户访问**"，单击 "**外部访问策略**"。

4.  在 "**外部访问策略**" 选项卡上，单击 "全局策略"，单击 "**编辑**"，然后单击 "**删除**"。

5.  当系统提示确认删除时，单击 **"确定"**。 将在页面顶部显示一条消息，通知您全局策略已重置。


## <a name="resetting-the-global-external-access-policy-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 重置全局外部访问策略

全局外部访问策略可以通过使用 Windows PowerShell 和 CsExternalAccessPolicy cmdlet 进行重置。 此 cmdlet 既可以从 Skype for Business 服务器管理外壳运行，也可以从远程会话 Windows PowerShell 运行。 

## <a name="to-reset-the-global-external-access-policy"></a>重置全局外部访问策略

  - 此命令将重置全局外部访问策略：
    
        Remove-CsExternalAccessPolicy -Identity "global"

有关详细信息，请参阅[CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExternalAccessPolicy) cmdlet 的帮助主题。


