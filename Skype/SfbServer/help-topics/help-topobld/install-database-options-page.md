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
description: 配置用于将数据库和日志文件放置到数据库和日志文件的高级SQL Server。 可用的选项有：
ms.openlocfilehash: f9c2553fb0a4fa8f538a70a2ce496eaf054a0dc4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806912"
---
# <a name="install-database-options-page"></a>安装数据库选项页

配置用于将数据库和日志文件放置到数据库和日志文件的高级SQL Server。 可用的选项有：

> [!IMPORTANT]
> 选择最符合你有关数据的要求和策略的选项，日志文件和SQL Server位置。

 **自动确定数据库文件位置**：默认选项使用一种算法来确定数据库上的可用空间SQL Server并分发数据库和日志文件以实现最佳性能。

 **使用SQL Server** 默认值：选择此选项可基于实例设置将数据库文件和日志文件放在SQL Server。 这些选项通常由数据库管理员管理和配置。

 目标 SQL Server 上的这些路径：选择此选项，通过键入要放置数据库和日志文件的驱动器和文件夹的完整路径来定义您自己的 SQL Server 数据库和日志文件路径。

> [!IMPORTANT]
> 输入的路径可能会根据安装中的性能优化算法进行修改。 有关详细信息，请参阅[Database Installation Using Lync Server Management Shell](https://technet.microsoft.com/library/c90a6449-4dd5-4b18-b21c-ea2c2a64dc3c.aspx)。

 **确定**：单击“确定”按钮以应用更改。

 **取消**：单击“取消”以放弃所有更改并返回到“安装数据库”屏幕。

 **帮助**：单击“帮助”按钮以访问此帮助页面。

## <a name="see-also"></a>另请参阅

[SQL Server 数据和日志文件放置](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx)
