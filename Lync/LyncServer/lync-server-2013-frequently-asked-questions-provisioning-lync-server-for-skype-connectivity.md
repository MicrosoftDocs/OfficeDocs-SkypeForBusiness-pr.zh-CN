---
title: 常见问题：设置适用于 Skype 连接的 Lync Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: 'Frequently Asked Questions: Provisioning Lync Server for Skype connectivity'
ms:assetid: 4d1b2bfc-780b-4b8c-afd5-11c2e59203b5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn440172(v=OCS.15)
ms:contentKeyID: 57793362
ms.date: 12/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0315104e4bbbd2d8741d5bc011455be2d28191dc
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48500809"
---
# <a name="frequently-asked-questions-provisioning-lync-server-2013-for-skype-connectivity"></a>常见问题：设置适用于 Skype 连接的 Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2019-03-22_

从2019年4月起，我们将停止通过 pic.lync.com 网站为 Skype 联盟预配的客户的联系信息的收集和保留。 进行此更改是为了确保 pic.lync.com 预配系统符合 Microsoft 隐私策略。 
 
此更改生效后，我们将不再能够在挂起的设置更改时提供电子邮件更新。 PIC 设置更改通常在输入后的24-48 小时内完成。 如果在提交设置请求后仍遇到 Skype 联合身份问题48小时，请与 Microsoft 技术支持人员联系，以进一步调查。

> [!IMPORTANT]
> 作为此更改的一部分，所有以前输入的联系信息将在2019年4月结束时从系统中清除。


**问： Microsoft Lync 和 Skype 之间支持哪些功能？**

**A：** 通过 Microsoft 系列的现已准备好，新可能会将统一通信方案扩展到数百个使用 Skype 的用户。 此组合将使 Lync 客户能够与供应商、客户和合作伙伴进行连接和协作，依赖 Lync 的丰富程度和 Skype 的覆盖范围。

  - 即时消息和音频和视频呼叫— Lync 和 Skype 用户之间的联合音频和视频呼叫和即时消息

  - 状态共享—联盟联系人之间的交换状态信息

  - 简单管理—根据组织策略和标准配置联合通信的设置和控件

**问：如何有资格将我的 Lync 部署与 Skype 连接？**

**A：** 如果你有以下任一种，则可以使用 Skype 连接许可：

  - Lync Server (2010 或 2013) 加上 Lync Server Standard Client Access 许可证 ( "Cal";对于组织中将连接到 Skype 的用户和/或设备，为2010或 2013) 。 

  - Lync Online (作为独立许可证，也可作为 Office 365 套件) 的一部分。但是，此服务 (pic.lync.com) 仅用于设置 Lync Server 和混合 Lync Server 和 Lync Online 部署。Lync Online PIC 预配在 Lync Online 控制面板中执行 (LOCP) 。

**问： Lync 最终用户必须要连接到 Skype 联系人？**

**A：** 在域被激活且组织的 Lync 管理员启用了这些功能之后，Lync 用户可以将 Skype 联系人添加到 Lync 客户端中的联系人列表中。

**问： Skype 最终用户必须要连接到 Lync 联系人？**

**A：** 希望连接到 Lync 用户的所有 Skype 用户必须具有与其 Skype Id 关联的 Microsoft 帐户，并使用 Microsoft 帐户登录。可以在 Skype 客户端中启用此功能。

**问：与 Windows Live 的联盟是否仍然可用？**

**A：** 从2012年10月起，Microsoft 开始帮助 Windows Live Messenger (WLM) 用户迁移到 Skype，通过途中路由最终注销 WLM。只要 WLM 在市场中，Lync 将继续支持与 WLM 联合身份验证，但不允许其他任何 Windows Live 域激活。WLM 用户的移动由 Skype 6.0 for Mac 和 Windows (启用。在10月25日发布的 2012) 这将允许使用 Microsoft 帐户登录 (即与 WLM) 相同的凭据。 简单地登录到 Skype 后，WLM 好友列表将自动填充到 Skype，用户可以利用 Skype 的扩展通信功能，如呼叫座机和 mobiles、屏幕共享、分组视频呼叫，以及对各种设备的支持。此外，WLM 用户的联合 Lync 联系人将转到 Skype 并将其好友列表的其余部分转换为 Skype，并且这些联系人的 Skype 和 Lync 之间的 IM 将立即可用。 Lync 客户无需执行任何操作即可启用此服务的连续性。

**问：与 Yahoo 或 AOL 的联盟是否 \! 仍然可用？**

**A：** 不。 与 Yahoo 的联盟\! 而且 AOL 因 Yahoo 提供了支持\! 和 AOL。对于这两个 Yahoo\! 和 AOL，服务在2014年6月30日结束。 

