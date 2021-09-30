---
title: 将监控报告与数据库中的镜像数据库Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 42b797c6-8db8-4ad7-886e-8ddf8deb06f9
description: 摘要：了解如何将监控报告与服务器使用的镜像Skype for Business Server。
ms.openlocfilehash: ecdf630f6839fa65bf163715e473a3a37cdbcece
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/30/2021
ms.locfileid: "60014396"
---
# <a name="associate-monitoring-reports-with-a-mirror-database-in-skype-for-business-server"></a>将监控报告与数据库中的镜像数据库Skype for Business Server 
 
**摘要：** 了解如何将监控报告与服务器使用的镜像数据库Skype for Business Server。
  
## <a name="monitor-reports-with-a-mirror-database"></a>使用镜像数据库监视报告

如果为监控数据库配置镜像，该镜像数据库将在发生故障转移时接管主数据库。 但是，如果您使用Skype for Business Server监控报告并发生故障转移，您可能会发现监控报告未连接到镜像数据库。 这是因为，在安装监控报告时，仅指定主数据库的位置;您不指定镜像数据库的位置。
  
若要使监控报告自动故障转移到镜像数据库，必须将镜像数据库作为"故障转移合作伙伴"添加到监控报告使用的两个数据库 (一个数据库用于呼叫详细记录数据，另一个数据库用于用户体验质量 (QoE) 数据) 。  (请注意，此步骤应在安装监控报告之后执行。) 可以通过手动编辑这两个数据库使用的连接字符串值来添加故障转移合作伙伴信息。 为此，请完成以下过程：
  
1. 使用 Internet Explorer **打开SQL Server Reporting Services主页**。 Reporting Services 主页 URL 包括：
    
   - **http：** 前缀。
    
   - 安装 Reporting Services 的计算机的完全限定 (FQDN (FQ) DN， `atl-sql-001.litwareinc.com` 例如) 。
    
   - 字符串 **/Reports_**。
    
   - 安装监控报告的数据库实例的名称 (，例如 **archinst**) 。
    
     例如，如果SQL Server Reporting Services，并且监控报告使用数据库实例 `atl-sql-001.litwareinc.com` archinst，则主页 URL 将如下所示：
    
     `http://atl-sql-001.litwareinc.com/Reports_archinst`
    
2. 访问 Reporting Services 主页后，单击 **"ServerReports"，** 然后单击 **"Reports_Content"。** 您将访问"监控 **Reports_Content** 的"Skype for Business Server页。
    
3. 在 **"Reports_Content"** 页上，单击 **"CDRDB"** 数据源。
    
4. 在 **CDRDB 页上** 的"属性 **"选项卡上** ，查找标记为"连接字符串 **"的文本框**。 当前连接字符串将类似于：
    
    Data source= (local) \archinst;initial catalog=LcsCDR
    
5. 编辑连接字符串以包括镜像数据库的服务器名称和数据库实例。 例如，如果服务器名为 atl-mirror-001，并且镜像数据库位于 archinst 实例中，则需要添加 以使用此语法指定镜像数据库：
    
    故障转移 Partner=atl-mirror-001\archinst
    
    编辑的连接字符串将如下所示：
    
    Data source= (local) \archinst;故障转移 Partner=atl-mirror-001\archinst;initial catalog=LcsCDR
    
6. 更新连接字符串后，单击"应用 **"。**
    
7. 在 **"CDRDB"** 页上，单击 **"Reports_Content** 链接。 单击 **QMSDB** 数据源，然后编辑 QoE 数据库的连接字符串。 例如：
    
    `Data source=(local)\archinst;Failover Partner=atl-mirror-001\archinst;initial catalog=QoEMetrics`
    
8. 单击“**应用**”。
    
## <a name="see-also"></a>另请参阅

[安装监控报告Skype for Business Server](install-monitoring-reports.md)
  
[使用监控报告Skype for Business Server](../../manage/health-and-monitoring/monitoring-reports.md)
