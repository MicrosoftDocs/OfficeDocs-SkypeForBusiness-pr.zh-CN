---
title: 安装本地配置存储调用（配置）
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployReplicaConfig
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 92dccbca-7a5b-4064-9f2e-964b8e62433c
description: 若要开始安装将保存中央管理存储的本地只读副本的数据库，请选择从已安装和配置的中央管理存储中检索使用拓扑生成器发布的已定义配置，还是从其他媒体读取定义的配置。 对于位于组织内部网络上的计算机，选择"从中央管理存储自动检索配置"。
ms.openlocfilehash: a2e0efdc33fdfb6070b445c0a1e7868dab0f0ff2
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/05/2022
ms.locfileid: "62411785"
---
# <a name="install-local-configuration-store-invoke-configure"></a>安装本地配置存储调用（配置）
 
若要开始安装将保存中央管理存储的本地只读副本的数据库，请选择从已安装和配置的中央管理存储中检索使用拓扑生成器发布的已定义配置，还是从其他媒体读取定义的配置。 对于位于组织内部网络上的计算机，选择"从中央管理存储 **自动检索配置"**。
  
如果要在边缘服务器上安装中央管理存储的副本，可以选择从便携式媒体（如 USB 闪存驱动器、USB 硬盘驱动器、CD-ROM 或其他媒体）读取配置文档的导出副本。 
  
> [!IMPORTANT]
> 如果要在边缘服务器上安装本地配置存储，则配置信息的格式必须是通过运行 Windows PowerShell cmdlet 从中央管理存储导出的格式：`Export-CsConfiguration -FileName <ConfigurationFilePath.zip>`
  
选择相应选项后，单击“下一步”。
  

