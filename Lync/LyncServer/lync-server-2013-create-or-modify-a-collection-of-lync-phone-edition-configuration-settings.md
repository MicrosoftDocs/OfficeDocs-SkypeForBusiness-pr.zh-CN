---
title: 创建或修改 Lync Phone Edition 配置设置的集合
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify a collection of Lync Phone Edition configuration settings
ms:assetid: 6cf714af-8f57-4a71-89ad-0a776302b2ba
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688086(v=OCS.15)
ms:contentKeyID: 49733683
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f3012ffeeb8dd4559ee05a45dd07becefd099691
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830816"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-collection-of-lync-phone-edition-configuration-settings-in-lync-server-2013"></a>在 Lync Server 2013 中创建或修改 Lync Phone Edition 配置设置的集合

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2013-02-23_

安装 Lync Server 时, 将获得一个全局 Lync Phone Edition 设置集合。 这些设置适用于你的部署中运行 Lync Phone Edition 的所有设备。 您可以随时更改这些设置。 你还可以设置新的设置集合, 这些设置适用于特定网站中的设备。 网站设置优先于全局设置。

配置设置包括集合名称、范围 (全局或网站)、SIP 安全设置、日志记录级别、语音服务质量 (QoS) 级别、电话锁定设置和电话锁定详细信息 (即 a) 解锁个人识别码的时间 (PIN) 在锁定自身之前, 必须是和 b 的电话保持空闲。

<div>

## <a name="to-create-a-collection-of-lync-phone-edition-configuration-settings-or-edit-settings-for-an-existing-collection"></a>为现有集合创建 Lync Phone Edition 配置设置或编辑设置的集合

1.  使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口, 然后输入 "管理员" URL 以打开 Lync Server "控制面板"。 有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息, 请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中, 单击 "**客户端**", 然后单击 "**设备配置**" 导航按钮。

4.  在 "**设备配置**" 页面上, 执行下列操作之一:
    
      - 若要创建新的 Lync Phone Edition 配置设置, 请单击 "**新建**", 选择一个网站, 单击 **"确定**", 查看默认设置, 如果需要, 可进行任何更改。
    
      - 若要编辑现有集合中的任何设置, 请单击该集合, 单击 "**编辑**" 菜单, 单击 "**显示详细信息**", 然后进行更改。
        
        <div>
        

        > [!TIP]
        > 若要返回到使用全局集合的默认设置, 请单击全局集合, 单击 "<STRONG>编辑</STRONG>" 菜单, 单击 "<STRONG>删除</STRONG>", 然后单击<STRONG>"确定"</STRONG>。 这不会删除全局集合;它只是将设置重置为默认值。

        
        </div>

5.  单击“**提交**”。

</div>

<div>

## <a name="creating-new-lync-phone-edition-configuration-settings-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 创建新的 Lync 手机版配置设置

你可以使用 Windows PowerShell 和**CsUCPhoneConfiguration** cmdlet 来创建 Lync Phone Edition 配置设置 (仅限在网站范围内)。 你可以从 Lync Server 2013 命令行管理程序或 Windows PowerShell 的远程会话运行此 cmdlet。 有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息, 请参阅 Lync Server Windows PowerShell 博客文章 "快速入门: 使用远程 PowerShell 管理 Microsoft Lync Server 2010" [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

<div>

## <a name="to-create-new-lync-phone-edition-configuration-settings-that-use-the-default-values"></a>创建使用默认值的新 Lync 手机版配置设置

  - 此命令为 Redmond 站点创建一组新的 UC 电话配置设置:
    
        New-CsUCPhoneConfiguration -Identity "site:Redmond"
    
    由于上述命令中未指定参数（不包括必需的 Identity 参数），新的配置设置集合的所有属性都将使用默认值。

</div>

<div>

## <a name="to-change-a-single-property-value-when-creating-new-lync-phone-edition-configuration-settings"></a>在创建新的 Lync Phone Edition 配置设置时更改单个属性值

  - 要创建使用不同属性值的设置，只需包含相应的参数和参数值。 例如, 若要创建一个 UC 电话配置设置的集合, 默认情况下, 需要电话锁定, 请使用如下所示的命令:
    
        New-CsUCPhoneConfiguration -Identity "site:Redmond" -EnforcePhoneLock $True

</div>

<div>

## <a name="to-change-multiple-property-values-when-creating-new-lync-phone-edition-configuration-settings"></a>创建新的 Lync Phone 版本配置设置时更改多个属性值

  - 可以通过包含多个参数来修改多个属性值。 例如, 此命令强制执行电话锁定, 并且将最小 PIN 长度设置为8位:
    
        New-CsUCPhoneConfiguration -Identity "site:Redmond" -EnforcePhoneLock $True -MinPhonePinLength 8

</div>

有关详细信息, 请参阅[CsUCPhoneConfiguration](https://technet.microsoft.com/en-us/library/Gg398445(v=OCS.15))。

</div>

<div>

## <a name="see-also"></a>另请参阅


[删除 Lync Server 2013 中的现有 Lync Phone Edition 配置设置集合](lync-server-2013-delete-an-existing-collection-of-lync-phone-edition-configuration-settings.md)  
[在 Lync Server 2013 中配置 Lync Phone Edition 的安全设置](lync-server-2013-configure-security-settings-for-lync-phone-edition.md)  
[在 Lync Server 2013 中强制执行电话锁定](lync-server-2013-enforce-phone-locking.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

