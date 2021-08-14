---
title: 启用或禁用联盟和公共 IM 连接
ms.reviewer: ''
ms:assetid: 8ec58f4b-9f6d-47b4-a187-d18a83fe4577
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182549(v=OCS.15)
ms:contentKeyID: 48184813
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 要使具有受信任客户或伙伴组织帐户的用户（包括伙伴域用户和支持的公共即时消息 (IM) 提供商用户）能够与组织中的用户进行协作，必须具有联盟支持。
ms.openlocfilehash: 105ed8a4090835be22847aa1ce2cc9788af74b5d
ms.sourcegitcommit: 97c2faab08ec9b8fc9967827883308733ec162ea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/13/2021
ms.locfileid: "58234167"
---
# <a name="enable-or-disable-federation-and-public-im-connectivity-in-skype-for-business-server"></a>启用或禁用联盟和公共 IM 连接Skype for Business Server

要使具有受信任客户或伙伴组织帐户的用户（包括伙伴域用户和支持的公共即时消息 (IM) 提供商用户）能够与组织中的用户进行协作，必须具有联盟支持。 此外，在使用托管 Exchange 服务提供商以便为其邮箱位于托管 Exchange 服务（例如，Microsoft Exchange Online）上的企业语音用户提供语音邮件时，也需要使用联盟。 当您与这些外部域建立信任关系后，您可以授权这些域中的用户访问您的部署并参与Skype for Business Server通信。 这种信任关系称为联盟，它与 Active Directory 信任关系无关，也不依赖于 Active Directory 信任关系。

要支持联盟域用户访问，必须启用联盟。如果为组织启用联盟，则还必须指定是否实现以下选项：

  - **启用合作伙伴域发现**  如果启用此选项，Skype for Business Server 将使用域名系统 (DNS) 记录尝试发现未列在允许域列表中的域，自动评估来自发现的联盟伙伴的传入流量，并基于信任级别、流量和管理员设置限制或阻止该流量。 如果不选择此选项，则仅对包括在允许域列表上的域中的用户启用联盟用户访问。 无论选择此选项，都可以指定阻止或允许各个域，包括限制对在联盟域中运行访问边缘服务的特定服务器的访问。 有关控制联盟域的访问的详细信息，请参阅 [配置对允许的外部域的支持](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server)。

  - **向联盟合作伙伴发送存档免责声明**    向联盟合作伙伴发送免责声明通知，告知在您的部署中使用了存档功能。如果支持存档与联盟伙伴域的外部通信，应启用存档免责声明通知以提醒伙伴将对他们的消息进行存档。

如果稍后要暂时或永久阻止联盟域用户访问，则可以为组织禁用联盟。可以使用本节中的过程为组织启用或禁用联盟用户访问，包括指定组织所支持的相应联盟选项。

> [!NOTE]  
> 为组织启用联盟只能指定运行访问边缘服务的服务器支持路由到联盟域。 只有至少再配置一个策略以支持联盟用户访问，联盟域中的用户才能参与组织中的 IM 或会议。 只有至少再配置一个策略以支持公共 IM 连接，公共 IM 服务提供商的用户才能参与组织中的 IM 或会议。 Skype for Business Server 在配置提供路由信息的托管语音邮件策略之前，Skype for Business Server 无法使用托管 Exchange 服务为邮箱位于托管 Exchange 服务上的用户提供呼叫应答、Outlook Voice Access (（包括语音邮件) ）或自动助理服务。 有关配置与其他组织中联盟域用户通信的策略的详细信息，请参阅管理组织的 [SIP 联盟域](../sip-domains/manage-sip-federated-domains-for-your-organization.md)。 此外，如果要支持与 IM 服务提供商用户的通信，必须配置支持此类通信的策略，还必须配置对要支持的各个服务提供商的支持。 有关详细信息，请参阅   [管理组织的 SIP 联盟提供程序](../sip-providers/manage-sip-federated-providers-for-your-organization.md)。


## <a name="to-enable-or-disable-federated-user-access-for-your-organization"></a>为组织启用或禁用联盟用户访问

1.  从 RTCUniversalServerAdmins 组 (或具有同等用户权限) 或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任意计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开Skype for Business Server控制面板。 

3.  在左侧导航栏中，单击“外部用户访问”，然后单击“访问边缘配置”。

4.  在“访问边缘配置”页上，单击“全局”，再单击“编辑”，然后单击“显示详细信息”。

5.  在“编辑访问边缘配置”中，执行下列操作之一：
    
      - 要为组织启用联盟用户访问，请选中“启用与联盟用户的通信”复选框。
    
      - 要为组织禁用联盟用户访问，请清除“启用与联盟用户的通信”复选框。

6.  如果已选中“启用与联盟用户的通信”复选框，请执行以下操作：
    
    1.  如果要支持伙伴域的自动发现，请选中“启用伙伴域发现”复选框。
    
    2.  如果组织支持外部通信的存档，请选中“向联盟伙伴发送存档免责声明”复选框。

7.  单击“提交”。

若要使联盟用户能够与 Skype for Business Server 部署中的用户进行协作，还必须至少配置一个外部访问策略以支持联盟用户访问。 有关详细信息，请参阅 [配置策略以控制联盟用户访问](../external-access-policies/configure-policies-to-control-federated-user-access.md)。 若要控制对特定联盟域的访问，请参阅 [配置对允许的外部域的支持](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server)。


## <a name="enabling-or-disabling-federation-and-public-im-connectivity-by-using-windows-powershell-cmdlets"></a>使用 cmdlet 启用或禁用联盟和公共 IM Windows PowerShell连接

联盟和公共 IM 连接也可使用 Windows PowerShell 和 Set-CsAccessEdgeConfiguration cmdlet 进行管理。 可以从命令行管理程序或 Skype for Business Server远程会话运行此 cmdlet Windows PowerShell。 

## <a name="to-enable-federation-and-public-im-connectivity"></a>启用联盟和公共 IM 连接

  - 若要启用联盟和公共 IM 连接，请将 **AllowFederatedUsers** 属性的值设置为 True ($True)：<br/><br/>Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True



## <a name="to-disable-federation-and-public-im-connectivity"></a>禁用联盟和公共 IM 连接

  - 若要禁用联盟和公共 IM 连接，请将 **AllowFederatedUsers** 属性的值设置为 False ($False)：<br/><br/>Set-CsAccessEdgeConfiguration -AllowFederatedUsers $False

