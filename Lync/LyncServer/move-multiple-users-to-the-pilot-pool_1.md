---
title: 将多个用户移动到引导池
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Move multiple users to the pilot pool
ms:assetid: 9492797f-2a26-4773-8ad2-97cb53fa68fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688143(v=OCS.15)
ms:contentKeyID: 49733745
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d659e879b821f27c159cee874dae9db0796f079b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034542"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-multiple-users-to-the-pilot-pool"></a>将多个用户移动到引导池

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-02_

您可以使用 Lync Server 2013 控制面板或 Lync Server 2013 命令行管理程序，将多个用户从 Office 通信服务器 2007 R2 池移动到 Lync Server 2013 引导池。

<div>

## <a name="to-move-multiple-users-by-using-the-lync-server-2013-control-panel"></a>使用 Lync Server 2013 控制面板移动多个用户

1.  打开“Lync Server 控制面板”****。

2.  从“用户搜索”**** 选项卡中，单击“搜索”**** 按钮。

3.  接下来，单击“添加筛选器”****。

4.  创建一个筛选器，其中的 **Office Communications Server 用户**等于 **True**。

5.  单击 "**查找**" 以搜索旧版 Office 通信服务器 2007 R2 用户。

6.  选择要移至 Lync Server 2013 池的两个用户。 在本例中，我们将移动用户 Chen Yang 和 Claus Hansen。
    
    ![通过搜索 OCS 用户显示的用户列表](images/JJ688143.76beb4fa-72e0-41ef-b96e-3553e96645c0(OCS.15).jpg "通过搜索 OCS 用户显示的用户列表")  

7.  在“操作”**** 菜单中，选择“将所选用户移动到池”****。

8.  从下拉列表中，选择 "Lync Server 2013" 池。

9.  单击“操作”****，然后单击“将所选用户移动到池”****。 单击“确定”。
    
    !["移动用户，目标注册器池" 对话框](images/JJ205401.8a375003-dc00-4541-b578-4d88f2010601(OCS.15).png ""移动用户，目标注册器池" 对话框")  

10. 确认用户的 "**注册器池**" 列现在包含 Lync Server 2013 池，这表明已成功移动用户。

</div>

<div>

## <a name="to-move-multiple-users-by-using-the-lync-server-2013-management-shell"></a>使用 Lync Server 2013 命令行管理程序移动多个用户

1.  打开 Lync Server 2013 命令行管理程序。

2.  在命令行中，键入以下内容，并**** 将 User1**和用户**2 替换为要移动的特定用户名，并将**池\_FQDN**替换为目标池的名称。 在本例中，我们将移动用户 Hao Chen 和 Katie Jordan。
    
        Get-CsUser -Filter {DisplayName -eq "User1" -or DisplayName - eq "User2"} | Move-CsLegacyUser -Target "pool_FQDN"
    
    ![移动旧版用户的示例 cmdlet](images/JJ688143.57cfc28e-3df5-459f-83ef-8b0edf182a25(OCS.15).jpg "移动旧版用户的示例 cmdlet")  

3.  在命令行中键入：
    
        Get-CsUser -Identity "User1"

4.  **注册器池**标识现在应指向您在上一步中指定为**池\_FQDN**的池。 存在该标识即可确认已成功移动用户。 重复此步骤以确认 **User2** 已移动。
    
    ![PowerShell UsUser cmdlet 的输出](images/JJ205096.8ff04c67-37a0-4156-bfbc-28f9f7b137c8(OCS.15).jpg "PowerShell UsUser cmdlet 的输出")  

</div>

<div>

## <a name="to-move-all-users-at-the-same-time-by-using-the-lync-server-2013-management-shell"></a>使用 Lync Server 2013 命令行管理程序同时移动所有用户

在此示例中，所有用户都已返回到 Office 通信服务器 2007 R2 池（pool01.contoso.net）。 使用 Lync Server 2013 命令行管理程序，我们将同时将所有用户移动到 Lync Server 2013 池（pool02.contoso.net）。

1.  打开**Lync Server 2013 命令行管理**程序。

2.  在命令行中键入：
    
        Get-CsUser -OnOfficeCommunicationServer | Move-CsLegacyUser -Target "pool_FQDN"
    
    ![移动池中的所有旧版用户的示例 cmdlet](images/JJ688143.e6a2d578-296e-476c-bd45-d757917ea853(OCS.15).jpg "移动池中的所有旧版用户的示例 cmdlet")  

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

