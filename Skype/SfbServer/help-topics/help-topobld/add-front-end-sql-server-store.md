---
title: 添加前端 SQL Server 存储
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dace9561-3eb4-4647-83cb-56c246919ae1
description: Standard Edition服务器部署会自动安装所需的Microsoft SQL Server Express数据库软件和SQL Server数据库。 因此，所有选项都预填充，你无法对默认配置进行更改。
ms.openlocfilehash: b6b0cd35f0436278b39c6126ed59bc3c95d1fb44131a80fb898297fdec512eda
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54314588"
---
# <a name="add-front-end-sql-server-store"></a>添加前端 SQL Server 存储

Standard Edition服务器部署会自动安装所需的Microsoft SQL Server Express数据库软件和SQL Server数据库。 因此，所有选项都预填充，你无法对默认配置进行更改。

服务器部署的前端池Enterprise Edition后端数据库支持 64 位版本的 SQL Server 数据库软件。 可以选择之前定义的 SQL Server 数据库用于后端数据库，或者通过指定 SQL Server SQL Server 数据库所在的服务器的完全限定域名 (FQDN) ，以及要用于新的 SQL Server 数据库 (（可以是默认实例）或指定) 的命名实例来定义新的 SQL Server 数据库。 还可以选择在数据库存储上启用镜像SQL Server，并指定用于自动故障转移的镜像见证。

有关支持SQL Server的详细信息，请参阅可支持性文档中的 Database [Software and Clustering](/previous-versions/office/lync-server-2013/lync-server-2013-database-software-support) Support。 有关设置 SQL Server 作为后端数据库的详细信息，请参阅部署文档中的[为 Lync Server 2010 配置 SQL Server](/previous-versions/office/lync-server-2013/lync-server-2013-configure-sql-server-for-lync-server)。

> [!NOTE]
> 如果用于发布拓扑的帐户具有相应的用户权限，您可以在发布拓扑时创建后端数据库 (实时通信 (RTC) ) 。 您稍后还可创建数据库（包括在安装过程中）。

> [!NOTE]
> 若要在基于 SQL Server 的服务器上为 Enterprise Edition 部署安装和部署数据库，您必须是安装数据库文件的基于 SQL Server 的服务器的 SQL Server sysadmins 组的成员。 如果您不是 sysadmins SQL Server的成员，则必须请求添加到组，直到部署数据库文件。 如果您无法成为 sysadmins 组的成员，您应向 SQL Server 数据库管理员提供用于配置和部署数据库的脚本。 有关完成这些过程所需的用户权限的详细信息，请参阅 Deployment [Permissions for SQL Server](/previous-versions/office/lync-server-2013/lync-server-2013-deployment-permissions-for-sql-server)。