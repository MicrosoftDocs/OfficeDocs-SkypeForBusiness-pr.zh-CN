---
title: 启用或禁用匿名用户访问
ms.reviewer: ''
ms:assetid: f10c19e6-b6f9-4d26-9923-0165f36e4af8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619192(v=OCS.15)
ms:contentKeyID: 49733872
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: ''
ms.openlocfilehash: a68790f870a6c62b513caab559580695763cd4df
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30892848"
---
# <a name="enable-or-disable-anonymous-user-access-in-skype-for-business-server"></a>启用或禁用匿名用户访问中 Skype 业务服务器

匿名用户是没有用户帐户，或组织的 Active Directory 域服务中支持联盟域，但可以邀请远程参加内部会议的用户。 通过允许匿名参与会议启用匿名用户 （即，用户通过会议或会议仅密钥验证其身份） 加入会议。 允许匿名参与需要启用您的组织。

如果您以后想要临时或永久防止匿名用户访问，您可以为组织禁用它。 使用本节中的过程以启用或禁用匿名用户访问您的组织。

> [!NOTE]  
> 通过启用匿名用户访问您的组织仅指定运行访问边缘服务的服务器支持匿名用户访问。 匿名用户不能参与组织中的任何会议，直到您还配置至少一个会议策略，并将其应用于一个或多个用户或用户组。 可以邀请匿名用户加入会议的唯一用户是指分配配置以支持匿名用户的会议策略的用户。 有关配置会议策略以支持邀请匿名用户的详细信息，请参阅[管理会议策略](../../conferencing/conferencing-policies.md)。

## <a name="to-enable-or-disable-anonymous-user-access-for-your-organization"></a>启用或禁用匿名用户访问您的组织

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。 

3.  在左侧的导航栏中，单击**外部用户访问**，然后单击**访问边缘配置**。

4.  在**访问边缘配置**页上，单击**全局**，单击**编辑**，然后单击**显示详细信息**。

5.  在**编辑访问边缘配置**中，执行下列选项之一：
    
      - 要为组织的匿名用户访问，请选中**启用与匿名用户的通信**复选框。
    
      - 若要禁用匿名用户访问您的组织，请清除**启用与匿名用户的通信**复选框。

6.  单击“**提交**”。


## <a name="enabling-or-disabling-anonymous-user-access-by-using-windows-powershell-cmdlets"></a>启用或禁用匿名用户访问使用 Windows PowerShell cmdlet

您可以使用 Windows PowerShell 和**Set-csaccessedgeconfiguration** cmdlet 来管理匿名用户访问。 可以从 Skype 业务 Server 命令行管理程序或从 Windows PowerShell 远程会话来运行此 cmdlet。 

## <a name="to-enable-anonymous-user-access"></a>若要启用匿名用户访问

  - 要启用匿名用户访问，请将**AllowAnonymousUsers**属性的值设置为 True ($True) 中：
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $True

## <a name="to-disable-anonymous-user-access"></a>若要禁用匿名用户访问

  - 要禁用匿名用户访问，请将**AllowAnonymousUsers**属性的值设置为 False ($False) 中：
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $False


## <a name="see-also"></a>另请参阅

[Set-CsClientPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsClientPolicy?view=skype-ps)  
  
