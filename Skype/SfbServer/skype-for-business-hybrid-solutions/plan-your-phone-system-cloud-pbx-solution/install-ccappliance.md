---
title: Install-CcAppliance
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 385453cd-3a96-4837-8bb4-513aa97a256b
description: Install-CcAppliance cmdlet 用于在主机服务器上安装 Skype for Business 云连接器版本设备，包括 AD、中央管理存储、中介服务器和边缘服务器虚拟机。
ms.openlocfilehash: 8f1a8b7d99a555006c1d69ee52f2403e9bf0a874
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30880212"
---
# <a name="install-ccappliance"></a><span data-ttu-id="44405-103">Install-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="44405-103">Install-CcAppliance</span></span>
 
<span data-ttu-id="44405-104">Install-CcAppliance cmdlet 用于在主机服务器上安装 Skype for Business 云连接器版本设备，包括 AD、中央管理存储、中介服务器和边缘服务器虚拟机。</span><span class="sxs-lookup"><span data-stu-id="44405-104">The Install-CcAppliance cmdlet installs the Skype for Business Cloud Connector Edition appliance—including the AD, Central Management Store, Mediation Server, and Edge Server virtual machines—on the host server.</span></span> 
  
```
Install-CcAppliance [-Steps <array>] [-SkipExistingObjects] [-Upgrade] [-UpdateAllCredentials] [<CommonParameters>]
Install-CcAppliance [-Steps <array>] [-PrepareOnly]  [<CommonParameters>]
Install-CcAppliance [-ShowStepsOnly]  [<CommonParameters>]
```

## <a name="examples"></a><span data-ttu-id="44405-105">示例</span><span class="sxs-lookup"><span data-stu-id="44405-105">Examples</span></span>
<span data-ttu-id="44405-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="44405-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="44405-107">示例 1</span><span class="sxs-lookup"><span data-stu-id="44405-107">Example 1</span></span>

<span data-ttu-id="44405-108">下面的示例在主机服务器上安装新的云连接器装置：</span><span class="sxs-lookup"><span data-stu-id="44405-108">The following example installs a new Cloud Connector appliance on the host server:</span></span>
  
```
Install-CcAppliance
```

### <a name="example-2"></a><span data-ttu-id="44405-109">示例 2</span><span class="sxs-lookup"><span data-stu-id="44405-109">Example 2</span></span>

<span data-ttu-id="44405-110">下面的示例升级到最新版本的云连接器：</span><span class="sxs-lookup"><span data-stu-id="44405-110">The following example upgrades Cloud Connector to the latest version:</span></span>
  
```
Install-CcAppliance -Upgrade
```

### <a name="example-3"></a><span data-ttu-id="44405-111">示例 3</span><span class="sxs-lookup"><span data-stu-id="44405-111">Example 3</span></span>

<span data-ttu-id="44405-112">下面的示例删除所有缓存的主机服务器上，提示用户指定再次，所有的凭据信息的云连接器凭据，然后安装云连接器：</span><span class="sxs-lookup"><span data-stu-id="44405-112">The following example removes all Cloud Connector credentials cached on the host server, prompts the user to specify all credential information again, and then installs Cloud Connector:</span></span>
  
```
Install-CcAppliance -UpdateAllCredentials
```

### <a name="example-4"></a><span data-ttu-id="44405-113">示例 4</span><span class="sxs-lookup"><span data-stu-id="44405-113">Example 4</span></span>

<span data-ttu-id="44405-114">以下示例显示 PowerShell 控制台中的所有部署步骤：</span><span class="sxs-lookup"><span data-stu-id="44405-114">The following example displays all deployment steps in the PowerShell console:</span></span>
  
```
Install-CcAppliance -ShowStepsOnly
```

<span data-ttu-id="44405-115">-ShowStepsOnly 参数仅用于故障排除。</span><span class="sxs-lookup"><span data-stu-id="44405-115">The -ShowStepsOnly parameter is for troubleshooting only.</span></span>
  
