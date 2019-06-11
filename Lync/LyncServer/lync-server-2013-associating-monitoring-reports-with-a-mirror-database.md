---
title: 'Lync Server 2013: 将监视报告与镜像数据库相关联'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Associating Monitoring Reports with a mirror database
ms:assetid: 42b797c6-8db8-4ad7-886e-8ddf8deb06f9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945624(v=OCS.15)
ms:contentKeyID: 51541467
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 19ff2455d473c83855320555cdffdc2e33001d0d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837906"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="associating-monitoring-reports-with-a-mirror-database-in-lync-server-2013"></a>将监视报告与 Lync Server 2013 中的镜像数据库相关联

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2014-02-07_

如果您为监控数据库配置了镜像，该镜像数据库将在发生故障转移时接任主数据库。 但是, 如果你使用 Lync Server Monitoring Reports, 并且发生故障转移, 你可能会发现你的监视报告未连接到镜像数据库。 这是因为在安装监控报告时，您仅指定了主数据库的位置，未指定镜像数据库的位置。

要使监控报告自动故障转移到镜像数据库，您必须将镜像数据库作为“故障转移合作伙伴”添加到监控报告使用的两个数据库（一个数据库用于存放呼叫详细信息记录数据，另一个用于存放用户体验质量 (QoE) 数据）。（注意，此步骤应在安装监控报告后执行。）您可以通过手动编辑这两个数据库使用的连接字符串值来添加故障转移伙伴信息。为此，请完成以下过程：

1.  使用 Internet Explorer 打开“**SQL Server Reporting Services**”主页。Reporting Services 主页 URL 包括：
    
      - **http:** 前缀。
    
      - 用于安装 Reporting Services 的计算机的完全限定域名 (FQDN)。（例如 **atl-sql-001.litwareinc.com**）。
    
      - 字符串 **/Reports\_**。
    
      - 用于安装监控报告的数据库实例的名称（例如 **archinst**）。
    
    例如，如果 SQL Server Reporting Services 安装在 atl-sql-001.litwareinc.com 上的计算机上，监控报告使用数据库实例 archinst，则主页 URL 如下所示：
    
    **http://atl-sql-001.litwareinc.com/Reports\_archinst**

2.  访问报表服务主页后, 单击 " **LyncServerReports**", 然后单击 "**报表\_内容**"。 将转到 Lync Server Monitoring Reports 的 "**报告\_内容**" 页面。

3.  在 "**报表\_内容**" 页面上, 单击 " **CDRDB** " 数据源。

4.  在“**CDRDB**”页上，在“**属性**”选项卡上查找标为“**连接字符串**”的文本框。当前连接字符串类似如下形式：
    
    **数据源 = (local)\\archinst; 初始目录 = LcsCDR**

5.  编辑连接字符串以包括服务器名称和镜像数据库的数据库实例。例如，如果服务器名为 atl-mirror-001，镜像数据库采用 archinst 实例，则您需要使用以下语法进行添加以指定镜像数据库：
    
    **故障转移合作伙伴 = atl-镜像-\\001 archinst**
    
    您编辑的连接字符串类似于以下形式：
    
    **数据源 = (本地)\\archinst;故障转移合作伙伴 = atl-镜像-\\001 archinst; 初始目录 = LcsCDR**

6.  更新连接字符串后，单击“**应用**”。

7.  在 " **CDRDB** " 页面上, 单击 "**报告\_内容**" 链接。 单击“**QMSDB**”数据源，然后编辑 QoE 数据库的连接字符串。 例如：
    
    **数据源 = (本地)\\archinst;故障转移合作伙伴 = atl-镜像-\\001 archinst; 初始目录 = QoEMetrics**

8.  单击“**应用**”。

<div>

## <a name="see-also"></a>另请参阅


[安装 Lync Server 2013 监视报告](lync-server-2013-installing-lync-server-2013-monitoring-reports.md)  
[在 Lync Server 2013 中使用监视报告](lync-server-2013-using-monitoring-reports.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

