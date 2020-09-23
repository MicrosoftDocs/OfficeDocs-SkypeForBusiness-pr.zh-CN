---
title: 安装镜像数据库选项页
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
- ms.lync.tb.InstallMirrorDatabaseOptionPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7500896a-14ea-4b11-aaee-be3d81314536
description: 通过以下定义配置“镜像数据库设置”：
ms.openlocfilehash: d522cc62f02d9021eaf6267db0b93aa4d42d3a3d
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/23/2020
ms.locfileid: "48215323"
---
# <a name="install-mirror-database-option-page"></a>安装镜像数据库选项页
 
通过以下定义配置“镜像数据库设置”****：
  
- 键入 **文件共享的路径** ，以定义要镜像的数据库的备份 SQL Server 文件的位置。
    
    > [!NOTE]
    > 主 SQL Server 实例 (命名实例或默认实例) 必须具有您在此处定义的文件共享的写入权限。 镜像 SQL Server 实例 (命名实例或默认实例) 必须具有对同一文件共享的读取权限。 
  
  **确定** 接受更改并通过对话框提交更改。
  
  **取消** 放弃更改并关闭对话框。
  
  **帮助** 显示此帮助屏幕。
  
## <a name="see-also"></a>另请参阅

[在 Skype for business Server 2015 中部署 SQL 镜像以实现后端服务器高可用性](../../deploy/deploy-high-availability-and-disaster-recovery/sql-mirroring-for-high-availability.md)
