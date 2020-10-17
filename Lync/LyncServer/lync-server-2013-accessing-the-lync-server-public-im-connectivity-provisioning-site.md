---
title: 访问 Lync Server 公共 IM 连接设置网站
description: 访问 Lync Server 公共 IM 连接设置网站。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Accessing the Lync Server public IM connectivity provisioning site
ms:assetid: 77a08234-6bcf-4f59-b43b-ee5fc1926585
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn440174(v=OCS.15)
ms:contentKeyID: 57793364
ms.date: 03/09/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e12916b12de1ef3a3f990c6bee54c312ba6c1992
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571128"
---
# <a name="accessing-the-lync-server-public-im-connectivity-provisioning-site-from-lync-server-2013"></a>从 Lync Server 2013 访问 Lync Server 公共 IM 连接设置网站

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2019-03-22_

与以前的 PIC 设置方法相比，Lync-Skype 连接的设置过程已发生变化。 此设置过程最长可能需要30天才能完成。 我们建议您先启动此过程，然后再完成本文档中的其余步骤。 为您的帐户完成 Lync-Skype 设置过程后，将激活该帐户，并为您的符合条件的用户启用公共 IM 连接。

### <a name="to-provision-lync-skype-connectivity-you-need-the-following-information"></a>若要设置 Lync-Skype 连接性，您需要以下信息：

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<tbody>
<tr class="odd">
<td><ol>
<li><p>Microsoft 协议编号</p></li>
<li><p> (FQDN) 的 Access Edge 服务完全限定的域名称</p></li>
<li><p>会话初始协议 (SIP) 域 (s) </p></li>
<li><p>任何其他访问边缘服务 Fqdn</p></li>
<li><p>联系人信息</p></li>
</ol></td>
</tr>
</tbody>
</table>

从2019年4月起，我们将停止通过 pic.lync.com 网站为 Skype 联盟预配的客户的联系信息的收集和保留。 进行此更改是为了确保 pic.lync.com 预配系统符合 Microsoft 隐私策略。 

此更改生效后，我们将不再能够在挂起的设置更改时提供电子邮件更新。 PIC 设置更改通常在输入后的24-48 小时内完成。 如果在提交设置请求后仍遇到 Skype 联合身份问题48小时，请与 Microsoft 技术支持人员联系，以进一步调查。

> [!IMPORTANT]
> 作为此更改的一部分，所有以前输入的联系信息将在2019年4月结束时从系统中清除。

### <a name="to-initiate-the-provisioning-process-for-lync-skype-connectivity"></a>若要启动 Lync-Skype 连接的设置过程，请执行以下操作：

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<tbody>
<tr class="odd">
<td><ol>
<li><p><strong>https://pic.lync.com</strong>使用 Microsoft Windows LIVE ID 登录网站。</p></li>
<li><p>选择 "Microsoft 许可协议类型"。</p></li>
<li><p>选中 "" 复选框，验证您是否已阅读并接受 Lync Server 的产品使用权限。</p></li>
<li><p>在 " <strong>启动设置请求</strong> " 页上，单击相应的链接以启动设置请求：</p></li>
<li><p>在 " <strong>指定设置信息</strong> " 页上，输入 <strong>访问边缘服务 FQDN</strong>。 例如， <strong>sip.contoso.com</strong>。</p>



> [!IMPORTANT]
> 7月1日之后，2017 Microsoft 将另外要求客户为公用 IM 连接部署了联合 DNS SRV 记录以继续工作。

</li>
<li><p>至少输入一个或多个 SIP 域名，然后单击 " <strong>添加</strong>"。</p>



> [!IMPORTANT]
> 必须至少有一个访问边缘服务器和一个 SIP 域才能完成设置过程。 SIP 域和访问边缘服务器必须在网络上处于活动状态、正常运行和可访问性。

</li>
<li><p>在 <strong>公用 IM 服务提供商</strong>列表中，选择 " <strong>Skype"，</strong> 然后单击 " <strong>下一步</strong> " 以添加联系人信息，并提交设置请求。</p></li>
</ol></td>
</tr>
</tbody>
</table>


提交设置请求后，最长可能需要30天才能激活该帐户，并为用户启用公共 IM 连接。

<div>

## <a name="enabling-federation-and-public-im-connectivity-pic"></a>启用 (PIC) 的联盟和公共 IM 连接

