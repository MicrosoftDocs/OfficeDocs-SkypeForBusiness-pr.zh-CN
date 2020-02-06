---
title: 启用或禁用联盟和公共 IM 连接
ms.reviewer: ''
ms:assetid: 8ec58f4b-9f6d-47b4-a187-d18a83fe4577
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182549(v=OCS.15)
ms:contentKeyID: 48184813
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
description: 若要使拥有具有受信任客户或合作伙伴组织的帐户的用户（包括合作伙伴域和你支持的公共即时消息（IM）提供者用户）与你所支持的公共即时消息（IM）提供者的用户协作，必须支持联合身份验证所在.
ms.openlocfilehash: 2e24d670295a751c4cd3f41048fe1807b0fe1723
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818383"
---
# <a name="enable-or-disable-federation-and-public-im-connectivity-in-skype-for-business-server"></a>在 Skype for Business 服务器中启用或禁用联盟和公共 IM 连接

若要使拥有具有受信任客户或合作伙伴组织的帐户的用户（包括合作伙伴域和你支持的公共即时消息（IM）提供者用户）与你所支持的公共即时消息（IM）提供者的用户协作，必须支持联合身份验证所在. 若要使用托管 Exchange 服务提供程序向企业语音用户提供语音邮件（其邮箱位于 Microsoft Exchange Online 等托管 Exchange 服务），还需要联合身份验证。 与这些外部域建立信任关系后，您可以授权这些域中的用户访问您的部署并参与 Skype for Business 服务器通信。 此信任关系称为联合体，它与 Active Directory 信任关系无关，或不依赖。

若要支持受联盟域的用户访问，必须启用联盟。 如果为您的组织启用联盟，还必须指定是否实现以下选项：

  - **启用合作伙伴域发现**   如果启用此选项，则 Skype for business 服务器使用域名系统（DNS）记录来尝试发现未在 "允许的域" 列表中列出的域，自动评估已发现的联盟伙伴的传入流量，并根据信任级别、流量和管理员设置限制或阻止该流量。 如果不选择此选项，则仅对在 "允许的域" 列表中包含的域中的用户启用 "联盟用户访问"。 无论是否选择此选项，您都可以指定要阻止或允许的单个域，包括限制对运行联盟域中的访问边缘服务的特定服务器的访问。 有关通过联盟域控制访问的详细信息，请参阅[配置对允许的外部域的支持](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server)。

  - **将存档免责声明发送给联盟合作伙伴**   声明通知将发送给联盟合作伙伴，以便在部署中存档存档。 如果您支持与联盟伙伴域的外部通信的存档，则应启用 "存档免责声明通知" 以警告合作伙伴其邮件正在存档。

如果稍后希望临时或永久阻止联盟域用户访问，则可以为你的组织禁用联盟。 使用此部分中的过程可为你的组织启用或禁用联盟用户访问权限，包括指定你的组织支持的相应联盟选项。

> [!NOTE]  
> 为你的组织启用联盟仅指定运行 Access Edge 服务的服务器支持路由到联盟域。 联盟域中的用户无法在你的组织中参与 IM 或会议，除非你还配置了至少一个策略来支持联合用户访问。 公共 IM 服务提供商的用户无法在你的组织中参与 IM 或会议，除非你还配置了至少一个策略来支持公用 IM 连接。 Skype for Business 服务器无法使用托管 Exchange 服务为邮箱位于托管 Exchange 服务上的用户提供呼叫应答、Outlook Voice Access （包括语音邮件）或自动助理服务，直到配置托管语音提供路由信息的邮件策略。 有关配置与其他组织中联盟域的用户进行通信的策略的详细信息，请参阅[管理组织的 SIP 联合域](../sip-domains/manage-sip-federated-domains-for-your-organization.md)。 此外，如果你想要支持与 IM 服务提供商的用户进行通信，你必须配置策略来支持它，还必须配置对要支持的单个服务提供商的支持。 有关详细信息，请参阅[管理你的组织的 SIP 联合提供商](../sip-providers/manage-sip-federated-providers-for-your-organization.md)。


## <a name="to-enable-or-disable-federated-user-access-for-your-organization"></a>为你的组织启用或禁用联盟用户访问

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口，然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。 

3.  在左侧导航栏中，单击 "**外部用户访问**"，然后单击 "**访问边缘配置**"。

4.  在 "**访问边缘配置**" 页面上，单击 "**全局**"，单击 "**编辑**"，然后单击 "**显示详细信息**"。

5.  在 "**编辑访问边缘配置**" 中，执行下列操作之一：
    
      - 若要为你的组织启用联盟用户访问，请选中 "**启用与联盟用户的通信**" 复选框。
    
      - 若要为你的组织禁用联盟用户访问，请清除 "**启用与联盟用户的通信**" 复选框。

6.  如果选中 "**启用与联盟用户的通信**" 复选框，请执行下列操作：
    
    1.  如果您希望支持自动发现合作伙伴域，请选中 "**启用合作伙伴域发现**" 复选框。
    
    2.  如果您的组织支持外部通信的存档，请选中 "将**存档声明发送给联盟伙伴**" 复选框。

7.  单击“**提交**”。

若要使联盟用户能够与 Skype for Business Server 部署中的用户进行协作，还必须至少配置一个外部访问策略以支持联合用户访问。 有关详细信息，请参阅[配置用于控制联盟用户访问的策略](../external-access-policies/configure-policies-to-control-federated-user-access.md)。 若要控制特定联盟域的访问权限，请参阅[配置对允许的外部域的支持](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server)。


## <a name="enabling-or-disabling-federation-and-public-im-connectivity-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell cmdlet 启用或禁用联盟和公共 IM 连接

联盟和公共 IM 连接也可以通过使用 Windows PowerShell 和 CsAccessEdgeConfiguration cmdlet 进行管理。 此 cmdlet 既可以从 Skype for Business 服务器管理外壳运行，也可以从 Windows PowerShell 的远程会话运行。 

## <a name="to-enable-federation-and-public-im-connectivity"></a>启用联盟和公共 IM 连接

  - 若要启用联盟和公共 IM 连接，请将**AllowFederatedUsers**属性的值设置为 True （$True）：
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True



## <a name="to-disable-federation-and-public-im-connectivity"></a>禁用联盟和公共 IM 连接

  - 若要禁用联盟和公共 IM 连接，请将**AllowFederatedUsers**属性的值设置为 False （$False）：
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $False

