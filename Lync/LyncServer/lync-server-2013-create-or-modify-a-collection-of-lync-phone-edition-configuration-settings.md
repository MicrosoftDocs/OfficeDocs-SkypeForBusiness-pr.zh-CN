---
title: 创建或修改 Lync Phone Edition 配置设置的集合
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a collection of Lync Phone Edition configuration settings
ms:assetid: 6cf714af-8f57-4a71-89ad-0a776302b2ba
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688086(v=OCS.15)
ms:contentKeyID: 49733683
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 359c08c0ce8be63019856f05988ee30cd4419bf7
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151874"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-collection-of-lync-phone-edition-configuration-settings-in-lync-server-2013"></a>在 Lync Server 2013 中创建或修改 Lync Phone Edition 配置设置的集合

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-23_

安装 Lync Server 时，将获取 Lync Phone Edition 设置的全局集合。 这些设置适用于部署中运行 Lync Phone Edition 的所有设备。 您可以随时更改这些设置。 还可以设置适用于特定站点中的设备的设置的新集合。 站点设置优先于全局设置。

配置设置包含集合名称、范围（全局或站点）、SIP 安全设置、日志记录级别、语音服务质量 (QoS) 级别、电话锁定设置和电话锁定详细信息（即，a) 解锁个人标识号 (PIN) 所需花费的时间和 b) 电话在自行锁定之前保持空闲状态的时间长度）。

<div>

## <a name="to-create-a-collection-of-lync-phone-edition-configuration-settings-or-edit-settings-for-an-existing-collection"></a>为现有集合创建 Lync Phone Edition 配置设置的集合或编辑设置的详细

1.  使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。 有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。

3.  在左侧导航栏中，单击“客户端”****，然后单击“设备配置”**** 导航按钮。

4.  在“设备配置”**** 页上，执行下列操作之一：
    
      - 若要创建新的 Lync Phone Edition 配置设置集合，请单击 "**新建**"，选择一个网站，单击 **"确定**"，查看默认设置，如果需要，请进行任何更改。
    
      - 若要编辑某个现有集合中的任意设置，请依次单击该集合、“编辑”**** 菜单和“显示详细信息”****，然后进行更改。
        
        <div>
        

        > [!TIP]
        > 若要继续使用全局集合的默认设置，请依次单击全局集合、“编辑”<STRONG></STRONG>菜单、“删除”<STRONG></STRONG>和“确定”<STRONG></STRONG>。这不会删除全局集合，而只是将设置重置为默认值。

        
        </div>

5.  单击“提交”****。

</div>

<div>

## <a name="creating-new-lync-phone-edition-configuration-settings-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 创建新的 Lync Phone Edition 配置设置

您可以使用 Windows PowerShell 和**CsUCPhoneConfiguration** cmdlet 来创建 Lync Phone Edition 配置设置（仅限在网站范围内）。 您可以从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行此 cmdlet。 有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅在上[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)的 Lync Server Windows powershell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010"。

<div>

## <a name="to-create-new-lync-phone-edition-configuration-settings-that-use-the-default-values"></a>创建使用默认值的新 Lync Phone Edition 配置设置

  - 此命令为 Redmond 站点创建一组新的 UC 电话配置设置：
    
        New-CsUCPhoneConfiguration -Identity "site:Redmond"
    
    由于前面的命令中未指定参数（必需的 Identity 参数之外），因此新的配置设置集合将对其所有属性使用默认值。

</div>

<div>

## <a name="to-change-a-single-property-value-when-creating-new-lync-phone-edition-configuration-settings"></a>创建新的 Lync Phone Edition 配置设置时更改单个属性值

  - 若要创建使用不同属性值的设置，只需包含相应的参数和参数值。例如，默认情况下，若要创建需要电话锁定的 UC 电话配置设置的集合，请使用与以下内容类似的命令：
    
        New-CsUCPhoneConfiguration -Identity "site:Redmond" -EnforcePhoneLock $True

</div>

<div>

## <a name="to-change-multiple-property-values-when-creating-new-lync-phone-edition-configuration-settings"></a>创建新的 Lync Phone Edition 配置设置时更改多个属性值

  - 可通过包含多个参数来修改多个属性值。例如，此命令强制电话锁定并将最小 PIN 长度设置为 8 位：
    
        New-CsUCPhoneConfiguration -Identity "site:Redmond" -EnforcePhoneLock $True -MinPhonePinLength 8

</div>

有关详细信息，请参阅[CsUCPhoneConfiguration](https://technet.microsoft.com/library/Gg398445(v=OCS.15))。

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中删除 Lync Phone Edition 配置设置的现有集合](lync-server-2013-delete-an-existing-collection-of-lync-phone-edition-configuration-settings.md)  
[在 Lync Server 2013 中配置 Lync Phone Edition 的安全设置](lync-server-2013-configure-security-settings-for-lync-phone-edition.md)  
[在 Lync Server 2013 中强制执行电话锁定](lync-server-2013-enforce-phone-locking.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

