---
title: 访问 Lync Server 公共 IM 连接设置站点
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
ms.openlocfilehash: dbcb2e46380e7ed4bbd8499e83f638cb314844e9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723382"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="accessing-the-lync-server-public-im-connectivity-provisioning-site-from-lync-server-2013"></a>从 Lync Server 2013 访问 Lync Server 公共 IM 连接设置站点

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2019-03-22_

与以前的 PIC 预配方法相比，Lync-Skype 连接的预配过程已发生更改。 完成此预配过程最多需要30天。 建议您在完成文档中的其余步骤之前先开始此过程。 为你的帐户完成 Lync-Skype 预配过程后，将激活该帐户，并为你的符合条件的用户启用公用 IM 连接。

### <a name="to-provision-lync-skype-connectivity-you-need-the-following-information"></a>若要设置 Lync-Skype 连接，您需要以下信息：

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<tbody>
<tr class="odd">
<td><ol>
<li><p>Microsoft 协议编号</p></li>
<li><p>访问边缘服务完全限定的域名 (FQDN)</p></li>
<li><p>会话初始协议 (SIP) 域</p></li>
<li><p>任何其他访问边缘服务 FQDN</p></li>
<li><p>联系信息</p></li>
</ol></td>
</tr>
</tbody>
</table>

从2019年4月起，我们将停止通过 pic.lync.com 网站为 Skype Federation 预配的客户的联系人信息的收集和保留。 进行此更改是为了确保 pic.lync.com 预配系统遵守 Microsoft 隐私策略。 

此更改生效后，我们将不再能够在挂起的预配更改上提供电子邮件更新。 PIC 预配更改通常在输入后的24-48 小时内完成。 如果你在提交预配请求后48小时仍遇到 Skype 联合身份验证问题，请与 Microsoft 技术支持人员联系以进一步调查。

> [!IMPORTANT]
> 作为此更改的一部分，所有以前输入的联系人信息将在2019年4月结束后从系统中清除。

### <a name="to-initiate-the-provisioning-process-for-lync-skype-connectivity"></a>要启动 Lync-Skype 连接的预配过程，请执行以下操作：

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<tbody>
<tr class="odd">
<td><ol>
<li><p>使用您的 Microsoft Windows Live <strong>https://pic.lync.com</strong>ID 登录到网站。</p></li>
<li><p>选择 Microsoft 许可协议类型。</p></li>
<li><p>选中复选框，验证您是否已阅读并接受 "Lync Server 的产品使用权限"。</p></li>
<li><p>在 "<strong>启动预配请求</strong>" 页面上，单击相应链接以启动设置请求：</p></li>
<li><p>在 "<strong>指定设置信息</strong>" 页面上，输入 "<strong>访问边缘服务" FQDN</strong>。 例如， <strong>sip.contoso.com</strong>。</p>



> [!IMPORTANT]
> 2017年7月1日之后，Microsoft 还将进一步要求客户为公共 IM 连接部署的联合身份验证 DNS SRV 记录才能继续工作。

</li>
<li><p>至少输入一个或多个 SIP 域名，然后单击 "<strong>添加</strong>"。</p>



> [!IMPORTANT]
> 必须至少有一个访问边缘服务器和一个 SIP 域才能完成预配过程。 SIP 域和访问边缘服务器必须处于活动状态、正在运行，并且在网络上可访问。

</li>
<li><p>在<strong>公用 IM 服务提供商</strong>列表中，选择 " <strong>Skype"，</strong>然后单击 "<strong>下一步</strong>" 添加联系人信息，并提交预配请求。</p></li>
</ol></td>
</tr>
</tbody>
</table>


提交预配请求后，最多可能需要30天才能激活该帐户，并为用户启用公用 IM 连接。

<div>

## <a name="enabling-federation-and-public-im-connectivity-pic"></a>启用联盟和公共 IM 连接 (PIC)

