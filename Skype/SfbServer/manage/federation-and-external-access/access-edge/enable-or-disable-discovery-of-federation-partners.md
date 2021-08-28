---
title: 启用或禁用联盟伙伴发现
ms.reviewer: ''
ms:assetid: 91fd036b-b1af-47cf-b1cf-0aa0a783c2aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182550(v=OCS.15)
ms:contentKeyID: 48184857
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
description: 在部署边缘服务器并为组织启用联盟时，应该已经指定了是否支持自动发现联盟伙伴域。
ms.openlocfilehash: c2263691e67b819a510087bde6fbd4f5b757e946
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58614092"
---
# <a name="enable-or-disable-discovery-of-federation-partners-in-skype-for-business-server"></a>启用或禁用联盟伙伴在 Skype for Business Server

在部署边缘服务器并为组织启用联盟时，应该已经指定了是否支持自动发现联盟伙伴域。使用本主题中的过程更改此配置。

> [!NOTE]  
> 以下过程假定您已为组织启用联盟。 有关启用联盟的详细信息，请参阅 [启用或禁用远程用户访问](enable-or-disable-remote-user-access.md)。

## <a name="to-enable-or-disable-automatic-discovery-of-federated-domains-for-your-organization"></a>为组织启用或禁用自动发现联盟域

1.  从 RTCUniversalServerAdmins 组 (或具有同等用户权限) 或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任意计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开Skype for Business Server控制面板。

3.  在左侧导航栏中，单击“外部用户访问”，然后单击“访问边缘配置”。

4.  在“访问边缘配置”页上，单击“全局”，再单击“编辑”，然后单击“显示详细信息”。

5.  在“编辑访问边缘配置”的“启用与联盟用户的通信”下，选中或清除“启用伙伴域发现”复选框以启用或禁用自动发现伙伴域。

6.  单击“提交”。

若要使联盟用户能够与 Skype for Business Server 部署中的用户进行协作，还必须至少配置一个外部访问策略以支持联盟用户访问。 有关详细信息，请参阅启用 [或禁用联盟和公共 IM 连接](enable-or-disable-federation-and-public-im-connectivity.md)。 有关控制对特定联盟域的访问的详细信息，请参阅管理 [SIP 联盟](../sip-domains/manage-sip-federated-domains-for-your-organization.md) 域和管理 [SIP 联盟提供程序](../sip-providers/manage-sip-federated-providers-for-your-organization.md)。


## <a name="enabling-or-disabling-discovery-of-federation-partners-by-using-windows-powershell-cmdlets"></a>使用 cmdlet 启用或禁用联盟伙伴Windows PowerShell发现

可以使用 Windows PowerShell cmdlet 管理联盟伙伴Set-CsAccessEdgeConfiguration发现。 此 cmdlet 可以从命令行管理程序Skype for Business Server或远程会话运行Windows PowerShell。 


## <a name="to-enable-discovery-of-federation-partners"></a>启用联盟伙伴发现

  - 要启用联盟伙伴的发现，请将 **EnablePartnerDiscovery** 属性的值设置为 True ($True)。请注意，必须启用 DNS SRV 路由才能更改此属性值。<br/><br/>Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $True


## <a name="to-disable-discovery-of-federation-partners"></a>禁用联盟伙伴发现

  - 要禁用联盟伙伴的发现，请将 **EnablePartnerDiscovery** 属性的值设置为 False ($False)：<br/><br/>Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $False

