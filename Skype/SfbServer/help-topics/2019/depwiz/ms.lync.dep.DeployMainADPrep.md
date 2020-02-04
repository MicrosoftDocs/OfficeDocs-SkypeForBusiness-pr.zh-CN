---
title: 准备 Active Directory
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.dep.DeployMainADPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a8c96311-9e1c-4d39-9870-681fd4e272ff
ROBOTS: NOINDEX, NOFOLLOW
description: 若要开始安装 Skype for Business 服务器，必须准备要托管服务器和用户的 Active Directory 域服务架构、林和域。 Skype for Business 服务器部署向导将引导你完成准备 Active Directory 所需的步骤，从架构开始，然后再到林准备。 确认 Active Directory 复制成功后，即可准备将托管用户或服务器的每个域。
ms.openlocfilehash: 1cb997223a9f613bac4aeeec45d3a029d4436e18
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2020
ms.locfileid: "41691857"
---
# <a name="prepare-active-directory"></a><span data-ttu-id="7c3ae-105">准备 Active Directory</span><span class="sxs-lookup"><span data-stu-id="7c3ae-105">Prepare Active Directory</span></span>

<span data-ttu-id="7c3ae-106">若要开始安装 Skype for Business 服务器，必须准备要托管服务器和用户的 Active Directory 域服务架构、林和域。</span><span class="sxs-lookup"><span data-stu-id="7c3ae-106">To begin the installation of Skype for Business Server, you must prepare the Active Directory Domain Services schema, forest, and domains that will host servers and users.</span></span> <span data-ttu-id="7c3ae-107">Skype for Business 服务器部署向导将引导你完成准备 Active Directory 所需的步骤，从架构开始，然后再到林准备。</span><span class="sxs-lookup"><span data-stu-id="7c3ae-107">The Skype for Business Server Deployment Wizard will guide you through the steps required to prepare Active Directory, beginning with the schema and then into the forest preparation.</span></span> <span data-ttu-id="7c3ae-108">确认 Active Directory 复制成功后，即可准备将托管用户或服务器的每个域。</span><span class="sxs-lookup"><span data-stu-id="7c3ae-108">After confirming that Active Directory replication is successful, you then prepare each domain that will host users or servers.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7c3ae-p103">要成功准备架构，必须以 Enterprise Admins 组和 Schema Admins 组成员身份登录。要准备林，必须以 Enterprise Admins 组成员身份或以林根中的管理员身份登录。对于域准备，必须以 Domain Admins 组成员身份登录。</span><span class="sxs-lookup"><span data-stu-id="7c3ae-p103">To successfully prepare the schema, you must be logged in as a member of the Enterprise Admins group and the Schema Admins group. To prepare the forest, you must be logged in as a member of the Enterprise Admins group or logged in as the administrator in the forest root. For domain preparation, you must be logged in as a member of the Domain Admins group.</span></span>

<span data-ttu-id="7c3ae-p104">有关支持的 Active Directory 拓扑的详细信息，请参阅可支持性文档中的 [Active Directory Support](https://technet.microsoft.com/library/28ed9ac4-586d-4803-ad45-99c4fa793f54.aspx)。有关 Active Directory 准备的详细信息，请参阅部署文档中的 [Overview of Active Directory Domain Services Preparation](https://technet.microsoft.com/library/cdd2a652-6a0d-4728-9950-3fcaa7a80066.aspx)。</span><span class="sxs-lookup"><span data-stu-id="7c3ae-p104">For details about supported Active Directory topologies, see [Active Directory Support](https://technet.microsoft.com/library/28ed9ac4-586d-4803-ad45-99c4fa793f54.aspx) in the Supportability documentation. For details about the Active Directory preparation, see [Overview of Active Directory Domain Services Preparation](https://technet.microsoft.com/library/cdd2a652-6a0d-4728-9950-3fcaa7a80066.aspx) in the Deployment documentation.</span></span>