**问：在购买 Lync 之前，可以试用 Skype 连接吗？**

**A：** 在试用版中不提供 Skype 连接。 在试用版中，鼓励具有符合条件的许可证的 Lync 客户只需注册服务即可进行测试。

**问：设置需要什么信息？**

**A：** 若要在合格的许可证下提交设置请求，您需要具备以下条件：

  - Microsoft 协议编号：
    
      - Microsoft 批量许可支持： Microsoft 批量许可协议编号
    
      - Microsoft 合作伙伴网络： Headquarter 合作伙伴 ID
    
      - 服务提供商许可协议：初始注册号码
    
      - 高容量服务：产品注册号

  - 访问边缘服务的 (Fqdn) 完全限定的域名称。
    
      - 至少需要一个访问边缘服务的 FQDN。
    
      - 如果您的组织有多台服务器运行访问边缘服务，请为每个额外的访问边缘服务指定 Fqdn。 重要说明：如果您先前已为访问边缘服务指定了 FQDN，并且想要更改它，则为更改设置可能需要几天才能完成，并可能导致服务中断。 为了防止服务中断，我们建议您保留以前指定的访问边缘服务的 FQDN。

  - 会话初始协议 (SIP) 域 (s) 。 这是用户当前用于即时消息的 SIP URI 的域后缀。 如果您的组织具有多个 SIP 域，请为用于即时消息的每个域指定域后缀。 例如，对于 user1@contoso.com，请指定 SIP 域的 contoso.com;对于 user1@example.fabrikam.com，将 example.fabrikam.com 指定为 SIP 域。
    
    <div>
    

    > [!NOTE]
    > 仅指定 SIP 域的域后缀。 请勿为 SIP 域指定任何 Fqdn，包括访问边缘服务的 FQDN。

    
    </div>

  - 联系人信息。 为您指定的每个 SIP 域的管理员指定一个电子邮件地址。

**问：如何在拆分域方案中启用 Lync-Skype 连接？**

**A：** 如果您具有 Lync Online 2013 和 Lync Server 本地拆分域方案 (与使用相同 SIP 域的联机和本地用户) ，请通过以下两个步骤按以下顺序启用 Lync-Skype 连接

1.  按照 PIC 设置指南中的说明，设置本地 Lync-Skype 连接。

2.  等待您看到您的域已由 Microsoft 设置的确认。

3.  在您看到确认后，请使用 Lync 管理中心打开 "外部通信"。 有关详细信息，请参阅 [https://office.microsoft.com/support/configure-external-communications-HA102817865.aspx?CTT=5\&origin=HA102817356](https://office.microsoft.com/support/configure-external-communications-ha102817865.aspx?ctt=5%26origin=ha102817356)

此顺序非常重要。您必须先设置本地连接，然后才能在 Lync Online 中启用通信。 如果订单已冲销，则在内部部署中输入的信息 <https://pic.lync.com> 将不会经过。 如果已经为与此域的外部通信设置了 Lync Online，则必须将其关闭，等待24小时，然后重新开始，首先在中输入本地信息， <https://pic.lync.com> 然后再打开 Lync Online 的外部通信。

**问：是否可以为 Skype 连接设置多个访问边缘服务 Fqdn？**

**A：** 可以为一个或多个域仅设置一个访问边缘 FQDN。 您可以设置多个访问边缘 Fqdn （每个请求最多10个）（如果它们具有不同的域）。

**问：是否可以获取为组织请求预配而找到的 Microsoft 帐户电子邮件地址列表？**

**A：** 不。 这些地址被视为个人身份信息且不共享。

**问：我如何添加 ID 包含 Windows Live 不支持的域的 Windows Live Messenger 联系人？**

**A：** 如果要使用包含非 Windows Live 域的帐户或 ID 添加 Windows Live Messenger 用户，请按以下格式输入该地址： \<user name\> (\<domain name\>) @msn .com，其中 \<domain name\> 是用户的电子邮件地址中的域名。 例如，如果您想要添加 ted@contoso.com，则可以使用以下格式：李小明 (contoso.com) @msn .com。 有关 Windows Live 管理的域的列表，请参阅中的 "在安装 Live 通信服务器 Service Pack 1 后，公共即时消息中出现的已知问题" 部分中的 "支持的域" 部分 https://support.microsoft.com/?kbid=897567 。

**问：预配过程需要多长时间？**

**A：** 设置可能需要30天。

**问：如何知道设置已完成？**

**A：** Microsoft 将在设置完成时发送电子邮件通知。

**问：怎样才能更新我提交的配置或联系人详细信息？**

**A：** 完成设置后，您可以在用于请求设置的相同网站上更新您的信息。 输入您的协议号码，然后单击 "更新服务"。

</div>

<span> </span>

</div>

</div>

</div>
