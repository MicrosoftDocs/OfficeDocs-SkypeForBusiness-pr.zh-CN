---
title: 准备 Active Directory
ms.reviewer: ''
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
description: 若要开始业务服务器 2015 Skype 的安装，必须准备 Active Directory 域服务架构、 林和域将承载服务器和用户。 Skype 的业务 Server 部署向导将指导您完成准备 Active Directory，开始与架构然后再转换林准备所需的步骤。 确认后 Active Directory 复制已成功，然后准备每个将承载任何用户或服务器的域。
ms.openlocfilehash: ba7cbe0b0cf571cc06637cba4e3047016e68f781
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30885053"
---
# <a name="prepare-active-directory"></a><span data-ttu-id="d978d-105">准备 Active Directory</span><span class="sxs-lookup"><span data-stu-id="d978d-105">Prepare Active Directory</span></span>

<span data-ttu-id="d978d-106">若要开始业务服务器 2015 Skype 的安装，必须准备 Active Directory 域服务架构、 林和域将承载服务器和用户。</span><span class="sxs-lookup"><span data-stu-id="d978d-106">To begin the installation of Skype for Business Server 2015, you must prepare the Active Directory Domain Services schema, forest, and domains that will host servers and users.</span></span> <span data-ttu-id="d978d-107">Skype 的业务 Server 部署向导将指导您完成准备 Active Directory，开始与架构然后再转换林准备所需的步骤。</span><span class="sxs-lookup"><span data-stu-id="d978d-107">The Skype for Business Server Deployment Wizard will guide you through the steps required to prepare Active Directory, beginning with the schema and then into the forest preparation.</span></span> <span data-ttu-id="d978d-108">确认后 Active Directory 复制已成功，然后准备每个将承载任何用户或服务器的域。</span><span class="sxs-lookup"><span data-stu-id="d978d-108">After confirming that Active Directory replication is successful, you then prepare each domain that will host users or servers.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d978d-p103">要成功准备架构，必须以 Enterprise Admins 组和 Schema Admins 组成员身份登录。要准备林，必须以 Enterprise Admins 组成员身份或以林根中的管理员身份登录。对于域准备，必须以 Domain Admins 组成员身份登录。</span><span class="sxs-lookup"><span data-stu-id="d978d-p103">To successfully prepare the schema, you must be logged in as a member of the Enterprise Admins group and the Schema Admins group. To prepare the forest, you must be logged in as a member of the Enterprise Admins group or logged in as the administrator in the forest root. For domain preparation, you must be logged in as a member of the Domain Admins group.</span></span>

<span data-ttu-id="d978d-p104">有关支持的 Active Directory 拓扑的详细信息，请参阅可支持性文档中的 [Active Directory Support](https://technet.microsoft.com/library/28ed9ac4-586d-4803-ad45-99c4fa793f54.aspx)。有关 Active Directory 准备的详细信息，请参阅部署文档中的 [Overview of Active Directory Domain Services Preparation](https://technet.microsoft.com/library/cdd2a652-6a0d-4728-9950-3fcaa7a80066.aspx)。</span><span class="sxs-lookup"><span data-stu-id="d978d-p104">For details about supported Active Directory topologies, see [Active Directory Support](https://technet.microsoft.com/library/28ed9ac4-586d-4803-ad45-99c4fa793f54.aspx) in the Supportability documentation. For details about the Active Directory preparation, see [Overview of Active Directory Domain Services Preparation](https://technet.microsoft.com/library/cdd2a652-6a0d-4728-9950-3fcaa7a80066.aspx) in the Deployment documentation.</span></span>


