---
title: Lync Server 2013：锁定或解锁用户 PIN
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lock or unlock a user PIN
ms:assetid: 3d293a8a-e182-4547-8b06-2603c3c77329
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688028(v=OCS.15)
ms:contentKeyID: 49733618
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ce748039b0e8f19a4efee56424c7661908fe6552
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765543"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lock-or-unlock-a-user-pin-in-lync-server-2013"></a>在 Lync Server 2013 中锁定或解锁用户 PIN

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2013-02-23_

你可以从 Lync Server 2013 控制面板的 "**用户**" 部分锁定或解除锁定用户的 PIN。

<div>

## <a name="to-lock-a-users-pin-in-lync-server-control-panel"></a>在 Lync Server "控制面板" 中锁定用户的 PIN

1.  使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口，然后输入 "管理员" URL 以打开 Lync Server "控制面板"。 有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息，请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左导航栏中，单击“用户”****。

4.  使用下列方法之一查找用户：
    
      - 在“搜索用户”**** 框中，键入用户帐户的显示名称、名字、姓氏、安全帐户管理器 (SAM) 帐户名、SIP 地址或线路统一资源标识符 (URI) 的全部或第一部分，然后单击“查找”****。
    
      - 如果具有保存的查询，请单击“打开查询”**** 图标，使用“打开”**** 对话框来检索该查询（.usf 文件），然后单击“查找”****。

5.  （可选）指定附加搜索条件以缩小结果的范围：
    
    1.  单击“添加筛选器”****。
    
    2.  通过键入用户属性，或单击下拉列表中的箭头选择属性来输入用户属性。
    
    3.  在“等于”**** 下拉列表中，单击运算符（例如“等于”**** 或“不等于”****）。
    
    4.  根据所选的用户属性，通过键入条件或单击下拉列表中的箭头输入用于筛选搜索结果的条件。
        
        <div>
        

        > [!TIP]  
        > 要向查询中添加附加搜索子句，请单击“添加筛选器”<STRONG></STRONG>。

        
        </div>
    
    5.  单击“查找”****。
    
    6.  单击用户，再单击“操作”****，然后单击“锁定 PIN”****。

</div>

<div>

## <a name="to-unlock-a-users-pin-in-lync-server-control-panel"></a>在 Lync Server "控制面板" 中解锁用户的 PIN

1.  使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口，然后输入 "管理员" URL 以打开 Lync Server "控制面板"。 有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息，请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左导航栏中，单击“用户”****。

4.  使用下列方法之一查找用户：
    
      - 在“搜索用户”**** 框中，键入用户帐户的显示名称、名字、姓氏、安全帐户管理器 (SAM) 帐户名、SIP 地址或线路统一资源标识符 (URI) 的全部或第一部分，然后单击“查找”****。
    
      - 如果具有保存的查询，请单击“打开查询”**** 图标，使用“打开”**** 对话框来检索该查询（.usf 文件），然后单击“查找”****。

5.  （可选）指定附加搜索条件以缩小结果的范围：
    
    1.  单击“添加筛选器”****。
    
    2.  通过键入用户属性，或单击下拉列表中的箭头选择属性来输入用户属性。
    
    3.  在“等于”**** 下拉列表中，单击运算符（例如“等于”**** 或“不等于”****）。
    
    4.  根据所选的用户属性，通过键入条件或单击下拉列表中的箭头输入用于筛选搜索结果的条件。
        
        <div>
        

        > [!TIP]  
        > 要向查询中添加附加搜索子句，请单击“添加筛选器”<STRONG></STRONG>。

        
        </div>
    
    5.  单击“查找”****。
    
    6.  单击用户，再单击“操作”****，然后单击“解锁 PIN”****。

</div>

<div>

## <a name="locking-and-unlocking-user-pins-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 锁定和解锁用户 Pin

你可以使用 Windows PowerShell 和 Lock-CsClientPin 和 CsClientPin cmdlet 锁定和解锁用户 Pin。 你可以从 Lync Server 2013 命令行管理程序或 Windows PowerShell 的远程会话运行这些 cmdlet。 有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅 Lync Server Windows PowerShell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010" [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

<div>

## <a name="to-lock-a-user-pin"></a>锁定用户 PIN

  - 若要锁定用户 PIN，请使用 Lock-CsClientPin cmdlet。例如：
    
        Lock-CsClientPin -Identity "Ken Myer"

</div>

<div>

## <a name="to-unlock-a-user-pin"></a>解锁用户 PIN

  - 若要解锁用户 PIN，请使用 Unlock-CsClientPin cmdlet。例如：
    
        Unlock-CsClientPin -Identity "Ken Myer"

</div>

有关详细信息，请参阅[Lock-CsClientPin](https://docs.microsoft.com/powershell/module/skype/Lock-CsClientPin)和[CsClientPin](https://docs.microsoft.com/powershell/module/skype/Unlock-CsClientPin) cmdlet 的帮助主题。

</div>

</div>

<span> </span>

</div>

</div>

</div>

