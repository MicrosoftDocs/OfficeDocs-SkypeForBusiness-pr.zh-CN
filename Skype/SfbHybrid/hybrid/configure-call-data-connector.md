---
title: 配置呼叫数据连接器
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: 有关配置呼叫数据连接器的说明, 允许使用 Skype for business Online 工具查看本地 Skype for business 中的遥测。
ms.openlocfilehash: 1851e1e0c430107a27d706f7bc16ad974c5abaed
ms.sourcegitcommit: a78fee3cad5b58bf41dd014a79f4316cf310c8d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/29/2019
ms.locfileid: "36160471"
---
# <a name="configure-call-data-connector"></a><span data-ttu-id="e0295-103">配置呼叫数据连接器</span><span class="sxs-lookup"><span data-stu-id="e0295-103">Configure Call Data Connector</span></span>

<span data-ttu-id="e0295-104">本文介绍如何配置呼叫数据连接器-一个可使用 Skype for business Online 通话质量仪表板 (CQD) 和呼叫分析 (CA) 工具查看 Skype for Business Server 呼叫质量数据的单一工具集。</span><span class="sxs-lookup"><span data-stu-id="e0295-104">This article describes how to configure Call Data Connector--a single toolset that enables viewing Skype for Business Server Call Quality Data using Skype for Business Online Call Quality Dashboard (CQD) and Call Analytics (CA) tools.</span></span> 

> [!NOTE]
> <span data-ttu-id="e0295-105">公共预览版版本中, 只有 "呼叫分析" 仪表板可用。</span><span class="sxs-lookup"><span data-stu-id="e0295-105">At public preview release, only Call Analytics dashboard is available.</span></span>

<span data-ttu-id="e0295-106">有关呼叫数据连接器的优点和先决条件的详细信息 (如角色要求和设置混合连接), 请参阅[Plan Call Data Connector](plan-call-data-connector.md)。</span><span class="sxs-lookup"><span data-stu-id="e0295-106">For more information about Call Data Connector benefits and pre-requisites, such as role requirements and setting up hybrid connectivity, see [Plan Call Data Connector](plan-call-data-connector.md).</span></span>

## <a name="enable-monitoring"></a><span data-ttu-id="e0295-107">启用监视</span><span class="sxs-lookup"><span data-stu-id="e0295-107">Enable Monitoring</span></span>
 
<span data-ttu-id="e0295-108">您必须在前端池监视中配置呼叫数据记录 (CDR) 和体验质量 (QoE) 数据收集 (使用本地 LCSCdr 和 QoEMetrics 数据库);否则, 呼叫分析和呼叫质量仪表板将不会获得要使用的数据。</span><span class="sxs-lookup"><span data-stu-id="e0295-108">You must configure Call Data Recording (CDR) and Quality of Experience (QoE) data collection in your front end pool Monitoring,with local LCSCdr and QoEMetrics databases; otherwise, the Call Analytics and Call Quality Dashboards won’t get data to work with.</span></span> <span data-ttu-id="e0295-109">在配置呼叫数据连接器之前, 请按照在[Skype For Business Server 中部署监控](../../SfbServer/deploy/deploy-monitoring/deploy-monitoring.md)中提供的步骤配置 CDR 和 QoE 以及基本监控。</span><span class="sxs-lookup"><span data-stu-id="e0295-109">Before you Configure Call Data Connector, follow the steps provided in [Deploy monitoring in Skype for Business Server](../../SfbServer/deploy/deploy-monitoring/deploy-monitoring.md) to configure both CDR and QoE as well as basic Monitoring.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e0295-110">如果前端池上未启用监控, 则呼叫数据连接器将无法正常工作。</span><span class="sxs-lookup"><span data-stu-id="e0295-110">Call Data Connector will not function if Monitoring is not enabled on the front end pool.</span></span>

## <a name="enable-call-data-connector"></a><span data-ttu-id="e0295-111">启用呼叫数据连接器</span><span class="sxs-lookup"><span data-stu-id="e0295-111">Enable Call Data Connector</span></span>

<span data-ttu-id="e0295-112">若要配置和启用呼叫数据连接器, 您将使用以下 cmdlet:</span><span class="sxs-lookup"><span data-stu-id="e0295-112">To configure and enable Call Data Connector, you will use the following cmdlets:</span></span>

