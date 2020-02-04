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
ms.openlocfilehash: 1f53e03ebfdc24ff969ff44a9b39149456ab3f16
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736043"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners-in-lync-server-2013"></a>在 Lync Server 2013 中启用或禁用向联盟伙伴发送存档免责声明

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2013-02-23_

在部署你的边缘服务器并为你的组织启用联盟后，你应该已指定是否要将存档免责声明自动发送给联盟伙伴。 如果您存档外部通信，则应启用发送存档免责声明。 使用本主题中的过程更改该配置。

<div>


> [!NOTE]
> 以下过程假定你已为你的组织启用联盟。 有关启用联盟的详细信息，请参阅在部署文档或操作文档中<A href="lync-server-2013-enable-or-disable-remote-user-access.md">启用或禁用 Lync Server 2013 中的远程用户访问</A>。



</div>

<div>

## <a name="to-enable-or-disable-sending-of-an-archiving-disclaimer-to-federated-partners"></a>启用或禁用向联盟伙伴发送存档免责声明

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口，然后输入 "管理员" URL 以打开 Lync Server "控制面板"。 有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息，请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击 "**外部用户访问**"，然后单击 "**访问边缘配置**"。

4.  在“**访问边缘配置**”选项卡上，单击“**全局**”，再单击“**编辑**”，然后单击“**显示详细信息**”。

5.  在 "**编辑访问边缘配置**" 下的 "**启用与联盟用户的通信**" 下，选中或清除 "**将存档声明发送给联盟伙伴**" 复选框以启用或禁用自动发送存档免责声明。

6.  单击“**提交**”。

若要使联盟用户能够与 Lync Server 2013 部署中的用户进行协作，你必须也配置了至少一个外部访问策略来支持联合用户访问。 有关详细信息，请参阅在部署文档或操作文档中[管理 Lync Server 2013 中的 XMPP 联盟合作伙伴](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)。 有关控制特定联盟域的访问权限的详细信息，请参阅部署文档或操作文档中的[在 Lync Server 2013 中配置对允许的外部域的支持](lync-server-2013-configure-support-for-allowed-external-domains.md)。

</div>

<div>

## <a name="enabling-or-disabling-the-archiving-disclaimer-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 启用或禁用存档放弃声明

可使用 Windows PowerShell 和 CsAccessEdgeConfiguration cmdlet 管理存档否认使用。 此 cmdlet 既可以从 Lync Server 2013 管理外壳运行，也可以从 Windows PowerShell 的远程会话运行。 有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅 Lync Server Windows PowerShell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010" [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

<div>

## <a name="to-enable-the-archiving-disclaimer"></a>启用存档免责声明

  - 要启用存档免责声明，请将 **EnableArchivingDisclaimer** 属性的值设置为 True ($True)：
    
        Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $True

</div>

<div>

## <a name="to-disable-the-archiving-disclaimer"></a>禁用存档放弃声明

  - 要禁用存档免责声明，请将 **EnableArchivingDisclaimer** 属性的值设置为 False ($False)：
    
        Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $False

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

