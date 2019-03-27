---
title: 安装本地配置存储调用（配置）
ms.reviewer: ''
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
description: 若要开始将保存中央管理存储的本地只读副本的数据库的安装，您选择之间检索发布使用拓扑生成器从已安装并配置管理中心的定义的配置管理存储或从其他媒体读取定义的配置。 对于位于组织的内部网络的计算机，选择检索配置自动从中央管理存储。
ms.openlocfilehash: d8577e6eb18d57669657afb93ed07da37ffa31cd
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30894647"
---
# <a name="install-local-configuration-store-invoke-configure"></a><span data-ttu-id="4fe6a-104">安装本地配置存储调用（配置）</span><span class="sxs-lookup"><span data-stu-id="4fe6a-104">Install Local Configuration Store Invoke (Configure)</span></span>
 
<span data-ttu-id="4fe6a-105">若要开始将保存中央管理存储的本地只读副本的数据库的安装，您选择之间检索发布使用拓扑生成器从已安装并配置管理中心的定义的配置管理存储或从其他媒体读取定义的配置。</span><span class="sxs-lookup"><span data-stu-id="4fe6a-105">To begin the installation of the database that will hold the local read-only copy of the Central Management store, you select between retrieving the defined configuration published by using Topology Builder from the already installed and configured Central Management store, or reading the defined configuration from other media.</span></span> <span data-ttu-id="4fe6a-106">对于位于组织的内部网络的计算机，选择**检索从中央管理存储的自动配置**。</span><span class="sxs-lookup"><span data-stu-id="4fe6a-106">For a machine that is on your organization's internal network, select **Retrieve configuration automatically from the Central Management Store**.</span></span>
  
<span data-ttu-id="4fe6a-107">如果您在边缘服务器上安装的中央管理存储副本，您选择从便携式介质，如 USB 闪存驱动器、 USB 硬盘驱动器、 CD-ROM 或其他介质读取导出的配置文档的副本。</span><span class="sxs-lookup"><span data-stu-id="4fe6a-107">If you are installing a replica of the Central Management store on an Edge Server, you select to read the exported copy of the configuration document from portable media, such as a USB flash drive, USB hard disk drive, CD-ROM, or other media.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="4fe6a-108">如果边缘服务器上安装本地配置存储区的配置信息必须是从中央管理已导出的格式将存储通过运行 Windows PowerShell cmdlet:`Export-CsConfiguration -FileName <ConfigurationFilePath.zip>`</span><span class="sxs-lookup"><span data-stu-id="4fe6a-108">If you are installing the Local Configuration store on an Edge Server, the configuration information must be in a format that was exported from the Central Management store by running the Windows PowerShell cmdlet:  `Export-CsConfiguration -FileName <ConfigurationFilePath.zip>`</span></span>
  
<span data-ttu-id="4fe6a-109">选择相应选项后，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="4fe6a-109">After you have selected the appropriate option, click **Next**.</span></span>
  

