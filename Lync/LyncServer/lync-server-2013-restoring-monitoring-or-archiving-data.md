---
title: 'Lync Server 2013: 还原监视或存档数据'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Restoring monitoring or archiving data
ms:assetid: 60118526-13bb-4b03-803e-6ffae219d436
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202175(v=OCS.15)
ms:contentKeyID: 51541483
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 803cb6050d4230653a13f1e3e66c2a092911c509
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822382"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-monitoring-or-archiving-data-in-lync-server-2013"></a>在 Lync Server 2013 中还原监视或存档数据

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2013-02-18_

恢复监视和存档数据无需在失败后获取 Lync 服务器并运行。 但是, 如果监视和存档数据对你的组织至关重要, 你将希望在重新创建数据库后还原数据。

以下过程介绍了如何使用 SQL Server Management Studio 还原存档或监视数据。

<div>

## <a name="to-restore-monitoring-or-archiving-data-from-a-backup-file"></a>还原对备份文件中的数据进行监视或存档

1.  以本地计算机上管理员组的成员或具有同等用户权限的组的成员身份登录到要还原的服务器。

2.  打开 SQL Server Management Studio: 单击 "**开始**", 单击 "**所有程序**", 单击 " **Microsoft sql Server 2012** " 或 " **microsoft sql server 2008 R2**", 然后单击 " **SQL server management Studio**"。

3.  在 "**连接到服务器**" 中, 通过至少提供服务器的名称和身份验证信息, 连接到 SQL Server 实例。

4.  在**对象资源管理器**中, 右键单击 "**数据库**", 然后单击 "**还原数据库**"。

5.  在 "**选择页面**" 下, 单击 "**常规**", 然后在 "**到数据库**" 中选择数据库名称, 如下所示:
    
      - 对于存档数据库, 请选择 " **LcsLog**"。
    
      - 对于呼叫详细记录 (CDR) 数据库, 请选择 " **LcsCDR**"。
    
      - 对于体验质量 (QoE) 数据库, 请选择 " **QoEMetrics**"。

6.  单击 "**从设备**"。

7.  在 "**选择要还原的备份集**" 下, 单击备份文件, 然后单击 "**还原**"。

8.  在 "**选择页面**" 下, 单击 "**选项**", 验证数据文件路径和日志路径是否位于正确的文件夹中, 然后单击 **"确定"**。

</div>

<div>

## <a name="to-make-sure-that-access-control-lists-acls-are-correct"></a>确保访问控制列表 (Acl) 正确无误

1.  展开 "**数据库**", 展开 "存档" 或 "监视数据库", 展开 "**安全性**", 然后展开 "**用户**"。

2.  验证域组 RTCComponentUniversalServices 是否作为用户存在。

3.  如果 "**用户**" 下不存在 RTCComponentUniversalServices, 请执行下列操作:
    
    1.  右键单击 "**用户**", 然后单击 "**新建用户**"。
    
    2.  在 "**登录名**" 中, 键入缺少的组名 RTCComponentUniversalServices。
    
    3.  在 "**数据库角色成员身份**" 下, 选择 " **ServerRole** " 权限, 然后单击 **"确定"**。
    
    <div>
    

    > [!NOTE]  
    > 不需要重新启动存档或监视服务。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

