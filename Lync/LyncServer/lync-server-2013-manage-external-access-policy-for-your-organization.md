---
title: Lync Server 2013：管理组织的外部访问策略
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Manage external access policy for your organization
ms:assetid: 5571811e-34c8-443a-b94c-1ab5d4275581
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520995(v=OCS.15)
ms:contentKeyID: 48184160
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 46242343d6da54a6ac1123663734645fd4f64a5a
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48524999"
---
# <a name="manage-external-access-policy-in-lync-server-2013"></a>在 Lync Server 2013 中管理外部访问策略

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-10-07_

部署一台或多台 Edge 服务器后，必须启用组织支持的外部访问类型。

默认情况下，即使已为组织启用对外部用户访问的支持，也不会将任何策略配置为支持外部用户访问（包括远程用户访问、联盟用户访问）。要控制外部用户访问的使用，必须配置一个或多个策略，并指定每个策略支持的外部用户访问类型。可创建和配置以下策略范围。默认情况下，将创建全局策略且无法被删除。

  - **全局策略**   在部署 Edge 服务器时创建全局策略。 默认情况下，全局策略中未启用任何外部用户访问选项。 要支持全局级别的外部用户访问，请将全局策略配置为支持一种或多种外部用户访问选项。 全局策略适用于组织中的所有用户，但站点策略和用户策略将覆盖全局策略。 如果删除全局策略，则不要将其移除。 相反，将其重置为默认设置。

  - **站点策略**   可创建和配置一个或多个站点策略，以将外部用户访问限制到指定站点。 站点策略中的配置将覆盖全局策略，但仅适用于站点策略覆盖的指定站点。 例如，如果在全局策略中启用远程用户访问，则可以指定禁用特定站点的远程用户访问的站点策略。 默认情况下，站点策略应用于该站点的所有用户，但可以将用户策略分配给用户以覆盖站点策略设置。

  - **用户策略**   可以创建和配置一个或多个用户策略，以将远程用户访问支持限制到指定用户。 用户策略中的配置将覆盖全局和站点策略，但仅适用于为其分配策略的特定用户。 例如，如果在全局策略和站点策略中启用远程用户访问，则可以指定禁用远程用户访问的用户策略，然后将该用户策略分配给特定用户。 如果创建用户策略，必须将其应用于一个或多个用户，然后才能生效。

<div>


> [!IMPORTANT]  
> 在一个策略级别应用的 Lync Server 策略设置可以覆盖在另一个策略级别应用的设置。 Lync Server 策略优先级为：用户策略 (影响最大的) 替代网站策略，然后网站策略将覆盖全局策略 (最小影响) 。 这意味着，策略设置越接近策略影响的对象，它对对象的影响就越大。



</div>

这些选项包括以下类型的外部访问：

  - **启用与联盟用户的通信**   如果要支持用户对联合伙伴域的访问，则启用此选项。 此设置配置用户与其他 SIP 联盟域进行通信的能力，以及 Microsoft 365 等托管提供程序。 通过选择此设置，可以选择允许与 XMPP 联盟域进行通信的选项。
    
    作为一种选择，如果您先选择“启用与联盟用户的通信”****，则可以选择“启用与 XMPP 联盟伙伴的通信”****。XMPP 联盟是与使用可扩展消息传递和状态协议 (XMPP) 的组织的联盟。
    
    <div>
    

    > [!NOTE]  
    > 如果启用 XMPP 联合身份验证，则还必须在拓扑生成器的 "边缘池" 配置部分中选择 "部署 <STRONG>XMPP 联合</STRONG> "。 为 XMPP 联合身份验证将在边缘服务器上部署 XMPP 代理，并在前端服务器上部署一个 XMPP 网关。

    
    </div>

  - **启用与远程用户**     的通信如果您希望组织中的用户（如正在旅行的远程办公和用户）能够通过 Internet 连接到 Lync Server，请启用此选项。

  - **启用与公共用户**     的通信如果希望内部用户能够与公共 IM 提供商联系人（如 Windows Live、Yahoo \! 和北美在线 (AOL) 提供）进行通信，请启用此选项。
    
    <div>
    

    > [!IMPORTANT]  
    > <UL>
    > <LI>
    > <P>从2012年9月1日起，Microsoft Lync 公共 IM 连接用户订阅许可证 ( "PIC USL" ) 不再可用于购买新的或更新的协议。 拥有主动许可证的客户将能够继续与 Yahoo！联合联合 信使，直到服务关闭日期。 AOL 和 Yahoo！的生命周期结束日期为2014年6月 已宣布。 有关详细信息，请参阅 <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 中的支持公用即时信使连接</A>。</P>
    > <LI>
    > <P>PIC USL 是 Lync Server 或 Office 通信服务器与 Yahoo！联合所需的每个用户每月订阅许可证。 Messenger. Microsoft 提供此服务的能力因 Yahoo！中的支持而受到了支持，其下凸的底层协议。</P>
    > <LI>
    > <P>Lync 是前所未有的强大工具，用于跨组织和世界各地的个人进行连接。 与 Windows Live Messenger 的联盟不需要除 Lync Standard CAL 之外的其他用户/设备许可证。 Skype 联合身份验证将添加到此列表中，使 Lync 用户可以使用即时消息和语音访问成百上千人。</P></LI></UL>

    
    </div>

<div>


> [!NOTE]  
> 除了启用外部用户访问支持外，还必须在用户可以使用任何类型的外部用户访问之前，配置策略以控制组织中外部用户访问的使用。 有关创建、配置和应用外部用户访问策略的详细信息，请参阅 <A href="lync-server-2013-enable-or-disable-remote-user-access.md">在 Lync Server 2013 中启用或禁用远程用户访问</A>。



</div>

**使用 Windows PowerShell cmdlet 查看外部访问策略**

  - 您可以通过使用 Lync Server 命令行管理程序和 **set-csexternalaccesspolicy** cmdlet 来查看外部访问策略。 您可以从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行此 cmdlet。 有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅在上的 Lync Server Windows PowerShell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010" [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。
    
    若要查看有关所有外部访问策略的信息，请在 Lync Server Management Shell 中键入以下命令，然后按 Enter：
    
        Get-CsExternalAccessPolicy
    
    此命令会返回类似下列信息：
    
        Identity                          : Global
        Description                       :
        EnableFederationAccess            : False
        EnableXmppAccess                  : False
        EnablePublicCloudAccess           : False
        EnablePublicCloudAudioVideoAccess : False
        EnableOutsideAccess               : False

<div>

## <a name="in-this-section"></a>本部分内容

  - [在 Lync Server 2013 中配置用于控制联合用户访问的策略](lync-server-2013-configure-policies-to-control-federated-user-access.md)

  - [在 Lync Server 2013 中配置策略以控制 XMPP 联盟用户访问](lync-server-2013-configure-policies-to-control-xmpp-federated-user-access.md)

  - [在 Lync Server 2013 中配置策略以控制远程用户访问](lync-server-2013-configure-policies-to-control-remote-user-access.md)

  - [配置策略以控制 Lync Server 2013 中的公共用户访问](lync-server-2013-configure-policies-to-control-public-user-access.md)

  - [在 Lync Server 2013 中将外部用户访问策略分配给启用 Lync 的用户](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)

  - [在 Lync Server 2013 中重置或删除外部用户访问策略](lync-server-2013-resetting-or-deleting-external-user-access-policies.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

