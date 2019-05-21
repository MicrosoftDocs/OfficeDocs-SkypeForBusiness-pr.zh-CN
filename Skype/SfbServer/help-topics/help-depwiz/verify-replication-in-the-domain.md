---
title: 验证域中的复制
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainVerifyDomainPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4846b787-d55e-4364-bdcd-2dee33f0251c
description: '若要验证在步骤 1: 准备架构中完成的域准备的复制, 必须从 Skype for Business Server Management Shell Lync Server Management Shell 运行 cmdlet。 若要运行 Windows PowerShell cmdlet, 请登录到属于你已准备的域成员的计算机, 以及作为域管理员组的成员。 请执行下列操作：'
ms.openlocfilehash: 7d5d9409554654b9c290dfd2df4e20f61c75ae20
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34289496"
---
# <a name="verify-replication-in-the-domain"></a><span data-ttu-id="054a8-105">验证域中的复制</span><span class="sxs-lookup"><span data-stu-id="054a8-105">Verify Replication in the Domain</span></span>
 
<span data-ttu-id="054a8-106">若要验证在**步骤 1: 准备架构**中完成的域准备的复制, 必须从 Skype For Business Server Management Shell Lync Server management shell 运行 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="054a8-106">To verify replication of the domain preparation accomplished in **Step 1: Prepare Schema**, it is necessary to run a cmdlet from the Skype for Business Server Management Shell Lync Server Management Shell.</span></span> <span data-ttu-id="054a8-107">若要运行 Windows PowerShell cmdlet, 请登录到属于你已准备的域成员的计算机, 以及作为域管理员组的成员。</span><span class="sxs-lookup"><span data-stu-id="054a8-107">To run the Windows PowerShell cmdlet, log on to a computer that is a member of the domain that you have prepared, and as a member of the Domain Admins group.</span></span> <span data-ttu-id="054a8-108">请执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="054a8-108">Do the following:</span></span>
  
1. <span data-ttu-id="054a8-109">启动 Skype for Business Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\* 和“Skype for Business 2015”\*\*\*\*，然后单击“Skype for Business Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="054a8-109">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="054a8-110">在 Windows PowerShell 中, 键入以下内容:</span><span class="sxs-lookup"><span data-stu-id="054a8-110">In Windows PowerShell, type the following:</span></span>
    
   ```
   Get-CsAdDomain [-Domain <Fqdn>] [-DomainController <Fqdn>] [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>]
   ```

    <span data-ttu-id="054a8-111">例如：</span><span class="sxs-lookup"><span data-stu-id="054a8-111">For example:</span></span>
    
   ```
   Get-CsAdDomain -Domain domain1.contoso.net -GlobalSettingsDomainController dc01.domain1.contoso.com
   ```

    > [!NOTE]
    > <span data-ttu-id="054a8-112">参数 GlobalSettingsDomainController 用于指示存储全局设置的位置。</span><span class="sxs-lookup"><span data-stu-id="054a8-112">The parameter GlobalSettingsDomainController enables you to indicate where global settings are stored.</span></span> <span data-ttu-id="054a8-113">如果你的设置存储在系统容器中 (这与未将全局设置迁移到配置容器的升级部署的典型设置), 请在 Active Directory 域服务林的根中定义域控制器。</span><span class="sxs-lookup"><span data-stu-id="054a8-113">If your settings are stored in the System container (which is typical with upgrade deployments that have not had the global setting migrated to the Configuration container), you define a domain controller in the root of your Active Directory Domain Services forest.</span></span> <span data-ttu-id="054a8-114">如果全局设置存储在“配置”容器中（在新部署或设置已迁移到“配置”容器的升级部署中时通常是这种情况），则定义林中的任何域控制器。</span><span class="sxs-lookup"><span data-stu-id="054a8-114">If the global settings are in the Configuration container (which is typical with new deployments or upgrade deployments where the settings have been migrated to the Configuration container), you define any domain controller in the forest.</span></span> <span data-ttu-id="054a8-115">如果未指定此参数，则 cmdlet 会假定设置存储在“配置”容器中，并引用 Active Directory 中的任何域控制器。</span><span class="sxs-lookup"><span data-stu-id="054a8-115">If you do not specify this parameter, the cmdlet assumes that the settings are stored in the Configuration container and refers to any domain controller in Active Directory.</span></span> 
  
    <span data-ttu-id="054a8-116">如果不指定 Domain 参数，则将该值设置为本地域。</span><span class="sxs-lookup"><span data-stu-id="054a8-116">If you do not specify the Domain parameter, the value is set to the local domain.</span></span> <span data-ttu-id="054a8-117">如果域准备已成功，则此 cmdlet 将返回 **LC_DOMAIN_SETTINGS_STATE_READY** 的值。</span><span class="sxs-lookup"><span data-stu-id="054a8-117">This cmdlet returns a value of **LC_DOMAIN_SETTINGS_STATE_READY** if domain preparation was successful.</span></span>
    

