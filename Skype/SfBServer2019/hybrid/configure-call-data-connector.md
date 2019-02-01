---
title: 配置呼叫数据连接器
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: 有关配置呼叫数据连接器，从而遥测从 Skype 的业务的本地业务在线工具使用 Skype 查看说明。
ms.openlocfilehash: 4b358562838cfd1412891514e999f2c8544f3a4f
ms.sourcegitcommit: 183a2e40af762e6ab36f05ee8ed31a98e8b8be57
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/01/2019
ms.locfileid: "29690457"
---
# <a name="configure-call-data-connector"></a><span data-ttu-id="8868b-103">配置呼叫数据连接器</span><span class="sxs-lookup"><span data-stu-id="8868b-103">Configure Call Data Connector</span></span>

<span data-ttu-id="8868b-104">本文介绍如何配置呼叫数据连接器-允许查看 Skype 业务服务器呼叫质量数据的业务联机呼叫质量仪表板 (CQD) 和呼叫分析 (CA) 工具使用 Skype 一个工具集。</span><span class="sxs-lookup"><span data-stu-id="8868b-104">This article describes how to configure Call Data Connector--a single toolset that enables viewing Skype for Business Server Call Quality Data using Skype for Business Online Call Quality Dashboard (CQD) and Call Analytics (CA) tools.</span></span> 

> [!NOTE]
> <span data-ttu-id="8868b-105">在公共预览发布，只呼叫分析仪表板才可用。</span><span class="sxs-lookup"><span data-stu-id="8868b-105">At public preview release, only Call Analytics dashboard is available.</span></span>

<span data-ttu-id="8868b-106">有关呼叫数据连接器的优点和必备组件，如角色的要求和混合连接性设置的详细信息，请参阅[规划呼叫数据连接器](plan-call-data-connector.md)。</span><span class="sxs-lookup"><span data-stu-id="8868b-106">For more information about Call Data Connector benefits and pre-requisites, such as role requirements and setting up hybrid connectivity, see [Plan Call Data Connector](plan-call-data-connector.md).</span></span>

## <a name="enable-monitoring"></a><span data-ttu-id="8868b-107">启用监控</span><span class="sxs-lookup"><span data-stu-id="8868b-107">Enable Monitoring</span></span>
 
<span data-ttu-id="8868b-108">您必须配置呼叫数据记录 (CDR) 和用户体验质量 (QoE) 中的数据收集您的前端池与本地 LcsCDR 和 QoEMetrics 数据库; 监控否则，呼叫分析和呼叫质量仪表板不会收到要处理的数据。</span><span class="sxs-lookup"><span data-stu-id="8868b-108">You must configure Call Data Recording (CDR) and Quality of Experience (QoE) data collection in your front end pool Monitoring,with local LcsCDR and QoEMetrics databases; otherwise, the Call Analytics and Call Quality Dashboards won’t get data to work with.</span></span> <span data-ttu-id="8868b-109">之前您配置呼叫数据连接器，请按照[部署监控 Skype 业务服务器中](../../SfbServer/deploy/deploy-monitoring/deploy-monitoring.md)配置 QoE 和 CDR 以及基本监控中提供的步骤。</span><span class="sxs-lookup"><span data-stu-id="8868b-109">Before you Configure Call Data Connector, follow the steps provided in [Deploy monitoring in Skype for Business Server](../../SfbServer/deploy/deploy-monitoring/deploy-monitoring.md) to configure both CDR and QoE as well as basic Monitoring.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8868b-110">如果在前端池上没有启用监控，将无法正常呼叫数据连接器。</span><span class="sxs-lookup"><span data-stu-id="8868b-110">Call Data Connector will not function if Monitoring is not enabled on the front end pool.</span></span>

## <a name="enable-call-data-connector"></a><span data-ttu-id="8868b-111">启用呼叫数据连接器</span><span class="sxs-lookup"><span data-stu-id="8868b-111">Enable Call Data Connector</span></span>

<span data-ttu-id="8868b-112">若要配置并启用呼叫数据连接器，您将使用以下 cmdlet:</span><span class="sxs-lookup"><span data-stu-id="8868b-112">To configure and enable Call Data Connector, you will use the following cmdlets:</span></span>

