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
description: 有关配置呼叫数据连接器的说明，允许使用 Skype for business Online 工具查看本地 Skype for business 中的遥测。
ms.openlocfilehash: 0354f5a1fd1b4794af29d23e0a0fc1bf49dfebd2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726922"
---
# <a name="configure-call-data-connector"></a>配置呼叫数据连接器

本文介绍如何配置呼叫数据连接器-一个可使用 Skype for business Online 通话质量仪表板（CQD）和呼叫分析（CA）工具查看 Skype for Business Server 呼叫质量数据的单一工具集。

有关呼叫数据连接器的优点和先决条件的详细信息（如角色要求和设置混合连接），请参阅[Plan Call Data Connector](plan-call-data-connector.md)。

## <a name="enable-monitoring"></a>启用监视
 
您必须在前端池监视中配置呼叫数据记录（CDR）和体验质量（QoE）数据收集（使用本地 LCSCdr 和 QoEMetrics 数据库）;否则，呼叫分析和呼叫质量仪表板将不会获得要使用的数据。 在配置呼叫数据连接器之前，请按照在[Skype For Business Server 中部署监控](../../SfbServer/deploy/deploy-monitoring/deploy-monitoring.md)中提供的步骤配置 CDR 和 QoE 以及基本监控。

> [!IMPORTANT]
> 如果前端池上未启用监控，则呼叫数据连接器将无法正常工作。

## <a name="enable-call-data-connector"></a>启用呼叫数据连接器

若要配置和启用呼叫数据连接器，您将使用以下 cmdlet：

| Cmdlet| 说明|
| :-----------------|---------------:|
| 新 CsCloudCallDataConnection | 建立联机数据收集器的联机 cmdlet。|
| CsCloudCallDataConnection | 一个用于检索现有联机数据收集器的联机 cmdlet。|  
| CsCloudCallDataConnector | 一个内部部署 cmdlet，用于检索由 CsCloudCallDataConnection cmdlet 创建的连接信息。 |
| CsCloudCallDataConnector | 一个本地 cmdlet，用于保存由 CsCloudCallDataConnection cmdlet 创建的连接信息的本地副本。 |  
| CsCloudCallDataConnectorConfiguration | 允许您启用或禁用连接器并自定义范围级别的本地 cmdlet。|

> [!NOTE]
> 若要擦除您的配置并重新开始，请使用 csclouddatconnectorconfiguration cmdlet。

### <a name="configure-your-environment"></a>配置环境 

若要将环境配置为启用联机数据收集器，必须先以管理员身份登录到 Skype for Business Online PowerShell。 有关详细信息，请参阅[使用 Office 365 PowerShell 管理 Skype For Business Online](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)。

有两种方法可以登录到 Skype for business Online PowerShell：

- 从 Skype for Business Server 2019 命令行管理程序（推荐方法）
- 从另一个 PowerShell 会话

#### <a name="log-in-to-skype-for-business-online-powershell-from-the-skype-for-business-server-management-shell-recommended-method"></a>从 Skype for Business Server 命令行管理程序（推荐方法）登录到 Skype for business Online PowerShell

1. 如果是第一次启用连接器，请运行以下命令：

   ```PowerShell
   New-CsCloudCallDataConnection | Set-CsCloudCallDataConnector -TenantId <tenant_id>
   ```

2. 如果遇到连接已存在的错误，则表示您的租户的呼叫数据连接已存在。 在这种情况下，请运行以下命令： 

   ```PowerShell
   Get-CsCloudCallDataConnection | Set-CsCloudCallDataConnector -TenantId <tenant_id>
   ```


#### <a name="log-in-to-skype-for-business-online-powershell-from-another-powershell-session-optional-method"></a>从另一个 PowerShell 会话登录到 Skype for Business Online PowerShell （可选方法）

1.  如果是第一次启用连接器，请运行以下命令： 

    ```PowerShell 
    New-CsCloudCallDataConnection 
    ```

2.  如果遇到连接已存在的错误，则表示您的租户的呼叫数据连接已存在。 在这种情况下，请运行以下命令： 

    ```PowerShell
    Get-CsCloudCallDataConnection  
    ```

上面的命令的输出包含一个令牌值，在配置本地环境时，您将需要执行以下操作：

在 Skype for Business Server 命令行管理程序中，指定以下命令：

```PowerShell
Set-CsCloudCallDataConnector -Identity Global -TenantId <tenant_id> -Token <token-copied-from-online>
```

### <a name="configure-the-scope"></a>配置作用域

您可以使用 Skype for Business Server 命令行管理程序中的 CsCloudCallDataConnectorConfiguration cmdlet 为特定网站或整个 Skype for Business Server 部署启用呼叫数据连接器。 例如，以下命令在全局范围内启用呼叫数据连接器：

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $True
```

除了全局设置，可以将呼叫数据连接器配置设置分配给网站范围。 这在监视方面提供了更多管理灵活性。 例如，管理员可以为 Redmond 站点启用呼叫数据连接器转发，但禁用了都柏林网站的呼叫数据连接器转发，如以下示例所示：

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "site:Redmond" -EnableCallDataConnector $True
```

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "site:Dublin" -EnableCallDataConnector $False
```

在 site 作用域配置的设置的优先于在 global 作用域配置的设置。 例如，假设在全局范围内启用了呼叫数据连接器转发，但在站点范围（针对 Redmond 站点）禁用了此功能。 这意味着不会为 Redmond 站点中的用户转发呼叫详细记录和 QoE 信息。 但是，其他网站中的用户（即由全局设置（而不是 Redmond 网站设置）管理的用户将会有呼叫详细记录和转发 QoE 信息。

下表显示了呼叫数据连接器使用的最常用设置的值：  

|属性|说明|默认值|
|:-----|:-----|:-----|
|EnableCallDataConnector  <br/> |指示是否已启用呼叫数据连接器。 如果为 True，则会将监视记录转发到联机监控。  <br/> |$False  <br/> |
| 标识 | 确定命令的范围级别： global 或 site。   | 全局性  |

## <a name="disable-call-data-connector"></a>禁用呼叫数据连接器

禁用呼叫数据连接器不会解除监视存储与前端池的关联，也不会卸载或以其他方式影响后端监控数据库。 禁用呼叫数据连接器时，将停止将 Skype for Business Server 上传到云的呼叫数据。 

您可以通过在 Skype for Business Server 命令行管理程序中使用 CsCloudCallDataConnectorConfiguration cmdlet 禁用呼叫数据连接器。 例如，以下命令通过将 EnableCallDataConnector 属性设置为 $False 来禁用全局范围的调用数据连接器：

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $False
```

如果要恢复向云上载调用数据，请将 EnableCallDataConnector 属性设置回 $True，如下面的示例所示：

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $True
```

## <a name="view-on-premises-data-through-the-online-dashboard"></a>通过联机仪表板查看本地数据

 启用呼叫数据连接器后，您可以在 "呼叫分析" 仪表板或 "呼叫质量" 仪表板上查看本地呼叫数据，如[使用呼叫分析来解决质量较差](https://docs.microsoft.com/skypeforbusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality)和[打开和使用 Microsoft 团队和 Skype for Business Online 的呼叫质量仪表板](/MicrosoftTeams/turning-on-and-using-call-quality-dashboard)中所述。

## <a name="for-more-information"></a>更多详细信息

有关 cmdlet 的详细信息，可以使用 Skype for Business Server 命令行管理程序中的 Get-Help 命令。 例如：

Get-help CsCloudCallDataConnector |多

Get-help CsCloudCallDataConnector |多

Get-help CsCloudCallDataConnectorConfiguration |多
