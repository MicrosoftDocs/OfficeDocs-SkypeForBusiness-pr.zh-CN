---
title: 安装数据库选项页
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.InstallDatabaseOptionPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 926c47a0-3957-4892-b61a-7a4b569552c3
description: 配置数据库和日志文件在数据库和日志文件上的位置的高级SQL Server。 可用的选项有：
ms.openlocfilehash: 392db6eb9b882ff66a9f15e1f5c4f0918cb140a5
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51116070"
---
# <a name="install-database-options-page"></a>安装数据库选项页

配置数据库和日志文件在数据库和日志文件上的位置的高级SQL Server。 可用的选项有：

> [!IMPORTANT]
> 选择最符合与数据和策略相关的要求和策略的选项，日志文件计算机上SQL Server位置。

 **自动确定数据库文件位置**：默认选项使用一种算法来确定数据库SQL Server并分发数据库和日志文件以实现最佳性能。

 **Use SQL Server instance defaults**： Select this option to place database file and log files based on the instance settings at SQL Server. 这些选项通常由数据库管理员管理和配置。

 目标数据库上的这些 **路径** SQL Server：通过键入要放置数据库和日志文件的驱动器和文件夹的完整路径，选择此选项可定义你自己的 SQL Server 数据库和日志文件路径。

> [!IMPORTANT]
> 输入的路径可能会根据安装中的性能优化算法进行修改。 有关详细信息，请参阅[Database Installation Using Lync Server Management Shell](/previous-versions/office/lync-server-2013/lync-server-2013-database-installation-using-lync-server-management-shell)。

 **确定**：单击“确定”按钮以应用更改。

 **取消**：单击“取消”以放弃所有更改并返回到“安装数据库”屏幕。

 **帮助**：单击“帮助”按钮以访问此帮助页面。

## <a name="see-also"></a>另请参阅

[SQL Server 数据和日志文件放置](/previous-versions/office/lync-server-2013/lync-server-2013-sql-server-data-and-log-file-placement)