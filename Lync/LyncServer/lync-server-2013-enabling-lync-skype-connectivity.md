---
title: Lync Server 2013：启用 Lync-Skype 连接
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling Lync-Skype connectivity
ms:assetid: 34c4db3e-582f-41fb-85c4-3438ae02f09f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn440170(v=OCS.15)
ms:contentKeyID: 57793361
ms.date: 12/16/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d2b950b8ff778ee48014dc951d89baafab59510c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048215"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-lync-skype-connectivity-in-lync-server-2013"></a>在 Lync Server 2013 中启用 Lync Skype 连接

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2014-12-16_

提交设置请求后，可以将重点放在 Lync Server 环境和配置 Lync-Skype 连接所需的管理任务上。 在本节中，我们假定 Lync Server 管理员已部署 Lync Server 并配置了外部访问权限。 有关为 Lync Server 配置外部访问的其他信息，请参阅在 lync server [2013 中规划外部用户访问](lync-server-2013-planning-for-external-user-access.md)和[在 lync Server 2013 中部署外部用户访问](lync-server-2013-deploying-external-user-access.md)。

若要准备 lync Server 环境以实现 Lync-Skype 连接，Lync Server 管理员必须完成以下三个任务：

<div>

## <a name="1-configure-federation-and-pic"></a>1\. 配置联盟和 PIC

若要使 Skype 用户能够与组织中的 Lync 用户进行通信，需要联合身份验证。 公共即时消息连接（PIC）是联合的一类，必须将其配置为使 Lync 用户能够与 Skype 用户进行通信。 联盟和 PIC 是使用 Lync Server 控制面板配置的，如下所示。

![显示 PIC](images/Dn440170.451b94e3-0b38-488c-835f-1f25690e8074(OCS.15).jpg "显示 PIC")

<div>


> [!IMPORTANT]  
> Live Communication Server 2005 SP1 或 Office 通信服务器2007不再支持 PIC 联盟。 PIC 联合的受支持平台包括 Lync Server 2013、Lync Server 2010 和 Office 通信服务器 2007 R2。



</div>

</div>

<div>

## <a name="2-configure-at-least-one-policy-to-support-federated-user-access"></a>2\. 至少配置一个用于支持联合用户访问的策略

使用 Lync Server 控制面板，管理员必须配置一个或多个外部用户访问策略，以控制 Skype 用户是否可以与内部 Lync Server 用户进行协作。

![策略](images/Dn440170.8fd46ad1-9749-422c-8c47-c16ac9032cdb(OCS.15).jpg "策略")

</div>

<div>

## <a name="3-configure-the-skype-pic-provider-setting-for-lync"></a>3\. 为 Lync 配置 Skype PIC 提供程序设置

通过使用 Lync Server 命令行管理程序，管理员必须将 Lync 客户端策略配置为将 Skype 显示为其他 PIC 提供程序。

<div>


> [!NOTE]  
> 公共即时消息连接（PIC）服务提供程序的用户在您的组织中无法加入 IM 或音频或视频会议，除非您还配置了至少一个策略（此过程中前面的步骤2）以支持公用 IM 连接。



</div>

1.  若要配置联盟和 PIC，请参阅中的[http://go.microsoft.com/fwlink/p/?LinkId=306063](http://go.microsoft.com/fwlink/p/?linkid=306063)"启用或禁用联盟和公共 IM 连接"。

2.  若要至少配置一个策略来支持联合用户访问，请参阅中的 "配置控制公用用户访问的[http://go.microsoft.com/fwlink/p/?LinkId=306064](http://go.microsoft.com/fwlink/p/?linkid=306064)策略"。

**编辑现有 Messenger 或 Skype PIC 提供商并为其配置 Skype**

1.  从 Lync Server 前端服务器，打开 Lync Server 命令行管理程序。

2.  运行以下两个命令：
    
    `Remove-CsPublicProvider -Identity <identity-name>`
    
    <div>
    

    > [!NOTE]  
    > 如果您的环境中尚未安装 PIC 提供程序，并且要创建新的 PIC 提供程序，则无需运行<STRONG>CsPublicProvider</STRONG> cmdlet。

    
    </div>
    
    `New-CsPublicProvider -ProxyFqdn federation.messenger.msn.com -Enabled 1 -Identity Skype  -VerificationLevel 2 -NameDecorationRoutingDomain msn.com -NameDecorationExcludedDomainList "msn.com,outlook.com,live.com,hotmail.com" -IconUrl "https://images.edge.messenger.live.com/Messenger_16x16.png"`
    
    <div>
    

    > [!NOTE]  
    > 在 Lync Server 2013 CU5 &amp; lync desktop Client in OFFICE 2013 SP1 中，NameDecorationRoutingDomain 和 NameDecorationExcludedDomainList 改进了 Lync 用户在其中添加需要 "装饰" 非 Microsoft 域的 skype 联系人以标识并将其路由到 Skype （格式为： user （contoso） @msn .com）的情况。 如果在 NameDecorationExcludedDomainList 中不包含域，这些新设置将允许自动设置地址用户在 "添加 Skype 联系人" 对话框中输入的格式（应设置为 "msn.com"），如果不包含 NameDecorationRoutingDomain 中的域（目前，我们可以支持 msn.com、live.com、Hotmail.com、outlook.com）。

    
    </div>

3.  在 Lync 客户端中，你现在可以选择 Skype 作为 PIC 提供程序，并通过指定其 Microsoft 帐户来添加 Skype 客户端。 此外，已使用 Microsoft 帐户进行合并和登录的 Skype 用户可以向 Lync 用户发送联系人请求。 有关 Microsoft 帐户的详细信息，请参阅[什么是 microsoft 帐户？](https://support.skype.com/en/faq/fa12059/what-is-a-microsoft-account)。 有关向 Lync 添加客户端的其他信息，请参阅[在 Lync Server 2013 中使用 lync-Skype 连接作为最终用户](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md)。
    
    ![添加 Skype 联系人](images/Dn440170.df0e6ed9-2374-4dfa-a815-87281989487c(OCS.15).jpg "添加 Skype 联系人")

4.  有关修改承载的提供程序的详细信息，请参阅处[http://go.microsoft.com/fwlink/p/?LinkId=306065](http://go.microsoft.com/fwlink/p/?linkid=306065)的 "创建或编辑托管的 SIP 联合提供程序"。

这将完成必须在服务器上执行的管理任务。 您现在已设置 Lync-Skype 连接。

</div>

</div>

<span> </span>

</div>

</div>

</div>

