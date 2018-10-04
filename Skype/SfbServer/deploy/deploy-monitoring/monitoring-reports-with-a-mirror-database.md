---
title: 将监控报告与 Skype 中的镜像数据库相关联的业务服务器
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 42b797c6-8db8-4ad7-886e-8ddf8deb06f9
description: 摘要： 了解如何将监控报告与业务服务器使用 Skype 镜像数据库相关联。
ms.openlocfilehash: fdca07874192a772a99145bf3ca2042995bb7aee
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25374363"
---
# <a name="associate-monitoring-reports-with-a-mirror-database-in-skype-for-business-server"></a>将监控报告与 Skype 中的镜像数据库相关联的业务服务器 
 
**摘要：** 了解如何将监控报告与业务服务器使用 Skype 镜像数据库相关联。
  
## <a name="monitor-reports-with-a-mirror-database"></a>监控报告与镜像数据库

如果您为监控数据库配置了镜像，该镜像数据库将在发生故障转移时接任主数据库。 但是，如果发生故障转移 Skype 用于业务服务器监控报告，您可能会发现，您监控报告未连接到镜像数据库。 这是因为在安装监控报告时，您仅指定了主数据库的位置，未指定镜像数据库的位置。
  
要使监控报告自动故障转移到镜像数据库，您必须将镜像数据库作为“故障转移合作伙伴”添加到监控报告使用的两个数据库（一个数据库用于存放呼叫详细信息记录数据，另一个用于存放用户体验质量 (QoE) 数据）。（注意，此步骤应在安装监控报告后执行。）您可以通过手动编辑这两个数据库使用的连接字符串值来添加故障转移伙伴信息。为此，请完成以下过程：
  
1. 使用 Internet Explorer 打开“**SQL Server Reporting Services**”主页。Reporting Services 主页 URL 包括：
    
   - **http:** 前缀。
    
   - 用于安装 Reporting Services 的计算机的完全限定域名 (FQDN)。（例如 **atl-sql-001.litwareinc.com**）。
    
   - 字符字符串 **/Reports_**。
    
   - 用于安装监控报告的数据库实例的名称（例如 **archinst**）。
    
     例如，如果 SQL Server Reporting Services 安装在 atl-sql-001.litwareinc.com 上的计算机上，监控报告使用数据库实例 archinst，则主页 URL 如下所示：
    
     **http://atl-sql-001.litwareinc.com/Reports_archinst**
    
2. 访问 Reporting Services 主页后，单击“**ServerReports**”，然后单击“**Reports_Content**”。 这样，就会 ' **Reports_Content**页上的 Skype 业务服务器监控报告。
    
3. 在“**Reports_Content**”页上，单击“**CDRDB**”数据源。
    
4. 在“**CDRDB**”页上，在“**属性**”选项卡上查找标为“**连接字符串**”的文本框。当前连接字符串类似如下形式：
    
    Data source=(local)\archinst;initial catalog=LcsCDR
    
5. 编辑连接字符串以包括服务器名称和镜像数据库的数据库实例。例如，如果服务器名为 atl-mirror-001，镜像数据库采用 archinst 实例，则您需要使用以下语法进行添加以指定镜像数据库：
    
    Failover Partner=atl-mirror-001\archinst
    
    您编辑的连接字符串类似于以下形式：
    
    Data source=(local)\archinst;Failover Partner=atl-mirror-001\archinst;initial catalog=LcsCDR
    
6. 更新连接字符串后，单击“**应用**”。
    
7. 在“**CDRDB**”页上，单击“**Reports_Content**”链接。单击“**QMSDB**”数据源，然后编辑 QoE 数据库的连接字符串。例如：
    
    Data source=(local)\archinst;Failover Partner=atl-mirror-001\archinst;initial catalog=QoEMetrics
    
8. 单击“**应用**”。
    
## <a name="see-also"></a>另请参阅

[为业务服务器在 Skype 安装监控报告](install-monitoring-reports.md)
  
[使用监控报告中 Skype 业务服务器](../../manage/health-and-monitoring/monitoring-reports.md)