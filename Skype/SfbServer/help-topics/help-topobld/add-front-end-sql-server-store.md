---
title: 添加前结束 SQL Server 存储
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/8/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dace9561-3eb4-4647-83cb-56c246919ae1
description: 标准版服务器部署自动安装所需的 Microsoft SQL Server Express 数据库软件和 SQL Server 数据库。 因此，预填充所有的选项，并且不能对默认配置进行更改。
ms.openlocfilehash: facb2e91511323e6fc87015016b060ba5076c8f6
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="add-front-end-sql-server-store"></a>添加前结束 SQL Server 存储
 
标准版服务器部署自动安装所需的 Microsoft SQL Server Express 数据库软件和 SQL Server 数据库。 因此，预填充所有的选项，并且不能对默认配置进行更改。
  
企业版服务器的部署前端池的后端数据库需要受支持的 64 位版本的 SQL Server 数据库软件。 可以选择以前定义的 SQL Server 数据库用作后端数据库中，或者通过指定的 SQL Server 数据库时所在的服务器和实例的 SQL S 完全合格的域名称 (FQDN) 来定义一个新的 SQL Server 数据库要使用新的 SQL Server 数据库 （它可以是默认实例或命名的实例指定） 的服务器。 此外可以选择启用镜像对 SQL Server 存储，并指定镜像见证的自动故障切换。
  
有关 SQL Server 支持，请参阅中的可支持性文档[数据库软件和群集支持](http://technet.microsoft.com/library/e05d0032-bbea-4e61-987d-d07b1c045fd5.aspx)。 有关 SQL Server 设置为后端数据库的详细信息，请参阅[Lync Server 2010 中的配置 SQL Server](http://technet.microsoft.com/library/375e5cc4-e436-46dc-9b02-5063f35cdcc1.aspx)部署文档。
  
> [!NOTE]
> 如果用于发布拓扑的帐户具有适当的用户权限和权限，则可以创建后端数据库 （实时通信 (RTC)） 在发布您的拓扑结构。 您还可以创建数据库之后，包括作为安装过程的一部分。 
  
> [!NOTE]
> 要安装和部署企业版部署的基于 SQL Server 的服务器上的数据库时，您必须是要安装的数据库文件的基于 SQL Server 的服务器的 SQL Server 系统管理员组的成员。 如果您不是 SQL Server 系统管理员组的成员，则您必须请求部署数据库文件之前要添加到组。 如果不能进行系统管理员组的成员，应将您的 SQL Server 数据库管理员提供的脚本来配置和部署数据库。 有关完成这些过程所需的权限和用户权限的详细信息，请参阅[SQL Server 部署权限](http://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx)。 
  

