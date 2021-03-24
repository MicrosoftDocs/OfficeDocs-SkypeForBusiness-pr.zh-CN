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
description: 若要开始安装 Skype for Business Server 2015，必须准备 Active Directory 域服务架构、林以及将托管服务器和用户的域。 Skype for Business Server 部署向导将指导你完成准备 Active Directory 所需的步骤，从架构开始，然后再准备林。 确认 Active Directory 复制成功后，准备将承载用户或服务器的每个域。
ms.openlocfilehash: b76361e855dc41ee0515939855932ae5f6920662
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51104558"
---
# <a name="prepare-active-directory"></a><span data-ttu-id="16ee7-105">准备 Active Directory</span><span class="sxs-lookup"><span data-stu-id="16ee7-105">Prepare Active Directory</span></span>

<span data-ttu-id="16ee7-106">若要开始安装 Skype for Business Server 2015，必须准备 Active Directory 域服务架构、林以及将托管服务器和用户的域。</span><span class="sxs-lookup"><span data-stu-id="16ee7-106">To begin the installation of Skype for Business Server 2015, you must prepare the Active Directory Domain Services schema, forest, and domains that will host servers and users.</span></span> <span data-ttu-id="16ee7-107">Skype for Business Server 部署向导将指导你完成准备 Active Directory 所需的步骤，从架构开始，然后再准备林。</span><span class="sxs-lookup"><span data-stu-id="16ee7-107">The Skype for Business Server Deployment Wizard will guide you through the steps required to prepare Active Directory, beginning with the schema and then into the forest preparation.</span></span> <span data-ttu-id="16ee7-108">确认 Active Directory 复制成功后，准备将承载用户或服务器的每个域。</span><span class="sxs-lookup"><span data-stu-id="16ee7-108">After confirming that Active Directory replication is successful, you then prepare each domain that will host users or servers.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="16ee7-p103">要成功准备架构，必须以 Enterprise Admins 组和 Schema Admins 组成员身份登录。要准备林，必须以 Enterprise Admins 组成员身份或以林根中的管理员身份登录。对于域准备，必须以 Domain Admins 组成员身份登录。</span><span class="sxs-lookup"><span data-stu-id="16ee7-p103">To successfully prepare the schema, you must be logged in as a member of the Enterprise Admins group and the Schema Admins group. To prepare the forest, you must be logged in as a member of the Enterprise Admins group or logged in as the administrator in the forest root. For domain preparation, you must be logged in as a member of the Domain Admins group.</span></span>

<span data-ttu-id="16ee7-112">有关支持的 Active Directory 拓扑的详细信息，请参阅可支持性文档中的 [Active Directory Support](/previous-versions/office/lync-server-2013/lync-server-2013-active-directory-support)。</span><span class="sxs-lookup"><span data-stu-id="16ee7-112">For details about supported Active Directory topologies, see [Active Directory Support](/previous-versions/office/lync-server-2013/lync-server-2013-active-directory-support) in the Supportability documentation.</span></span> <span data-ttu-id="16ee7-113">有关 Active Directory 准备的详细信息，请参阅部署文档中的 [Overview of Active Directory Domain Services Preparation](/previous-versions/office/lync-server-2013/lync-server-2013-overview-of-active-directory-domain-services-preparation)。</span><span class="sxs-lookup"><span data-stu-id="16ee7-113">For details about the Active Directory preparation, see [Overview of Active Directory Domain Services Preparation](/previous-versions/office/lync-server-2013/lync-server-2013-overview-of-active-directory-domain-services-preparation) in the Deployment documentation.</span></span>