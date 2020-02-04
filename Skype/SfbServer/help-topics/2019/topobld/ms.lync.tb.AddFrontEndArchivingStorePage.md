---
title: 添加前端存档存储
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddFrontEndArchivingStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ce1723eb-7c93-424a-a622-9c888bf6d3bc
ROBOTS: NOINDEX, NOFOLLOW
description: 存档需要支持的 Microsoft SQL Server 数据库软件的64位版本才能存储存档数据。 你可以选择用于存档的以前定义的 SQL Server 数据库，也可以通过指定 sql Server 数据库所驻留的服务器的完全限定的域名（FQDN），以及 SQL Se 的实例来定义新的 SQL Server 数据库。要用于新 SQL Server 数据库的 rver （可以是默认实例或你指定的命名实例）。
ms.openlocfilehash: d5ef47dd0df4063ce92b7c4adad955596e776f50
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2020
ms.locfileid: "41702937"
---
# <a name="add-front-end-archiving-store"></a>添加前端存档存储

存档需要支持的 Microsoft SQL Server 数据库软件的64位版本才能存储存档数据。 你可以选择用于存档的以前定义的 SQL Server 数据库，也可以通过指定 sql Server 数据库所驻留的服务器的完全限定的域名（FQDN），以及 SQL Se 的实例来定义新的 SQL Server 数据库。要用于新 SQL Server 数据库的 rver （可以是默认实例或你指定的命名实例）。

> [!NOTE]
> 如果用于发布拓扑的帐户具有相应的用户权利和权限，则可以在发布拓扑时创建监视数据库。 也可以稍后创建数据库（包括在安装过程中）。

> [!NOTE]
> 若要在基于 SQL Server 的服务器上安装和部署数据库以进行监视，您必须是要在其中安装数据库文件的基于 SQL Server 的服务器的 SQL Server sysadmin 组的成员。 如果你不是 SQL Server sysadmin 组的成员，则必须请求将添加到组中，直到部署数据库文件。 如果你不能成为 sysadmin 组的成员，你应该向 SQL Server 数据库管理员提供用于配置和部署数据库的脚本。 有关完成这些步骤所需的用户权限和权限的详细信息，请参阅部署文档中的[SQL Server 部署权限](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx)。


