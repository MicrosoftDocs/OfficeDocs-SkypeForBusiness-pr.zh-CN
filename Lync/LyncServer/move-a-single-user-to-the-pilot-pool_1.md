---
title: 将单个用户移动到 "引导" 池
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Move a single user to the pilot pool
ms:assetid: 80d5b365-f153-4c61-a148-f9e18ce6e027
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688109(v=OCS.15)
ms:contentKeyID: 49733708
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 086af622644f8d8285ef5f7be8e17f75ff436000
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845186"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-a-single-user-to-the-pilot-pool"></a>将单个用户移动到 "引导" 池

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-09-28_

你可以使用 Lync Server 2013 控制面板或 Lync Server 2013 命令行管理程序将用户从 Office 通信服务器 2007 R2 池移动到 Lync Server 2013 试点项目池中。 在下面的示例中, 在 "注册机构池" 列中, ** \<"office 通信服务器\> ** " 是 office 通信服务器 2007 R2 池, 这些用户中的所有六个用户都连接到该池。 使用以下过程, 使用 Lync Server 2013 控制面板和 Lync Server Management Shell 将用户移动到您的 Lync Server 2013 池。

![在 Lync Server "控制面板" 中搜索 OCS 用户](images/JJ688109.d2008fd6-868b-4f26-84cf-57bb69e073d3(OCS.15).jpg "在 Lync Server \"控制面板\" 中搜索 OCS 用户")

<div>

## <a name="to-move-a-user-by-using-the-lync-server-2013-control-panel"></a>使用 Lync Server 2013 "控制面板" 移动用户

1.  使用具有 RTCUniversalServerAdmins 组成员身份或 CsAdministrator 或 CsUserAdministrator 管理角色成员身份的帐户登录到前端服务器。

2.  打开“Lync Server 控制面板”。

3.  单击 "**用户**"。

4.  从 "**用户搜索**" 选项卡中, 单击 "**搜索**" 按钮。

5.  接下来, 单击 "**添加筛选器**"。

6.  创建**Office 通信服务器用户**等于**True**的筛选器。

7.  单击 "**查找**" 以搜索旧版 Office 通信服务器 2007 R2 用户。
    
    ![在 Lync Server "控制面板" 中搜索 OCS 用户](images/JJ688109.09528349-7915-41e1-91b4-6ab5c12b1b38(OCS.15).jpg "在 Lync Server \"控制面板\" 中搜索 OCS 用户")  

8.  选择要移动到 Lync Server 2013 池的用户。 在此示例中，将移动用户 Sara Davis。

9.  在“操作”**** 菜单中，选择“将所选用户移动到池”****。

10. 从下拉列表中, 选择 "Lync Server 2013" 池。

11. 单击“操作”****，然后单击“将所选用户移动到池”****。 单击“**确定**”。
    
    ![在 "移动用户" 对话框中设置目标池](images/JJ688109.d7dc0759-87c5-4c23-938f-361576621504(OCS.15).jpg "在 \"移动用户\" 对话框中设置目标池")  

12. 验证用户的**注册池**列现在是否包含 Lync Server 2013 池, 这表示用户已成功移动

</div>

<div>

## <a name="to-move-a-user-by-using-the-lync-server-2013-management-shell"></a>使用 Lync Server 2013 命令行管理程序移动用户

1.  打开 Lync Server 命令行管理程序。

2.  在命令行中键入：
    
        Move-CsLegacyUser -Identity "David Pelton" -Target "pool02.contoso.net"

3.  接下来, 在命令行键入以下命令:
    
        Get-CsUser -Identity "David Pelton"

4.  **RegistrarPool**标识现在指向 Lync Server 2013 池。 此标识的存在可确认用户已成功移动。
    
    ![Move-csuser cmdlet 和 Identity filter 的输出](images/JJ205401.bc5d4672-8068-4475-b882-dbd305c801a9(OCS.15).jpg "Move-csuser cmdlet 和 Identity filter 的输出")  
    
    <div>
    

    > [!NOTE]  
    > 有关<STRONG>move-csuser</STRONG> cmdlet 的详细信息, 请运行: <STRONG>Get-help move-csuser-详细</STRONG>信息

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