### <a name="example-5"></a><span data-ttu-id="44405-116">示例 5</span><span class="sxs-lookup"><span data-stu-id="44405-116">Example 5</span></span>

<span data-ttu-id="44405-117">以下示例在主机服务器上为每个部署步骤生成配置文件。</span><span class="sxs-lookup"><span data-stu-id="44405-117">The following example generates configuration files for each deployment step on the host server.</span></span> <span data-ttu-id="44405-118">配置文件保存到\<ApplianceRoot\>\Instances\\<Version\>-default\ExportedConfig 主机服务器上的文件夹：</span><span class="sxs-lookup"><span data-stu-id="44405-118">Configuration files are saved to the \<ApplianceRoot\>\Instances\\<Version\>-default\ExportedConfig folder on the host server:</span></span>
  
```
Install-CcAppliance -PrepareOnly
```

<span data-ttu-id="44405-119">要确定设备根，请运行 Get-CcApplianceDirectory cmdlet。</span><span class="sxs-lookup"><span data-stu-id="44405-119">To determine the appliance root, run the Get-CcApplianceDirectory cmdlet.</span></span> 
  
### <a name="example-6"></a><span data-ttu-id="44405-120">示例 6</span><span class="sxs-lookup"><span data-stu-id="44405-120">Example 6</span></span>

<span data-ttu-id="44405-p102">在以下示例中，云连接器运行部署步骤 1、2 和 3 来创建虚拟交换机、创建 AD 虚拟机以及在 AD 服务器上安装域服务。如果已执行某步骤，则跳过该步骤：</span><span class="sxs-lookup"><span data-stu-id="44405-p102">In the following example, Cloud Connector runs deployment steps 1, 2, and 3 to create virtual switches, create an AD virtual machine, and install the domain service on the AD server. It skips the step if the step has already been executed:</span></span>
  
```
Install-CcAppliance -Steps @(1,2,3) -SkipExistingObjects
```

<span data-ttu-id="44405-123">SkipExistingObjects 参数必须与 Steps 参数一起使用。</span><span class="sxs-lookup"><span data-stu-id="44405-123">The SkipExistingObjects parameter must be used in conjunction with the Steps parameter.</span></span>
  
> [!NOTE]
> <span data-ttu-id="44405-124">Steps 参数仅用于故障排除目的。</span><span class="sxs-lookup"><span data-stu-id="44405-124">The Steps parameter is for troubleshooting purposes only.</span></span> <span data-ttu-id="44405-125">请勿使用此参数来部署设备或升级正在使用的设备。</span><span class="sxs-lookup"><span data-stu-id="44405-125">Do not use this parameter to deploy an appliance or to upgrade an appliance that is in service.</span></span> 
  
<span data-ttu-id="44405-126">要确定部署步骤，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="44405-126">To determine the steps of the deployment, run the following command:</span></span>
  
<span data-ttu-id="44405-127">Install-CcAppliance -ShowStepsOnly</span><span class="sxs-lookup"><span data-stu-id="44405-127">Install-CcAppliance -ShowStepsOnly</span></span>
  
## <a name="detailed-description"></a><span data-ttu-id="44405-128">详细说明</span><span class="sxs-lookup"><span data-stu-id="44405-128">Detailed Description</span></span>
<span data-ttu-id="44405-129"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="44405-129"></span></span>

<span data-ttu-id="44405-130">安装 CcAppliance cmdlet 用于将云连接器部署到新装置或升级到最新版本的现有设备。</span><span class="sxs-lookup"><span data-stu-id="44405-130">The Install-CcAppliance cmdlet is used to deploy Cloud Connector to a new appliance or to upgrade an existing appliance to the latest version.</span></span>
  
