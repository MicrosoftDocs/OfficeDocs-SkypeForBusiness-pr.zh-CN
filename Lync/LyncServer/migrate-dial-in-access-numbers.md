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
ms.openlocfilehash: eaef027180304fca2a64294177faffcc0811e565
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42148911"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrate-dial-in-access-numbers"></a>迁移拨入访问号码

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-19_

若要将拨入访问号码从 Lync Server 2010 迁移到 Lync Server 2013，则需要运行**CsApplicationEndpoint** cmdlet 以迁移 contact 对象。 在 Lync Server 2010 和 Lync Server 2013 共存期间，您在 Lync Server 2013 中创建的拨入访问号码与您在 Lync Server 2010 中创建的拨入访问号码类似，如本节中所述。

在迁移之前或之后，在 Lync Server 2010 中创建的电话拨入访问号码已移动到 Lync server 2013，或者在迁移过程中或迁移后2013创建，具有以下特征：

  - 不会出现在 Office 通信服务器 2007 R2 会议邀请和 "拨入访问号码" 页上。

  - 显示在 Lync Server 2010 会议邀请和 "拨入访问号码" 页上。

  - 显示在 Lync Server 2013 会议邀请和 "拨入访问号码" 页上。

  - 无法在 Office 通信服务器 2007 R2 管理工具中查看或修改。

  - 可以在 Lync Server 2010 控制面板中和 Lync Server 2010 命令行管理程序中查看和修改。

  - 可以在 Lync Server 2013 控制面板中和 Lync Server 2013 命令行管理程序中查看和修改。

  - 可以通过使用 Set-csdialinconferencingaccessnumber cmdlet 和 Priority 参数在区域内重新排序。

在停用 Lync Server 2010 池之前，您必须完成指向 Lync Server 2010 池的拨入访问号码的迁移。 如果您未按以下过程所述完成拨入访问号码迁移，则对访问号码的传入呼叫将失败。

<div>


> [!IMPORTANT]  
> 必须先执行此过程，然后才能解除 Lync Server 2010 池。



</div>

<div>


> [!NOTE]  
> 我们建议您在网络使用率较低时移动拨入访问号码，以防出现短时间的服务中断。



</div>

**标识和移动拨入访问号码**

1.  启动 Lync Server 命令行管理程序：依次单击“开始”****、“所有程序”****、“Microsoft Lync Server 2013”**** 和“Lync Server 命令行管理程序”****。

2.  若要将每个拨入访问号码移到驻留在 Lync Server 2013 上的池，请在命令行中运行：
    
        Move-CsApplicationEndpoint -Identity <SIP URI of the access number to be moved> -Target <FQDN of the pool to which the access number is moving>

3.  打开“Lync Server 控制面板”。

4.  在左侧导航栏中，单击“会议”****。

5.  单击 "**拨入访问号码**" 选项卡。

6.  验证您要从中迁移的 Lync Server 2010 池没有保留的拨入访问号码。
    
    <div>
    

    > [!NOTE]  
    > 当所有拨入访问号码指向 Lync Server 2013 池时，您就可以停止使用 Lync Server 2010 池了。

    
    </div>

**使用 Lync Server 控制面板验证拨入访问号码迁移**

1.  从分配给**CsUserAdministrator**角色或**CsAdministrator**角色的用户帐户中，登录到内部部署中的任何计算机。

2.  打开“Lync Server 控制面板”。

3.  在左侧导航栏中，单击“会议”****。

4.  单击 "**拨入访问号码**" 选项卡。

5.  验证是否已将所有拨入访问号码迁移到在 Lync Server 2013 上托管的池。

**使用 Lync Server 命令行管理程序验证拨入访问号码迁移**

1.  打开 Lync Server 命令行管理程序。

2.  若要从命令行运行，以返回已迁移的所有电话拨入式会议访问号码，请执行以下操作：
    
        Get-CsDialInConferencingAccessNumber -Filter {Pool -eq "<FQDN of the pool to which the access number is moved>"}

3.  验证是否已将所有拨入访问号码迁移到在 Lync Server 2013 上托管的池。

</div>

<span> </span>

</div>

</div>

</div>

