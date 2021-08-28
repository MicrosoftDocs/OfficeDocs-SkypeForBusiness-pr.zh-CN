---
title: 重置外部用户访问的全局策略
ms.reviewer: ''
ms:assetid: 8207e1b1-de9e-461f-975f-fcc5c526849a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182545(v=OCS.15)
ms:contentKeyID: 48184675
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: 无法完全删除全局策略。 使用 **全局** 策略上的"删除"选项仅将全局策略重置为默认设置，其中不包括任何外部用户访问选项的支持。
ms.openlocfilehash: 316e0dab6004c3f4b5d07e8428215b4cc0f2deab
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58621048"
---
# <a name="reset-the-global-policy-for-external-user-access-in-skype-for-business-server"></a>重置外部用户访问的全局策略Skype for Business Server 

如果已创建或配置了不再需要的外部用户访问策略，可以使用以下方法：

  - 删除已创建的任何站点策略或用户策略。

  - 将全局策略重置为默认设置。 默认的全局策略设置拒绝任何外部用户访问。 无法删除全局策略。

无法完全删除全局策略。 全局 **策略** 上的"删除"选项仅将全局策略重置为默认设置，其中不包括任何外部用户访问选项的支持。

## <a name="to-reset-the-global-policy-to-the-default-settings"></a>将全局策略重置为默认设置

1.  从 RTCUniversalServerAdmins 组的成员或具有同等用户权限的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任意计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开Skype for Business Server控制面板。

3.  在左侧导航栏中，单击“外部用户访问”，然后单击“外部访问策略”。

4.  在“外部访问策略”选项卡上，单击全局策略，再单击“编辑”，然后单击“删除”。

5.  当系统提示您确认删除时，单击“确定”。此时会在页面顶部显示一条消息，通知您已重置全局策略。


## <a name="resetting-the-global-external-access-policy-by-using-windows-powershell-cmdlets"></a>使用 Cmdlet 重置全局外部访问Windows PowerShell策略

全局外部访问策略可以使用 Windows PowerShell cmdlet Remove-CsExternalAccessPolicy重置。 可以从命令行管理程序或远程Skype for Business Server命令行管理程序运行此 cmdlet Windows PowerShell。 

## <a name="to-reset-the-global-external-access-policy"></a>重置全局外部访问策略

  - 此命令重置全局外部访问策略：<br/><br/>Remove-CsExternalAccessPolicy -Identity "global"

有关详细信息，请参阅 [Remove-CsExternalAccessPolicy](/powershell/module/skype/Remove-CsExternalAccessPolicy) cmdlet 的帮助主题。
