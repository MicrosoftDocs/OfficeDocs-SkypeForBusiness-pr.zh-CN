---
title: 安装数据库选项页面
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.InstallDatabaseOptionPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 926c47a0-3957-4892-b61a-7a4b569552c3
ROBOTS: NOINDEX, NOFOLLOW
description: 在 SQL Server 上配置数据库和日志文件的位置的高级选项。 可用选项包括：
ms.openlocfilehash: 6725c85ee8ccd755e1846f2e2030fd4cab4c5f22
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2020
ms.locfileid: "41688425"
---
# <a name="install-database-options-page"></a>安装数据库选项页面

在 SQL Server 上配置数据库和日志文件的位置的高级选项。 可用选项包括：

> [!IMPORTANT]
> 选择最适合你的要求和策略的选项，这些选项与你的 SQL Server 计算机上的数据和日志文件的位置有关。

 **自动确定数据库文件位置**：默认选项使用一个算法来确定 SQL Server 上的可用空间，并分发数据库和日志文件以获得最佳性能。

 **使用 Sql server 实例默认值**：选择此选项可根据 SQL Server 上的实例设置放置数据库文件和日志文件。 选项通常由数据库管理员管理和配置。

 **我们在目标 SQL Server 上的这些路径**：选择此选项可通过键入要在其中放置数据库和日志文件的驱动器和文件夹的完整路径来定义你自己的 SQL Server 数据库和日志文件的路径。

> [!IMPORTANT]
> 你输入的路径可能会根据安装中的性能优化算法进行修改。 有关详细信息，请参阅[使用 Lync Server 命令行管理程序进行数据库安装](https://technet.microsoft.com/library/c90a6449-4dd5-4b18-b21c-ea2c2a64dc3c.aspx)。

 **确定**：单击 "确定" 按钮提交所做的更改。

 **取消**：单击 "取消" 放弃任何更改并返回到 "安装数据库" 屏幕。

 **帮助**：单击 "帮助" 按钮以访问此帮助页面。

## <a name="see-also"></a>另请参阅

[SQL Server 数据和日志文件放置](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx)
