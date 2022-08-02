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
description: 有关配置呼叫数据连接器的说明，该连接器允许使用 Skype for Business Online 工具查看来自Skype for Business本地的遥测数据。
ms.openlocfilehash: 0d92d31798cd4b3fb5a1b4c555ff0ff00c2bdf31
ms.sourcegitcommit: 07761c26b53d92fc36b82cab7b3e38a6de4ff945
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/02/2022
ms.locfileid: "67156930"
---
# <a name="configure-call-data-connector"></a>配置呼叫数据连接器

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]


本文介绍如何配置呼叫数据连接器，这是一个单一工具集，可使用 Microsoft 呼叫质量仪表板 (CQD) 和调用分析查看Skype for Business Server调用质量数据， (CA) 工具。

有关呼叫数据连接器权益和先决条件（例如角色要求和设置混合连接）的详细信息，请参阅 [计划呼叫数据连接器](plan-call-data-connector.md)。

## <a name="enable-monitoring"></a>启用监视
 
必须使用本地 LCSCdr 和 QoEMetrics 数据库在前端池监视中配置呼叫数据记录 (CDR) 和体验质量 (QoE) 数据收集;否则，呼叫分析和呼叫质量仪表板将无法获取要处理的数据。 在配置呼叫数据连接器之前，请按照[在 Skype for Business Server 中部署监视中](../../SfbServer/deploy/deploy-monitoring/deploy-monitoring.md)提供的步骤来配置 CDR 和 QoE 以及基本监视。

> [!IMPORTANT]
> 如果前端池上未启用监视，则调用数据连接器将不起作用。

## <a name="enable-call-data-connector"></a>启用呼叫数据连接器

若要配置和启用呼叫数据连接器，将使用以下 cmdlet：

| Cmdlet| 说明|
| :-----------------|---------------:|
| New-CsCloudCallDataConnection | 建立联机数据收集器的联机 cmdlet。|
| Get-CsCloudCallDataConnection | 用于检索现有联机数据收集器的联机 cmdlet。|  
| Get-CsCloudCallDataConnector | 一个本地 cmdlet，用于检索由New-CsCloudCallDataConnection cmdlet 创建的连接信息。 |
| Set-CsCloudCallDataConnector | 一个本地 cmdlet，用于保存由New-CsCloudCallDataConnection cmdlet 创建的连接信息的本地副本。 |  
| Set-CsCloudCallDataConnectorConfiguration | 一个本地 cmdlet，可用于启用或禁用连接器并自定义范围级别。|

> [!NOTE]
> 若要擦除配置并重新开始，请使用 Remove-csclouddatconnectorconfiguration cmdlet。

### <a name="configure-your-environment"></a>配置环境 

若要将环境配置为启用联机数据收集器，必须先以管理员身份登录到 Microsoft Teams PowerShell 模块。 有关详细信息，请参阅 [Microsoft Teams PowerShell 概述](/microsoftteams/teams-powershell-overview)。

有两种方法可用于登录到 Microsoft Teams PowerShell 模块：

- 从 Skype for Business Server 2019 管理外壳 (建议的方法) 
- 从另一个 PowerShell 会话

#### <a name="log-in-to-microsoft-teams-powershell-module-from-the-skype-for-business-server-management-shell-recommended-method"></a>从 Skype for Business Server 管理 shell 登录到 Microsoft Teams PowerShell 模块 (建议的方法) 

1. 如果首次启用连接器，请运行以下命令：

   ```PowerShell
   New-CsCloudCallDataConnection | Set-CsCloudCallDataConnector -TenantId <tenant_id>
   ```

2. 如果收到连接已存在的错误，则表示租户已存在调用数据连接。 在这种情况下，请运行以下命令： 

   ```PowerShell
   Get-CsCloudCallDataConnection | Set-CsCloudCallDataConnector -TenantId <tenant_id>
   ```