<span data-ttu-id="44405-131">如果你有新设备，请务必先阅读“为云连接器准备你的环境”，运行 Register-CcAppliance cmdlet 来注册该设备，然后运行 Install-CcAppliance cmdlet。</span><span class="sxs-lookup"><span data-stu-id="44405-131">If you have a new appliance, be sure to read Prepare your environment for Cloud Connector first, run the Register-CcAppliance cmdlet to register the appliance, and then run the Install-CcAppliance cmdlet.</span></span> <span data-ttu-id="44405-132">有关详细信息，请参阅[Deploy a single site in Cloud Connector](deploy-a-single-site-in-cloud-connector.md)和[Deploy multiple sites in Cloud Connector](deploy-multiple-sites-in-cloud-connector.md)。</span><span class="sxs-lookup"><span data-stu-id="44405-132">For more information, see [Deploy a single site in Cloud Connector](deploy-a-single-site-in-cloud-connector.md) and [Deploy multiple sites in Cloud Connector](deploy-multiple-sites-in-cloud-connector.md).</span></span> 
  
<span data-ttu-id="44405-133">如果您具有云连接器的现有部署并且要升级，请按照[升级到云连接符的新版本](upgrade-to-a-new-version-of-cloud-connector.md)中的说明。</span><span class="sxs-lookup"><span data-stu-id="44405-133">If you have an existing deployment of Cloud Connector and you want to upgrade, please follow the instructions in [Upgrade to a new version of Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md).</span></span>
  
## <a name="parameters"></a><span data-ttu-id="44405-134">参数</span><span class="sxs-lookup"><span data-stu-id="44405-134">Parameters</span></span>
<span data-ttu-id="44405-135"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="44405-135"></span></span>

