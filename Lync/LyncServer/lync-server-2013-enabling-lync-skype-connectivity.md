---
title: Lync Server 2013：启用 Lync-Skype 连接
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enabling Lync-Skype connectivity
ms:assetid: 34c4db3e-582f-41fb-85c4-3438ae02f09f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn440170(v=OCS.15)
ms:contentKeyID: 57793361
ms.date: 12/16/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 794d2a71c07e742a3ab5597d4bd2aff77157d675
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830264"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-lync-skype-connectivity-in-lync-server-2013"></a>在 Lync Server 2013 中启用 Lync-Skype 连接

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2014-12-16_

提交预配请求后, 你可以专注于 Lync Server 环境和配置 Lync-Skype 连接所需的管理任务。 在此部分中, 我们假设 Lync Server 管理员已部署 Lync Server 和配置的外部访问权限。 有关配置 Lync Server 的外部访问的其他信息, 请参阅在[lync server 2013 中规划外部用户访问](lync-server-2013-planning-for-external-user-access.md)和[在 lync Server 2013 中部署外部用户访问](lync-server-2013-deploying-external-user-access.md)。

要准备 lync Server 环境以实现 Lync-Skype 连接, Lync Server 管理员必须完成以下三个任务:

<div>

## <a name="1-configure-federation-and-pic"></a>1 \。 配置联盟和 PIC

必须使用联盟才能使 Skype 用户能够与组织中的 Lync 用户通信。 公共即时消息连接 (PIC) 是一种联盟类, 必须将其配置为使 Lync 用户能够与 Skype 用户通信。 联盟和 PIC 是使用 Lync Server 控制面板配置的, 如下所示。

![显示 PIC](images/Dn440170.451b94e3-0b38-488c-835f-1f25690e8074(OCS.15).jpg "显示 PIC")

<div>


> [!IMPORTANT]  
> Live Communication Server 2005 SP1 或 Office Communications Server 2007 不再支持 PIC 联盟。 PIC 联盟支持的平台包括 Lync Server 2013、Lync Server 2010 和 Office 通信服务器 2007 R2。



</div>

</div>

<div>

## <a name="2-configure-at-least-one-policy-to-support-federated-user-access"></a>2 \。 配置至少一个策略以支持联盟的用户访问

使用 Lync Server 控制面板, 管理员必须配置一个或多个外部用户访问策略, 以控制 Skype 用户是否可以与内部 Lync Server 用户进行协作。

![策略](images/Dn440170.8fd46ad1-9749-422c-8c47-c16ac9032cdb(OCS.15).jpg "策略")

</div>

<div>

## <a name="3-configure-the-skype-pic-provider-setting-for-lync"></a>3。 配置 Lync 的 Skype PIC 提供商设置

使用 Lync Server 命令行管理程序, 管理员必须将 Lync 客户端策略配置为将 Skype 显示为其他 PIC 提供商。

<div>


> [!NOTE]  
> 公共即时消息连接 (PIC) 服务提供商的用户无法在你的组织中参与 IM 或音频或视频会议, 直到你还配置了至少一个策略 (步骤 2, 在此过程的前面) 才能支持公用 IM 连接。



</div>

1.  若要配置联盟和 PIC, 请参阅 "启用或禁用联盟和公用 IM 连接[http://go.microsoft.com/fwlink/p/?LinkId=306063](http://go.microsoft.com/fwlink/p/?linkid=306063)"。

2.  若要配置至少一个策略以支持联合用户访问, 请参阅 "配置用于控制公共用户访问的策略[http://go.microsoft.com/fwlink/p/?LinkId=306064](http://go.microsoft.com/fwlink/p/?linkid=306064)"。

**编辑现有 Messenger 或 Skype PIC 提供商并为其配置 Skype**

1.  从 Lync Server 前端服务器, 打开 Lync Server 命令行管理程序。

2.  运行以下两个命令：
    
    `Remove-CsPublicProvider -Identity <identity-name>`
    
    <div>
    

    > [!NOTE]  
    > 如果你的环境中尚未安装 PIC 提供程序, 而是创建新的 PIC 提供商, 则无需运行<STRONG>CsPublicProvider</STRONG> cmdlet。

    
    </div>
    
    `New-CsPublicProvider -ProxyFqdn federation.messenger.msn.com -Enabled 1 -Identity Skype  -VerificationLevel 2 -NameDecorationRoutingDomain msn.com -NameDecorationExcludedDomainList "msn.com,outlook.com,live.com,hotmail.com" -IconUrl "https://images.edge.messenger.live.com/Messenger_16x16.png"`
    
    <div>
    

    > [!NOTE]  
    > 在 Lync Server 2013 CU5 &amp;中添加的 OFFICE 2013 SP1 中的 lync 桌面客户端, NameDecorationRoutingDomain 和 NameDecorationExcludedDomainList 改善了 lync 用户将 "装饰" 非 Microsoft 域所需的 Skype 联系人添加到标识并将其路由到 Skype (格式为: user (contoso) @msn .com)。 这些新设置可自动格式化用户通过 NameDecorationRoutingDomain（应设为 msn.com）在“添加 Skype 联系人”对话框中输入的地址（如果其不包含 NameDecorationExcludedDomainList 中的域）（我们当前支持 msn.com、live.com、Hotmail.com、outlook.com）。

    
    </div>

3.  通过 Lync 客户端, 您现在可以选择 Skype 作为 PIC 提供商, 并通过指定其 Microsoft 帐户来添加 Skype 客户端。 此外, 已使用其 Microsoft 帐户合并和登录的 Skype 用户可以向 Lync 用户发送联系人请求。 有关 Microsoft 帐户的详细信息, 请参阅[什么是 microsoft 帐户？](https://support.skype.com/en/faq/fa12059/what-is-a-microsoft-account)。 有关将客户端添加到 Lync 的其他信息, 请参阅[在 Lync Server 2013 中使用 lync-Skype 连接作为最终用户](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md)。
    
    ![添加 Skype 联系人](images/Dn440170.df0e6ed9-2374-4dfa-a815-87281989487c(OCS.15).jpg "添加 Skype 联系人")

4.  有关修改托管提供商的详细信息, 请参阅 "创建或编辑托管的 SIP 联合[http://go.microsoft.com/fwlink/p/?LinkId=306065](http://go.microsoft.com/fwlink/p/?linkid=306065)提供商"。

这将完成必须在服务器上执行的管理任务。 您现在已为 Lync-Skype 连接设置。

</div>

</div>

<span> </span>

</div>

</div>

</div>

