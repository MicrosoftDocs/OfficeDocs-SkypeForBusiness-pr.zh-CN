---
title: 请求、安装或分配证书
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.dep.DeployMainCerts
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 332ec40f-78be-440a-8c1d-ada6114897db
ROBOTS: NOINDEX, NOFOLLOW
description: 单击“运行”后，“步骤 3：请求、安装或分配证书”会启动证书向导。 通过向导配置的证书基于 Skype for Business 服务器拓扑的定义，该拓扑由拓扑生成器配置和发布到中央管理存储。 要成功运行组织中联机证书颁发机构 (CA) 的证书向导，必须以计算机本地 Administrators 组成员的用户身份登录计算机。 您还必须是计算机和 CA 所在的域中经过身份验证的域用户。 证书向导提供了指定用于访问组织的 CA 的备用凭据的功能。
ms.openlocfilehash: a95ebcde6e66c5665a6089c2ce3714eb65ef8abe
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2020
ms.locfileid: "41691867"
---
# <a name="request-install-or-assign-certificates"></a><span data-ttu-id="e75a9-107">请求、安装或分配证书</span><span class="sxs-lookup"><span data-stu-id="e75a9-107">Request, Install, or Assign Certificates</span></span>
 
 <span data-ttu-id="e75a9-108">单击“**运行**”后，“**步骤 3：请求、安装或分配证书**”会启动证书向导。</span><span class="sxs-lookup"><span data-stu-id="e75a9-108">**Step 3: Request, Install or Assign Certificates** starts the Certificate Wizard when you click **Run**.</span></span> <span data-ttu-id="e75a9-109">通过向导配置的证书基于 Skype for Business 服务器拓扑的定义，该拓扑由拓扑生成器配置和发布到中央管理存储。</span><span class="sxs-lookup"><span data-stu-id="e75a9-109">The certificates that are configured through the wizard are based on the definition of the Skype for Business Server topology that is configured and published by Topology Builder to the Central Management store.</span></span> <span data-ttu-id="e75a9-110">要成功运行组织中联机证书颁发机构 (CA) 的证书向导，必须以计算机本地 Administrators 组成员的用户身份登录计算机。</span><span class="sxs-lookup"><span data-stu-id="e75a9-110">To successfully run the Certificate Wizard for an online certification authority (CA) in your organization, you must be logged on to the computer as a user who is a member of the computer local administrators group.</span></span> <span data-ttu-id="e75a9-111">您还必须是计算机和 CA 所在的域中经过身份验证的域用户。</span><span class="sxs-lookup"><span data-stu-id="e75a9-111">You must also be an authenticated Domain User in the domain where the computer and the CA exist.</span></span> <span data-ttu-id="e75a9-112">证书向导提供了指定用于访问组织的 CA 的备用凭据的功能。</span><span class="sxs-lookup"><span data-stu-id="e75a9-112">The certificate wizard does provide the ability to specify alternate credentials for access your organization's CA.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e75a9-p103">您还可以使用证书向导请求和处理发送到公共 CA 或其他脱机公钥基础结构 (PKI) 的脱机证书请求。要生成脱机请求，除登录计算机所需的组成员身份外，没有其他特定的要求。要处理公共 CA 响应并将证书分配给计算机和角色，必须以本地 Administrators 组成员或等效身份登录。</span><span class="sxs-lookup"><span data-stu-id="e75a9-p103">You can also use the Certificate Wizard to request and process offline certificate requests that are sent to a public CA or other offline public key infrastructure (PKI). There are no specific group memberships, other than those needed to log on to the computer, to generate an offline request. To process the public CA response and to assign the certificate to the computer and role, you must be logged on as a member of the local Administrators group or equivalent.</span></span> 
  