|<span data-ttu-id="44405-136">**参数**</span><span class="sxs-lookup"><span data-stu-id="44405-136">**Parameter**</span></span>|<span data-ttu-id="44405-137">**必需**</span><span class="sxs-lookup"><span data-stu-id="44405-137">**Required**</span></span>|<span data-ttu-id="44405-138">**类型**</span><span class="sxs-lookup"><span data-stu-id="44405-138">**Type**</span></span>|<span data-ttu-id="44405-139">**说明**</span><span class="sxs-lookup"><span data-stu-id="44405-139">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="44405-140">PrepareOnly</span><span class="sxs-lookup"><span data-stu-id="44405-140">PrepareOnly</span></span>  <br/> |<span data-ttu-id="44405-141">可选</span><span class="sxs-lookup"><span data-stu-id="44405-141">Optional</span></span>  <br/> |<span data-ttu-id="44405-142">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="44405-142">System.Management.Automation.SwitchParameter</span></span>  <br/> | <span data-ttu-id="44405-p105">为每个部署步骤生成配置文件。此参数仅用于故障排除。</span><span class="sxs-lookup"><span data-stu-id="44405-p105">Generate configuration files for each deployment step. This parameter is for troubleshooting only.</span></span> <br/> |
|<span data-ttu-id="44405-145">ShowStepsOnly</span><span class="sxs-lookup"><span data-stu-id="44405-145">ShowStepsOnly</span></span>  <br/> |<span data-ttu-id="44405-146">可选</span><span class="sxs-lookup"><span data-stu-id="44405-146">Optional</span></span>  <br/> |<span data-ttu-id="44405-147">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="44405-147">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="44405-p106">仅显示部署步骤名称。此参数仅用于故障排除。</span><span class="sxs-lookup"><span data-stu-id="44405-p106">Display deployment step names only. This parameter is for troubleshooting only.</span></span>  <br/> |
|<span data-ttu-id="44405-150">SkipExistingObjects</span><span class="sxs-lookup"><span data-stu-id="44405-150">SkipExistingObjects</span></span>  <br/> |<span data-ttu-id="44405-151">可选</span><span class="sxs-lookup"><span data-stu-id="44405-151">Optional</span></span>  <br/> |<span data-ttu-id="44405-152">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="44405-152">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="44405-p107">此参数必须与 Steps 参数一起使用。此参数仅用于故障排除。</span><span class="sxs-lookup"><span data-stu-id="44405-p107">This parameter must be used in conjunction with the Steps parameter. This parameter is for troubleshooting only.</span></span>  <br/> |
|<span data-ttu-id="44405-155">步骤</span><span class="sxs-lookup"><span data-stu-id="44405-155">Steps</span></span>  <br/> |<span data-ttu-id="44405-156">可选</span><span class="sxs-lookup"><span data-stu-id="44405-156">Optional</span></span>  <br/> |<span data-ttu-id="44405-157">System.Array</span><span class="sxs-lookup"><span data-stu-id="44405-157">System.Array</span></span>  <br/> |<span data-ttu-id="44405-p108">运行部署步骤。此参数仅用于故障排除。</span><span class="sxs-lookup"><span data-stu-id="44405-p108">Run the deployment steps. This parameter is for troubleshooting only.</span></span>  <br/> |
|<span data-ttu-id="44405-160">升级</span><span class="sxs-lookup"><span data-stu-id="44405-160">Upgrade</span></span>  <br/> |<span data-ttu-id="44405-161">可选</span><span class="sxs-lookup"><span data-stu-id="44405-161">Optional</span></span>  <br/> |<span data-ttu-id="44405-162">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="44405-162">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="44405-163">将现有云连接器升级到最新版本。</span><span class="sxs-lookup"><span data-stu-id="44405-163">Upgrade existing Cloud Connector to the latest version.</span></span>  <br/> |
|<span data-ttu-id="44405-164">UpdateAllCredentials</span><span class="sxs-lookup"><span data-stu-id="44405-164">UpdateAllCredentials</span></span>  <br/> |<span data-ttu-id="44405-165">可选</span><span class="sxs-lookup"><span data-stu-id="44405-165">Optional</span></span>  <br/> |<span data-ttu-id="44405-166">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="44405-166">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="44405-167">在缓存中删除所有云连接器凭据。</span><span class="sxs-lookup"><span data-stu-id="44405-167">Remove all Cloud Connector credentials in the cache.</span></span> <span data-ttu-id="44405-168">提示用户为安装指定新凭据信息。</span><span class="sxs-lookup"><span data-stu-id="44405-168">Prompt the user to specify new credential information for the installation.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="44405-169">输入类型</span><span class="sxs-lookup"><span data-stu-id="44405-169">Input Types</span></span>
<span data-ttu-id="44405-170"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="44405-170"></span></span>

<span data-ttu-id="44405-p110">无。Install-CcAppliance cmdlet 不接受主线输入。</span><span class="sxs-lookup"><span data-stu-id="44405-p110">None. The Install-CcAppliance cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="44405-173">返回类型</span><span class="sxs-lookup"><span data-stu-id="44405-173">Return Types</span></span>
<span data-ttu-id="44405-174"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="44405-174"></span></span>

<span data-ttu-id="44405-175">无</span><span class="sxs-lookup"><span data-stu-id="44405-175">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="44405-176">另请参阅</span><span class="sxs-lookup"><span data-stu-id="44405-176">See also</span></span>
<span data-ttu-id="44405-177"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="44405-177"></span></span>

[<span data-ttu-id="44405-178">Publish-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="44405-178">Publish-CcAppliance</span></span>](publish-ccappliance.md)
  
[<span data-ttu-id="44405-179">Register-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="44405-179">Register-CcAppliance</span></span>](register-ccappliance.md)
  
[<span data-ttu-id="44405-180">Unregister-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="44405-180">Unregister-CcAppliance</span></span>](unregister-ccappliance.md)
  
[<span data-ttu-id="44405-181">Uninstall-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="44405-181">Uninstall-CcAppliance</span></span>](uninstall-ccappliance.md)
  

