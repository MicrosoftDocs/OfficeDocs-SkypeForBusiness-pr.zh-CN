---
title: 启用或禁用联盟和公共 IM 连接
ms:assetid: 8ec58f4b-9f6d-47b4-a187-d18a83fe4577
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182549(v=OCS.15)
ms:contentKeyID: 48184813
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 支持的联合身份验证，则需要启用具有与受信任客户或合作伙伴组织，包括伙伴域和公共即时消息 (IM) 提供程序用户的支持，与中的用户进行协作的用户帐户的用户您组织。
ms.openlocfilehash: 9e293c70565832944a10e3c6d2533425c747197e
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2018
ms.locfileid: "27222994"
---
# <a name="enable-or-disable-federation-and-public-im-connectivity-in-skype-for-business-server"></a>启用或禁用联盟和公共 IM 连接中 Skype 业务服务器

支持的联合身份验证，则需要启用具有与受信任客户或合作伙伴组织，包括伙伴域和公共即时消息 (IM) 提供程序用户的支持，与中的用户进行协作的用户帐户的用户您组织。 使用承载的 Exchange 服务提供商向其邮箱位于托管 Exchange 服务，如 Microsoft Exchange Online 的企业语音用户提供语音邮件还需要联合身份验证。 建立与这些外部域的信任关系之后，您可以授权这些域中的用户能够访问您的部署和参与 Skype 的业务服务器通信。 此信任关系称为联盟，它不相关，或取决于，Active Directory 信任关系。

若要支持联盟域用户访问，必须启用联合身份验证。 如果您为组织启用联盟，您还必须指定是否要实现以下选项：

  - **启用伙伴域发现**   Skype 业务服务器如果您启用此选项，使用域名系统 (DNS) 记录尝试发现不在允许的域列表中，列出来自自动计算传入通信发现的域联盟伙伴和限制或阻止基于信任级别，请量通信和管理员设置的通信。 如果您未选择此选项，仅对您在允许的域列表包含的域中的用户启用联盟的用户访问。 是否选择此选项，您可以指定的单个域阻止或允许，包括限制对特定服务器的联盟域中运行访问边缘服务的访问。 有关控制联盟域访问的详细信息，请参阅[支持的允许的外部域的配置](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server)。

  - **向联盟伙伴发送存档免责声明**   免责声明通知发送给联盟伙伴的就地存档部署中是。 如果您支持与联盟的伙伴域的外部通信的存档，则应启用存档放弃通知以提醒伙伴已存档其消息。

如果您以后想要临时或永久阻止的联盟域用户访问，您可以为组织禁用联盟。 使用本节中的过程以启用或禁用您的组织，包括指定相应的联合身份验证选项为您的组织支持的联盟的用户访问。

> [!NOTE]  
> 启用联盟的组织仅指定运行访问边缘服务的服务器支持传送到联盟域。 联盟域中的用户不能参与 IM 或会议组织也配置至少一个策略以支持联盟的用户访问之前。 公共 IM 服务提供商的用户不能参与 IM 或会议组织也配置至少一个策略以支持公共 IM 连接之前。 Skype 业务服务器不能使用托管的 Exchange 服务来提供呼叫应答、 Outlook Voice Access （包括语音邮件） 或位于其邮箱的用户的自动助理服务托管 Exchange 服务上配置托管的语音之前提供的路由信息的邮件策略。 有关配置与其他组织中的联盟域的用户进行通信的策略的详细信息，请参阅[管理 SIP 联盟域为您的组织](../sip-domains/manage-sip-federated-domains-for-your-organization.md)。 此外，如果您想要支持与用户的 IM 服务提供商的通信，则必须配置策略以支持和还配置您想要支持的单个服务提供程序的支持。 有关详细信息，请参阅[管理 SIP 联盟提供程序为您的组织](../sip-providers/manage-sip-federated-providers-for-your-organization.md)。


## <a name="to-enable-or-disable-federated-user-access-for-your-organization"></a>启用或禁用组织的联盟的用户访问

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。 

3.  在左侧的导航栏中，单击**外部用户访问**，然后单击**访问边缘配置**。

4.  在**访问边缘配置**页上，单击**全局**，单击**编辑**，然后单击**显示详细信息**。

5.  在**编辑访问边缘配置**中，执行下列选项之一：
    
      - 要为组织的联盟的用户访问，请选中**启用与联盟用户的通信**复选框。
    
      - 若要禁用组织的联盟的用户访问，请清除**启用与联盟用户的通信**复选框。

6.  如果您选择**启用与联盟用户的通信**复选框，请执行以下操作：
    
    1.  如果您想要支持伙伴域的自动发现，选择**启用伙伴域发现**复选框。
    
    2.  如果您的组织支持外部通信的存档，请选中**向联盟伙伴发送存档免责声明**复选框。

7.  单击“**提交**”。

若要启用联盟的用户与您 Skype 业务服务器部署中的用户进行协作，还必须配置至少一个外部访问策略以支持联盟的用户访问。 有关详细信息，请参阅[配置策略以控制联盟用户访问](../external-access-policies/configure-policies-to-control-federated-user-access.md)。 若要控制特定联盟域的访问，请参阅[配置允许的外部域的支持](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server)。


## <a name="enabling-or-disabling-federation-and-public-im-connectivity-by-using-windows-powershell-cmdlets"></a>启用或禁用联盟和公共 IM 连接使用 Windows PowerShell cmdlet

也可以通过使用 Windows PowerShell 和 Set-csaccessedgeconfiguration cmdlet 来管理联盟和公共 IM 连接。 从业务 Server 命令行管理程序 Skype 或 Windows PowerShell 远程会话，则可以运行此 cmdlet。 

## <a name="to-enable-federation-and-public-im-connectivity"></a>要启用联盟和公共 IM 连接

  - 要启用联盟和公共 IM 连接，请将**AllowFederatedUsers**属性的值设置为 True ($True):
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True



## <a name="to-disable-federation-and-public-im-connectivity"></a>若要禁用联盟和公共 IM 连接

  - 要禁用联盟和公共 IM 连接，请将**AllowFederatedUsers**属性的值设置为 False ($False) 中：
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $False

