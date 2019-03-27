---
title: 重置外部用户访问的全局策略
ms.reviewer: ''
ms:assetid: 8207e1b1-de9e-461f-975f-fcc5c526849a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182545(v=OCS.15)
ms:contentKeyID: 48184675
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 不能完全删除全局策略。 使用全局策略上的**删除**选项仅将重置全局策略为默认设置，不包括支持外部用户访问的任何选项。
ms.openlocfilehash: 048d1f1aabd2e188cefa25358068ea6ec150b8f3
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30877872"
---
# <a name="reset-the-global-policy-for-external-user-access-in-skype-for-business-server"></a>Skype 中的外部用户访问的全局策略重置为业务服务器 

如果您已创建或配置不再想要使用的外部用户访问策略，您可以执行以下操作：

  - 删除您创建的任何站点或用户策略。

  - 全局策略重置为默认设置。 默认全局策略设置拒绝所有外部用户访问。 无法删除全局策略。

不能完全删除全局策略。 使用全局策略上的**删除**选项仅将重置全局策略为默认设置，不包括支持外部用户访问的任何选项。

## <a name="to-reset-the-global-policy-to-the-default-settings"></a>若要将全局策略重置为默认设置

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。

3.  在左侧的导航栏中，单击**外部用户访问**，单击**外部访问策略**。

4.  在**外部访问策略**选项卡上，单击该全局策略，单击**编辑**，然后单击**删除**。

5.  当提示您确认删除操作，请单击**确定**。 在告知您已被重置全局策略页的顶部显示一条消息。


## <a name="resetting-the-global-external-access-policy-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 重全局外部访问策略

使用 Windows PowerShell 和 Remove-csexternalaccesspolicy cmdlet，可以重置全局外部访问策略。 从业务 Server 命令行管理程序 Skype 或 Windows PowerShell 远程会话，则可以运行此 cmdlet。 

## <a name="to-reset-the-global-external-access-policy"></a>若要重置全局外部访问策略

  - 此命令重置全局外部访问策略：
    
        Remove-CsExternalAccessPolicy -Identity "global"

有关详细信息，请参阅[Remove-csexternalaccesspolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExternalAccessPolicy) cmdlet 的帮助主题。


