---
title: 安装镜像数据库选项页面
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.InstallMirrorDatabaseOptionPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7500896a-14ea-4b11-aaee-be3d81314536
description: 可通过定义以下内容来配置镜像数据库设置：
ms.openlocfilehash: dde906a5b4d9544cb357e2eed20cb7769f232be8
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41819794"
---
# <a name="install-mirror-database-option-page"></a>安装镜像数据库选项页面
 
可通过定义以下内容来配置**镜像数据库设置**：
  
- 键入**文件共享的路径**以定义要镜像的数据库的备份 SQL Server 文件的位置。
    
    > [!NOTE]
    > 主 SQL Server 实例（命名实例或默认实例）必须对您在此处定义的文件共享具有写权限。 镜像 SQL Server 实例（命名实例或默认实例）必须具有对同一文件共享的读取权限。 
  
  **确定** 接受更改并通过对话框提交更改。
  
  **取消** 放弃更改并关闭对话框。
  
  **帮助** 显示此帮助屏幕。
  
## <a name="see-also"></a>另请参阅

[在 Skype for Business Server 2015 中针对后端服务器高可用性部署 SQL 镜像](../../deploy/deploy-high-availability-and-disaster-recovery/sql-mirroring-for-high-availability.md)