| <span data-ttu-id="8868b-113">Cmdlet</span><span class="sxs-lookup"><span data-stu-id="8868b-113">Cmdlet</span></span>| <span data-ttu-id="8868b-114">描述</span><span class="sxs-lookup"><span data-stu-id="8868b-114">Description</span></span>|
| :-----------------|---------------:|
| <span data-ttu-id="8868b-115">新 CsCloudCallDataConnection</span><span class="sxs-lookup"><span data-stu-id="8868b-115">New-CsCloudCallDataConnection</span></span> | <span data-ttu-id="8868b-116">建立 online 数据收集器 online cmdlet。</span><span class="sxs-lookup"><span data-stu-id="8868b-116">An online cmdlet that establishes an online data collector.</span></span>|
| <span data-ttu-id="8868b-117">Get CsCloudCallDataConnection</span><span class="sxs-lookup"><span data-stu-id="8868b-117">Get-CsCloudCallDataConnection</span></span> | <span data-ttu-id="8868b-118">检索现有 online 数据收集器 online cmdlet。</span><span class="sxs-lookup"><span data-stu-id="8868b-118">An online cmdlet that retrieves an existing online data collector.</span></span>|  
| <span data-ttu-id="8868b-119">Get CsCloudCallDataConnector</span><span class="sxs-lookup"><span data-stu-id="8868b-119">Get-CsCloudCallDataConnector</span></span> | <span data-ttu-id="8868b-120">在本地 cmdlet 检索通过新建 CsCloudCallDataConnection cmdlet 创建的连接信息。</span><span class="sxs-lookup"><span data-stu-id="8868b-120">An on-premises cmdlet that retrieves the connection information created by the New-CsCloudCallDataConnection cmdlet.</span></span> |
| <span data-ttu-id="8868b-121">设置 CsCloudCallDataConnector</span><span class="sxs-lookup"><span data-stu-id="8868b-121">Set-CsCloudCallDataConnector</span></span> | <span data-ttu-id="8868b-122">保存通过新建 CsCloudCallDataConnection cmdlet 创建的连接信息的本地副本的本地 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="8868b-122">An on-premises cmdlet that saves an on-premises copy of the connection information created by the New-CsCloudCallDataConnection cmdlet.</span></span> |  
| <span data-ttu-id="8868b-123">设置 CsCloudCallDataConnectorConfiguration</span><span class="sxs-lookup"><span data-stu-id="8868b-123">Set-CsCloudCallDataConnectorConfiguration</span></span> | <span data-ttu-id="8868b-124">在本地 cmdlet，使您能够启用或禁用连接器和自定义作用域级别。</span><span class="sxs-lookup"><span data-stu-id="8868b-124">An on-premises cmdlet that allows you to enable or disable the connector and customize the scope level.</span></span>|

### <a name="configure-your-environment"></a><span data-ttu-id="8868b-125">配置环境</span><span class="sxs-lookup"><span data-stu-id="8868b-125">Configure your environment</span></span> 

<span data-ttu-id="8868b-126">若要配置您的环境以启用联机数据收集器，您必须首先以登录到 Skype 业务 Online PowerShell 中的管理员。</span><span class="sxs-lookup"><span data-stu-id="8868b-126">To configure your environment to enable an online data collector, you must first log in to Skype for Business Online PowerShell as an administrator.</span></span> <span data-ttu-id="8868b-127">有关详细信息，请参阅[管理业务 online 与 Office 365 PowerShell 中的 Skype](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)。</span><span class="sxs-lookup"><span data-stu-id="8868b-127">For more information, see [Manage Skype for Business Online with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).</span></span>

<span data-ttu-id="8868b-128">有两种方法，用于登录到 Skype 并业务 Online PowerShell 中：</span><span class="sxs-lookup"><span data-stu-id="8868b-128">There are two methods for logging in to Skype for Business Online PowerShell:</span></span>

- <span data-ttu-id="8868b-129">从业务服务器 2019年命令行管理程序 （推荐方法） 的 Skype</span><span class="sxs-lookup"><span data-stu-id="8868b-129">From the Skype for Business Server 2019 management shell (recommended method)</span></span>
- <span data-ttu-id="8868b-130">从另一个 PowerShell 会话</span><span class="sxs-lookup"><span data-stu-id="8868b-130">From another PowerShell session</span></span>

