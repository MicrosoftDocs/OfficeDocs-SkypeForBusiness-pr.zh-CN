---
title: Lync Server 2013：配置策略以控制公共用户访问
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure policies to control public user access
ms:assetid: 090aea0f-ef0b-49da-9c80-02d9279f2fa6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520946(v=OCS.15)
ms:contentKeyID: 48183343
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5e3993c2259d42bfa632394cb3c9acaf70f26cdc
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035294"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-policies-to-control-public-user-access-in-lync-server-2013"></a>配置策略以控制 Lync Server 2013 中的公共用户访问

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-10-07_

公共即时消息（IM）连接使组织中的用户能够使用 IM 与公共 IM 服务提供商提供的 IM 服务的用户通信，包括 Internet 服务、Yahoo\!和 AOL 的 Windows Live 网络。 您可以配置一个或多个外部用户访问策略，以控制公用用户是否可以与内部 Lync Server 用户进行协作。 公共即时消息连接是一项附加功能，它依赖于部署和用户的配置。 它还取决于在公用 IM 提供商处设置服务。 有关如何设置部署以使用公共提供程序的信息，请参阅 "适用于 Microsoft Lync Server、Office 通信服务器和实时通信服务器的公共 IM 连接设置指南" 指南：[http://go.microsoft.com/fwlink/?LinkId=269821](http://go.microsoft.com/fwlink/?linkid=269821)

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P>从2012年9月1日起，Microsoft Lync 公共 IM 连接用户订阅许可证（"PIC USL"）不再可用于购买新的或更新的协议。 拥有主动许可证的客户将能够继续与 Yahoo！联合联合 信使，直到服务关闭日期。 AOL 和 Yahoo！的生命周期结束日期为2014年6月 已宣布。 有关详细信息，请参阅<A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 中的支持公用即时信使连接</A>。</P>
> <LI>
> <P>PIC USL 是 Lync Server 或 Office 通信服务器与 Yahoo！联合所需的每个用户每月订阅许可证。 Messenger. Microsoft 提供此服务的能力因 Yahoo！中的支持而受到了支持，其下凸的底层协议。</P>
> <LI>
> <P>Lync 是前所未有的强大工具，用于跨组织和世界各地的个人进行连接。 与 Windows Live Messenger 的联盟不需要除 Lync Standard CAL 之外的其他用户/设备许可证。 Skype 联合身份验证将添加到此列表中，使 Lync 用户可以使用即时消息和语音访问成百上千人。</P></LI></UL>



</div>

若要访问 Microsoft Lync Server 公共 IM 连接设置网站，请使用以下链接：[http://go.microsoft.com/fwlink/p/?linkId=212638](http://go.microsoft.com/fwlink/p/?linkid=212638)

若要控制公共用户访问，可以在全局、站点和用户级别配置策略。 有关您可以配置的策略类型的详细信息，请参阅部署文档或规划文档中的在[Lync Server 2013 中配置对外部用户访问的支持](lync-server-2013-configuring-support-for-external-user-access.md)。 在一个策略级别应用的 Lync Server 策略设置可以覆盖在另一个策略级别应用的设置。 Lync Server 策略优先级为：用户策略（最具影响力）替代网站策略，然后网站策略将覆盖全局策略（最不影响）。 这意味着，策略设置越接近策略所影响的对象，它对对象的影响越大。

对于 IM 邀请，响应取决于客户端软件。除非外部发件人被用户配置的规则（即，用户客户端的“允许”**** 和“阻止”**** 列表中的设置）显式阻止，否则将接受请求。此外，如果用户选择阻止来自其“允许”**** 列表之外的用户的所有 IM，也可以阻止 IM 邀请。

<div>


> [!NOTE]  
> 即使没有为组织启用联盟，也可以配置控制公共用户访问的策略。 但是，只有为组织启用联盟后，配置的策略才会生效。 有关启用联合的详细信息，请参阅部署文档或操作文档中的在<A href="lync-server-2013-enable-or-disable-remote-user-access.md">Lync Server 2013 中启用或禁用远程用户访问</A>。 此外，如果您指定了用于控制公用用户访问的用户策略，则该策略仅适用于启用了 Lync Server 并配置为使用该策略的用户。 有关指定可登录到 Lync Server 的公共用户的详细信息，请参阅部署文档或操作文档中的在<A href="lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md">Lync server 2013 中将外部用户访问策略分配给启用 Lync 的用户</A>。



</div>

使用以下过程来配置策略，以支持一个或多个公共 IM 提供商的用户进行访问。

<div>

## <a name="to-configure-an-external-access-policy-to-support-public-user-access"></a>配置外部访问策略以支持公共用户访问

1.  从作为 RTCUniversalServerAdmins 组成员的用户帐户（或具有等效的用户权限）或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。 有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。

3.  在左侧导航栏中，单击“外部用户访问”****，然后单击“外部访问策略”****。

4.  在“外部访问策略”**** 页上，执行下列操作之一：
    
      - 要将全局策略配置为支持公共用户访问，请单击该全局策略，再单击“编辑”****，然后单击“显示详细信息”****。
    
      - 要创建新的站点策略，请单击“新建”****，然后单击“站点策略”****。在“选择站点”**** 中，单击列表中相应的站点，然后单击“确定”****。
    
      - 要创建新的用户策略，请单击“新建”****，然后单击“用户策略”****。在“新建外部访问策略”**** 的“名称”**** 字段中，创建一个唯一的名称以指示用户策略的作用范围（例如，**EnablePublicUsers** 代表启用公共用户通信的用户策略）。
    
      - 要更改现有的策略，请单击表中列出的相应策略，再单击“编辑”****，然后单击“显示详细信息”****。

5.  （可选）如果要添加或编辑说明，请在“说明”**** 中为策略指定相应的信息。

6.  执行以下操作之一：
    
      - 要为策略启用公共用户访问，请选中“启用与公共用户的通信”**** 复选框。
    
      - 要为策略禁用公共用户访问，请清除“启用与公共用户的通信”**** 复选框。

7.  单击“提交”****。

要启用公共用户访问，还必须在组织中启用对联盟的支持。 有关详细信息，请参阅[在 Lync Server 2013 中配置用于控制联盟用户访问的策略](lync-server-2013-configure-policies-to-control-federated-user-access.md)。

如果这是一个用户策略，您还必须将该策略应用到您希望能与公共用户协作的公共用户。 有关详细信息，请参阅[在 Lync Server 2013 中分配每用户策略](lync-server-2013-assigning-per-user-policies.md)。

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中创建或编辑公共 SIP 联合提供程序](lync-server-2013-create-or-edit-public-sip-federated-providers.md)  


[在 Lync Server 2013 中管理组织的 SIP 联合提供程序](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