提交设置请求后，您可以将精力集中在配置 Lync-Skype 连接所需的 Lync Server 环境和管理任务上。 在本节中，我们假定 Lync Server 管理员已部署 Lync Server 并配置了外部访问权限。 有关为 Lync Server 配置外部访问的其他信息，请参阅中的 "规划外部用户访问" [https://go.microsoft.com/fwlink/p/?LinkID=273772](https://go.microsoft.com/fwlink/p/?linkid=273772) 和 "部署外部用户访问" [https://go.microsoft.com/fwlink/p/?LinkID=27378](https://go.microsoft.com/fwlink/p/?linkid=27378) 。

若要准备 Lync Server 环境以进行 Lync-Skype 连接，Lync Server 管理员必须完成以下三个任务：

<div>

## <a name="1-configure-federation-and-pic"></a>1\. 配置联盟和 PIC

若要使 Skype 用户能够与组织中的 Lync 用户进行通信，需要联合身份验证。 公共即时消息连接 (PIC) 是一种联盟类别，必须将其配置为使 Lync 用户能够与 Skype 用户进行通信。 联盟和 PIC 是使用 Lync Server 控制面板配置的，如下所示。

<div>


> [!IMPORTANT]
> Live Communication Server 2005 SP1 或 Office 通信服务器2007不再支持 PIC 联盟。 PIC 联合的受支持平台包括 Lync Server 2013、Lync Server 2010 和 Office 通信服务器 2007 R2。



</div>

</div>

<div>

## <a name="2-configure-at-least-one-policy-to-support-federated-user-access"></a>2\. 至少配置一个用于支持联合用户访问的策略

使用 Lync Server 控制面板，管理员必须配置一个或多个外部用户访问策略，以控制 Skype 用户是否可以与内部 Lync Server 用户进行协作。

</div>

<div>

## <a name="3-configure-the-skype-pic-provider-setting-for-lync"></a>3\. 为 Lync 配置 Skype PIC 提供程序设置

通过使用 Lync Server 命令行管理程序，管理员必须将 Lync 客户端策略配置为将 Skype 显示为其他 PIC 提供程序。

<div>


> [!NOTE]
>  (PIC) 服务提供程序的公共即时消息连接的用户在您的组织中无法加入 IM 或会议，除非您在此过程前面的步骤中至少配置了一个策略 (步骤 2) 以支持公用 IM 连接。<BR>若要配置联盟和 PIC，请参阅中的 "启用或禁用联盟和公共 IM 连接" <A href="https://go.microsoft.com/fwlink/p/?linkid=306063">https://go.microsoft.com/fwlink/p/?LinkId=306063</A> 。<BR>若要至少配置一个策略来支持联合用户访问，请参阅中的 "配置控制公用用户访问的策略" <A href="https://go.microsoft.com/fwlink/p/?linkid=306064">https://go.microsoft.com/fwlink/p/?LinkId=306064</A> 。



</div>

1.  从 Lync Server 前端服务器，打开 Lync Server 命令行管理程序。

2.  运行以下两个命令：
    
      - `Remove-CsPublicProvider -Identity <identity-name>`
        
        <div>
        

        > [!NOTE]
        > 如果您的环境中尚未安装 PIC 提供程序，并且要创建新的 PIC 提供程序，则无需运行 <STRONG>CsPublicProvider</STRONG> cmdlet。

        
        </div>
    
      - `New-CsPublicProvider -ProxyFqdn federation.messenger.msn.com -Enabled 1 -Identity Skype  -VerificationLevel 2 -NameDecorationRoutingDomain msn.com -NameDecorationExcludedDomainList "msn.com,outlook.com,live.com,hotmail.com" -IconUrl "https://images.edge.messenger.live.com/Messenger_16x16.png"`
        
        <div>
        

        > [!NOTE]
        > 在 Lync Server 2013 CU5 &amp; lync desktop client In Office 2013 SP1 中，NameDecorationRoutingDomain 和 NameDecorationExcludedDomainList 改进了 Lync 用户在其中添加需要 "装饰" 非 Microsoft 域的 skype 联系人以标识并将其路由到 skype (的的情况。) 的格式：用户 (contoso.com) @msn .com。 这些新设置将允许使用 NameDecorationRoutingDomain (自动设置地址用户在 "添加 Skype 联系人" 对话框中输入的格式，如果不包含 (NameDecorationExcludedDomainList 中的域，则应将其设置为 msn.com) 如果当前可以支持 msn.com、live.com、Hotmail.com、outlook.com) 。

        
        </div>

3.  在 Lync 客户端中，你现在可以选择 Skype 作为 PIC 提供程序，并通过指定其 Microsoft 帐户来添加 Skype 客户端。 此外，已使用 Microsoft 帐户进行合并和登录的 Skype 用户可以向 Lync 用户发送联系人请求。 有关 Microsoft 帐户的详细信息，请参阅 [什么是 microsoft 帐户？](https://support.skype.com/en/faq/fa12059/what-is-a-microsoft-account)。 有关向 Lync 添加客户端的其他信息，请参阅 [在 Lync Server 2013 中使用 Lync-Skype 连接作为最终用户](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md)。

4.  有关修改承载的提供程序的详细信息，请参阅处的 "创建或编辑托管的 SIP 联合提供程序" [https://go.microsoft.com/fwlink/p/?LinkId=306065](https://go.microsoft.com/fwlink/p/?linkid=306065) 。

这将完成必须在服务器上执行的管理任务。 您现在已设置 Lync-Skype 连接。

</div>

</div>

<div>

## <a name="additional-resources"></a>其他资源

[在 Lync Server 2013 中使用 Lync-Skype 连接作为最终用户](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md)

[Lync Server 2013 中 Lync-Skype 连接的预配指南](lync-server-2013-provisioning-guide-for-lync-skype-connectivity.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