#### <a name="log-in-to-skype-for-business-online-powershell-from-the-skype-for-business-server-management-shell-recommended-method"></a><span data-ttu-id="8868b-131">登录到 Skype 的业务 Online PowerShell 从 Business Server 命令行管理程序 （推荐方法） 的 Skype</span><span class="sxs-lookup"><span data-stu-id="8868b-131">Log in to Skype for Business Online PowerShell from the Skype for Business Server management shell (recommended method)</span></span>

1. <span data-ttu-id="8868b-132">如果第一次启用连接器，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="8868b-132">If enabling the connector for the first time, run the following command:</span></span>

   ```
   New-CsCloudCallDataConnection | Set-CsCloudCallDataConnector -TenantId <tenant_id>
   ```

2. <span data-ttu-id="8868b-133">如果您收到一条错误，连接已存在，这意味着调用数据连接已存在租户。</span><span class="sxs-lookup"><span data-stu-id="8868b-133">If you get an error that the connection already exists, this means that the call data connection already exists for your tenant.</span></span> <span data-ttu-id="8868b-134">在这种情况下，运行命令：</span><span class="sxs-lookup"><span data-stu-id="8868b-134">In this case, run the command:</span></span> 

   ```
   Get-CsCloudCallDataConnection | Set-CsCloudCallDataConnector -TenantId <tenant_id>
   ```


#### <a name="log-in-to-skype-for-business-online-powershell-from-another-powershell-session-optional-method"></a><span data-ttu-id="8868b-135">登录到 Skype 的业务 Online PowerShell 从另一个 PowerShell 会话 （可选方法）</span><span class="sxs-lookup"><span data-stu-id="8868b-135">Log in to Skype for Business Online PowerShell from another PowerShell session (optional method)</span></span>

1.  <span data-ttu-id="8868b-136">如果第一次启用连接器，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="8868b-136">If enabling the connector for the first time, run the following command:</span></span> 

    ``` 
    New-CsCloudCallDataConnection 
    ```

2.  <span data-ttu-id="8868b-137">如果您收到一条错误，连接已存在，这意味着调用数据连接已存在租户。</span><span class="sxs-lookup"><span data-stu-id="8868b-137">If you get an error that the connection already exists, this means that the call data connection already exists for your tenant.</span></span> <span data-ttu-id="8868b-138">在这种情况下，运行命令：</span><span class="sxs-lookup"><span data-stu-id="8868b-138">In this case, run the command:</span></span> 

    ```
    Get-CsCloudCallDataConnection  
    ```

<span data-ttu-id="8868b-139">上述命令的输出包含一个令牌值，该值，如下所示配置您的本地环境时，您将需要：</span><span class="sxs-lookup"><span data-stu-id="8868b-139">The output of the above commands contains a token value, which you will need when configuring your on-premises environment as follows:</span></span>

<span data-ttu-id="8868b-140">从业务 Server 命令行管理程序 Skype 中指定以下命令：</span><span class="sxs-lookup"><span data-stu-id="8868b-140">From within the Skype for Business Server management shell, specify the following command:</span></span>

```
Set-CsCloudCallDataConnector -Identity Global -TenantId <tenant_id> -Token <token-copied-from-online>
```

### <a name="configure-the-scope"></a><span data-ttu-id="8868b-141">配置作用域</span><span class="sxs-lookup"><span data-stu-id="8868b-141">Configure the scope</span></span>

<span data-ttu-id="8868b-142">使用 for Business Server 命令行管理程序中 Skype 集 CsCloudCallDataConnectorConfiguration cmdlet，可以为特定站点或业务服务器部署在整个 Skype 启用呼叫数据连接器。</span><span class="sxs-lookup"><span data-stu-id="8868b-142">You can enable Call Data Connector for a particular site or for your entire Skype for Business Server deployment by using the Set-CsCloudCallDataConnectorConfiguration cmdlet from within the Skype for Business Server management shell.</span></span> <span data-ttu-id="8868b-143">例如，以下命令可使呼叫在全局范围内的数据连接器：</span><span class="sxs-lookup"><span data-stu-id="8868b-143">For example, the following command enables Call Data Connector at the global scope:</span></span>

```
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $True
```

