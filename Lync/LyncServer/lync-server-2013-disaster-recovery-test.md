---
title: Lync Server 2013：灾难恢复测试
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Disaster recovery test
ms:assetid: 04f5e747-d837-4350-9fc0-8605dbf025a7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn747887(v=OCS.15)
ms:contentKeyID: 63969571
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c0b274d933fbb1c9f47b219a492403bd1c5f58d5
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42197495"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="disaster-recovery-test-in-lync-server-2013"></a>Lync Server 2013 中的灾难恢复测试

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2015-01-26_

为 Lync Server 2013 池服务器执行系统恢复，以测试已记录的灾难恢复过程。 此测试将模拟一台服务器的完全硬件故障，并将帮助确保资源、计划和数据可用于恢复。 尝试每月旋转测试的焦点，以便您的组织每次都测试不同的服务器或其他设备的故障。

请注意，组织执行灾难恢复测试的计划将有所不同。 不会忽略或忽略灾难恢复测试，这一点非常重要。

<div>


将 Lync Server 2013 拓扑、策略和配置设置导出到文件中。 此外，还可以使用此文件在升级后将此信息还原到中央管理存储，或者在发生硬件故障或其他一些问题导致数据丢失的情况下。

将 Lync Server 2013 拓扑、策略和配置设置导入到中央管理存储或本地计算机，如以下命令所示：

`Import-CsConfiguration -ByteInput <Byte[]> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]`

`Import-CsConfiguration -FileName <String> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]`

若要备份 Lync Server 2013 数据，请执行以下操作：

  - 使用标准 SQL Server 备份过程将数据库转储到文件或磁带转储设备，从而备份 RTC 和 LCSLog 数据库。

  - 使用第三方备份应用程序将数据备份到文件或磁带。

  - 使用 Export-csuserdata cmdlet 可以创建整个 RTC 数据库的 XML 导出。

  - 使用文件系统备份或第三方备份会议内容和合规性日志。

  - 使用 CsConfiguration 命令行工具备份 Lync Server 2013 设置。

故障转移过程中的第一步包括将用户从生产池强制移动到灾难恢复池。

这将是强制移动，因为生产池将不能接受用户重新定位。

除了 RTC SQL 数据库上的记录更新之外，Lync Server 2013 移动用户过程实际上也是对用户帐户对象上属性的更改。

可以通过以下两个过程来还原这些数据：

  - 使用标准 SQL Server 还原过程或使用第三方备份/还原实用程序，可以从生产 SQL Server 从原始备份转储设备还原 RTC 数据库。

  - 可以使用 DBIMPEXP 实用工具，使用从生产 SQL Server 导出创建的 XML 文件来还原用户联系人数据。

还原此数据后，用户可以有效地连接到灾难恢复 Lync Server 2013 池，并照常运行。

若要使用户能够连接到灾难恢复 Lync Server 2013 池，将需要进行 DNS 记录更改。

使用以下各项的自动配置和 DNS SRV 记录，客户端将引用生产 Lync Server 2013 池：

  - SRV： \_sip。\_tls。\<域\> /CNAME： SIP。\<域\>

  - CNAME： SIP。\<域\> /cvc-pool-1。\<域\>

为了便于进行故障转移，必须更新此 CNAME 记录以引用 DROCSPool FQDN：

  - CNAME： SIP。\<域\> /DROCSPool。\<域\>

  - Sip.\<域\>

  - AV.\<域\>

  - webconf.\<域\>

  - OCSServices.\<域\>

<div>


> [!IMPORTANT]  
> 有关详细的管理和管理过程，请参阅<A href="lync-server-2013-backing-up-and-restoring-lync-server.md">备份和还原 Lync Server 2013</A>。



</div>

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中规划高可用性和灾难恢复](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)  
[Lync Server 2013 中的备份和高可用性 cmdlet](https://docs.microsoft.com/powershell/module/skype/?view=skype-ps)  


[Import-CsConfiguration](https://docs.microsoft.com/powershell/module/skype/Import-CsConfiguration)  
[备份和还原 Lync Server 2013](lync-server-2013-backing-up-and-restoring-lync-server.md)  
[管理 Lync Server 2013 灾难恢复、高可用性和备份服务](lync-server-2013-managing-lync-server-disaster-recovery-high-availability-and-backup-service.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

