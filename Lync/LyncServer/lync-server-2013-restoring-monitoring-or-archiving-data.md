---
title: Lync Server 2013：还原监视或存档数据
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring monitoring or archiving data
ms:assetid: 60118526-13bb-4b03-803e-6ffae219d436
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202175(v=OCS.15)
ms:contentKeyID: 51541483
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5be8d5409a5770ef2ee928075c147c126ce4219a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144668"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="restoring-monitoring-or-archiving-data-in-lync-server-2013"></a>在 Lync Server 2013 中还原监视或存档数据

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-18_

在出现故障后，无需还原监视和存档数据即可使 Lync Server 启动并运行。 但是，如果监视和存档数据对您的组织至关重要，您将需要在重新创建数据库后还原数据。

以下过程介绍如何使用 SQL Server Management Studio 还原存档或监视数据。

<div>

## <a name="to-restore-monitoring-or-archiving-data-from-a-backup-file"></a>从备份文件中还原监控或存档数据

1.  以本地计算机上 Administrators 组的成员或具有同等用户权限的组的成员身份登录到要还原的服务器。

2.  打开 SQL Server Management Studio：依次单击 "**开始**"、"**所有程序**"、" **Microsoft sql Server 2012** " 或 " **microsoft sql server 2008 R2**"，然后单击 " **SQL server management Studio**"。

3.  在“连接到服务器”**** 中，至少提供服务器的名称和身份验证信息，以连接到 SQL Server 实例。

4.  在“对象资源管理器”**** 中，右键单击“数据库”****，然后单击“还原数据库”****。

5.  在“选择页”**** 下，单击“常规”****，然后在“目标数据库”**** 中选择数据库名称，如下所示：
    
      - 对于存档数据库，请选择 " **LcsLog**"。
    
      - 对于呼叫详细信息记录 (CDR) 数据库，请选择“LcsCDR”****。
    
      - 对于用户体验质量 (QoE) 数据库，请选择“QoEMetrics”****。

6.  单击“自设备”****。

7.  在“选择用于还原的备份集”**** 下，单击备份文件，然后单击“还原”****。

8.  在“选择页”**** 下，单击“选项”****，确认数据文件路径和日志路径位于正确的文件夹中，然后单击“确定”****。

</div>

<div>

## <a name="to-make-sure-that-access-control-lists-acls-are-correct"></a>确保访问控制列表（Acl）正确

1.  依次展开“数据库”****、存档数据库或监控数据库、“安全”****，然后展开“用户”****。

2.  确认域组 RTCComponentUniversalServices 作为用户存在。

3.  如果 "**用户**" 下不存在 RTCComponentUniversalServices，请执行以下操作：
    
    1.  右键单击“用户”****，然后单击“新建用户”****。
    
    2.  在 "**登录名**" 中，键入缺少的组名称 RTCComponentUniversalServices。
    
    3.  在“数据库角色成员身份”**** 中，选择“ServerRole”**** 权限，然后单击“确定”****。
    
    <div>
    

    > [!NOTE]  
    > 无需重新启动存档服务或监控服务。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

