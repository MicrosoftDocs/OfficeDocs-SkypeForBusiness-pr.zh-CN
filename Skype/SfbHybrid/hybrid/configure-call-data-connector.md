---
title: 配置呼叫数据连接器
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: 有关配置呼叫数据连接器的说明，允许使用 Skype for Business Online 工具查看本地 Skype for Business 中的遥测。
ms.openlocfilehash: f78d59d02964bd826fc705bc193cae3e21b293a5
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51118991"
---
# <a name="configure-call-data-connector"></a><span data-ttu-id="f2310-103">配置呼叫数据连接器</span><span class="sxs-lookup"><span data-stu-id="f2310-103">Configure Call Data Connector</span></span>

<span data-ttu-id="f2310-104">本文介绍如何配置呼叫数据连接器，这是一个工具集，支持使用 Skype for Business Online 呼叫质量仪表板 (CQD) 和呼叫分析 (CA) 工具查看 Skype for Business Server 呼叫质量数据。</span><span class="sxs-lookup"><span data-stu-id="f2310-104">This article describes how to configure Call Data Connector--a single toolset that enables viewing Skype for Business Server Call Quality Data using Skype for Business Online Call Quality Dashboard (CQD) and Call Analytics (CA) tools.</span></span>

<span data-ttu-id="f2310-105">有关呼叫数据连接器的好处和先决条件（如角色要求和设置混合连接）详细信息，请参阅规划 [呼叫数据连接器](plan-call-data-connector.md)。</span><span class="sxs-lookup"><span data-stu-id="f2310-105">For more information about Call Data Connector benefits and pre-requisites, such as role requirements and setting up hybrid connectivity, see [Plan Call Data Connector](plan-call-data-connector.md).</span></span>

## <a name="enable-monitoring"></a><span data-ttu-id="f2310-106">启用监控</span><span class="sxs-lookup"><span data-stu-id="f2310-106">Enable Monitoring</span></span>
 
<span data-ttu-id="f2310-107">必须使用本地 LCSCdr 和 QoEMetrics 数据库在前端池监控中配置呼叫数据记录 (CDR) 和用户体验质量 (QoE) 数据收集;否则，通话分析和通话质量仪表板将不会获得要处理的数据。</span><span class="sxs-lookup"><span data-stu-id="f2310-107">You must configure Call Data Recording (CDR) and Quality of Experience (QoE) data collection in your front end pool Monitoring,with local LCSCdr and QoEMetrics databases; otherwise, the Call Analytics and Call Quality Dashboards won’t get data to work with.</span></span> <span data-ttu-id="f2310-108">配置呼叫数据连接器之前，请按照在 [Skype for Business Server](../../SfbServer/deploy/deploy-monitoring/deploy-monitoring.md) 中部署监控中提供的步骤配置 CDR 和 QoE 以及基本监控。</span><span class="sxs-lookup"><span data-stu-id="f2310-108">Before you Configure Call Data Connector, follow the steps provided in [Deploy monitoring in Skype for Business Server](../../SfbServer/deploy/deploy-monitoring/deploy-monitoring.md) to configure both CDR and QoE as well as basic Monitoring.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f2310-109">如果未在前端池上启用监控，呼叫数据连接器将无法正常工作。</span><span class="sxs-lookup"><span data-stu-id="f2310-109">Call Data Connector will not function if Monitoring is not enabled on the front end pool.</span></span>

## <a name="enable-call-data-connector"></a><span data-ttu-id="f2310-110">启用呼叫数据连接器</span><span class="sxs-lookup"><span data-stu-id="f2310-110">Enable Call Data Connector</span></span>

<span data-ttu-id="f2310-111">若要配置和启用呼叫数据连接器，您将使用以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="f2310-111">To configure and enable Call Data Connector, you will use the following cmdlets:</span></span>

