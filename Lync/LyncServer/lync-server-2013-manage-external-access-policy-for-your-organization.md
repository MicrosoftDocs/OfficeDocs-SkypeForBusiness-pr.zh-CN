---
title: Lync Server 2013：管理组织的外部访问策略
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Manage external access policy for your organization
ms:assetid: 5571811e-34c8-443a-b94c-1ab5d4275581
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520995(v=OCS.15)
ms:contentKeyID: 48184160
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 10a08e096d517d2ac53866df763ab2f553480da5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829914"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="manage-external-access-policy-in-lync-server-2013"></a>在 Lync Server 2013 中管理组织的外部访问策略

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2013-10-07_

部署一个或多个边缘服务器后, 必须启用组织支持的外部访问类型。

默认情况下, 没有配置任何可支持外部用户访问的策略, 包括远程用户访问权限、联盟用户访问权限, 即使你已启用组织的外部用户访问支持。 若要控制外部用户访问的使用, 必须配置一个或多个策略, 指定每个策略支持的外部用户访问类型。 以下策略作用域可用于创建和配置。 默认情况下, 创建全局策略, 但不能删除。

  - **全局策略**   当你部署 Edge 服务器时, 将创建全局策略。 默认情况下, 全局策略中未启用任何外部用户访问选项。 若要在全局级别支持外部用户访问, 请将全局策略配置为支持一种或多种类型的外部用户访问选项。 全局策略适用于组织中的所有用户, 但网站策略和用户策略替代全局策略。 如果您删除全局策略, 则不会将其删除。 而是将其重置为默认设置。

  - **网站策略**   您可以创建和配置一个或多个网站策略, 以限制对特定网站的外部用户访问的支持。 站点策略中的配置将覆盖全局策略，但是仅限于站点策略所涉及的特定站点。 例如, 如果在全局策略中启用 "远程用户访问", 则可以指定一个网站策略, 该策略可禁用特定网站的远程用户访问。 默认情况下, 网站策略应用于该网站的所有用户, 但你可以将用户策略分配给用户以替代网站策略设置。

  - **用户策略**   您可以创建和配置一个或多个用户策略, 以限制对特定用户的远程用户访问的支持。 用户策略中的配置替代全局和网站策略, 但仅适用于为其分配用户策略的特定用户。 例如, 如果在全局策略和网站策略中启用远程用户访问, 则可以指定禁用远程用户访问的用户策略, 然后将该用户策略分配给特定用户。 如果创建用户策略, 则必须将其应用于一个或多个用户, 然后它才会生效。

<div>


> [!IMPORTANT]  
> 在一个策略级别应用的 Lync Server 策略设置可以覆盖在其他策略级别应用的设置。 Lync 服务器策略优先级为: 用户策略 (最受影响) 覆盖网站策略, 然后网站策略覆盖全局策略 (最不影响)。 这意味着，策略设置与策略所影响的对象距离越近，它对该对象的影响力越大。



</div>

这些选项包括以下类型的外部访问:

  - ****   如果你希望支持用户对联盟伙伴域的访问权限, 请启用与联盟用户的通信。 此设置将用户配置为与其他 SIP 联盟域以及托管提供商 (如 Microsoft Office 365) 进行通信的能力。 选择此设置允许你选择允许与 XMPP 联盟域通信的选项。
    
    作为一个选项, 如果你首先选择 "**启用与联盟用户的通信**", 则可以选择 "**启用与 XMPP 联盟合作伙伴的通信**"。 XMPP 联盟是使用可扩展消息和状态协议 (XMPP) 的组织的联盟。
    
    <div>
    

    > [!NOTE]  
    > 如果启用 XMPP 联合身份验证, 还必须在拓扑生成器的 "边缘池配置" 部分中选择 "部署<STRONG>XMPP 联盟</STRONG>"。 为 XMPP 联合身份验证将在 Edge 服务器上部署 XMPP 代理, 并在前端服务器上部署 XMPP 网关。

    
    </div>

  - **启用与远程用户**   的通信如果你希望你的组织中的用户 (如出差的远程办公和用户) 能够通过 Internet 连接到 Lync 服务器, 请启用此选项。

  - **启用与公共用户**   的通信如果希望内部用户能够与公共 IM 提供商的联系人 (如 Windows Live、Yahoo\!和北美网络 (AOL)) 通信, 请启用此选项。
    
    <div>
    

    > [!IMPORTANT]  
    > <UL>
    > <LI>
    > <P>从2012年9月1日起, Microsoft Lync 公共 IM 连接用户订阅许可证 ("PIC USL") 不再可用于购买新的或续订协议。 具有活动许可证的客户将能够继续与 Yahoo! 进行联盟 Messenger, 直到服务关闭日期。 AOL 和 Yahoo! 的有效期结束日期为2014年6月 已宣布。 有关详细信息, 请参阅<A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 中的公共即时消息连接支持</A>。</P>
    > <LI>
    > <P>PIC USL 是 Lync Server 或 Office 通信服务器与 Yahoo! 联合所需的每个每个用户每月订阅许可证。 Messenger. Microsoft 提供此服务的能力已作为对 Yahoo! 的支持, 它的底层协议被向下缠绕。</P>
    > <LI>
    > <P>Lync 比以往更多, 是一种强大的工具, 用于跨组织和全球各地的人员进行连接。 与 Windows Live Messenger 的联盟不需要除 Lync 标准 CAL 之外的其他用户/设备许可证。 Skype 联盟将添加到此列表, 使 Lync 用户可以通过 IM 和语音与成百上千人联系。</P></LI></UL>

    
    </div>

<div>


> [!NOTE]  
> 除了启用外部用户访问支持外, 你还必须配置策略, 以控制在你的组织中使用外部用户访问, 然后再向用户提供任何类型的外部用户访问权限。 有关创建、配置和应用外部用户访问策略的详细信息, 请参阅<A href="lync-server-2013-enable-or-disable-remote-user-access.md">在 Lync Server 2013 中启用或禁用远程用户访问</A>。



</div>

**使用 Windows PowerShell cmdlet 查看外部访问策略**

  - 你可以使用 Lync Server 命令行管理程序和**CsExternalAccessPolicy** cmdlet 查看外部访问策略。 你可以从 Lync Server 2013 命令行管理程序或 Windows PowerShell 的远程会话运行此 cmdlet。 有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息, 请参阅 Lync Server Windows PowerShell 博客文章 "快速入门: 使用远程 PowerShell 管理 Microsoft Lync Server 2010" [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。
    
    若要查看有关所有外部访问策略的信息, 请在 Lync Server 命令行管理程序中键入以下命令, 然后按 ENTER:
    
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

## <a name="in-this-section"></a>本节内容

  - [在 Lync Server 2013 中配置策略以控制联盟用户访问](lync-server-2013-configure-policies-to-control-federated-user-access.md)

  - [在 Lync Server 2013 中配置策略以控制 XMPP 联盟用户访问](lync-server-2013-configure-policies-to-control-xmpp-federated-user-access.md)

  - [在 Lync Server 2013 中配置策略以控制远程用户访问](lync-server-2013-configure-policies-to-control-remote-user-access.md)

  - [在 Lync Server 2013 中配置策略以控制公共用户访问](lync-server-2013-configure-policies-to-control-public-user-access.md)

  - [在 Lync Server 2013 中将外部用户访问策略分配到启用 Lync 的用户](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)

  - [在 Lync Server 2013 中重置或删除外部用户访问策略](lync-server-2013-resetting-or-deleting-external-user-access-policies.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

