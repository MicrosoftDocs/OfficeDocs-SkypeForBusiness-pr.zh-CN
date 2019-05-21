---
title: 安装本地配置存储调用（配置）
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployReplicaConfig
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 92dccbca-7a5b-4064-9f2e-964b8e62433c
description: 若要开始安装保存中央管理存储的本地只读副本的数据库, 您可以选择从已安装和已配置的中心中使用拓扑生成器检索已发布的配置管理存储或从其他媒体中读取已定义的配置。 对于组织内部网络上的计算机, 请选择 "从中央管理存储自动检索配置"。
ms.openlocfilehash: a9f72ca18c1e8848c52545ecc254dd2b142b8137
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34302946"
---
# <a name="install-local-configuration-store-invoke-configure"></a>安装本地配置存储调用（配置）
 
若要开始安装保存中央管理存储的本地只读副本的数据库, 您可以选择从已安装和已配置的中心中使用拓扑生成器检索已发布的配置管理存储或从其他媒体中读取已定义的配置。 对于组织内部网络上的计算机, 请选择 **"从中央管理存储自动检索配置"**。
  
如果要在 Edge 服务器上安装中央管理存储的副本, 请选择从便携式媒体 (如 USB 闪存驱动器、USB 硬盘驱动器、cd-rom 或其他媒体) 读取配置文档的导出副本。 
  
> [!IMPORTANT]
> 如果要在边缘服务器上安装本地配置存储, 则配置信息必须采用从中央管理存储导出的格式, 方法是运行 Windows PowerShell cmdlet:`Export-CsConfiguration -FileName <ConfigurationFilePath.zip>`
  
选择相应的选项后, 单击 "**下一步**"。
  

