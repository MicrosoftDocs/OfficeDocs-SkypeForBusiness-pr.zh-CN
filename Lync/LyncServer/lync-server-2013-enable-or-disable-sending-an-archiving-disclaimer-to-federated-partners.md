---
title: 启用或禁用向联盟伙伴发送存档免责声明
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable sending an Archiving disclaimer to federated partners
ms:assetid: c8e9a2fa-9dc1-4e4d-919f-56ece8004864
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182584(v=OCS.15)
ms:contentKeyID: 48185391
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7f0715a7fc0dd9ab81d84fd996d5b87682af3f69
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42187935"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners-in-lync-server-2013"></a>在 Lync Server 2013 中启用或禁用向联盟伙伴发送存档免责声明

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-23_

在部署边缘服务器并为组织启用联盟时，应该已经指定了是否自动向联盟伙伴发送存档免责声明。如果要对外部通信进行存档，应启用发送存档免责声明。使用本主题中的过程更改此配置。

<div>


> [!NOTE]
> 以下过程假定您已为组织启用联盟。 有关启用联合的详细信息，请参阅部署文档或操作文档中的在<A href="lync-server-2013-enable-or-disable-remote-user-access.md">Lync Server 2013 中启用或禁用远程用户访问</A>。



</div>

<div>

## <a name="to-enable-or-disable-sending-of-an-archiving-disclaimer-to-federated-partners"></a>启用或禁用向联盟伙伴发送存档免责声明

1.  从作为 RTCUniversalServerAdmins 组成员的用户帐户（或具有等效的用户权限）或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。 有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。

3.  在左侧导航栏中，单击“外部用户访问”****，然后单击“访问边缘配置”****。

4.  在“访问边缘配置”**** 选项卡上，单击“全局”****，再单击“编辑”****，然后单击“显示详细信息”****。

5.  在“编辑访问边缘配置”**** 的“启用与联盟用户的通信”**** 下，选中或清除“向联盟伙伴发送存档免责声明”**** 复选框以启用或禁用自动发送存档免责声明。

6.  单击“提交”****。

若要使联合用户能够与 Lync Server 2013 部署中的用户进行协作，您还必须至少配置一个外部访问策略来支持联合用户访问。 有关详细信息，请参阅部署文档或操作文档中的[MANAGE XMPP 联盟合作伙伴 In Lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md) 。 有关控制对特定联盟域的访问权限的详细信息，请参阅部署文档或操作文档中的在[Lync Server 2013 中配置对允许的外部域的支持](lync-server-2013-configure-support-for-allowed-external-domains.md)。

</div>

<div>

## <a name="enabling-or-disabling-the-archiving-disclaimer-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 启用或禁用存档免责声明

可以使用 Windows PowerShell 和 Set-csaccessedgeconfiguration cmdlet 来管理存档免责声明。 此 cmdlet 可从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行。 有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅在上[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)的 Lync Server Windows powershell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010"。

<div>

## <a name="to-enable-the-archiving-disclaimer"></a>启用存档免责声明

  - 要启用存档免责声明，请将 **EnableArchivingDisclaimer** 属性的值设置为 True ($True)：
    
        Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $True

</div>

<div>

## <a name="to-disable-the-archiving-disclaimer"></a>禁用存档免责声明

  - 要禁用存档免责声明，请将 **EnableArchivingDisclaimer** 属性的值设置为 False ($False)：
    
        Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $False

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

