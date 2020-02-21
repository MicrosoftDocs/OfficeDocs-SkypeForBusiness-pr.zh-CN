---
title: 删除 Lync Phone Edition 配置设置的现有集合
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete an existing collection of Lync Phone Edition configuration settings
ms:assetid: 1bfc427d-4dcd-4199-b25f-8d5cfec2164f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687984(v=OCS.15)
ms:contentKeyID: 49733574
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1e5c601726cfc18d230519741ebcc7561da54d73
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42202709"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="delete-an-existing-collection-of-lync-phone-edition-configuration-settings-in-lync-server-2013"></a>在 Lync Server 2013 中删除 Lync Phone Edition 配置设置的现有集合

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-23_

如果您不想再对运行 Lync Phone Edition 的设备使用设置集合，请将其删除。 如果删除某一站点的集合，则全局设置将应用于该站点中的电话。 不能删除全局集合。

<div>


> [!NOTE]
> 您可能不想删除集合，只是想更改其中的一些设置。 有关如何执行此操作的详细信息，请参阅<A href="lync-server-2013-create-or-modify-a-collection-of-lync-phone-edition-configuration-settings.md">在 Lync Server 2013 中创建或修改 Lync Phone Edition 配置设置的集合</A>。



</div>

<div>

## <a name="to-delete-a-collection-of-lync-phone-edition-configuration-settings"></a>删除 Lync Phone Edition 配置设置的集合

1.  使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。 有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。

3.  在左侧导航栏中，单击“客户端”****，然后单击“设备配置”**** 导航按钮。

4.  在“设备配置”**** 页上，单击要删除的集合，单击“编辑”**** 菜单，然后单击“删除”****。
    
    <div>
    

    > [!NOTE]
    > 如果删除全局集合，设置将只恢复为默认设置。集合不会消失。

    
    </div>

5.  在确认框中，单击“确定”****。

</div>

<div>

## <a name="removing-lync-phone-edition-configuration-settings-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 删除 Lync Phone Edition 配置设置

您可以使用 Windows PowerShell 和**CsUCConfiguration** Cmdlet 删除 Lync Phone Edition 配置设置。 您可以从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行此 cmdlet。 有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅在上[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)的 Lync Server Windows powershell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010"。

<div>

## <a name="to-remove-a-specified-collection-of-lync-phone-edition-configuration-settings"></a>删除指定的 Lync Phone Edition 配置设置集合

  - 此命令可删除应用于 Redmond 站点的 UC 电话配置设置：
    
        Remove-CsUCPhoneConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-of-the-lync-phone-edition-configuration-settings-applied-to-the-site-scope"></a>删除应用到站点范围的所有 Lync Phone Edition 配置设置

  - 此命令可删除应用于服务范围的所有 UC 电话配置设置：
    
        Get-CsUCPhoneConfiguration -Filter "site:*" | Remove-CsUCPhoneConfiguration

</div>

<div>

## <a name="to-remove-all-of-the-lync-phone-edition-configuration-settings-where-phone-locking-is-disabled"></a>删除禁用电话锁定的所有 Lync Phone Edition 配置设置

  - 此命令可删除已禁用电话锁定的所有 UC 电话配置设置集合：
    
        Get-CsUCPhoneConfiguration | Where-Object {$_.EnforcePhoneLock -eq $False} | Remove-CsUCPhoneConfiguration

</div>

有关详细信息，请参阅[CsUCPhoneConfiguration](https://technet.microsoft.com/library/Gg398249(v=OCS.15))。

</div>

</div>

<span> </span>

</div>

</div>

</div>

