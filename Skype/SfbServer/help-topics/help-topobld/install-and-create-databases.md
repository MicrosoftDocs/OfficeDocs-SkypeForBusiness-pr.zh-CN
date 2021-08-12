---
title: 安装和创建数据库
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
- ms.lync.tb.InstallDatabaseCreateDatabasePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 515754ad-1344-42dc-8219-ee973de2e4c4
description: 选择要为部署创建的数据库。 默认情况下，将在已定义网站中定义的 SQL Server 上创建数据库，并基于要放置数据库的 SQL Server自动部署和配置数据库文件。
ms.openlocfilehash: 1a26353ed44529cd19f94b70fdf25f72fbd8f8d4bb81aa0da41c523d3d35a500
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54281055"
---
# <a name="install-and-create-databases"></a>安装和创建数据库

选择要为部署创建的数据库。 默认情况下，将在已定义网站中定义的 SQL Server 上创建数据库，并基于要放置数据库的 SQL Server自动部署和配置数据库文件。

 **选择要创建的数据库**：选中要部署和配置的任何数据库的复选框。 选中要部署的任何或所有数据库的复选框。

> [!CAUTION]
> 如果必须SQL Server任何) 和防火墙端口以适应要部署数据库的实例，则必须为实例 (配置该端口。 有关详细信息，请参阅[Configure SQL Server for Lync Server 2013 Preview](/previous-versions/office/lync-server-2013/lync-server-2013-configure-sql-server-for-lync-server)

 **高级**：单击SQL Server然后单击"高级"按钮以选择数据库中数据库文件位置SQL Server。 有关高级数据库文件放置的详细信息，请参阅 Database [Installation Using Lync Server Management Shell](/previous-versions/office/lync-server-2013/lync-server-2013-database-installation-using-lync-server-management-shell)

 **返回**：单击此按钮将返回到上一 (可能并不总是可用，根据你到达此对话框) 。

 **Next**： Clicking this button commits your selection on the current dialog and takes you to the next dialog for configuring additional information

 **取消**：单击此按钮将退出配置并放弃更改。 如果要退出并放弃更改，某些（但不是所有）配置屏幕将提示你。 选择 **"** 是"将关闭当前配置并关闭当前配置，并返回到拓扑生成器。 选择 **否** 将返回到当前配置对话框，并允许你继续配置。

 **帮助**：单击 **"帮助** "按钮将显示与当前配置对话框关联的帮助信息。