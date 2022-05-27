---
title: 启用或禁用联盟和公共 IM 连接
ms.reviewer: ''
ms:assetid: 8ec58f4b-9f6d-47b4-a187-d18a83fe4577
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182549(v=OCS.15)
ms:contentKeyID: 48184813
mtps_version: v=OCS.15
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: 要使具有受信任客户或伙伴组织帐户的用户（包括伙伴域用户和支持的公共即时消息 (IM) 提供商用户）能够与组织中的用户进行协作，必须具有联盟支持。
ms.openlocfilehash: 0b78eacd473422c204f8614464b406657f3dc92b
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/25/2022
ms.locfileid: "65675744"
---
# <a name="enable-or-disable-federation-and-public-im-connectivity-in-skype-for-business-server"></a>在Skype for Business Server中启用或禁用联合身份验证和公共 IM 连接

要使具有受信任客户或伙伴组织帐户的用户（包括伙伴域用户和支持的公共即时消息 (IM) 提供商用户）能够与组织中的用户进行协作，必须具有联盟支持。 此外，在使用托管 Exchange 服务提供商以便为其邮箱位于托管 Exchange 服务（例如，Microsoft Exchange Online）上的企业语音用户提供语音邮件时，也需要使用联盟。 与这些外部域建立信任关系后，可以授权这些域中的用户访问部署并参与Skype for Business Server通信。 这种信任关系称为联盟，它与 Active Directory 信任关系无关，也不依赖于 Active Directory 信任关系。

要支持联盟域用户访问，必须启用联盟。如果为组织启用联盟，则还必须指定是否实现以下选项：

  - **启用合作伙伴域发现**  如果启用此选项，Skype for Business Server使用域名系统 (DNS) 记录来尝试发现未在允许的域列表中列出的域，自动评估来自已发现的联合伙伴的传入流量，并根据信任级别、流量量和管理员设置限制或阻止该流量。 如果未选择此选项，则仅对允许域列表中包含的域中的用户启用联合用户访问权限。 无论是否选择此选项，都可以指定要阻止或允许的单个域，包括限制对在联合域中运行 Access Edge 服务的特定服务器的访问。 有关控制联合域访问权限的详细信息，请参阅 [配置对允许的外部域的支持](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server)。

  - **向联盟合作伙伴发送存档免责声明**    向联盟合作伙伴发送免责声明通知，告知在您的部署中使用了存档功能。如果支持存档与联盟伙伴域的外部通信，应启用存档免责声明通知以提醒伙伴将对他们的消息进行存档。

如果稍后要暂时或永久阻止联盟域用户访问，则可以为组织禁用联盟。可以使用本节中的过程为组织启用或禁用联盟用户访问，包括指定组织所支持的相应联盟选项。

> [!NOTE]  
> 为组织启用联盟只能指定运行访问边缘服务的服务器支持路由到联盟域。 只有至少再配置一个策略以支持联盟用户访问，联盟域中的用户才能参与组织中的 IM 或会议。 只有至少再配置一个策略以支持公共 IM 连接，公共 IM 服务提供商的用户才能参与组织中的 IM 或会议。 Skype for Business Server无法使用托管Exchange服务为邮箱位于托管Exchange上的用户提供呼叫应答、Outlook Voice Access (包括语音邮件) 或自动助理服务 服务，直到配置提供路由信息的托管语音邮件策略。 有关配置策略以与其他组织中联合域的用户通信的详细信息，请参阅 [管理组织的 SIP 联合域](../sip-domains/manage-sip-federated-domains-for-your-organization.md)。 此外，如果要支持与 IM 服务提供商用户的通信，必须配置支持此类通信的策略，还必须配置对要支持的各个服务提供商的支持。 有关详细信息，请参阅   [管理组织的 SIP 联合提供商](../sip-providers/manage-sip-federated-providers-for-your-organization.md)。


## <a name="to-enable-or-disable-federated-user-access-for-your-organization"></a>为组织启用或禁用联盟用户访问

1.  从 RTCUniversalServerAdmins 组的成员 (或具有等效用户权限) 或分配给 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理员 URL 以打开Skype for Business Server 控制面板。 

3.  在左侧导航栏中，单击“外部用户访问”，然后单击“访问边缘配置”。

4.  在“访问边缘配置”页上，单击“全局”，再单击“编辑”，然后单击“显示详细信息”。

5.  在“编辑访问边缘配置”中，执行下列操作之一：
    
      - 要为组织启用联盟用户访问，请选中“启用与联盟用户的通信”复选框。
    
      - 要为组织禁用联盟用户访问，请清除“启用与联盟用户的通信”复选框。

6.  如果已选中“启用与联盟用户的通信”复选框，请执行以下操作：
    
    1.  如果要支持伙伴域的自动发现，请选中“启用伙伴域发现”复选框。
    
    2.  如果组织支持外部通信的存档，请选中“向联盟伙伴发送存档免责声明”复选框。

7.  单击“提交”。

若要使联合用户能够在Skype for Business Server部署中与用户协作，还必须配置至少一个外部访问策略以支持联合用户访问。 有关详细信息，请参阅 [配置策略以控制联合用户访问权限](../external-access-policies/configure-policies-to-control-federated-user-access.md)。 若要控制特定联合域的访问，请参阅 [配置对允许的外部域的支持](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server)。


## <a name="enabling-or-disabling-federation-and-public-im-connectivity-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell cmdlet 启用或禁用联合身份验证和公共 IM 连接

还可以使用Windows PowerShell和Set-CsAccessEdgeConfiguration cmdlet 来管理联合身份验证和公共 IM 连接。 此 cmdlet 可以从 Skype for Business Server Management Shell 运行，也可以从远程Windows PowerShell会话运行。 

## <a name="to-enable-federation-and-public-im-connectivity"></a>启用联合身份验证和公共 IM 连接

  - 若要启用联盟和公共 IM 连接，请将 **AllowFederatedUsers** 属性的值设置为 True ($True)：<br/><br/>Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True



## <a name="to-disable-federation-and-public-im-connectivity"></a>禁用联合身份验证和公共 IM 连接

  - 若要禁用联盟和公共 IM 连接，请将 **AllowFederatedUsers** 属性的值设置为 False ($False)：<br/><br/>Set-CsAccessEdgeConfiguration -AllowFederatedUsers $False