| <span data-ttu-id="e0295-113">Cmdlet</span><span class="sxs-lookup"><span data-stu-id="e0295-113">Cmdlet</span></span>| <span data-ttu-id="e0295-114">说明</span><span class="sxs-lookup"><span data-stu-id="e0295-114">Description</span></span>|
| :-----------------|---------------:|
| <span data-ttu-id="e0295-115">新 CsCloudCallDataConnection</span><span class="sxs-lookup"><span data-stu-id="e0295-115">New-CsCloudCallDataConnection</span></span> | <span data-ttu-id="e0295-116">建立联机数据收集器的联机 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="e0295-116">An online cmdlet that establishes an online data collector.</span></span>|
| <span data-ttu-id="e0295-117">CsCloudCallDataConnection</span><span class="sxs-lookup"><span data-stu-id="e0295-117">Get-CsCloudCallDataConnection</span></span> | <span data-ttu-id="e0295-118">一个用于检索现有联机数据收集器的联机 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="e0295-118">An online cmdlet that retrieves an existing online data collector.</span></span>|  
| <span data-ttu-id="e0295-119">CsCloudCallDataConnector</span><span class="sxs-lookup"><span data-stu-id="e0295-119">Get-CsCloudCallDataConnector</span></span> | <span data-ttu-id="e0295-120">一个内部部署 cmdlet, 用于检索由 CsCloudCallDataConnection cmdlet 创建的连接信息。</span><span class="sxs-lookup"><span data-stu-id="e0295-120">An on-premises cmdlet that retrieves the connection information created by the New-CsCloudCallDataConnection cmdlet.</span></span> |
| <span data-ttu-id="e0295-121">CsCloudCallDataConnector</span><span class="sxs-lookup"><span data-stu-id="e0295-121">Set-CsCloudCallDataConnector</span></span> | <span data-ttu-id="e0295-122">一个本地 cmdlet, 用于保存由 CsCloudCallDataConnection cmdlet 创建的连接信息的本地副本。</span><span class="sxs-lookup"><span data-stu-id="e0295-122">An on-premises cmdlet that saves an on-premises copy of the connection information created by the New-CsCloudCallDataConnection cmdlet.</span></span> |  
| <span data-ttu-id="e0295-123">CsCloudCallDataConnectorConfiguration</span><span class="sxs-lookup"><span data-stu-id="e0295-123">Set-CsCloudCallDataConnectorConfiguration</span></span> | <span data-ttu-id="e0295-124">允许您启用或禁用连接器并自定义范围级别的本地 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="e0295-124">An on-premises cmdlet that allows you to enable or disable the connector and customize the scope level.</span></span>|

> [!NOTE]
> <span data-ttu-id="e0295-125">若要擦除您的配置并重新开始, 请使用 csclouddatconnectorconfiguration cmdlet。</span><span class="sxs-lookup"><span data-stu-id="e0295-125">To erase your configuration and start over, please use the Remove-csclouddatconnectorconfiguration cmdlet.</span></span>

### <a name="configure-your-environment"></a><span data-ttu-id="e0295-126">配置环境</span><span class="sxs-lookup"><span data-stu-id="e0295-126">Configure your environment</span></span> 

<span data-ttu-id="e0295-127">若要将环境配置为启用联机数据收集器, 必须先以管理员身份登录到 Skype for Business Online PowerShell。</span><span class="sxs-lookup"><span data-stu-id="e0295-127">To configure your environment to enable an online data collector, you must first log in to Skype for Business Online PowerShell as an administrator.</span></span> <span data-ttu-id="e0295-128">有关详细信息, 请参阅[使用 Office 365 PowerShell 管理 Skype For Business Online](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)。</span><span class="sxs-lookup"><span data-stu-id="e0295-128">For more information, see [Manage Skype for Business Online with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).</span></span>

<span data-ttu-id="e0295-129">有两种方法可以登录到 Skype for business Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="e0295-129">There are two methods for logging in to Skype for Business Online PowerShell:</span></span>

- <span data-ttu-id="e0295-130">从 Skype for Business Server 2019 命令行管理程序 (推荐方法)</span><span class="sxs-lookup"><span data-stu-id="e0295-130">From the Skype for Business Server 2019 management shell (recommended method)</span></span>
- <span data-ttu-id="e0295-131">从另一个 PowerShell 会话</span><span class="sxs-lookup"><span data-stu-id="e0295-131">From another PowerShell session</span></span>