| <span data-ttu-id="f2310-112">Cmdlet</span><span class="sxs-lookup"><span data-stu-id="f2310-112">Cmdlet</span></span>| <span data-ttu-id="f2310-113">说明</span><span class="sxs-lookup"><span data-stu-id="f2310-113">Description</span></span>|
| :-----------------|---------------:|
| <span data-ttu-id="f2310-114">New-CsCloudCallDataConnection</span><span class="sxs-lookup"><span data-stu-id="f2310-114">New-CsCloudCallDataConnection</span></span> | <span data-ttu-id="f2310-115">建立联机数据收集器的联机 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="f2310-115">An online cmdlet that establishes an online data collector.</span></span>|
| <span data-ttu-id="f2310-116">Get-CsCloudCallDataConnection</span><span class="sxs-lookup"><span data-stu-id="f2310-116">Get-CsCloudCallDataConnection</span></span> | <span data-ttu-id="f2310-117">检索现有联机数据收集器的联机 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="f2310-117">An online cmdlet that retrieves an existing online data collector.</span></span>|  
| <span data-ttu-id="f2310-118">Get-CsCloudCallDataConnector</span><span class="sxs-lookup"><span data-stu-id="f2310-118">Get-CsCloudCallDataConnector</span></span> | <span data-ttu-id="f2310-119">本地 cmdlet，用于检索由 New-CsCloudCallDataConnection cmdlet 创建的连接信息。</span><span class="sxs-lookup"><span data-stu-id="f2310-119">An on-premises cmdlet that retrieves the connection information created by the New-CsCloudCallDataConnection cmdlet.</span></span> |
| <span data-ttu-id="f2310-120">Set-CsCloudCallDataConnector</span><span class="sxs-lookup"><span data-stu-id="f2310-120">Set-CsCloudCallDataConnector</span></span> | <span data-ttu-id="f2310-121">本地 cmdlet，用于保存由 New-CsCloudCallDataConnection cmdlet 创建的连接信息本地副本。</span><span class="sxs-lookup"><span data-stu-id="f2310-121">An on-premises cmdlet that saves an on-premises copy of the connection information created by the New-CsCloudCallDataConnection cmdlet.</span></span> |  
| <span data-ttu-id="f2310-122">Set-CsCloudCallDataConnectorConfiguration</span><span class="sxs-lookup"><span data-stu-id="f2310-122">Set-CsCloudCallDataConnectorConfiguration</span></span> | <span data-ttu-id="f2310-123">允许启用或禁用连接器并自定义范围级别的本地 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="f2310-123">An on-premises cmdlet that allows you to enable or disable the connector and customize the scope level.</span></span>|

> [!NOTE]
> <span data-ttu-id="f2310-124">若要擦除配置并重新开始，请使用 Remove-csclouddatconnectorconfiguration cmdlet。</span><span class="sxs-lookup"><span data-stu-id="f2310-124">To erase your configuration and start over, please use the Remove-csclouddatconnectorconfiguration cmdlet.</span></span>

### <a name="configure-your-environment"></a><span data-ttu-id="f2310-125">配置环境</span><span class="sxs-lookup"><span data-stu-id="f2310-125">Configure your environment</span></span> 

<span data-ttu-id="f2310-126">若要配置环境以启用联机数据收集器，必须先以管理员角色登录到 Skype for Business Online PowerShell。</span><span class="sxs-lookup"><span data-stu-id="f2310-126">To configure your environment to enable an online data collector, you must first log in to Skype for Business Online PowerShell as an administrator.</span></span> <span data-ttu-id="f2310-127">有关详细信息，请参阅使用[Office 365 PowerShell 管理 Skype for Business Online。](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)</span><span class="sxs-lookup"><span data-stu-id="f2310-127">For more information, see [Manage Skype for Business Online with Office 365 PowerShell](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).</span></span>

<span data-ttu-id="f2310-128">有两种方法可以登录到 Skype for Business Online PowerShell：</span><span class="sxs-lookup"><span data-stu-id="f2310-128">There are two methods for logging in to Skype for Business Online PowerShell:</span></span>

- <span data-ttu-id="f2310-129">从 Skype for Business Server 2019 命令行管理程序 (推荐) </span><span class="sxs-lookup"><span data-stu-id="f2310-129">From the Skype for Business Server 2019 management shell (recommended method)</span></span>
- <span data-ttu-id="f2310-130">从另一个 PowerShell 会话</span><span class="sxs-lookup"><span data-stu-id="f2310-130">From another PowerShell session</span></span>

