---
title: 迁移拨入访问号码
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrate dial-in access numbers
ms:assetid: e0dfaed2-64c7-45cb-aaa9-d6117a26625d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721909(v=OCS.15)
ms:contentKeyID: 49733843
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0638ae76a9aa1108b11c1d1ff98fdd3eef08c938
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762940"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-dial-in-access-numbers"></a>迁移拨入访问号码

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-10-19_

将 Lync Server 2010 中的拨入访问号码迁移到 Lync Server 2013 需要运行**CsApplicationEndpoint** cmdlet 以迁移联系人对象。 在 Lync Server 2010 和 Lync Server 2013 共存期内，在 Lync Server 2013 中创建的拨入访问号码与您在 Lync Server 2010 中创建的拨入访问号码类似，如本部分所述。

您在 Lync Server 2010 中创建的拨入接入号码，但迁移到 Lync Server 2013 或在迁移期间或之后在 Lync Server 2013 中创建的号码具有以下特征：

  - 不会出现在 Office 通信服务器 2007 R2 邀请和 "拨入访问号码" 页面上。

  - 显示在 Lync Server 2010 的 "会议邀请" 和 "拨入访问号码" 页面上。

  - 显示在 Lync Server 2013 的 "会议邀请" 和 "拨入访问号码" 页面上。

  - 无法在 Office 通信服务器 2007 R2 管理工具中查看或修改。

  - 可在 Lync Server 2010 控制面板和 Lync Server 2010 管理外壳程序中查看和修改。

  - 可在 Lync Server 2013 控制面板和 Lync Server 2013 管理外壳程序中查看和修改。

  - 可通过将 CsDialinConferencingAccessNumber cmdlet 与 Priority 参数一起使用来在区域内重新排序。

在解除 Lync Server 2010 池之前，必须完成指向 Lync Server 2010 池的迁移拨入访问号码的迁移。 如果您没有完成拨入访问号码迁移，如以下过程中所述，对接入号码的拨入调用将失败。

<div>


> [!IMPORTANT]  
> 必须先执行此过程，然后才能解除 Lync Server 2010 池。



</div>

<div>


> [!NOTE]  
> 我们建议你在网络使用率较低时移动拨入访问号码，以防出现短时间的服务中断。



</div>

**标识和移动拨入访问号码**

1.  启动 Lync Server 命令行管理程序：依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server Management shell**"。

2.  要将每个拨入访问号码从命令行运行到 Lync Server 2013 上托管的池，请执行以下操作：
    
        Move-CsApplicationEndpoint -Identity <SIP URI of the access number to be moved> -Target <FQDN of the pool to which the access number is moving>

3.  打开“Lync Server 控制面板”。

4.  在左侧导航栏中，单击“**会议**”。

5.  单击 "**拨入访问号码**" 选项卡。

6.  验证你要从中迁移的 Lync Server 2010 池不会保留拨入访问号码。
    
    <div>
    

    > [!NOTE]  
    > 当所有拨入访问号码都指向 Lync Server 2013 池时，您就可以停止 Lync Server 2010 池。

    
    </div>

**使用 Lync Server "控制面板" 验证拨入访问号码迁移**

1.  从分配给**CsUserAdministrator**角色或**CsAdministrator**角色的用户帐户登录到内部部署中的任何计算机。

2.  打开“Lync Server 控制面板”。

3.  在左侧导航栏中，单击“**会议**”。

4.  单击 "**拨入访问号码**" 选项卡。

5.  验证所有拨入访问号码是否已迁移到 Lync Server 2013 上托管的池。

**使用 Lync Server 命令行管理程序验证拨入访问号码迁移**

1.  打开 Lync Server 命令行管理程序。

2.  要从命令行中返回已迁移的所有拨入式会议访问号码，请执行以下操作：
    
        Get-CsDialInConferencingAccessNumber -Filter {Pool -eq "<FQDN of the pool to which the access number is moved>"}

3.  验证所有拨入访问号码是否已迁移到 Lync Server 2013 上托管的池。

</div>

<span> </span>

</div>

</div>

</div>