#### <a name="log-in-to-skype-for-business-online-powershell-from-the-skype-for-business-server-management-shell-recommended-method"></a><span data-ttu-id="e0295-132">从 Skype for Business Server 命令行管理程序 (推荐方法) 登录到 Skype for business Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="e0295-132">Log in to Skype for Business Online PowerShell from the Skype for Business Server management shell (recommended method)</span></span>

1. <span data-ttu-id="e0295-133">如果是第一次启用连接器, 请运行以下命令:</span><span class="sxs-lookup"><span data-stu-id="e0295-133">If enabling the connector for the first time, run the following command:</span></span>

   ```
   New-CsCloudCallDataConnection | Set-CsCloudCallDataConnector -TenantId <tenant_id>
   ```

2. <span data-ttu-id="e0295-134">如果遇到连接已存在的错误, 则表示您的租户的呼叫数据连接已存在。</span><span class="sxs-lookup"><span data-stu-id="e0295-134">If you get an error that the connection already exists, this means that the call data connection already exists for your tenant.</span></span> <span data-ttu-id="e0295-135">在这种情况下, 请运行以下命令:</span><span class="sxs-lookup"><span data-stu-id="e0295-135">In this case, run the command:</span></span> 

   ```
   Get-CsCloudCallDataConnection | Set-CsCloudCallDataConnector -TenantId <tenant_id>
   ```


#### <a name="log-in-to-skype-for-business-online-powershell-from-another-powershell-session-optional-method"></a><span data-ttu-id="e0295-136">从另一个 PowerShell 会话登录到 Skype for Business Online PowerShell (可选方法)</span><span class="sxs-lookup"><span data-stu-id="e0295-136">Log in to Skype for Business Online PowerShell from another PowerShell session (optional method)</span></span>

1.  <span data-ttu-id="e0295-137">如果是第一次启用连接器, 请运行以下命令:</span><span class="sxs-lookup"><span data-stu-id="e0295-137">If enabling the connector for the first time, run the following command:</span></span> 

    ``` 
    New-CsCloudCallDataConnection 
    ```

2.  <span data-ttu-id="e0295-138">如果遇到连接已存在的错误, 则表示您的租户的呼叫数据连接已存在。</span><span class="sxs-lookup"><span data-stu-id="e0295-138">If you get an error that the connection already exists, this means that the call data connection already exists for your tenant.</span></span> <span data-ttu-id="e0295-139">在这种情况下, 请运行以下命令:</span><span class="sxs-lookup"><span data-stu-id="e0295-139">In this case, run the command:</span></span> 

    ```
    Get-CsCloudCallDataConnection  
    ```

<span data-ttu-id="e0295-140">上面的命令的输出包含一个令牌值, 在配置本地环境时, 您将需要执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="e0295-140">The output of the above commands contains a token value, which you will need when configuring your on-premises environment as follows:</span></span>

<span data-ttu-id="e0295-141">在 Skype for Business Server 命令行管理程序中, 指定以下命令:</span><span class="sxs-lookup"><span data-stu-id="e0295-141">From within the Skype for Business Server management shell, specify the following command:</span></span>

```
Set-CsCloudCallDataConnector -Identity Global -TenantId <tenant_id> -Token <token-copied-from-online>
```

### <a name="configure-the-scope"></a><span data-ttu-id="e0295-142">配置作用域</span><span class="sxs-lookup"><span data-stu-id="e0295-142">Configure the scope</span></span>

<span data-ttu-id="e0295-143">您可以使用 Skype for Business Server 命令行管理程序中的 CsCloudCallDataConnectorConfiguration cmdlet 为特定网站或整个 Skype for Business Server 部署启用呼叫数据连接器。</span><span class="sxs-lookup"><span data-stu-id="e0295-143">You can enable Call Data Connector for a particular site or for your entire Skype for Business Server deployment by using the Set-CsCloudCallDataConnectorConfiguration cmdlet from within the Skype for Business Server management shell.</span></span> <span data-ttu-id="e0295-144">例如, 以下命令在全局范围内启用呼叫数据连接器:</span><span class="sxs-lookup"><span data-stu-id="e0295-144">For example, the following command enables Call Data Connector at the global scope:</span></span>

```
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $True
```

