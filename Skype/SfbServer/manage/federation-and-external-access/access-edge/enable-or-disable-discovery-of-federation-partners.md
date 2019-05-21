---
title: 启用或禁用联盟伙伴发现
ms.reviewer: ''
ms:assetid: 91fd036b-b1af-47cf-b1cf-0aa0a783c2aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182550(v=OCS.15)
ms:contentKeyID: 48184857
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 在部署你的边缘服务器并为你的组织启用联盟时, 你应该已指定是否支持联盟伙伴域的自动发现。
ms.openlocfilehash: a5569639cf870d2a5da16ef81aa733724a6701b3
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280255"
---
# <a name="enable-or-disable-discovery-of-federation-partners-in-skype-for-business-server"></a>在 Skype for Business 服务器中启用或禁用联盟合作伙伴的发现

在部署你的边缘服务器并为你的组织启用联盟时, 你应该已指定是否支持联盟伙伴域的自动发现。 使用本主题中的过程更改该配置。

> [!NOTE]  
> 以下过程假定你已为你的组织启用联盟。 有关启用联盟的详细信息, 请参阅[启用或禁用远程用户访问](enable-or-disable-remote-user-access.md)。

## <a name="to-enable-or-disable-automatic-discovery-of-federated-domains-for-your-organization"></a>为你的组织启用或禁用自动发现联盟域

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口, 然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。

3.  在左侧导航栏中, 单击 "**外部用户访问**", 然后单击 "**访问边缘配置**"。

4.  在 "**访问边缘配置**" 页面上, 单击 "**全局**", 单击 "**编辑**", 然后单击 "**显示详细信息**"。

5.  在 "**编辑访问边缘配置**" 下的 "**启用与联盟用户的通信**" 下, 选中或清除 "**启用合作伙伴域发现**" 复选框以启用或禁用自动发现合作伙伴域。

6.  单击“**提交**”。

若要使联盟用户能够与 Skype for Business Server 部署中的用户进行协作, 你必须也配置了至少一个外部访问策略来支持联合用户访问。 有关详细信息, 请参阅[启用或禁用联盟和公用 IM 连接](enable-or-disable-federation-and-public-im-connectivity.md)。 有关控制特定联盟域的访问权限的详细信息, 请参阅[管理 sip 联合域](../sip-domains/manage-sip-federated-domains-for-your-organization.md)和[管理 sip 联合提供程序](../sip-providers/manage-sip-federated-providers-for-your-organization.md)。


## <a name="enabling-or-disabling-discovery-of-federation-partners-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell cmdlet 启用或禁用联合身份验证合作伙伴的发现

可使用 Windows PowerShell 和 CsAccessEdgeConfiguration cmdlet 管理联合身份验证合作伙伴的发现。 此 cmdlet 既可以从 Skype for Business 服务器管理外壳运行, 也可以从 Windows PowerShell 的远程会话运行。 


## <a name="to-enable-discovery-of-federation-partners"></a>启用联合合作伙伴的发现

  - 若要启用联合合作伙伴的发现, 请将**EnablePartnerDiscovery**属性的值设置为 True ($True)。 请注意, 必须启用 DNS SRV 路由才能更改此属性值。
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $True


## <a name="to-disable-discovery-of-federation-partners"></a>禁用联盟伙伴的发现

  - 若要禁用联盟伙伴的发现, 请将**EnablePartnerDiscovery**属性的值设置为 False ($False):
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $False

