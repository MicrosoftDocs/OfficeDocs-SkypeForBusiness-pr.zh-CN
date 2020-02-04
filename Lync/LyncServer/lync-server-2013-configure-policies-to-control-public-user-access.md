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
ms.openlocfilehash: b348abcce00eb57988c7aa5184c0cfb5ea302adb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763274"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-policies-to-control-public-user-access-in-lync-server-2013"></a>在 Lync Server 2013 中配置策略以控制公共用户访问

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2013-10-07_

公共即时消息（IM）连接使组织中的用户能够使用 IM 与由公共 IM 服务提供商提供的 IM 服务的用户进行通信，包括 Internet 服务、Yahoo\!和 AOL 的 Windows Live 网络。 配置一个或多个外部用户访问策略，以控制公共用户是否可以与内部 Lync Server 用户进行协作。 公共即时消息连接是一种附加的功能，可依赖于部署和用户的配置。 它还取决于在公共 IM 提供商处提供的服务。 有关如何设置你的部署以使用公共提供程序的信息，请参阅 Microsoft Lync Server、Office 通信服务器和实时通信服务器的公共 IM 连接预配指南：[http://go.microsoft.com/fwlink/?LinkId=269821](http://go.microsoft.com/fwlink/?linkid=269821)

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P>从2012年9月1日起，Microsoft Lync 公共 IM 连接用户订阅许可证（"PIC USL"）不再可用于购买新的或续订协议。 具有活动许可证的客户将能够继续与 Yahoo！进行联盟 Messenger，直到服务关闭日期。 AOL 和 Yahoo！的有效期结束日期为2014年6月 已宣布。 有关详细信息，请参阅<A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 中的公共即时消息连接支持</A>。</P>
> <LI>
> <P>PIC USL 是 Lync Server 或 Office 通信服务器与 Yahoo！联合所需的每个每个用户每月订阅许可证。 Messenger. Microsoft 提供此服务的能力已作为对 Yahoo！的支持，它的底层协议被向下缠绕。</P>
> <LI>
> <P>Lync 比以往更多，是一种强大的工具，用于跨组织和全球各地的人员进行连接。 与 Windows Live Messenger 的联盟不需要除 Lync 标准 CAL 之外的其他用户/设备许可证。 Skype 联盟将添加到此列表，使 Lync 用户可以通过 IM 和语音与成百上千人联系。</P></LI></UL>



</div>

若要访问 Microsoft Lync Server 公共 IM 连接设置网站，请使用以下链接：[http://go.microsoft.com/fwlink/p/?linkId=212638](http://go.microsoft.com/fwlink/p/?linkid=212638)

若要控制公共用户访问，可以在全局、网站和用户级别配置策略。 有关可以配置的策略类型的详细信息，请参阅在部署文档或规划文档中[配置 Lync Server 2013 中的外部用户访问支持](lync-server-2013-configuring-support-for-external-user-access.md)。 在一个策略级别应用的 Lync Server 策略设置可以覆盖在其他策略级别应用的设置。 Lync 服务器策略优先级为：用户策略（最受影响）覆盖网站策略，然后网站策略覆盖全局策略（最不影响）。 这意味着，策略设置与策略所影响的对象距离越近，它对该对象的影响力越大。

对于 IM 邀请，响应取决于客户端软件。 除非由用户配置的规则明确阻止外部发件人（即用户的客户端**允许**和**阻止**名单中的设置），否则将接受该请求。 此外，如果用户将阻止来自不在其**允许**列表中的用户的所有 IM，则可以阻止 IM 邀请。

<div>


> [!NOTE]  
> 你可以配置策略来控制公共用户访问，即使你没有为组织启用联盟。 但是，仅当你的组织启用了联合身份验证时，你配置的策略才有效。 有关启用联盟的详细信息，请参阅在部署文档或操作文档中<A href="lync-server-2013-enable-or-disable-remote-user-access.md">启用或禁用 Lync Server 2013 中的远程用户访问</A>。 此外，如果你指定用于控制公共用户访问的用户策略，该策略将仅应用于已启用 Lync Server 且配置为使用该策略的用户。 有关指定可登录 Lync Server 的公共用户的详细信息，请参阅部署文档或操作文档中的<A href="lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md">Lync server 2013 中的 "将外部用户访问策略分配给启用 lync 的用户</A>"。



</div>

使用以下过程配置策略以支持一个或多个公共 IM 提供商的用户访问。

<div>

## <a name="to-configure-an-external-access-policy-to-support-public-user-access"></a>将外部访问策略配置为支持公共用户访问

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口，然后输入 "管理员" URL 以打开 Lync Server "控制面板"。 有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息，请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击 "**外部用户访问**"，然后单击 "**外部访问策略**"。

4.  在 "**外部访问策略**" 页面上，执行下列操作之一：
    
      - 若要将全局策略配置为支持公共用户访问，请单击全局策略，单击 "**编辑**"，然后单击 "**显示详细信息**"。
    
      - 若要创建新的网站策略，请单击 "**新建**"，然后单击 "**网站策略**"。 在 "**选择网站**" 中，从列表中单击相应的网站，然后单击 **"确定"**。
    
      - 若要创建新的用户策略，请单击 "**新建**"，然后单击 "**用户策略**"。 在 "**新的外部访问策略**" 中，在 "**名称**" 字段中创建一个唯一名称，用于指示用户策略所涉及的内容（例如， **EnablePublicUsers**为公共用户启用通信的用户策略）。
    
      - 若要更改现有策略，请单击表中列出的相应策略，单击 "**编辑**"，然后单击 "**显示详细信息**"。

5.  可选如果要添加或编辑说明，请在 "**说明**" 中指定策略的信息。

6.  请执行下列操作之一：
    
      - 若要为策略启用公共用户访问权限，请选中 "**启用与公共用户的通信**" 复选框。
    
      - 若要禁用该策略的公共用户访问权限，请清除 "**启用与公共用户的通信**" 复选框。

7.  单击“**提交**”。

若要启用公共用户访问，还必须在组织中启用联盟支持。 有关详细信息，请参阅[在 Lync Server 2013 中配置用于控制联盟用户访问的策略](lync-server-2013-configure-policies-to-control-federated-user-access.md)。

如果这是用户策略，你还必须将策略应用于你希望能够与公共用户协作的公共用户。 有关详细信息，请参阅[在 Lync Server 2013 中分配每个用户的策略](lync-server-2013-assigning-per-user-policies.md)。

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中创建或编辑公共 SIP 联盟提供程序](lync-server-2013-create-or-edit-public-sip-federated-providers.md)  


[在 Lync Server 2013 中管理组织的 SIP 联盟提供程序](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

