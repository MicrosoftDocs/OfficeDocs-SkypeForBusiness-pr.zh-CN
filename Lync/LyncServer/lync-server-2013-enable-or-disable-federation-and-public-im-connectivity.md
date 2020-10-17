---
title: Lync Server 2013：启用或禁用联盟和公共 IM 连接
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable federation and public IM connectivity
ms:assetid: 8ec58f4b-9f6d-47b4-a187-d18a83fe4577
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182549(v=OCS.15)
ms:contentKeyID: 48184813
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c94b75aff1b79650adc846d3d761580e9429035d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48526789"
---
# <a name="enable-or-disable-federation-and-public-im-connectivity-in-lync-server-2013"></a>在 Lync Server 2013 中启用或禁用联盟和公共 IM 连接

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-06-24_

要使具有受信任客户或伙伴组织帐户的用户（包括伙伴域用户和支持的公共即时消息 (IM) 提供商用户）能够与组织中的用户进行协作，必须具有联盟支持。 此外，在使用托管 Exchange 服务提供商以便为其邮箱位于托管 Exchange 服务（例如，Microsoft Exchange Online）上的企业语音用户提供语音邮件时，也需要使用联盟。 建立与这些外部域的信任关系后，您可以授权这些域中的用户访问您的部署并参与 Lync Server 通信。 这种信任关系称为联盟，它与 Active Directory 信任关系无关，也不依赖于 Active Directory 信任关系。

要支持联盟域用户访问，必须启用联盟。如果为组织启用联盟，则还必须指定是否实现以下选项：

  - **启用合作伙伴域发现**    如果启用此选项，Lync Server 将使用域名系统 (DNS) 记录以尝试发现未在 "允许的域" 列表中列出的域，并自动评估已发现的联盟伙伴的传入流量，并根据信任级别、流量量和管理员设置来限制或阻止该流量。 如果未选择此选项，则仅对您在允许的域列表中包含的域中的用户启用联合用户访问权限。 无论您是否选择此选项，您都可以指定要阻止或允许的单个域，包括限制对在联合域中运行访问边缘服务的特定服务器的访问。 有关通过联盟域控制访问的详细信息，请参阅 [在 Lync Server 2013 中配置对允许的外部域的支持](lync-server-2013-configure-support-for-allowed-external-domains.md)。

  - **向联盟伙伴**     发送存档免责声明将免责声明通知发送给联盟伙伴，以便在您的部署中存档存档。 如果您支持存档与联盟伙伴域的外部通信，则应启用存档免责声明通知，以警告合作伙伴其邮件正在被存档。

如果稍后要暂时或永久阻止联盟域用户访问，则可以为组织禁用联盟。可以使用本节中的过程为组织启用或禁用联盟用户访问，包括指定组织所支持的相应联盟选项。

<div>


> [!NOTE]  
> 为组织启用联盟只能指定运行访问边缘服务的服务器支持路由到联盟域。 只有至少再配置一个策略以支持联盟用户访问，联盟域中的用户才能参与组织中的 IM 或会议。 只有至少再配置一个策略以支持公共 IM 连接，公共 IM 服务提供商的用户才能参与组织中的 IM 或会议。 只有配置提供路由信息的托管语音邮件策略，Lync Server 才能使用托管 Exchange 服务向邮箱位于托管 Exchange 服务上的用户提供呼叫应答、Outlook Voice Access（包括语音邮件）或自助服务。 有关配置策略以与其他组织中的联盟域的用户进行通信的详细信息，请参阅操作文档中的在 <A href="lync-server-2013-manage-sip-federated-domains-for-your-organization.md">Lync Server 2013 中管理组织的 SIP 联盟域</A> 。 此外，如果要支持与 IM 服务提供商用户的通信，必须配置支持此类通信的策略，还必须配置对要支持的各个服务提供商的支持。 有关详细信息，请参阅操作文档中的 <A href="lync-server-2013-manage-sip-federated-providers-for-your-organization.md">在 Lync Server 2013 中管理组织的 SIP 联合提供程序</A> 。 有关创建托管语音邮件策略的详细信息，请参阅部署文档中的在 <A href="lync-server-2013-manage-hosted-voice-mail-policies.md">Lync Server 2013 中管理托管的语音邮件策略</A> 。



</div>

<div>

## <a name="to-enable-or-disable-federated-user-access-for-your-organization"></a>为组织启用或禁用联盟用户访问

1.  从作为 RTCUniversalServerAdmins 组成员的用户帐户 (或具有等效的用户权限) 或分配给 CsAdministrator 角色，请登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。 有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅 [Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。

3.  在左侧导航栏中，单击“外部用户访问”****，然后单击“访问边缘配置”****。

4.  在“访问边缘配置”**** 页上，单击“全局”****，再单击“编辑”****，然后单击“显示详细信息”****。

5.  在“编辑访问边缘配置”**** 中，执行下列操作之一：
    
      - 要为组织启用联盟用户访问，请选中“启用与联盟用户的通信”**** 复选框。
    
      - 要为组织禁用联盟用户访问，请清除“启用与联盟用户的通信”**** 复选框。

6.  如果已选中“启用与联盟用户的通信”**** 复选框，请执行以下操作：
    
    1.  如果要支持伙伴域的自动发现，请选中“启用伙伴域发现”**** 复选框。
    
    2.  如果组织支持外部通信的存档，请选中“向联盟伙伴发送存档免责声明”**** 复选框。

7.  单击“提交”****。

若要使联合用户能够与 Lync Server 2013 部署中的用户进行协作，您还必须配置至少一个外部访问策略以支持联合用户访问。 有关详细信息，请参阅部署文档或操作文档中的 [配置策略以控制 Lync Server 2013 中的联合用户访问](lync-server-2013-configure-policies-to-control-federated-user-access.md) 。 若要控制对特定联盟域的访问权限，请参阅部署文档或操作文档中的在 [Lync Server 2013 中配置对允许的外部域的支持](lync-server-2013-configure-support-for-allowed-external-domains.md) 。

</div>

<div>

## <a name="enabling-or-disabling-federation-and-public-im-connectivity-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 启用或禁用联合身份验证和公共 IM 连接

此外，还可以使用 Windows PowerShell 和 Set-CsAccessEdgeConfiguration cmdlet 来管理联盟和公共 IM 连接。 此 cmdlet 可从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行。 有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅在上的 Lync Server Windows PowerShell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010" [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。

<div>

## <a name="to-enable-federation-and-public-im-connectivity"></a>启用联盟和公共 IM 连接

  - 若要启用联盟和公共 IM 连接，请将 **AllowFederatedUsers** 属性的值设置为 True ($True)：
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True

</div>

<div>

## <a name="to-disable-federation-and-public-im-connectivity"></a>禁用联盟和公共 IM 连接

  - 若要禁用联盟和公共 IM 连接，请将 **AllowFederatedUsers** 属性的值设置为 False ($False)：
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $False

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

