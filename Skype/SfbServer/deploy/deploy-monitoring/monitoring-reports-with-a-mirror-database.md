---
title: 将监控报告与 Skype for Business Server 中的镜像数据库关联
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 42b797c6-8db8-4ad7-886e-8ddf8deb06f9
description: 摘要：了解如何将监控报告与 Skype for Business Server 使用的镜像数据库关联。
ms.openlocfilehash: 4ce6d420f6b29a5c6160b9b220e5fd190a977f9d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802162"
---
# <a name="associate-monitoring-reports-with-a-mirror-database-in-skype-for-business-server"></a>将监控报告与 Skype for Business Server 中的镜像数据库关联 
 
**摘要：** 了解如何将监控报告与 Skype for Business Server 使用的镜像数据库关联。
  
## <a name="monitor-reports-with-a-mirror-database"></a>使用镜像数据库监视报告

如果为监控数据库配置镜像，该镜像数据库将在发生故障转移时接管为主数据库。 但是，如果使用 Skype for Business Server 监控报告并发生故障转移，您可能会发现监控报告未连接到镜像数据库。 这是因为，在安装监控报告时，仅指定主数据库的位置;不指定镜像数据库的位置。
  
若要使监控报告自动故障转移到镜像数据库，必须将镜像数据库作为"故障转移合作伙伴"添加到监控报告使用的两个数据库中 (一个数据库用于呼叫详细信息记录数据，另一个数据库用于用户体验质量 (QoE) 数据) 。  (请注意，应在安装监控报告后执行此步骤。) 可以通过手动编辑这两个数据库使用的连接字符串值来添加故障转移合作伙伴信息。 为此，请完成以下过程：
  
1. 使用Internet Explorer打开 **SQL Server Reporting Services** 主页。 Reporting Services 主页 URL 包括：
    
   - **http：** 前缀。
    
   - 例如， (安装 Reporting Services) 的计算机的完全限定域名 (FQDN **atl-sql-001.litwareinc.com) 。**
    
   - 字符字符串 **/Reports_。**
    
   - 安装了监控报告的数据库实例的名称 (例如 **，archinst) 。**
    
     例如，如果SQL Server Reporting Services 安装在计算机上atl-sql-001.litwareinc.com监控报告使用数据库实例 archinst，则主页 URL 如下所示：
    
     **http://atl-sql-001.litwareinc.com/Reports_archinst**
    
2. 访问 Reporting Services 主页后，单击 **ServerReports，****然后单击Reports_Content。** 这将将你介绍 skype for **Business Reports_Content** 报告的信息页面。
    
3. 在 **Reports_Content** 页上，单击 **CDRDB** 数据源。
    
4. 在 **CDRDB 页上** 的"属性 **"选项卡上** ，查找标记为"连接" **字符串的文本框**。 当前连接字符串将类似于：
    
    Data source= (local) \archinst;initial catalog=LcsCDR
    
5. 编辑连接字符串以包含镜像数据库的服务器名称和数据库实例。 例如，如果服务器名为 atl-mirror-001，并且镜像数据库位于 archinst 实例中，则需要添加它以使用此语法指定镜像数据库：
    
    故障转移 Partner=atl-mirror-001\archinst
    
    编辑的连接字符串如下所示：
    
    Data source= (local) \archinst;故障转移 Partner=atl-mirror-001\archinst;initial catalog=LcsCDR
    
6. 更新连接字符串后，单击"应用 **"。**
    
7. 在 **CDRDB 页上** ，单击 **Reports_Content链接** 。 单击 **QMSDB** 数据源，然后编辑 QoE 数据库的连接字符串。 例如：
    
    Data source= (local) \archinst;故障转移 Partner=atl-mirror-001\archinst;initial catalog=QoEMetrics
    
8. 单击“**应用**”。
    
## <a name="see-also"></a>另请参阅

[在 Skype for Business Server 中安装监控报告](install-monitoring-reports.md)
  
[在 Skype for Business Server 中使用监控报告](../../manage/health-and-monitoring/monitoring-reports.md)