<span data-ttu-id="e0295-145">除了全局设置, 可以将呼叫数据连接器配置设置分配给网站范围。</span><span class="sxs-lookup"><span data-stu-id="e0295-145">In addition to the global settings, Call Data Connector configuration settings can be assigned to the site scope.</span></span> <span data-ttu-id="e0295-146">这在监视方面提供了更多管理灵活性。</span><span class="sxs-lookup"><span data-stu-id="e0295-146">This provides additional management flexibility when it comes to monitoring.</span></span> <span data-ttu-id="e0295-147">例如, 管理员可以为 Redmond 站点启用呼叫数据连接器转发, 但禁用了都柏林网站的呼叫数据连接器转发, 如以下示例所示:</span><span class="sxs-lookup"><span data-stu-id="e0295-147">For example, an administrator can enable Call Data Connector forwarding for the Redmond site but disable Call Data Connector forwarding for the Dublin site, as shown in the following example:</span></span>

```
Set-CsCloudCallDataConnectorConfiguration -Identity "site:Redmond" -EnableCallDataConnector $True
```

```
Set-CsCloudCallDataConnectorConfiguration -Identity "site:Dublin" -EnableCallDataConnector $False
```

<span data-ttu-id="e0295-148">在 site 作用域配置的设置的优先于在 global 作用域配置的设置。</span><span class="sxs-lookup"><span data-stu-id="e0295-148">Settings configured at the site scope take precedence over settings configured at the global scope.</span></span> <span data-ttu-id="e0295-149">例如, 假设在全局范围内启用了呼叫数据连接器转发, 但在站点范围 (针对 Redmond 站点) 禁用了此功能。</span><span class="sxs-lookup"><span data-stu-id="e0295-149">For example, suppose Call Data Connector forwarding is enabled at the global scope, but disabled at the site scope (for the Redmond site).</span></span> <span data-ttu-id="e0295-150">这意味着不会为 Redmond 站点中的用户转发呼叫详细记录和 QoE 信息。</span><span class="sxs-lookup"><span data-stu-id="e0295-150">That means that call detail recording and QoE information will not be forwarded for users in the Redmond site.</span></span> <span data-ttu-id="e0295-151">但是, 其他网站中的用户 (即由全局设置 (而不是 Redmond 网站设置) 管理的用户将会有呼叫详细记录和转发 QoE 信息。</span><span class="sxs-lookup"><span data-stu-id="e0295-151">However, users in other sites (that is, users managed by the global settings instead of the Redmond site settings) will have their call detail recording and QoE information forwarded.</span></span>

<span data-ttu-id="e0295-152">下表显示了呼叫数据连接器使用的最常用设置的值:</span><span class="sxs-lookup"><span data-stu-id="e0295-152">Values for the most commonly used settings used by Call Data Connector are shown in the following table:</span></span>  

|<span data-ttu-id="e0295-153">属性</span><span class="sxs-lookup"><span data-stu-id="e0295-153">Property</span></span>|<span data-ttu-id="e0295-154">说明</span><span class="sxs-lookup"><span data-stu-id="e0295-154">Description</span></span>|<span data-ttu-id="e0295-155">默认值</span><span class="sxs-lookup"><span data-stu-id="e0295-155">Default value</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e0295-156">EnableCallDataConnector</span><span class="sxs-lookup"><span data-stu-id="e0295-156">EnableCallDataConnector</span></span>  <br/> |<span data-ttu-id="e0295-157">指示是否已启用呼叫数据连接器。</span><span class="sxs-lookup"><span data-stu-id="e0295-157">Indicates whether Call Data Connector is enabled.</span></span> <span data-ttu-id="e0295-158">如果为 True, 则会将监视记录转发到联机监控。</span><span class="sxs-lookup"><span data-stu-id="e0295-158">If True, monitoring records will be forwarded to online monitoring.</span></span>  <br/> |<span data-ttu-id="e0295-159">$False</span><span class="sxs-lookup"><span data-stu-id="e0295-159">$False</span></span>  <br/> |
| <span data-ttu-id="e0295-160">标识</span><span class="sxs-lookup"><span data-stu-id="e0295-160">Identity</span></span> | <span data-ttu-id="e0295-161">确定命令的范围级别: global 或 site。</span><span class="sxs-lookup"><span data-stu-id="e0295-161">Determines the scope level for the command: global or site.</span></span>   | <span data-ttu-id="e0295-162">全局性</span><span class="sxs-lookup"><span data-stu-id="e0295-162">global</span></span>  |

## <a name="disable-call-data-connector"></a><span data-ttu-id="e0295-163">禁用呼叫数据连接器</span><span class="sxs-lookup"><span data-stu-id="e0295-163">Disable Call Data Connector</span></span>

<span data-ttu-id="e0295-164">禁用呼叫数据连接器不会解除监视存储与前端池的关联, 也不会卸载或以其他方式影响后端监控数据库。</span><span class="sxs-lookup"><span data-stu-id="e0295-164">Disabling Call Data Connector does not disassociate the monitoring store from the Front End pool, nor does it uninstall or otherwise affect the backend monitoring database.</span></span> <span data-ttu-id="e0295-165">禁用呼叫数据连接器时, 将停止将 Skype for Business Server 上传到云的呼叫数据。</span><span class="sxs-lookup"><span data-stu-id="e0295-165">When you disable Call Data Connector, you stop Skype for Business Server from uploading call data to the cloud.</span></span> 

<span data-ttu-id="e0295-166">您可以通过在 Skype for Business Server 命令行管理程序中使用 CsCloudCallDataConnectorConfiguration cmdlet 禁用呼叫数据连接器。</span><span class="sxs-lookup"><span data-stu-id="e0295-166">You disable Call Data Connector by using the Set-CsCloudCallDataConnectorConfiguration cmdlet from within the Skype for Business Server management shell.</span></span> <span data-ttu-id="e0295-167">例如, 以下命令通过将 EnableCallDataConnector 属性设置为 $False 来禁用全局范围的调用数据连接器:</span><span class="sxs-lookup"><span data-stu-id="e0295-167">For example, the following command disables Call Data Connector at the global scope by setting the EnableCallDataConnector property to $False:</span></span>

```
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $False
```

<span data-ttu-id="e0295-168">如果要恢复向云上载调用数据, 请将 EnableCallDataConnector 属性设置回 $True, 如下面的示例所示:</span><span class="sxs-lookup"><span data-stu-id="e0295-168">If you want to resume uploading call data to the cloud, set the EnableCallDataConnector property back to $True, as shown in the following example:</span></span>

```
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $True
```

## <a name="view-on-premises-data-through-the-online-dashboard"></a><span data-ttu-id="e0295-169">通过联机仪表板查看本地数据</span><span class="sxs-lookup"><span data-stu-id="e0295-169">View on-premises data through the online dashboard</span></span>

 <span data-ttu-id="e0295-170">启用呼叫数据连接器后, 您可以在 "呼叫分析" 仪表板上查看本地呼叫数据, 如[使用呼叫分析解决质量差](https://docs.microsoft.com/skypeforbusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality)一节中所述。</span><span class="sxs-lookup"><span data-stu-id="e0295-170">After Call Data Connector is enabled, you can view your on-premises call data on the Call Analytics dashboard as described in  [Use Call Analytics to troubleshoot poor quality](https://docs.microsoft.com/skypeforbusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality).</span></span>


## <a name="for-more-information"></a><span data-ttu-id="e0295-171">详细信息</span><span class="sxs-lookup"><span data-stu-id="e0295-171">For more information</span></span>

<span data-ttu-id="e0295-172">有关 cmdlet 的详细信息, 可以使用 Skype for Business Server 命令行管理程序中的 Get-Help 命令。</span><span class="sxs-lookup"><span data-stu-id="e0295-172">For more information on the cmdlets, you can use the Get-Help command from the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="e0295-173">例如：</span><span class="sxs-lookup"><span data-stu-id="e0295-173">For example:</span></span>

<span data-ttu-id="e0295-174">Get-help CsCloudCallDataConnector |多</span><span class="sxs-lookup"><span data-stu-id="e0295-174">Get-Help Get-CsCloudCallDataConnector | more</span></span>

<span data-ttu-id="e0295-175">Get-help CsCloudCallDataConnector |多</span><span class="sxs-lookup"><span data-stu-id="e0295-175">Get-Help Set-CsCloudCallDataConnector | more</span></span>

<span data-ttu-id="e0295-176">Get-help CsCloudCallDataConnectorConfiguration |多</span><span class="sxs-lookup"><span data-stu-id="e0295-176">Get-Help Set-CsCloudCallDataConnectorConfiguration | more</span></span>
