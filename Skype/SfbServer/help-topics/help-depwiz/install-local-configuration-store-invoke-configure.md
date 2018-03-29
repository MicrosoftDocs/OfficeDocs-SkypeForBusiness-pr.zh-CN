---
title: 安装本地配置存储调用 （配置）
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/8/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployReplicaConfig
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 92dccbca-7a5b-4064-9f2e-964b8e62433c
description: 若要开始安装的数据库将包含中央管理存储的本地只读副本，之间进行选择检索使用拓扑生成器从已安装和配置中央发布定义的配置管理存储库，或从其他媒体读取定义的配置。 对于您的组织的内部网络上的计算机，选择检索配置自动从中央管理存储。
ms.openlocfilehash: 74269ee40116b91097c77702942f42de9f7d882a
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="install-local-configuration-store-invoke-configure"></a><span data-ttu-id="7f805-104">安装本地配置存储调用 （配置）</span><span class="sxs-lookup"><span data-stu-id="7f805-104">Install Local Configuration Store Invoke (Configure)</span></span>
 
<span data-ttu-id="7f805-105">若要开始安装的数据库将包含中央管理存储的本地只读副本，之间进行选择检索使用拓扑生成器从已安装和配置中央发布定义的配置管理存储库，或从其他媒体读取定义的配置。</span><span class="sxs-lookup"><span data-stu-id="7f805-105">To begin the installation of the database that will hold the local read-only copy of the Central Management store, you select between retrieving the defined configuration published by using Topology Builder from the already installed and configured Central Management store, or reading the defined configuration from other media.</span></span> <span data-ttu-id="7f805-106">您组织的内部网络上的计算机，请选择**检索从中央管理存储中自动配置**。</span><span class="sxs-lookup"><span data-stu-id="7f805-106">For a machine that is on your organization's internal network, select **Retrieve configuration automatically from the Central Management Store**.</span></span>
  
<span data-ttu-id="7f805-107">如果您在边缘服务器上安装中央管理存储的副本，则选择从便携式媒体，如 USB 闪存驱动器、 USB 硬盘驱动器、 CD-ROM 或其他介质读取导出的副本的配置文档。</span><span class="sxs-lookup"><span data-stu-id="7f805-107">If you are installing a replica of the Central Management store on an Edge Server, you select to read the exported copy of the configuration document from portable media, such as a USB flash drive, USB hard disk drive, CD-ROM, or other media.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="7f805-108">如果要在边缘服务器上安装的本地配置存储，配置信息必须可从集中管理所导出的格式存储通过运行 Windows PowerShell cmdlet:`Export-CsConfiguration -FileName <ConfigurationFilePath.zip>`</span><span class="sxs-lookup"><span data-stu-id="7f805-108">If you are installing the Local Configuration store on an Edge Server, the configuration information must be in a format that was exported from the Central Management store by running the Windows PowerShell cmdlet:  `Export-CsConfiguration -FileName <ConfigurationFilePath.zip>`</span></span>
  
<span data-ttu-id="7f805-109">选择相应的选项后，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="7f805-109">After you have selected the appropriate option, click **Next**.</span></span>
  

