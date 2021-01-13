---
title: 安装本地配置存储调用（配置）
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployReplicaConfig
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 92dccbca-7a5b-4064-9f2e-964b8e62433c
description: 若要开始安装将保存中央管理存储的本地只读副本的数据库，可选择从已安装和配置的中央管理存储中检索使用拓扑生成器发布的已定义配置，还是从其他媒体读取定义的配置。 对于位于组织内部网络上的计算机，选择"从中央管理存储自动检索配置"。
ms.openlocfilehash: f0e2f54e83831cf6ad626b5d83cf068f40110f07
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827202"
---
# <a name="install-local-configuration-store-invoke-configure"></a><span data-ttu-id="925e8-104">安装本地配置存储调用（配置）</span><span class="sxs-lookup"><span data-stu-id="925e8-104">Install Local Configuration Store Invoke (Configure)</span></span>
 
<span data-ttu-id="925e8-105">若要开始安装将保存中央管理存储的本地只读副本的数据库，可选择从已安装和配置的中央管理存储中检索使用拓扑生成器发布的已定义配置，还是从其他媒体读取定义的配置。</span><span class="sxs-lookup"><span data-stu-id="925e8-105">To begin the installation of the database that will hold the local read-only copy of the Central Management store, you select between retrieving the defined configuration published by using Topology Builder from the already installed and configured Central Management store, or reading the defined configuration from other media.</span></span> <span data-ttu-id="925e8-106">对于位于组织内部网络上的计算机，选择"从中央管理存储 **自动检索配置"。**</span><span class="sxs-lookup"><span data-stu-id="925e8-106">For a machine that is on your organization's internal network, select **Retrieve configuration automatically from the Central Management Store**.</span></span>
  
<span data-ttu-id="925e8-107">如果要在边缘服务器上安装中央管理存储的副本，可以选择从便携式媒体（如 USB 闪存驱动器、USB 硬盘驱动器、CD-ROM 或其他媒体）读取配置文档的导出副本。</span><span class="sxs-lookup"><span data-stu-id="925e8-107">If you are installing a replica of the Central Management store on an Edge Server, you select to read the exported copy of the configuration document from portable media, such as a USB flash drive, USB hard disk drive, CD-ROM, or other media.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="925e8-108">如果要在边缘服务器上安装本地配置存储，则配置信息的格式必须是通过运行 Windows PowerShell cmdlet 从中央管理存储导出的格式：  `Export-CsConfiguration -FileName <ConfigurationFilePath.zip>`</span><span class="sxs-lookup"><span data-stu-id="925e8-108">If you are installing the Local Configuration store on an Edge Server, the configuration information must be in a format that was exported from the Central Management store by running the Windows PowerShell cmdlet:  `Export-CsConfiguration -FileName <ConfigurationFilePath.zip>`</span></span>
  
<span data-ttu-id="925e8-109">选择相应选项后，单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="925e8-109">After you have selected the appropriate option, click **Next**.</span></span>
  

