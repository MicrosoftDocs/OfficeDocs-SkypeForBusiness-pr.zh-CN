---
title: 迁移拨入访问号码
TOCTitle: 迁移拨入访问号码
ms:assetid: e0dfaed2-64c7-45cb-aaa9-d6117a26625d
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ721909(v=OCS.15)
ms:contentKeyID: 49888642
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 迁移拨入访问号码

 

_**上一次修改主题：** 2012-10-19_

将拨入访问号码从 Lync Server 2010 迁移到 Lync Server 2013 需要运行 **Move-CsApplicationEndpoint** cmdlet 以迁移联系人对象。在 Lync Server 2010 与 Lync Server 2013 共存期间，您在 Lync Server 2013 中创建的拨入访问号码的行为与在 Lync Server 2010 中创建的拨入访问号码相似，如本节所述。

您在 Lync Server 2010 中创建但移动到 Lync Server 2013 的拨入访问号码或在迁移之前、期间或之后在 Lync Server 2013 中创建的拨入访问号码具有以下特性：

  - 不在 Office Communications Server 2007 R2 会议邀请和拨入访问号码页上显示。

  - 在 Lync Server 2010 会议邀请和拨入访问号码页上显示。

  - 在 Lync Server 2013 会议邀请和拨入访问号码页上显示。

  - 无法在 Office Communications Server 2007 R2 管理工具中查看或修改。

  - 可以在 Lync Server 2010 控制面板和 Lync Server 2010 命令行管理程序中查看和修改。

  - 可以在 Lync Server 2013 控制面板和 Lync Server 2013 命令行管理程序中查看和修改。

  - 可以使用带有 Priority 参数的 Set-CsDialinConferencingAccessNumber cmdlet 在区域内重新排序。

在停用 Lync Server 2010 池之前，必须完成迁移指向 Lync Server 2010 池的拨入访问号码。如果未按以下过程所述完成拨入访问号码的迁移，对该访问号码的传入呼叫将失败。

> [!IMPORTANT]
> 在停用 Lync Server 2010 池之前必须执行此过程。


> [!NOTE]  
> 建议您在网络使用率较低时移动拨入访问号码，以免服务出现短暂中断。


**确认和移动拨入访问号码**

1.  启动 Lync Server 命令行管理程序：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 命令行管理程序”。

2.  要将每个拨入访问号码移动到 Lync Server 2013 上承载的池，请在命令行中运行：
    
        Move-CsApplicationEndpoint -Identity <SIP URI of the access number to be moved> -Target <FQDN of the pool to which the access number is moving>

3.  打开 Lync Server 控制面板。

4.  在左侧导航栏中，单击“会议”。

5.  单击“拨入访问号码”选项卡。

6.  确认将拨入访问号码迁移出的 Lync Server 2010 池没有保留任何拨入访问号码。
    
    > [!NOTE]
    > 当所有拨入访问号码均指向 Lync Server 2013 池后，可以停用 Lync Server 2010 池。


**使用 Lync Server 控制面板确认拨入访问号码迁移**

1.  使用分配给 **CsUserAdministrator** 角色或 **CsAdministrator** 角色的用户帐户登录到内部部署中的任一台计算机。

2.  打开 Lync Server 控制面板。

3.  在左侧导航栏中，单击“会议”。

4.  单击“拨入访问号码”选项卡。

5.  确认所有拨入访问号码均已迁移到 Lync Server 2013 上承载的池。

**使用 Lync Server 命令行管理程序确认拨入访问号码迁移**

1.  打开 Lync Server 命令行管理程序。

2.  要返回所有移植的拨入式会议访问号码，请从命令行运行：
    
        Get-CsDialInConferencingAccessNumber -Filter {Pool -eq "<FQDN of the pool to which the access number is moved>"}

3.  确认所有拨入访问号码均已迁移到 Lync Server 2013 上承载的池。