#### <a name="log-in-to-skype-for-business-online-powershell-from-the-skype-for-business-server-management-shell-recommended-method"></a><span data-ttu-id="f2310-131">从 Skype for Business Server 命令行管理程序 (Skype for Business Online PowerShell) </span><span class="sxs-lookup"><span data-stu-id="f2310-131">Log in to Skype for Business Online PowerShell from the Skype for Business Server management shell (recommended method)</span></span>

1. <span data-ttu-id="f2310-132">如果是首次启用连接器，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="f2310-132">If enabling the connector for the first time, run the following command:</span></span>

   ```PowerShell
   New-CsCloudCallDataConnection | Set-CsCloudCallDataConnector -TenantId <tenant_id>
   ```

2. <span data-ttu-id="f2310-133">如果收到连接已存在的错误，这意味着租户的呼叫数据连接已存在。</span><span class="sxs-lookup"><span data-stu-id="f2310-133">If you get an error that the connection already exists, this means that the call data connection already exists for your tenant.</span></span> <span data-ttu-id="f2310-134">在这种情况下，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="f2310-134">In this case, run the command:</span></span> 

   ```PowerShell
   Get-CsCloudCallDataConnection | Set-CsCloudCallDataConnector -TenantId <tenant_id>
   ```


#### <a name="log-in-to-skype-for-business-online-powershell-from-another-powershell-session-optional-method"></a><span data-ttu-id="f2310-135">从另一个 PowerShell 会话登录到 Skype for Business Online PowerShell， (可选) </span><span class="sxs-lookup"><span data-stu-id="f2310-135">Log in to Skype for Business Online PowerShell from another PowerShell session (optional method)</span></span>

1.  <span data-ttu-id="f2310-136">如果是首次启用连接器，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="f2310-136">If enabling the connector for the first time, run the following command:</span></span> 

    ```PowerShell 
    New-CsCloudCallDataConnection 
    ```

2.  <span data-ttu-id="f2310-137">如果收到连接已存在的错误，这意味着租户的呼叫数据连接已存在。</span><span class="sxs-lookup"><span data-stu-id="f2310-137">If you get an error that the connection already exists, this means that the call data connection already exists for your tenant.</span></span> <span data-ttu-id="f2310-138">在这种情况下，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="f2310-138">In this case, run the command:</span></span> 

    ```PowerShell
    Get-CsCloudCallDataConnection  
    ```

<span data-ttu-id="f2310-139">上述命令的输出包含一个令牌值，在配置本地环境时将需要此值，如下所示：</span><span class="sxs-lookup"><span data-stu-id="f2310-139">The output of the above commands contains a token value, which you will need when configuring your on-premises environment as follows:</span></span>

<span data-ttu-id="f2310-140">在 Skype for Business Server 命令行管理程序内，指定以下命令：</span><span class="sxs-lookup"><span data-stu-id="f2310-140">From within the Skype for Business Server management shell, specify the following command:</span></span>

```PowerShell
Set-CsCloudCallDataConnector -Identity Global -TenantId <tenant_id> -Token <token-copied-from-online>
```

### <a name="configure-the-scope"></a><span data-ttu-id="f2310-141">配置作用域</span><span class="sxs-lookup"><span data-stu-id="f2310-141">Configure the scope</span></span>

