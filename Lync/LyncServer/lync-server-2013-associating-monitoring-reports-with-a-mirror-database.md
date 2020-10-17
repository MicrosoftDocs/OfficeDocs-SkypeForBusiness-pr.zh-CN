---
title: Lync Server 2013：将监控报告与镜像数据库相关联
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Associating Monitoring Reports with a mirror database
ms:assetid: 42b797c6-8db8-4ad7-886e-8ddf8deb06f9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945624(v=OCS.15)
ms:contentKeyID: 51541467
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 655c6ec788b934a533295fee577e72febb7818de
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48527099"
---
# <a name="associating-monitoring-reports-with-a-mirror-database-in-lync-server-2013"></a>在 Lync Server 2013 中将监控报告与镜像数据库相关联

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2014-02-07_

如果为监视数据库配置了镜像，则在发生故障转移时，镜像数据库将接管主数据库。 但是，如果您使用 Lync Server 监控报告，并且发生故障转移，则您可能会发现监视报告未连接到镜像数据库。 这是因为，在安装监控报告时，仅指定主数据库的位置;您不指定镜像数据库的位置。

若要获取监控报告以自动故障转移到镜像数据库，您必须将镜像数据库作为 "故障转移合作伙伴" 添加到用于监视报告的两个数据库 (一个数据库用于呼叫详细信息记录数据，另一个用于 (QoE) 数据) 的经验质量。  (请注意，在安装了监控报告之后，应执行此步骤。 ) 您可以通过手动编辑这两个数据库使用的连接字符串值来添加故障转移合作伙伴信息。 为此，请完成以下过程：

1.  使用 Internet Explorer 打开 **SQL Server Reporting Services** 主页。 Reporting Services 主页 URL 包括：
    
      - **Http：** 前缀。
    
      - 安装 Reporting Services 的计算机的完全限定的域名 (FQDN)  (例如， **atl-sql-001.litwareinc.com**) 。
    
      - 字符字符串 **/Reports \_ **。
    
      - 在其中安装监视报告的数据库实例的名称 (例如， **archinst**) 。
    
    例如，如果在计算机 atl-sql-001.litwareinc.com 上安装了 SQL Server Reporting Services，并且监控报告使用的是数据库实例 archinst，则主页 URL 将如下所示：
    
    **http://atl-sql-001.litwareinc.com/Reports\_archinst**

2.  访问 Reporting Services 主页后，单击 " **LyncServerReports**"，然后单击 " **报告 \_ 内容**"。 这将转到 Lync Server Monitoring 报告的 " **报告 \_ 内容** " 页。

3.  在 " **报告 \_ 内容** " 页上，单击 " **CDRDB** " 数据源。

4.  在 " **CDRDB** " 页上的 " **属性** " 选项卡上，查找标有 " **连接字符串**" 的文本框。 当前连接字符串将如下所示：
    
    **数据源 = (local) \\ archinst; 初始目录 = LcsCDR**

5.  编辑连接字符串以包含镜像数据库的服务器名称和数据库实例。 例如，如果服务器名为 atl-001，镜像数据库在 archinst 实例中，则需要使用以下语法添加以指定镜像数据库：
    
    **故障转移合作伙伴 = atl-mirror-001 \\ archinst**
    
    已编辑的连接字符串将如下所示：
    
    **数据源 = (local) \\ archinst;故障转移合作伙伴 = atl-mirror-001 \\ archinst; 初始目录 = LcsCDR**

6.  更新连接字符串后，单击 " **应用**"。

7.  在 " **CDRDB** " 页上，单击 " **报告 \_ 内容** " 链接。 单击 " **QMSDB** " 数据源，然后编辑 QoE 数据库的连接字符串。 例如：
    
    **数据源 = (local) \\ archinst;故障转移合作伙伴 = atl-mirror-001 \\ archinst; 初始目录 = QoEMetrics**

8.  单击“**应用**”。

<div>

## <a name="see-also"></a>另请参阅


[安装 Lync Server 2013 监控报告](lync-server-2013-installing-lync-server-2013-monitoring-reports.md)  
[在 Lync Server 2013 中使用监控报告](lync-server-2013-using-monitoring-reports.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