<span data-ttu-id="8868b-144">除了全局设置中，调用数据连接器配置设置可分配给站点作用域。</span><span class="sxs-lookup"><span data-stu-id="8868b-144">In addition to the global settings, Call Data Connector configuration settings can be assigned to the site scope.</span></span> <span data-ttu-id="8868b-145">当谈到监控，这可以提供额外的管理灵活性。</span><span class="sxs-lookup"><span data-stu-id="8868b-145">This provides additional management flexibility when it comes to monitoring.</span></span> <span data-ttu-id="8868b-146">例如，管理员可以启用为 Redmond 站点的呼叫数据连接器转发，但禁用都柏林网站中，调用数据连接器转发，如下面的示例中所示：</span><span class="sxs-lookup"><span data-stu-id="8868b-146">For example, an administrator can enable Call Data Connector forwarding for the Redmond site but disable Call Data Connector forwarding for the Dublin site, as shown in the following example:</span></span>

```
Set-CsCloudCallDataConnectorConfiguration -Identity "site:Redmond" -EnableCallDataConnector $True
```

```
Set-CsCloudCallDataConnectorConfiguration -Identity "site:Dublin" -EnableCallDataConnector $False
```

<span data-ttu-id="8868b-147">在 site 作用域配置的设置的优先于在 global 作用域配置的设置。</span><span class="sxs-lookup"><span data-stu-id="8868b-147">Settings configured at the site scope take precedence over settings configured at the global scope.</span></span> <span data-ttu-id="8868b-148">例如，假设调用数据连接器转接已启用在全局范围内，但是禁用在站点范围 （对于 Redmond 站点）。</span><span class="sxs-lookup"><span data-stu-id="8868b-148">For example, suppose Call Data Connector forwarding is enabled at the global scope, but disabled at the site scope (for the Redmond site).</span></span> <span data-ttu-id="8868b-149">不会为 Redmond 站点中的用户转发呼叫详细信息记录和 QoE 信息的方法。</span><span class="sxs-lookup"><span data-stu-id="8868b-149">That means that call detail recording and QoE information will not be forwarded for users in the Redmond site.</span></span> <span data-ttu-id="8868b-150">但是，在其他网站 （即，由全局设置而非雷德蒙德站点设置管理的用户） 中的用户将有其呼叫详细信息记录和 QoE 信息转发。</span><span class="sxs-lookup"><span data-stu-id="8868b-150">However, users in other sites (that is, users managed by the global settings instead of the Redmond site settings) will have their call detail recording and QoE information forwarded.</span></span>

<span data-ttu-id="8868b-151">下表中所示使用调用数据连接器的最常用设置的值：</span><span class="sxs-lookup"><span data-stu-id="8868b-151">Values for the most commonly used settings used by Call Data Connector are shown in the following table:</span></span>  

|<span data-ttu-id="8868b-152">属性</span><span class="sxs-lookup"><span data-stu-id="8868b-152">Property</span></span>|<span data-ttu-id="8868b-153">说明</span><span class="sxs-lookup"><span data-stu-id="8868b-153">Description</span></span>|<span data-ttu-id="8868b-154">默认值</span><span class="sxs-lookup"><span data-stu-id="8868b-154">Default value</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="8868b-155">EnableCallDataConnector</span><span class="sxs-lookup"><span data-stu-id="8868b-155">EnableCallDataConnector</span></span>  <br/> |<span data-ttu-id="8868b-156">指示是否启用呼叫数据连接器。</span><span class="sxs-lookup"><span data-stu-id="8868b-156">Indicates whether Call Data Connector is enabled.</span></span> <span data-ttu-id="8868b-157">如果为 True，则会向联机监视转接监控记录。</span><span class="sxs-lookup"><span data-stu-id="8868b-157">If True, monitoring records will be forwarded to online monitoring.</span></span>  <br/> |<span data-ttu-id="8868b-158">$False</span><span class="sxs-lookup"><span data-stu-id="8868b-158">$False</span></span>  <br/> |
| <span data-ttu-id="8868b-159">Identity </span><span class="sxs-lookup"><span data-stu-id="8868b-159">Identity</span></span> | <span data-ttu-id="8868b-160">确定该命令的作用域级别： 全局或站点。</span><span class="sxs-lookup"><span data-stu-id="8868b-160">Determines the scope level for the command: global or site.</span></span>   | <span data-ttu-id="8868b-161">全局</span><span class="sxs-lookup"><span data-stu-id="8868b-161">global</span></span>  |

