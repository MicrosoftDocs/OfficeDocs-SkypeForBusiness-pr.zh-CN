---
title: 启用或禁用联盟伙伴发现
ms.reviewer: ''
ms:assetid: 91fd036b-b1af-47cf-b1cf-0aa0a783c2aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182550(v=OCS.15)
ms:contentKeyID: 48184857
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 次部署边缘服务器和启用联盟组织中，您应指定是否支持自动发现联盟的伙伴域。
ms.openlocfilehash: de61d8180a8f4e8f8be13abaab3d8911d2c6e22c
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32199939"
---
# <a name="enable-or-disable-discovery-of-federation-partners-in-skype-for-business-server"></a>启用或禁用业务服务器中 Skype 的联盟伙伴的发现

次部署边缘服务器和启用联盟组织中，您应指定是否支持自动发现联盟的伙伴域。 使用本主题中的过程来更改的配置。

> [!NOTE]  
> 下面的过程假定您已为您的组织中启用了联盟。 有关启用联合身份验证的详细信息，请参阅[启用或禁用远程用户访问](enable-or-disable-remote-user-access.md)。

## <a name="to-enable-or-disable-automatic-discovery-of-federated-domains-for-your-organization"></a>启用或禁用组织的联合域的自动发现

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。

3.  在左侧的导航栏中，单击**外部用户访问**，单击**访问边缘配置**。

4.  在**访问边缘配置**页上，单击**全局**，单击**编辑**，然后单击**显示详细信息**。

5.  在**编辑访问边缘配置**下**启用与联盟用户的通信**，请选中或清除**启用伙伴域发现**复选框以启用或禁用自动发现的伙伴域。

6.  单击“**提交**”。

若要启用联盟的用户与您 Skype 业务服务器部署中的用户进行协作，您必须还配置至少一个外部访问策略以支持联盟的用户访问。 有关详细信息，请参阅[启用或禁用联盟和公共 IM 连接](enable-or-disable-federation-and-public-im-connectivity.md)。 有关控制对特定联盟域访问的详细信息，请参阅[管理 SIP 联盟域](../sip-domains/manage-sip-federated-domains-for-your-organization.md)和[管理 SIP 联盟提供商](../sip-providers/manage-sip-federated-providers-for-your-organization.md)。


## <a name="enabling-or-disabling-discovery-of-federation-partners-by-using-windows-powershell-cmdlets"></a>启用或禁用联盟伙伴的发现，通过使用 Windows PowerShell cmdlet

可以使用 Windows PowerShell 和 Set-csaccessedgeconfiguration cmdlet 来管理联盟伙伴的发现。 从业务 Server 命令行管理程序 Skype 或 Windows PowerShell 远程会话，则可以运行此 cmdlet。 


## <a name="to-enable-discovery-of-federation-partners"></a>若要启用联盟伙伴的发现

  - 若要启用联盟伙伴的发现，设置为 True ($True)**将 EnablePartnerDiscovery**属性的值。 请注意，您必须启用 DNS SRV 路由来更改此属性值。
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $True


## <a name="to-disable-discovery-of-federation-partners"></a>若要禁用联盟伙伴的发现

  - 若要禁用联盟伙伴的发现，设置为 False ($False)**将 EnablePartnerDiscovery**属性的值：
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $False

