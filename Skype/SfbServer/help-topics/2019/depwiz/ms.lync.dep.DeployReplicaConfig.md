---
title: 安装本地配置存储调用（配置）
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployReplicaConfig
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
ms.localizationpriority: medium
ms.assetid: 92dccbca-7a5b-4064-9f2e-964b8e62433c
ROBOTS: NOINDEX, NOFOLLOW
description: 若要开始安装将保存中央管理存储的本地只读副本的数据库，请选择从已安装和配置的中央管理存储中检索使用拓扑生成器发布的已定义配置，还是从其他媒体读取定义的配置。 对于位于组织内部网络上的计算机，选择"从中央管理存储自动检索配置"。
ms.openlocfilehash: 78c5a1697c77ed1a370739dd173718a74ead148e
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60742798"
---
# <a name="install-local-configuration-store-invoke-configure"></a>安装本地配置存储调用（配置）
 
若要开始安装将保存中央管理存储的本地只读副本的数据库，请选择从已安装和配置的中央管理存储中检索使用拓扑生成器发布的已定义配置，还是从其他媒体读取定义的配置。 对于组织内部网络上的计算机，选择"从中央管理存储 **自动检索配置"。**
  
如果要在边缘服务器上安装中央管理存储的副本，可以选择从便携式媒体（如 USB 闪存驱动器、USB 硬盘驱动器、CD-ROM 或其他媒体）读取配置文档的导出副本。 
  
> [!IMPORTANT]
> 如果要在边缘服务器上安装本地配置存储，则配置信息的格式必须是通过运行 Windows PowerShell cmdlet 从中央管理存储导出的格式：`Export-CsConfiguration -FileName <ConfigurationFilePath.zip>`
  
选择相应选项后，单击“下一步”。
  

