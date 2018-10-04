---
title: 验证域中的复制
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainVerifyDomainPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4846b787-d55e-4364-bdcd-2dee33f0251c
ROBOTS: NOINDEX, NOFOLLOW
description: 要验证复制在步骤 1 中完成的域准备： 准备架构，它所需从 Skype 的业务服务器管理命令行管理程序 Lync Server Management Shell 中运行 cmdlet。 若要运行 Windows PowerShell cmdlet，登录到成员已经准备好的域的 Domain Admins 组的成员以及的计算机。 请执行下列操作：
ms.openlocfilehash: f5cf028cfb0957d339a2ac2a40a239f0c145a2c0
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25373511"
---
# <a name="verify-replication-in-the-domain"></a><span data-ttu-id="7535f-105">验证域中的复制</span><span class="sxs-lookup"><span data-stu-id="7535f-105">Verify Replication in the Domain</span></span>
 
<span data-ttu-id="7535f-106">若要验证中完成域准备的复制**步骤 1： 准备架构**，需从 Skype 的业务服务器管理命令行管理程序 Lync Server Management Shell 中运行 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="7535f-106">To verify replication of the domain preparation accomplished in **Step 1: Prepare Schema**, it is necessary to run a cmdlet from the Skype for Business Server Management Shell Lync Server Management Shell.</span></span> <span data-ttu-id="7535f-107">若要运行 Windows PowerShell cmdlet，登录到成员已经准备好的域的 Domain Admins 组的成员以及的计算机。</span><span class="sxs-lookup"><span data-stu-id="7535f-107">To run the Windows PowerShell cmdlet, log on to a computer that is a member of the domain that you have prepared, and as a member of the Domain Admins group.</span></span> <span data-ttu-id="7535f-108">请执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="7535f-108">Do the following:</span></span>
  
1. <span data-ttu-id="7535f-109">为业务 Server 命令行管理程序启动 Skype： 单击**开始**，单击**所有程序**、 都单击**for Business 的 Skype**，，然后都单击**Skype 的业务 Server Management Shell**。</span><span class="sxs-lookup"><span data-stu-id="7535f-109">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="7535f-110">在 Windows PowerShell 中，键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="7535f-110">In Windows PowerShell, type the following:</span></span>
    
   ```
   Get-CsAdDomain [-Domain <Fqdn>] [-DomainController <Fqdn>] [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>]
   ```

    <span data-ttu-id="7535f-111">例如：</span><span class="sxs-lookup"><span data-stu-id="7535f-111">For example:</span></span>
    
   ```
   Get-CsAdDomain -Domain domain1.contoso.net -GlobalSettingsDomainController dc01.domain1.contoso.com
   ```

    > [!NOTE]
    > <span data-ttu-id="7535f-112">参数 GlobalSettingsDomainController 用于指示存储全局设置的位置。</span><span class="sxs-lookup"><span data-stu-id="7535f-112">The parameter GlobalSettingsDomainController enables you to indicate where global settings are stored.</span></span> <span data-ttu-id="7535f-113">如果您的设置存储在系统容器 （这是不过全局设置迁移到配置容器的升级部署典型） 中，您的 Active Directory 域服务林根中定义的域控制器。</span><span class="sxs-lookup"><span data-stu-id="7535f-113">If your settings are stored in the System container (which is typical with upgrade deployments that have not had the global setting migrated to the Configuration container), you define a domain controller in the root of your Active Directory Domain Services forest.</span></span> <span data-ttu-id="7535f-114">如果全局设置存储在“配置”容器中（在新部署或设置已迁移到“配置”容器的升级部署中时通常是这种情况），则定义林中的任何域控制器。</span><span class="sxs-lookup"><span data-stu-id="7535f-114">If the global settings are in the Configuration container (which is typical with new deployments or upgrade deployments where the settings have been migrated to the Configuration container), you define any domain controller in the forest.</span></span> <span data-ttu-id="7535f-115">如果未指定此参数，则 cmdlet 会假定设置存储在“配置”容器中，并引用 Active Directory 中的任何域控制器。</span><span class="sxs-lookup"><span data-stu-id="7535f-115">If you do not specify this parameter, the cmdlet assumes that the settings are stored in the Configuration container and refers to any domain controller in Active Directory.</span></span> 
  
    <span data-ttu-id="7535f-116">如果不指定 Domain 参数，则将该值设置为本地域。</span><span class="sxs-lookup"><span data-stu-id="7535f-116">If you do not specify the Domain parameter, the value is set to the local domain.</span></span> <span data-ttu-id="7535f-117">如果域准备已成功，则此 cmdlet 返回的值为**LC_DOMAIN_SETTINGS_STATE_READY** 。</span><span class="sxs-lookup"><span data-stu-id="7535f-117">This cmdlet returns a value of **LC_DOMAIN_SETTINGS_STATE_READY** if domain preparation was successful.</span></span>
    