提交预配请求后，你可以专注于 Lync Server 环境和配置 Lync-Skype 连接所需的管理任务。 在此部分中，我们假设 Lync Server 管理员已部署 Lync Server 和配置的外部访问权限。 有关配置 Lync Server 的外部访问的其他信息，请参阅中的 "规划外部用户访问[https://go.microsoft.com/fwlink/p/?LinkID=273772](https://go.microsoft.com/fwlink/p/?linkid=273772) " 和 "部署外部用户访问" [https://go.microsoft.com/fwlink/p/?LinkID=27378](https://go.microsoft.com/fwlink/p/?linkid=27378)。

要准备 lync Server 环境以实现 Lync-Skype 连接，Lync Server 管理员必须完成以下三个任务：

<div>

## <a name="1-configure-federation-and-pic"></a>1 \。 配置联盟和 PIC

必须使用联盟才能使 Skype 用户能够与组织中的 Lync 用户通信。 公共即时消息连接（PIC）是一种联盟类，必须将其配置为使 Lync 用户能够与 Skype 用户通信。 联盟和 PIC 是使用 Lync Server 控制面板配置的，如下所示。

<div>


> [!IMPORTANT]
> Live Communication Server 2005 SP1 或 Office Communications Server 2007 不再支持 PIC 联盟。 PIC 联盟支持的平台包括 Lync Server 2013、Lync Server 2010 和 Office 通信服务器 2007 R2。



</div>

</div>

<div>

## <a name="2-configure-at-least-one-policy-to-support-federated-user-access"></a>2 \。 配置至少一个策略以支持联盟的用户访问

使用 Lync Server 控制面板，管理员必须配置一个或多个外部用户访问策略，以控制 Skype 用户是否可以与内部 Lync Server 用户进行协作。

</div>

<div>

## <a name="3-configure-the-skype-pic-provider-setting-for-lync"></a>3。 配置 Lync 的 Skype PIC 提供商设置

使用 Lync Server 命令行管理程序，管理员必须将 Lync 客户端策略配置为将 Skype 显示为其他 PIC 提供商。

<div>


> [!NOTE]
> 只有至少再配置一个策略（步骤 2，此过程前面所述）以支持公共 IM 连接，公共即时消息连接 (PIC) 服务提供商的用户才能参与组织中的 IM 或会议。<BR>若要配置联盟和 PIC，请参阅 "启用或禁用联盟和公用 IM 连接<A href="https://go.microsoft.com/fwlink/p/?linkid=306063">https://go.microsoft.com/fwlink/p/?LinkId=306063</A>"。<BR>若要配置至少一个策略以支持联合用户访问，请参阅 "配置用于控制公共用户访问的策略<A href="https://go.microsoft.com/fwlink/p/?linkid=306064">https://go.microsoft.com/fwlink/p/?LinkId=306064</A>"。



</div>

1.  从 Lync Server 前端服务器，打开 Lync Server 命令行管理程序。

2.  运行以下两个命令：
    
      - `Remove-CsPublicProvider -Identity <identity-name>`
        
        <div>
        

        > [!NOTE]
        > 如果你的环境中尚未安装 PIC 提供程序，而是创建新的 PIC 提供商，则无需运行<STRONG>CsPublicProvider</STRONG> cmdlet。

        
        </div>
    
      - `New-CsPublicProvider -ProxyFqdn federation.messenger.msn.com -Enabled 1 -Identity Skype  -VerificationLevel 2 -NameDecorationRoutingDomain msn.com -NameDecorationExcludedDomainList "msn.com,outlook.com,live.com,hotmail.com" -IconUrl "https://images.edge.messenger.live.com/Messenger_16x16.png"`
        
        <div>
        

        > [!NOTE]
        > 在 Lync Server 2013 CU5 &amp;中添加了 OFFICE 2013 SP1 中的 lync 桌面客户端，NameDecorationRoutingDomain 和 NameDecorationExcludedDomainList 改进了 Lync 用户添加了 "装饰" 非 Microsoft 域所需的 Skype 联系人以标识和将其路由到 Skype 的情况（格式为： user （contoso） @msn .com）。 这些新设置可自动格式化用户通过 NameDecorationRoutingDomain（应设为 msn.com）在“添加 Skype 联系人”对话框中输入的地址（如果其不包含 NameDecorationExcludedDomainList 中的域）（我们当前支持 msn.com、live.com、Hotmail.com、outlook.com）。

        
        </div>

3.  通过 Lync 客户端，您现在可以选择 Skype 作为 PIC 提供商，并通过指定其 Microsoft 帐户来添加 Skype 客户端。 此外，已使用其 Microsoft 帐户合并和登录的 Skype 用户可以向 Lync 用户发送联系人请求。 有关 Microsoft 帐户的详细信息，请参阅[什么是 microsoft 帐户？](https://support.skype.com/en/faq/fa12059/what-is-a-microsoft-account)。 有关将客户端添加到 Lync 的其他信息，请参阅[在 Lync Server 2013 中使用 lync-Skype 连接作为最终用户](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md)。

4.  有关修改托管提供商的详细信息，请参阅 "创建或编辑托管的 SIP 联合[https://go.microsoft.com/fwlink/p/?LinkId=306065](https://go.microsoft.com/fwlink/p/?linkid=306065)提供商"。

这将完成必须在服务器上执行的管理任务。 您现在已为 Lync-Skype 连接设置。

</div>

</div>

<div>

## <a name="additional-resources"></a>其他资源

[在 Lync Server 2013 中使用 Lync-Skype 连接作为最终用户](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md)

[Lync Server 2013 中的 Lync-Skype 连接设置指南](lync-server-2013-provisioning-guide-for-lync-skype-connectivity.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

