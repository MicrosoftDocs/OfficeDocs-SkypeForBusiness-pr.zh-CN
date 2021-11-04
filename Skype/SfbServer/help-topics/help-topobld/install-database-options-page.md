---
title: 安装数据库选项页
ms.reviewer: ''
ms.author: v-mahoffman
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
ms.localizationpriority: medium
ms.assetid: 926c47a0-3957-4892-b61a-7a4b569552c3
description: 配置用于将数据库和日志文件放置到数据库和日志文件的高级SQL Server。 可用的选项有：
ms.openlocfilehash: 3bf2eaacd374234795806d3a3ff21ad1d38dc646
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60777382"
---
# <a name="install-database-options-page"></a>安装数据库选项页

配置用于将数据库和日志文件放置到数据库和日志文件的高级SQL Server。 可用的选项有：

> [!IMPORTANT]
> 选择最符合你与数据和策略相关的要求和策略的选项，日志文件你的SQL Server位置。

 **自动确定数据库文件位置**：默认选项使用一种算法来确定数据库SQL Server并分发数据库和日志文件以实现最佳性能。

 **Use SQL Server instance defaults**： Select this option to place database file and log files based on the instance settings at SQL Server. 这些选项通常由数据库管理员管理和配置。

 目标 SQL Server 上的这些路径：选择此选项，通过键入要放置数据库和日志文件的驱动器和文件夹的完整路径，为 SQL Server 数据库和日志文件定义你自己的路径。

> [!IMPORTANT]
> 输入的路径可能会根据安装中的性能优化算法进行修改。有关详细信息，请参阅[Database Installation Using Lync Server Management Shell](/previous-versions/office/lync-server-2013/lync-server-2013-database-installation-using-lync-server-management-shell)。

 **确定**：单击“确定”按钮以应用更改。

 **取消**：单击“取消”以放弃所有更改并返回到“安装数据库”屏幕。

 **帮助**：单击“帮助”按钮以访问此帮助页面。

## <a name="see-also"></a>另请参阅

[SQL Server 数据和日志文件放置](/previous-versions/office/lync-server-2013/lync-server-2013-sql-server-data-and-log-file-placement)