<span data-ttu-id="f2310-142">可以在 Skype for Business Server 命令行管理程序内使用 Set-CsCloudCallDataConnectorConfiguration cmdlet 为特定站点或整个 Skype for Business Server 部署启用呼叫数据连接器。</span><span class="sxs-lookup"><span data-stu-id="f2310-142">You can enable Call Data Connector for a particular site or for your entire Skype for Business Server deployment by using the Set-CsCloudCallDataConnectorConfiguration cmdlet from within the Skype for Business Server management shell.</span></span> <span data-ttu-id="f2310-143">例如，以下命令在全局范围启用呼叫数据连接器：</span><span class="sxs-lookup"><span data-stu-id="f2310-143">For example, the following command enables Call Data Connector at the global scope:</span></span>

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $True
```

<span data-ttu-id="f2310-144">除了全局设置之外，还可以将呼叫数据连接器配置设置分配给站点范围。</span><span class="sxs-lookup"><span data-stu-id="f2310-144">In addition to the global settings, Call Data Connector configuration settings can be assigned to the site scope.</span></span> <span data-ttu-id="f2310-145">这为监控提供了更大的管理灵活性。</span><span class="sxs-lookup"><span data-stu-id="f2310-145">This provides additional management flexibility when it comes to monitoring.</span></span> <span data-ttu-id="f2310-146">例如，管理员可以为 Redmond 站点启用呼叫数据连接器转发，但对 Dublin 站点禁用呼叫数据连接器转发，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="f2310-146">For example, an administrator can enable Call Data Connector forwarding for the Redmond site but disable Call Data Connector forwarding for the Dublin site, as shown in the following example:</span></span>

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "site:Redmond" -EnableCallDataConnector $True
```

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "site:Dublin" -EnableCallDataConnector $False
```

<span data-ttu-id="f2310-147">在 site 作用域配置的设置的优先于在 global 作用域配置的设置。</span><span class="sxs-lookup"><span data-stu-id="f2310-147">Settings configured at the site scope take precedence over settings configured at the global scope.</span></span> <span data-ttu-id="f2310-148">例如，假设呼叫数据连接器在全局范围启用，但在 Redmond 站点呼叫的站点 (禁用) 。</span><span class="sxs-lookup"><span data-stu-id="f2310-148">For example, suppose Call Data Connector forwarding is enabled at the global scope, but disabled at the site scope (for the Redmond site).</span></span> <span data-ttu-id="f2310-149">这意味着不会为 Redmond 站点中的用户转发呼叫详细信息记录和 QoE 信息。</span><span class="sxs-lookup"><span data-stu-id="f2310-149">That means that call detail recording and QoE information will not be forwarded for users in the Redmond site.</span></span> <span data-ttu-id="f2310-150">但是，其他站点 (，即由全局设置而不是 Redmond 站点设置) 管理的用户将转发其呼叫详细信息记录和 QoE 信息。</span><span class="sxs-lookup"><span data-stu-id="f2310-150">However, users in other sites (that is, users managed by the global settings instead of the Redmond site settings) will have their call detail recording and QoE information forwarded.</span></span>

<span data-ttu-id="f2310-151">下表显示了呼叫数据连接器最常用的设置的值：</span><span class="sxs-lookup"><span data-stu-id="f2310-151">Values for the most commonly used settings used by Call Data Connector are shown in the following table:</span></span>  

|<span data-ttu-id="f2310-152">属性</span><span class="sxs-lookup"><span data-stu-id="f2310-152">Property</span></span>|<span data-ttu-id="f2310-153">说明</span><span class="sxs-lookup"><span data-stu-id="f2310-153">Description</span></span>|<span data-ttu-id="f2310-154">默认值</span><span class="sxs-lookup"><span data-stu-id="f2310-154">Default value</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="f2310-155">EnableCallDataConnector</span><span class="sxs-lookup"><span data-stu-id="f2310-155">EnableCallDataConnector</span></span>  <br/> |<span data-ttu-id="f2310-156">指示是否已启用呼叫数据连接器。</span><span class="sxs-lookup"><span data-stu-id="f2310-156">Indicates whether Call Data Connector is enabled.</span></span> <span data-ttu-id="f2310-157">如果为 True，则监控记录将转发到联机监视。</span><span class="sxs-lookup"><span data-stu-id="f2310-157">If True, monitoring records will be forwarded to online monitoring.</span></span>  <br/> |<span data-ttu-id="f2310-158">$False</span><span class="sxs-lookup"><span data-stu-id="f2310-158">$False</span></span>  <br/> |
| <span data-ttu-id="f2310-159">标识</span><span class="sxs-lookup"><span data-stu-id="f2310-159">Identity</span></span> | <span data-ttu-id="f2310-160">确定命令的范围级别：全局或站点。</span><span class="sxs-lookup"><span data-stu-id="f2310-160">Determines the scope level for the command: global or site.</span></span>   | <span data-ttu-id="f2310-161">global</span><span class="sxs-lookup"><span data-stu-id="f2310-161">global</span></span>  |

## <a name="disable-call-data-connector"></a><span data-ttu-id="f2310-162">禁用呼叫数据连接器</span><span class="sxs-lookup"><span data-stu-id="f2310-162">Disable Call Data Connector</span></span>

<span data-ttu-id="f2310-163">禁用呼叫数据连接器不会解除监控存储与前端池的关联，也不会卸载或以其他方式影响后端监控数据库。</span><span class="sxs-lookup"><span data-stu-id="f2310-163">Disabling Call Data Connector does not disassociate the monitoring store from the Front End pool, nor does it uninstall or otherwise affect the backend monitoring database.</span></span> <span data-ttu-id="f2310-164">禁用呼叫数据连接器时，将阻止 Skype for Business Server 将呼叫数据上载到云。</span><span class="sxs-lookup"><span data-stu-id="f2310-164">When you disable Call Data Connector, you stop Skype for Business Server from uploading call data to the cloud.</span></span> 

<span data-ttu-id="f2310-165">通过使用 skype for Business Server 命令行管理程序内的 Set-CsCloudCallDataConnectorConfiguration cmdlet 禁用呼叫数据连接器。</span><span class="sxs-lookup"><span data-stu-id="f2310-165">You disable Call Data Connector by using the Set-CsCloudCallDataConnectorConfiguration cmdlet from within the Skype for Business Server management shell.</span></span> <span data-ttu-id="f2310-166">例如，以下命令通过设置 EnableCallDataConnector 属性来禁用全局范围的呼叫数据$False：</span><span class="sxs-lookup"><span data-stu-id="f2310-166">For example, the following command disables Call Data Connector at the global scope by setting the EnableCallDataConnector property to $False:</span></span>

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $False
```

