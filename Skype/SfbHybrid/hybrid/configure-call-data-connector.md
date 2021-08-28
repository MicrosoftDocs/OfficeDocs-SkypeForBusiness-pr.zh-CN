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
ms.localizationpriority: medium
ms.collection: ''
description: 有关配置呼叫数据连接器的说明，该连接器允许使用 Skype for Business Online 工具查看本地Skype for Business遥测。
ms.openlocfilehash: 0e064e26ce7b8bfb97793666808b0b8a88ab2efc
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58581146"
---
# <a name="configure-call-data-connector"></a>配置呼叫数据连接器

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]


本文介绍如何配置呼叫数据连接器，这是一个工具集，支持使用 Skype for Business Online 呼叫质量仪表板 (CQD) 和 Call Analytics (CA) 工具查看 Skype for Business Server 通话质量数据。

有关呼叫数据连接器的好处和先决条件（如角色要求和设置混合连接）详细信息，请参阅规划 [呼叫数据连接器](plan-call-data-connector.md)。

## <a name="enable-monitoring"></a>启用监控
 
必须使用本地 LCSCdr 和 QoEMetrics 数据库在前端池监控中配置呼叫数据记录 (CDR) 和用户体验质量 (QoE) 数据收集;否则，通话分析和通话质量仪表板将不会获得要处理的数据。 配置呼叫数据连接器之前，请按照在 Skype for Business Server 部署[](../../SfbServer/deploy/deploy-monitoring/deploy-monitoring.md)监控中提供的步骤配置 CDR 和 QoE 以及基本监控。

> [!IMPORTANT]
> 如果未在前端池上启用监控，呼叫数据连接器将无法正常工作。

## <a name="enable-call-data-connector"></a>启用呼叫数据连接器

若要配置和启用呼叫数据连接器，您将使用以下 cmdlet：

| Cmdlet| 说明|
| :-----------------|---------------:|
| New-CsCloudCallDataConnection | 建立联机数据收集器的联机 cmdlet。|
| Get-CsCloudCallDataConnection | 检索现有联机数据收集器的联机 cmdlet。|  
| Get-CsCloudCallDataConnector | 一个本地 cmdlet，用于检索由 New-CsCloudCallDataConnection cmdlet 创建的连接信息。 |
| Set-CsCloudCallDataConnector | 本地 cmdlet，用于保存由 New-CsCloudCallDataConnection cmdlet 创建的连接信息本地副本。 |  
| Set-CsCloudCallDataConnectorConfiguration | 允许启用或禁用连接器并自定义范围级别的本地 cmdlet。|

> [!NOTE]
> 若要擦除配置并重新开始，请使用 Remove-csclouddatconnectorconfiguration cmdlet。

### <a name="configure-your-environment"></a>配置环境 

若要配置环境以启用联机数据收集器，必须先以管理员Skype for Business联机 PowerShell 登录。 有关详细信息，请参阅使用[Skype for Business PowerShell 管理 Office 365 Online。](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)

有两种方法可以登录到 Skype for Business Online PowerShell：

- 从 Skype for Business Server 2019 命令行管理程序 (推荐的方法) 
- 从另一个 PowerShell 会话

#### <a name="log-in-to-skype-for-business-online-powershell-from-the-skype-for-business-server-management-shell-recommended-method"></a>从命令行Skype for Business命令行管理程序Skype for Business Server联机 PowerShell (推荐) 

1. 如果是首次启用连接器，请运行以下命令：

   ```PowerShell
   New-CsCloudCallDataConnection | Set-CsCloudCallDataConnector -TenantId <tenant_id>
   ```

2. 如果收到连接已存在的错误，这意味着租户的呼叫数据连接已存在。 在这种情况下，请运行以下命令： 

   ```PowerShell
   Get-CsCloudCallDataConnection | Set-CsCloudCallDataConnector -TenantId <tenant_id>
   ```


