---
title: 验证域中的复制
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/26/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainVerifyDomainPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4846b787-d55e-4364-bdcd-2dee33f0251c
description: 要验证复制的在第 1 步中完成域准备工作： 准备架构，有必要从 Skype 业务服务器管理外壳 Lync 服务器管理外壳程序运行 cmdlet。 若要运行 Windows PowerShell cmdlet，登录到计算机所属的域已做好了准备，并作为域管理员组的成员。 请执行下列操作：
ms.openlocfilehash: e3dca892ccb4937bcd84148a954270b4bd1362f5
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="verify-replication-in-the-domain"></a><span data-ttu-id="78ac7-105">验证域中的复制</span><span class="sxs-lookup"><span data-stu-id="78ac7-105">Verify Replication in the Domain</span></span>
 
<span data-ttu-id="78ac7-106">要验证复制中完成域准备工作的**第 1 步： 准备架构**，有必要从 Skype 业务服务器管理外壳 Lync 服务器管理外壳程序运行 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="78ac7-106">To verify replication of the domain preparation accomplished in **Step 1: Prepare Schema**, it is necessary to run a cmdlet from the Skype for Business Server Management Shell Lync Server Management Shell.</span></span> <span data-ttu-id="78ac7-107">若要运行 Windows PowerShell cmdlet，登录到计算机所属的域已做好了准备，并作为域管理员组的成员。</span><span class="sxs-lookup"><span data-stu-id="78ac7-107">To run the Windows PowerShell cmdlet, log on to a computer that is a member of the domain that you have prepared, and as a member of the Domain Admins group.</span></span> <span data-ttu-id="78ac7-108">请执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="78ac7-108">Do the following:</span></span>
  
1. <span data-ttu-id="78ac7-109">启动 Skype for Business Server 命令行管理程序：依次单击“**开始**”、“**所有程序**”和“**Skype for Business 2015**”，然后单击“**Skype for Business Server 命令行管理程序**”。</span><span class="sxs-lookup"><span data-stu-id="78ac7-109">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="78ac7-110">在 Windows PowerShell，键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="78ac7-110">In Windows PowerShell, type the following:</span></span>
    
  ```
  Get-CsAdDomain [-Domain <Fqdn>] [-DomainController <Fqdn>] [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>]
  ```

    <span data-ttu-id="78ac7-111">例如：</span><span class="sxs-lookup"><span data-stu-id="78ac7-111">For example:</span></span>
    
  ```
  Get-CsAdDomain -Domain domain1.contoso.net -GlobalSettingsDomainController dc01.domain1.contoso.com
  ```

    > [!NOTE]
    > <span data-ttu-id="78ac7-112">参数 GlobalSettingsDomainController 用于指示存储全局设置的位置。</span><span class="sxs-lookup"><span data-stu-id="78ac7-112">The parameter GlobalSettingsDomainController enables you to indicate where global settings are stored.</span></span> <span data-ttu-id="78ac7-113">如果您的设置存储在系统容器 （此为典型与升级部署尚未迁移到配置容器的全局设置） 中，域控制器定义 Active Directory 域服务林的根目录中。</span><span class="sxs-lookup"><span data-stu-id="78ac7-113">If your settings are stored in the System container (which is typical with upgrade deployments that have not had the global setting migrated to the Configuration container), you define a domain controller in the root of your Active Directory Domain Services forest.</span></span> <span data-ttu-id="78ac7-114">如果全局设置存储在“配置”容器中（在新部署或设置已迁移到“配置”容器的升级部署中时通常是这种情况），则定义林中的任何域控制器。</span><span class="sxs-lookup"><span data-stu-id="78ac7-114">If the global settings are in the Configuration container (which is typical with new deployments or upgrade deployments where the settings have been migrated to the Configuration container), you define any domain controller in the forest.</span></span> <span data-ttu-id="78ac7-115">如果未指定此参数，则 cmdlet 会假定设置存储在“配置”容器中，并引用 Active Directory 中的任何域控制器。</span><span class="sxs-lookup"><span data-stu-id="78ac7-115">If you do not specify this parameter, the cmdlet assumes that the settings are stored in the Configuration container and refers to any domain controller in Active Directory.</span></span> 
  
    <span data-ttu-id="78ac7-116">如果不指定 Domain 参数，则将该值设置为本地域。</span><span class="sxs-lookup"><span data-stu-id="78ac7-116">If you do not specify the Domain parameter, the value is set to the local domain.</span></span> <span data-ttu-id="78ac7-117">此 cmdlet 返回值为**LC_DOMAIN_SETTINGS_STATE_READY** ，如果域准备成功。</span><span class="sxs-lookup"><span data-stu-id="78ac7-117">This cmdlet returns a value of **LC_DOMAIN_SETTINGS_STATE_READY** if domain preparation was successful.</span></span>
    

