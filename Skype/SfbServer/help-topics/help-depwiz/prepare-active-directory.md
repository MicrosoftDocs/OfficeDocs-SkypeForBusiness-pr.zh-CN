---
title: 准备 Active Directory
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployMainADPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a8c96311-9e1c-4d39-9870-681fd4e272ff
description: 若要开始安装 Skype for Business Server 2015，必须准备将承载服务器和用户的 Active Directory 域服务架构、林和域。 Skype for Business Server 部署向导将指导你完成准备 Active Directory 所需的步骤，从架构开始，然后再准备林。 确认 Active Directory 复制成功后，准备将承载用户或服务器的每个域。
ms.openlocfilehash: 9a741e56166d3235096a154bc2ef86770409adb9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804832"
---
# <a name="prepare-active-directory"></a><span data-ttu-id="fe639-105">准备 Active Directory</span><span class="sxs-lookup"><span data-stu-id="fe639-105">Prepare Active Directory</span></span>

<span data-ttu-id="fe639-106">若要开始安装 Skype for Business Server 2015，必须准备将承载服务器和用户的 Active Directory 域服务架构、林和域。</span><span class="sxs-lookup"><span data-stu-id="fe639-106">To begin the installation of Skype for Business Server 2015, you must prepare the Active Directory Domain Services schema, forest, and domains that will host servers and users.</span></span> <span data-ttu-id="fe639-107">Skype for Business Server 部署向导将指导你完成准备 Active Directory 所需的步骤，从架构开始，然后再准备林。</span><span class="sxs-lookup"><span data-stu-id="fe639-107">The Skype for Business Server Deployment Wizard will guide you through the steps required to prepare Active Directory, beginning with the schema and then into the forest preparation.</span></span> <span data-ttu-id="fe639-108">确认 Active Directory 复制成功后，准备将承载用户或服务器的每个域。</span><span class="sxs-lookup"><span data-stu-id="fe639-108">After confirming that Active Directory replication is successful, you then prepare each domain that will host users or servers.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fe639-p103">要成功准备架构，必须以 Enterprise Admins 组和 Schema Admins 组成员身份登录。要准备林，必须以 Enterprise Admins 组成员身份或以林根中的管理员身份登录。对于域准备，必须以 Domain Admins 组成员身份登录。</span><span class="sxs-lookup"><span data-stu-id="fe639-p103">To successfully prepare the schema, you must be logged in as a member of the Enterprise Admins group and the Schema Admins group. To prepare the forest, you must be logged in as a member of the Enterprise Admins group or logged in as the administrator in the forest root. For domain preparation, you must be logged in as a member of the Domain Admins group.</span></span>

<span data-ttu-id="fe639-112">有关支持的 Active Directory 拓扑的详细信息，请参阅可支持性文档中的 [Active Directory Support](https://technet.microsoft.com/library/28ed9ac4-586d-4803-ad45-99c4fa793f54.aspx)。</span><span class="sxs-lookup"><span data-stu-id="fe639-112">For details about supported Active Directory topologies, see [Active Directory Support](https://technet.microsoft.com/library/28ed9ac4-586d-4803-ad45-99c4fa793f54.aspx) in the Supportability documentation.</span></span> <span data-ttu-id="fe639-113">有关 Active Directory 准备的详细信息，请参阅部署文档中的 [Overview of Active Directory Domain Services Preparation](https://technet.microsoft.com/library/cdd2a652-6a0d-4728-9950-3fcaa7a80066.aspx)。</span><span class="sxs-lookup"><span data-stu-id="fe639-113">For details about the Active Directory preparation, see [Overview of Active Directory Domain Services Preparation](https://technet.microsoft.com/library/cdd2a652-6a0d-4728-9950-3fcaa7a80066.aspx) in the Deployment documentation.</span></span>