<span data-ttu-id="f2310-167">如果要恢复将呼叫数据上载到云，将 EnableCallDataConnector 属性设置回 $True，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="f2310-167">If you want to resume uploading call data to the cloud, set the EnableCallDataConnector property back to $True, as shown in the following example:</span></span>

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $True
```

## <a name="view-on-premises-data-through-the-online-dashboard"></a><span data-ttu-id="f2310-168">通过联机仪表板查看本地数据</span><span class="sxs-lookup"><span data-stu-id="f2310-168">View on-premises data through the online dashboard</span></span>

 <span data-ttu-id="f2310-169">启用呼叫数据连接器后，可以在通话分析仪表板或通话质量仪表板上查看本地呼叫数据，如使用通话分析排查质量差和[](/skypeforbusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality)启用并使用 Microsoft Teams 和[Skype for Business Online](/MicrosoftTeams/turning-on-and-using-call-quality-dashboard)的通话质量仪表板中所述。</span><span class="sxs-lookup"><span data-stu-id="f2310-169">After Call Data Connector is enabled, you can view your on-premises call data on the Call Analytics dashboard or Call Quality Dashboard as described in  [Use Call Analytics to troubleshoot poor quality](/skypeforbusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality) and [Turn on and use Call Quality Dashboard for Microsoft Teams and Skype for Business Online](/MicrosoftTeams/turning-on-and-using-call-quality-dashboard).</span></span>

## <a name="for-more-information"></a><span data-ttu-id="f2310-170">更多信息</span><span class="sxs-lookup"><span data-stu-id="f2310-170">For more information</span></span>

<span data-ttu-id="f2310-171">有关 cmdlet 详细信息，可以使用 Skype for Business Server 命令行管理Get-Help中的 Get-Help 命令。</span><span class="sxs-lookup"><span data-stu-id="f2310-171">For more information on the cmdlets, you can use the Get-Help command from the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="f2310-172">例如：</span><span class="sxs-lookup"><span data-stu-id="f2310-172">For example:</span></span>

<span data-ttu-id="f2310-173">Get-Help Get-CsCloudCallDataConnector |more</span><span class="sxs-lookup"><span data-stu-id="f2310-173">Get-Help Get-CsCloudCallDataConnector | more</span></span>

<span data-ttu-id="f2310-174">Get-Help Set-CsCloudCallDataConnector |more</span><span class="sxs-lookup"><span data-stu-id="f2310-174">Get-Help Set-CsCloudCallDataConnector | more</span></span>

<span data-ttu-id="f2310-175">Get-Help Set-CsCloudCallDataConnectorConfiguration |more</span><span class="sxs-lookup"><span data-stu-id="f2310-175">Get-Help Set-CsCloudCallDataConnectorConfiguration | more</span></span>