## <a name="disable-call-data-connector"></a><span data-ttu-id="8868b-162">禁用呼叫数据连接器</span><span class="sxs-lookup"><span data-stu-id="8868b-162">Disable Call Data Connector</span></span>

<span data-ttu-id="8868b-163">禁用呼叫数据连接器不解除关联监控存储与前端池，也不会卸载或否则影响监控后端数据库。</span><span class="sxs-lookup"><span data-stu-id="8868b-163">Disabling Call Data Connector does not disassociate the monitoring store from the Front End pool, nor does it uninstall or otherwise affect the backend monitoring database.</span></span> <span data-ttu-id="8868b-164">禁用呼叫数据连接器时，您停止 Skype 业务服务器从呼叫数据上载到云。</span><span class="sxs-lookup"><span data-stu-id="8868b-164">When you disable Call Data Connector, you stop Skype for Business Server from uploading call data to the cloud.</span></span> 

<span data-ttu-id="8868b-165">使用适用于 Business Server 命令行管理程序中 Skype 集 CsCloudCallDataConnectorConfiguration cmdlet 禁用呼叫数据连接器。</span><span class="sxs-lookup"><span data-stu-id="8868b-165">You disable Call Data Connector by using the Set-CsCloudCallDataConnectorConfiguration cmdlet from within the Skype for Business Server management shell.</span></span> <span data-ttu-id="8868b-166">例如，下面的命令通过 EnableCallDataConnector 属性设置为 $False 禁用呼叫在全局范围内的数据连接器：</span><span class="sxs-lookup"><span data-stu-id="8868b-166">For example, the following command disables Call Data Connector at the global scope by setting the EnableCallDataConnector property to $False:</span></span>

```
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $False
```

<span data-ttu-id="8868b-167">如果您想要恢复呼叫数据上载到云，将设置回 $True，EnableCallDataConnector 属性，如下面的示例中所示：</span><span class="sxs-lookup"><span data-stu-id="8868b-167">If you want to resume uploading call data to the cloud, set the EnableCallDataConnector property back to $True, as shown in the following example:</span></span>

```
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $True
```

## <a name="view-on-premises-data-through-the-online-dashboard"></a><span data-ttu-id="8868b-168">查看本地通过联机仪表板的数据</span><span class="sxs-lookup"><span data-stu-id="8868b-168">View on-premises data through the online dashboard</span></span>

 <span data-ttu-id="8868b-169">启用呼叫数据连接器后，您可以查看您的本地呼叫数据上调用分析仪表板[使用调用分析解决质量不佳](https://docs.microsoft.com/skypeforbusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality)中所述。</span><span class="sxs-lookup"><span data-stu-id="8868b-169">After Call Data Connector is enabled, you can view your on-premises call data on the Call Analytics dashboard as described in  [Use Call Analytics to troubleshoot poor quality](https://docs.microsoft.com/skypeforbusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality).</span></span>


## <a name="for-more-information"></a><span data-ttu-id="8868b-170">有关详细信息</span><span class="sxs-lookup"><span data-stu-id="8868b-170">For more information</span></span>

<span data-ttu-id="8868b-171">有关这些 cmdlet 的详细信息，可用于业务 Server 命令行管理程序 Skype Get-help 命令。</span><span class="sxs-lookup"><span data-stu-id="8868b-171">For more information on the cmdlets, you can use the Get-Help command from the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="8868b-172">例如：</span><span class="sxs-lookup"><span data-stu-id="8868b-172">For example:</span></span>

<span data-ttu-id="8868b-173">获取帮助 Get CsCloudCallDataConnector |更多</span><span class="sxs-lookup"><span data-stu-id="8868b-173">Get-Help Get-CsCloudCallDataConnector | more</span></span>

<span data-ttu-id="8868b-174">获取帮助设置 CsCloudCallDataConnector |更多</span><span class="sxs-lookup"><span data-stu-id="8868b-174">Get-Help Set-CsCloudCallDataConnector | more</span></span>

<span data-ttu-id="8868b-175">获取帮助设置 CsCloudCallDataConnectorConfiguration |更多</span><span class="sxs-lookup"><span data-stu-id="8868b-175">Get-Help Set-CsCloudCallDataConnectorConfiguration | more</span></span>
