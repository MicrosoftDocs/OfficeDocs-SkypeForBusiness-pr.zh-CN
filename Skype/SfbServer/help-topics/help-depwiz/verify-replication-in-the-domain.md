---
title: 验证域中的复制
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
- ms.lync.dep.DeployMainVerifyDomainPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4846b787-d55e-4364-bdcd-2dee33f0251c
description: 若要验证复制步骤 1 中完成的域准备：准备架构，需要从 Skype for Business Server 命令行管理程序 Lync Server 命令行管理程序 运行 cmdlet。 要运行 Windows PowerShell cmdlet，请以 Domain Admins 组成员的身份登录到作为已准备的域成员的计算机。 请执行以下操作：
ms.openlocfilehash: d002a0623d6788183a5b09f8e58262fc1c68a823
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49800592"
---
# <a name="verify-replication-in-the-domain"></a><span data-ttu-id="6ed87-105">验证域中的复制</span><span class="sxs-lookup"><span data-stu-id="6ed87-105">Verify Replication in the Domain</span></span>
 
<span data-ttu-id="6ed87-106">若要验证复制步骤 **1** 中完成的域准备：准备架构，需要从 Skype for Business Server 命令行管理程序 Lync Server 命令行管理程序 运行 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="6ed87-106">To verify replication of the domain preparation accomplished in **Step 1: Prepare Schema**, it is necessary to run a cmdlet from the Skype for Business Server Management Shell Lync Server Management Shell.</span></span> <span data-ttu-id="6ed87-107">要运行 Windows PowerShell cmdlet，请以 Domain Admins 组成员的身份登录到作为已准备的域成员的计算机。</span><span class="sxs-lookup"><span data-stu-id="6ed87-107">To run the Windows PowerShell cmdlet, log on to a computer that is a member of the domain that you have prepared, and as a member of the Domain Admins group.</span></span> <span data-ttu-id="6ed87-108">请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="6ed87-108">Do the following:</span></span>
  
1. <span data-ttu-id="6ed87-109">启动 Skype for Business Server命令行管理程序：单击"开始"，**单击"所有** 程序"，再单击 **"Skype for Business 2015"，** 然后单击 **"Skype for Business Server 命令行管理程序"。**</span><span class="sxs-lookup"><span data-stu-id="6ed87-109">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="6ed87-110">在Windows PowerShell中，键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="6ed87-110">In Windows PowerShell, type the following:</span></span>
    
   ```PowerShell
   Get-CsAdDomain [-Domain <Fqdn>] [-DomainController <Fqdn>] [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>]
   ```

    <span data-ttu-id="6ed87-111">例如：</span><span class="sxs-lookup"><span data-stu-id="6ed87-111">For example:</span></span>
    
   ```PowerShell
   Get-CsAdDomain -Domain domain1.contoso.net -GlobalSettingsDomainController dc01.domain1.contoso.com
   ```

    > [!NOTE]
    > <span data-ttu-id="6ed87-112">参数 GlobalSettingsDomainController 用于指示存储全局设置的位置。</span><span class="sxs-lookup"><span data-stu-id="6ed87-112">The parameter GlobalSettingsDomainController enables you to indicate where global settings are stored.</span></span> <span data-ttu-id="6ed87-113">如果您的设置存储在系统容器 (这一点在尚未将全局设置迁移到配置容器) 的升级部署中是典型的，则定义 Active Directory 域服务林的根目录中的域控制器。</span><span class="sxs-lookup"><span data-stu-id="6ed87-113">If your settings are stored in the System container (which is typical with upgrade deployments that have not had the global setting migrated to the Configuration container), you define a domain controller in the root of your Active Directory Domain Services forest.</span></span> <span data-ttu-id="6ed87-114">如果全局设置存储在“配置”容器中（通常在新部署或设置已迁移到“配置”容器的升级部署中是这种情况），则定义林中的任何域控制器。</span><span class="sxs-lookup"><span data-stu-id="6ed87-114">If the global settings are in the Configuration container (which is typical with new deployments or upgrade deployments where the settings have been migrated to the Configuration container), you define any domain controller in the forest.</span></span> <span data-ttu-id="6ed87-115">如果不指定此参数，此 cmdlet 将假定设置存储在"配置"容器中，并引用 Active Directory 中的任意域控制器。</span><span class="sxs-lookup"><span data-stu-id="6ed87-115">If you do not specify this parameter, the cmdlet assumes that the settings are stored in the Configuration container and refers to any domain controller in Active Directory.</span></span> 
  
    <span data-ttu-id="6ed87-116">如果不指定 Domain 参数，则将该值设置为本地域。</span><span class="sxs-lookup"><span data-stu-id="6ed87-116">If you do not specify the Domain parameter, the value is set to the local domain.</span></span> <span data-ttu-id="6ed87-117">如果域准备已成功，则此 cmdlet 将返回 **LC_DOMAIN_SETTINGS_STATE_READY** 的值。</span><span class="sxs-lookup"><span data-stu-id="6ed87-117">This cmdlet returns a value of **LC_DOMAIN_SETTINGS_STATE_READY** if domain preparation was successful.</span></span>
    