#### <a name="log-in-to-skype-for-business-online-powershell-from-another-powershell-session-optional-method"></a>通过可选Skype for Business另一个 PowerShell 会话 (联机 PowerShell) 

1.  如果是首次启用连接器，请运行以下命令： 

    ```PowerShell 
    New-CsCloudCallDataConnection 
    ```

2.  如果收到连接已存在的错误，这意味着租户的呼叫数据连接已存在。 在这种情况下，请运行以下命令： 

    ```PowerShell
    Get-CsCloudCallDataConnection  
    ```

上述命令的输出包含一个令牌值，在配置本地环境时将需要此值，如下所示：

在命令行Skype for Business Server中，指定以下命令：

```PowerShell
Set-CsCloudCallDataConnector -Identity Global -TenantId <tenant_id> -Token <token-copied-from-online>
```

### <a name="configure-the-scope"></a>配置作用域

可以在命令行管理程序内使用 Set-CsCloudCallDataConnectorConfiguration cmdlet 为特定站点或整个 Skype for Business Server 部署启用呼叫数据Skype for Business Server连接器。 例如，以下命令在全局范围启用呼叫数据连接器：

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $True
```

除了全局设置之外，还可以将呼叫数据连接器配置设置分配给站点范围。 这为监控提供了更大的管理灵活性。 例如，管理员可以为 Redmond 站点启用呼叫数据连接器转发，但对 Dublin 站点禁用呼叫数据连接器转发，如以下示例所示：

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "site:Redmond" -EnableCallDataConnector $True
```

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "site:Dublin" -EnableCallDataConnector $False
```

在 site 作用域配置的设置的优先于在 global 作用域配置的设置。 例如，假设呼叫数据连接器在全局范围启用，但在 Redmond 站点呼叫的站点 (禁用) 。 这意味着不会为 Redmond 站点中的用户转发呼叫详细信息记录和 QoE 信息。 但是，其他站点 (，即由全局设置而不是 Redmond 站点设置) 管理的用户将转发其呼叫详细信息记录和 QoE 信息。

下表显示了呼叫数据连接器最常用的设置的值：  

|属性|说明|默认值|
|:-----|:-----|:-----|
|EnableCallDataConnector  <br/> |指示是否已启用呼叫数据连接器。 如果为 True，则监控记录将转发到联机监视。  <br/> |$False  <br/> |
| 标识 | 确定命令的范围级别：全局或站点。   | global  |

## <a name="disable-call-data-connector"></a>禁用呼叫数据连接器

禁用呼叫数据连接器不会解除监控存储与前端池的关联，也不会卸载或以其他方式影响后端监控数据库。 禁用呼叫数据连接器时，Skype for Business Server将呼叫数据上传到云。 

通过使用命令行管理程序内的 Set-CsCloudCallDataConnectorConfiguration cmdlet 禁用呼叫Skype for Business Server连接器。 例如，以下命令通过设置 EnableCallDataConnector 属性来禁用全局范围的呼叫数据$False：

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $False
```

如果要恢复将呼叫数据上载到云，请重新将 EnableCallDataConnector 属性设置为 $True，如以下示例所示：

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $True
```

## <a name="view-on-premises-data-through-the-online-dashboard"></a>通过联机仪表板查看本地数据

 启用呼叫数据连接器后，可以在通话分析仪表板或通话质量仪表板上查看本地呼叫数据，如使用通话分析解决质量差问题以及[](/skypeforbusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality)启用并使用 Microsoft Teams 和 Skype for Business [Online](/MicrosoftTeams/turning-on-and-using-call-quality-dashboard)的通话质量仪表板中所述。

## <a name="for-more-information"></a>详细信息

有关 cmdlet 详细信息，可以使用命令行管理Get-Help中的 Skype for Business Server 命令。 例如：

Get-Help Get-CsCloudCallDataConnector |more

Get-Help Set-CsCloudCallDataConnector |more

Get-Help Set-CsCloudCallDataConnectorConfiguration |more