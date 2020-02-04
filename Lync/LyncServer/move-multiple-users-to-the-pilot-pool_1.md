---
title: 将多个用户移动到 "引导" 池
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
ms.openlocfilehash: 70d031481746f9f7408cc7b5e36081bb977b189d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743762"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-multiple-users-to-the-pilot-pool"></a>将多个用户移动到 "引导" 池

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-10-02_

你可以使用 Lync Server 2013 控制面板或 Lync Server 2013 命令行管理程序，将多个用户从 Office 通信服务器 2007 R2 池中移动到 Lync Server 2013 试验池。

<div>

## <a name="to-move-multiple-users-by-using-the-lync-server-2013-control-panel"></a>使用 Lync Server 2013 "控制面板" 移动多个用户

1.  打开“Lync Server 控制面板”****。

2.  从 "**用户搜索**" 选项卡中，单击 "**搜索**" 按钮。

3.  接下来，单击 "**添加筛选器**"。

4.  创建**Office 通信服务器用户**等于**True**的筛选器。

5.  单击 "**查找**" 以搜索旧版 Office 通信服务器 2007 R2 用户。

6.  选择要移动到 Lync Server 2013 池的两个用户。 在此示例中，我们将用户移动 Chen's 的 Hansen 和 Claus。
    
    ![通过搜索 OCS 用户显示的用户列表](images/JJ688143.76beb4fa-72e0-41ef-b96e-3553e96645c0(OCS.15).jpg "通过搜索 OCS 用户显示的用户列表")  

7.  从 "**操作**" 菜单中，选择 "**将所选用户移至池**"。

8.  从下拉列表中，选择 "Lync Server 2013" 池。

9.  单击“操作”****，然后单击“将所选用户移动到池”****。 单击“确定”。
    
    !["移动用户"、"目标注册机构池" 对话框](images/JJ205401.8a375003-dc00-4541-b578-4d88f2010601(OCS.15).png ""移动用户"、"目标注册机构池" 对话框")  

10. 验证用户的**注册池**列现在是否包含 Lync Server 2013 池，这表示用户已成功移动。

</div>

<div>

## <a name="to-move-multiple-users-by-using-the-lync-server-2013-management-shell"></a>使用 Lync Server 2013 命令行管理程序移动多个用户

1.  打开 Lync Server 2013 命令行管理程序。

2.  在命令行中，键入以下内容并将**User1**和用户2与要移动的特定**用户名进行替换**，并将**池\_FQDN**替换为目标池的名称。 在此示例中，我们将在 Hao Chen's 和 Katie 约旦之间移动用户。
    
        Get-CsUser -Filter {DisplayName -eq "User1" -or DisplayName - eq "User2"} | Move-CsLegacyUser -Target "pool_FQDN"
    
    ![用于移动旧版用户的 cmdlet 示例](images/JJ688143.57cfc28e-3df5-459f-83ef-8b0edf182a25(OCS.15).jpg "用于移动旧版用户的 cmdlet 示例")  

3.  在命令行中，键入以下内容
    
        Get-CsUser -Identity "User1"

4.  **注册机构池**标识现在应指向您在上一步中指定为**\_池 FQDN**的池。 此标识的存在可确认用户已成功移动。 重复步骤**以验证服务2是否已**移动。
    
    ![PowerShell UsUser-Identity cmdlet 的输出](images/JJ205096.8ff04c67-37a0-4156-bfbc-28f9f7b137c8(OCS.15).jpg "PowerShell UsUser-Identity cmdlet 的输出")  

</div>

<div>

## <a name="to-move-all-users-at-the-same-time-by-using-the-lync-server-2013-management-shell"></a>使用 Lync Server 2013 命令行管理程序同时移动所有用户

在此示例中，所有用户均已返回到 Office 通信服务器 2007 R2 池（pool01.contoso.net）。 使用 Lync Server 2013 命令行管理程序，我们将同时将所有用户同时移动到 Lync Server 2013 池（pool02.contoso.net）。

1.  打开**Lync Server 2013 命令行管理**程序。

2.  在命令行中键入：
    
        Get-CsUser -OnOfficeCommunicationServer | Move-CsLegacyUser -Target "pool_FQDN"
    
    ![移动池中的所有旧式用户的示例 cmdlet](images/JJ688143.e6a2d578-296e-476c-bd45-d757917ea853(OCS.15).jpg "移动池中的所有旧式用户的示例 cmdlet")  

3.  接下来，为一个试验用户运行**move-csuser** 。
    
        Get-CsUser -Identity "Hao Chen"

4.  每个用户的**注册池**标识现在指向您在上一步中指定为\_"池 FQDN" 的池。 此标识的存在可确认用户已成功移动。

5.  此外，我们还可以查看 Lync Server 2013 控制面板中的用户列表，并验证注册机构池值是否现在指向 Lync Server 2013 池。
    
    ![Lync Server 2013 控制面板用户列表](images/JJ205096.3f2e87a7-ec59-43c5-82cb-e770108bfb04(OCS.15).jpg "Lync Server 2013 控制面板用户列表")  

</div>

</div>

<span> </span>

</div>

</div>

</div>

