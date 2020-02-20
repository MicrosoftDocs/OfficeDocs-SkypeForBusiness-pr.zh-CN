---
title: 将单个用户移动到引导池
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Move a single user to the pilot pool
ms:assetid: e9de81a8-40dd-4446-81e7-a2b810eaea50
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205401(v=OCS.15)
ms:contentKeyID: 48185905
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 187b0b3055710f89b8c16d8167c1b6692d5eaac2
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42148681"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="move-a-single-user-to-the-pilot-pool"></a>将单个用户移动到引导池

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-26_

您可以使用 Lync Server 2013 控制面板或 Lync Server 2013 命令行管理程序，将用户从 Lync Server 2010 池移动到 Lync Server 2013 引导池。 在下面的示例中，在 "注册器池" 列中， **pool01.contoso.net**是 Lync Server 2010 池，所有这六个用户都连接到此池。 使用以下过程将用户移动到使用 Lync Server 2013 控制面板和 Lync Server 命令行管理程序的 Lync Server 2013 池。

<div>

## <a name="to-move-a-user-by-using-the-lync-server-2013-control-panel"></a>使用 Lync Server 2013 控制面板移动用户

**Lync Server 2013 控制面板中的用户列表**

![Lync Server 控制面板 "移动用户" 对话框](images/JJ721870.a2bce284-0392-4db3-9bb2-9f12699738e7(OCS.15).jpg "Lync Server 控制面板 "移动用户" 对话框")

1.  使用具有 RTCUniversalServerAdmins 组成员身份或者 CsAdministrator 或 CsUserAdministrator 管理角色成员身份的帐户登录到前端服务器。

2.  打开“Lync Server 控制面板”****。

3.  单击“用户”****，再单击“搜索”，然后单击“查找”****。

4.  选择要移到 Lync Server 2013 池的用户。 在本示例中，我们将移动用户 Sara Davis。

5.  在“操作”**** 菜单中，选择“将所选用户移动到池”****。

6.  从下拉列表中，选择 "Lync Server 2013" 池。

7.  单击“操作”****，然后单击“将所选用户移动到池”****。 单击“确定”****。
    
    !["移动用户，目标注册器池" 对话框](images/JJ205401.8a375003-dc00-4541-b578-4d88f2010601(OCS.15).png ""移动用户，目标注册器池" 对话框")  

8.  确认用户的 "**注册器池**" 列现在包含 Lync Server 2013 池，这表明已成功移动该用户。

</div>

<div>

## <a name="to-move-a-user-by-using-the-lync-server-2013-management-shell"></a>使用 Lync Server 2013 命令行管理程序移动用户

1.  打开 Lync Server 命令行管理程序。

2.  在命令行中键入：
    
        Move-CsUser -Identity "David Pelton" -Target "pool02.contoso.net"

3.  接下来，在命令行处键入：
    
        Get-CsUser -Identity "David Pelton"

4.  **RegistrarPool**标识现在指向 Lync Server 2013 池。 存在该标识即可确认已成功移动用户。
    
    ![使用标识筛选器的 Get-csuser cmdlet 的输出](images/JJ205401.bc5d4672-8068-4475-b882-dbd305c801a9(OCS.15).jpg "使用标识筛选器的 Get-csuser cmdlet 的输出")  
    
    <div>
    

    > [!NOTE]  
    > 有关 <STRONG>Get-CsUser</STRONG> cmdlet 的详细信息，请运行：<STRONG>Get-Help Get-CsUser –Detailed</STRONG>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

