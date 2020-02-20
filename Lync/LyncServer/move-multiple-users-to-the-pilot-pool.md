---
title: 将多个用户移动到引导池
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Move multiple users to the pilot pool
ms:assetid: 90d0590c-922c-4933-b778-9dd850b59310
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205096(v=OCS.15)
ms:contentKeyID: 48184838
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5616dd5fc48b90c52c2733802023385441c371d7
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42148631"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="move-multiple-users-to-the-pilot-pool"></a>将多个用户移动到引导池

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-02_

您可以使用 Lync Server 2013 控制面板或 Lync Server 2013 命令行管理程序将您的 Lync Server 2010 池中的多个用户移动到 Lync Server 2013 引导池。

<div>

## <a name="to-move-multiple-users-by-using-the-lync-server-2013-control-panel"></a>使用 Lync Server 2013 控制面板移动多个用户

1.  打开“Lync Server 控制面板”****。

2.  单击“用户”****，再单击“搜索”，然后单击“查找”****。

3.  选择要移至 Lync Server 2013 池的两个用户。 在本例中，我们将移动用户 Chen Yang 和 Claus Hansen。
    
    ![将用户移动到特定的注册池](images/JJ205096.70d510e1-8e6b-40a5-a80b-27cbc63fc337(OCS.15).jpg "将用户移动到特定的注册池")  

4.  在“操作”**** 菜单中，选择“将所选用户移动到池”****。

5.  从下拉列表中，选择 "Lync Server 2013" 池。

6.  单击“操作”****，然后单击“将所选用户移动到池”****。 单击“确定”。
    
    !["移动用户，目标注册器池" 对话框](images/JJ205401.8a375003-dc00-4541-b578-4d88f2010601(OCS.15).png ""移动用户，目标注册器池" 对话框")  

7.  确认用户的 "**注册器池**" 列现在包含 Lync Server 2013 池，这表明已成功移动用户。

</div>

<div>

## <a name="to-move-multiple-users-by-using-the-lync-server-2013-management-shell"></a>使用 Lync Server 2013 命令行管理程序移动多个用户

1.  打开 Lync Server 2013 命令行管理程序。

2.  在命令行中，键入以下内容，并**** 将 User1**和用户**2 替换为要移动的特定用户名，并将**池\_FQDN**替换为目标池的名称。 在本例中，我们将移动用户 Hao Chen 和 Katie Jordan。
    
        Get-CsUser -Filter {DisplayName -eq "User1" -or DisplayName - eq "User2"} | Move-CsUser -Target "pool_FQDN"
    
    ![PowerShell Get-csuser cmdlet 示例](images/JJ205096.767ff9fc-755d-4a80-a710-5b1367aecbe0(OCS.15).jpg "PowerShell Get-csuser cmdlet 示例")  

3.  在命令行中键入：
    
        Get-CsUser -Identity "User1"

4.  **注册器池**标识现在应指向您在上一步中指定为**池\_FQDN**的池。 存在该标识即可确认已成功移动用户。 重复此步骤以确认 **User2** 已移动。
    
    ![PowerShell UsUser cmdlet 的输出](images/JJ205096.8ff04c67-37a0-4156-bfbc-28f9f7b137c8(OCS.15).jpg "PowerShell UsUser cmdlet 的输出")  

</div>

<div>

## <a name="to-move-all-users-at-the-same-time-by-using-the-lync-server-2013-management-shell"></a>使用 Lync Server 2013 命令行管理程序同时移动所有用户

在此示例中，所有用户都已返回到 Lync Server 2010 池（pool01.contoso.net）。 使用 Lync Server 2013 命令行管理程序，我们将同时将所有用户移动到 Lync Server 2013 池（pool02.contoso.net）。

1.  打开**Lync Server 2013 命令行管理**程序。

2.  在命令行中键入：
    
        Get-CsUser -OnLyncServer | Move-CsUser -Target "pool_FQDN"
    
    ![PowerShell cmdlet 和命令行管理程序中的结果](images/JJ205096.1e57ccb1-9378-4dc7-82b7-dcaa63a285c6(OCS.15).png "PowerShell cmdlet 和命令行管理程序中的结果")  

3.  接下来，为试点用户之一运行 **Get-CsUser**。
    
        Get-CsUser -Identity "Hao Chen"

4.  每个用户的**注册器池**标识现在指向您在上一步中指定\_为 "池 FQDN" 的池。 存在该标识即可确认已成功移动用户。

5.  此外，我们还可以查看 Lync Server 2013 控制面板中的用户列表，并验证注册器池值是否现在指向 Lync Server 2013 池。
    
    ![Lync Server 2013 控制面板用户列表](images/JJ205096.3f2e87a7-ec59-43c5-82cb-e770108bfb04(OCS.15).jpg "Lync Server 2013 控制面板用户列表")  

</div>

</div>

<span> </span>

</div>

</div>

</div>