#### <a name="log-in-to-microsoft-teams-powershell-module-from-another-powershell-session-optional-method"></a>从另一个 PowerShell 会话登录到 Microsoft Teams PowerShell 模块 (可选方法) 

1.  如果首次启用连接器，请运行以下命令： 

    ```PowerShell 
    New-CsCloudCallDataConnection 
    ```

2.  如果收到连接已存在的错误，则表示租户已存在调用数据连接。 在这种情况下，请运行以下命令： 

    ```PowerShell
    Get-CsCloudCallDataConnection  
    ```

上述命令的输出包含一个令牌值，在配置本地环境时需要该值，如下所示：

在 Skype for Business Server 管理外壳中，指定以下命令：

```PowerShell
Set-CsCloudCallDataConnector -Identity Global -TenantId <tenant_id> -Token <token-copied-from-online>
```

### <a name="configure-the-scope"></a>配置作用域

可以使用Skype for Business Server管理外壳中的Set-CsCloudCallDataConnectorConfiguration cmdlet 为特定站点或整个Skype for Business Server部署启用呼叫数据连接器。 例如，以下命令在全局范围内启用呼叫数据连接器：

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $True
```

除了全局设置，还可以将呼叫数据连接器配置设置分配给站点范围。 这可在监视方面提供额外的管理灵活性。 例如，管理员可以为 Redmond 站点启用呼叫数据连接器转发，但禁用都柏林站点的呼叫数据连接器转发，如以下示例所示：

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "site:Redmond" -EnableCallDataConnector $True
```

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "site:Dublin" -EnableCallDataConnector $False
```

在 site 作用域配置的设置的优先于在 global 作用域配置的设置。 例如，假设调用数据连接器转发已在全局范围内启用，但在 Redmond 站点) 的站点范围 (禁用。 这意味着，Redmond 网站中的用户不会转发通话详细记录和 QoE 信息。 但是，其他网站中的用户 (即，由全局设置（而不是 Redmond 网站设置）管理的用户) 将转发其通话详细信息记录和 QoE 信息。

下表显示了呼叫数据连接器使用的最常用设置的值：  

|属性|说明|默认值|
|:-----|:-----|:-----|
|EnableCallDataConnector  <br/> |指示是否启用呼叫数据连接器。 如果为 True，则监视记录将转发到联机监视。  <br/> |$False  <br/> |
| 标识 | 确定命令的范围级别：全局或站点。   | 全球  |

## <a name="disable-call-data-connector"></a>禁用呼叫数据连接器

禁用呼叫数据连接器不会将监视存储与前端池脱钩，也不会卸载或以其他方式影响后端监视数据库。 禁用呼叫数据连接器时，将停止Skype for Business Server将呼叫数据上传到云。 

可在 Skype for Business Server 管理外壳中使用Set-CsCloudCallDataConnectorConfiguration cmdlet 禁用呼叫数据连接器。 例如，以下命令通过将 EnableCallDataConnector 属性设置为$False，在全局范围内禁用调用数据连接器：

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $False
```

如果要继续将呼叫数据上传到云，请将 EnableCallDataConnector 属性设置回$True，如以下示例所示：

```PowerShell
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $True
```

## <a name="view-on-premises-data-through-the-online-dashboard"></a>通过联机仪表板查看本地数据

 启用呼叫数据连接器后，可以在呼叫分析仪表板或呼叫质量仪表板上查看本地呼叫数据，如“使用呼叫分析”中所述，[以排查质量不佳的问题](/skypeforbusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality)，并[打开并使用 Microsoft Teams 和 Skype for Business Online 的呼叫质量仪表板](/MicrosoftTeams/turning-on-and-using-call-quality-dashboard)。

## <a name="for-more-information"></a>详细信息

有关 cmdlet 的详细信息，可以使用 Skype for Business Server Management Shell 中的Get-Help命令。 例如：

Get-Help Get-CsCloudCallDataConnector |更多

Get-Help Set-CsCloudCallDataConnector |更多

Get-Help Set-CsCloudCallDataConnectorConfiguration |更多
