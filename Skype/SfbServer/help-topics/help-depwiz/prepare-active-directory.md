---
title: 准备 Active Directory
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/26/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainADPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a8c96311-9e1c-4d39-9870-681fd4e272ff
description: 开始业务服务器 2015 Skype 的安装，您必须准备 Active Directory 域服务架构、 林和域将承载的服务器和用户。 Skype 业务服务器部署向导将指导您完成准备 Active Directory，开始与架构，然后到林准备过程所需的步骤。 确认后 Active Directory 复制成功，然后准备将承载用户或服务器的每个域。
ms.openlocfilehash: 29000132b65350d6b1e723934333209fb3c55b42
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="prepare-active-directory"></a><span data-ttu-id="99c7b-105">准备 Active Directory</span><span class="sxs-lookup"><span data-stu-id="99c7b-105">Prepare Active Directory</span></span>
 
<span data-ttu-id="99c7b-106">开始业务服务器 2015 Skype 的安装，您必须准备 Active Directory 域服务架构、 林和域将承载的服务器和用户。</span><span class="sxs-lookup"><span data-stu-id="99c7b-106">To begin the installation of Skype for Business Server 2015, you must prepare the Active Directory Domain Services schema, forest, and domains that will host servers and users.</span></span> <span data-ttu-id="99c7b-107">Skype 业务服务器部署向导将指导您完成准备 Active Directory，开始与架构，然后到林准备过程所需的步骤。</span><span class="sxs-lookup"><span data-stu-id="99c7b-107">The Skype for Business Server Deployment Wizard will guide you through the steps required to prepare Active Directory, beginning with the schema and then into the forest preparation.</span></span> <span data-ttu-id="99c7b-108">确认后 Active Directory 复制成功，然后准备将承载用户或服务器的每个域。</span><span class="sxs-lookup"><span data-stu-id="99c7b-108">After confirming that Active Directory replication is successful, you then prepare each domain that will host users or servers.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="99c7b-p103">要成功准备架构，必须以 Enterprise Admins 组和 Schema Admins 组成员身份登录。要准备林，必须以 Enterprise Admins 组成员身份或以林根中的管理员身份登录。对于域准备，必须以 Domain Admins 组成员身份登录。</span><span class="sxs-lookup"><span data-stu-id="99c7b-p103">To successfully prepare the schema, you must be logged in as a member of the Enterprise Admins group and the Schema Admins group. To prepare the forest, you must be logged in as a member of the Enterprise Admins group or logged in as the administrator in the forest root. For domain preparation, you must be logged in as a member of the Domain Admins group.</span></span> 
  
<span data-ttu-id="99c7b-112">有关受支持的 Active Directory 拓扑的详细信息，请参阅支持文档中的[活动目录支持](http://technet.microsoft.com/library/28ed9ac4-586d-4803-ad45-99c4fa793f54.aspx)。</span><span class="sxs-lookup"><span data-stu-id="99c7b-112">For details about supported Active Directory topologies, see [Active Directory Support](http://technet.microsoft.com/library/28ed9ac4-586d-4803-ad45-99c4fa793f54.aspx) in the Supportability documentation.</span></span> <span data-ttu-id="99c7b-113">Active Directory 准备的详细信息，请参阅部署文档中[概述的活动目录域服务准备工作](http://technet.microsoft.com/library/cdd2a652-6a0d-4728-9950-3fcaa7a80066.aspx)。</span><span class="sxs-lookup"><span data-stu-id="99c7b-113">For details about the Active Directory preparation, see [Overview of Active Directory Domain Services Preparation](http://technet.microsoft.com/library/cdd2a652-6a0d-4728-9950-3fcaa7a80066.aspx) in the Deployment documentation.</span></span>
  

