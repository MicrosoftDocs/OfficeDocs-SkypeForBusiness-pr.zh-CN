---
title: 安装数据库选项页
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 您可以为 SQL Server 上的数据库和日志文件的放置配置高级选项。 可用的选项有：
ms.openlocfilehash: 4c8c456aa1fd0e9eee150e184b4d1f7934c26b65
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/23/2020
ms.locfileid: "48215303"
---
# <a name="install-database-options-page"></a>安装数据库选项页

您可以为 SQL Server 上的数据库和日志文件的放置配置高级选项。 可用的选项有：

> [!IMPORTANT]
> 选择最适合您的要求和策略的选项，这些要求和策略与 SQL Server 计算机上的数据和日志文件放置相关。

 **自动确定数据库文件位置**：默认选项使用一个算法来确定 SQL Server 上的可用空间，并分发数据库和日志文件以实现最佳性能。

 **使用 Sql server 实例默认值**：选择此选项可根据 SQL Server 上的实例设置放置数据库文件和日志文件。 这些选项通常由数据库管理员管理和配置。

 **我们在目标 SQL Server 上的这些路径**：选择此选项可通过键入要放置数据库和日志文件的驱动器和文件夹的完整路径，从而定义您自己的 SQL server 数据库和日志文件的路径。

> [!IMPORTANT]
> 输入的路径可能会根据安装中的性能优化算法进行修改。 有关详细信息，请参阅[Database Installation Using Lync Server Management Shell](https://technet.microsoft.com/library/c90a6449-4dd5-4b18-b21c-ea2c2a64dc3c.aspx)。

 **确定**：单击“确定”按钮以应用更改。

 **取消**：单击“取消”以放弃所有更改并返回到“安装数据库”屏幕。

 **帮助**：单击“帮助”按钮以访问此帮助页面。

## <a name="see-also"></a>另请参阅

[SQL Server 数据和日志文件放置](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx)
