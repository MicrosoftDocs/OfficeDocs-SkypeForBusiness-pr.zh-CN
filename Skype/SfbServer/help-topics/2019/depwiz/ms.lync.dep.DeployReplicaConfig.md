---
title: 安装本地配置存储调用（配置）
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployReplicaConfig
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 92dccbca-7a5b-4064-9f2e-964b8e62433c
ROBOTS: NOINDEX, NOFOLLOW
description: 若要开始安装保存中央管理存储的本地只读副本的数据库，您可以选择从已安装和已配置的中心中使用拓扑生成器检索已发布的配置管理存储或从其他媒体中读取已定义的配置。 对于组织内部网络上的计算机，请选择 "从中央管理存储自动检索配置"。
ms.openlocfilehash: b4cc16b26e40b0215a72917c5cab47de8bce5e1b
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41794721"
---
# <a name="install-local-configuration-store-invoke-configure"></a><span data-ttu-id="56de0-104">安装本地配置存储调用（配置）</span><span class="sxs-lookup"><span data-stu-id="56de0-104">Install Local Configuration Store Invoke (Configure)</span></span>
 
<span data-ttu-id="56de0-105">若要开始安装保存中央管理存储的本地只读副本的数据库，您可以选择从已安装和已配置的中心中使用拓扑生成器检索已发布的配置管理存储或从其他媒体中读取已定义的配置。</span><span class="sxs-lookup"><span data-stu-id="56de0-105">To begin the installation of the database that will hold the local read-only copy of the Central Management store, you select between retrieving the defined configuration published by using Topology Builder from the already installed and configured Central Management store, or reading the defined configuration from other media.</span></span> <span data-ttu-id="56de0-106">对于组织内部网络上的计算机，请选择 **"从中央管理存储自动检索配置"**。</span><span class="sxs-lookup"><span data-stu-id="56de0-106">For a machine that is on your organization's internal network, select **Retrieve configuration automatically from the Central Management Store**.</span></span>
  
<span data-ttu-id="56de0-107">如果要在 Edge 服务器上安装中央管理存储的副本，请选择从便携式媒体（如 USB 闪存驱动器、USB 硬盘驱动器、cd-rom 或其他媒体）读取配置文档的导出副本。</span><span class="sxs-lookup"><span data-stu-id="56de0-107">If you are installing a replica of the Central Management store on an Edge Server, you select to read the exported copy of the configuration document from portable media, such as a USB flash drive, USB hard disk drive, CD-ROM, or other media.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="56de0-108">如果要在边缘服务器上安装本地配置存储，则配置信息必须采用从中央管理存储导出的格式，方法是运行 Windows PowerShell cmdlet：`Export-CsConfiguration -FileName <ConfigurationFilePath.zip>`</span><span class="sxs-lookup"><span data-stu-id="56de0-108">If you are installing the Local Configuration store on an Edge Server, the configuration information must be in a format that was exported from the Central Management store by running the Windows PowerShell cmdlet:  `Export-CsConfiguration -FileName <ConfigurationFilePath.zip>`</span></span>
  
<span data-ttu-id="56de0-109">选择相应的选项后，单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="56de0-109">After you have selected the appropriate option, click **Next**.</span></span>
  

