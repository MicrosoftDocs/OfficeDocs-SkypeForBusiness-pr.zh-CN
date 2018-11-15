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
ms.openlocfilehash: 959bb182da91029fd43ebc3ccb99fb5a69d820b2
ms.sourcegitcommit: 30620021ceba916a505437ab641a23393f55827a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/15/2018
ms.locfileid: "26533132"
---
# <a name="configure-call-data-connector"></a>配置呼叫数据连接器

本文介绍如何配置呼叫数据连接器-允许查看 Skype 业务服务器呼叫质量数据的业务联机呼叫质量仪表板 (CQD) 和呼叫分析 (CA) 工具使用 Skype 一个工具集。 

> [!NOTE]
> 在公共预览发布，只呼叫分析仪表板才可用。

有关呼叫数据连接器的优点和必备组件，如角色的要求和混合连接性设置的详细信息，请参阅[规划呼叫数据连接器](plan-call-data-connector.md)。

## <a name="enable-monitoring"></a>启用监控
 
您必须配置呼叫数据记录 (CDR) 和用户体验质量 (QoE) 中的数据收集您的前端池与本地 LCSCdr 和 QoEMetrics 数据库; 监控否则，呼叫分析和呼叫质量仪表板不会收到要处理的数据。 之前您配置呼叫数据连接器，请按照[部署监控 Skype 业务服务器中](../../SfbServer/deploy/deploy-monitoring/deploy-monitoring.md)配置 QoE 和 CDR 以及基本监控中提供的步骤。

> [!IMPORTANT]
> 如果在前端池上没有启用监控，将无法正常呼叫数据连接器。

## <a name="enable-call-data-connector"></a>启用呼叫数据连接器

若要配置并启用呼叫数据连接器，您将使用以下 cmdlet:

| Cmdlet| 描述|
| :-----------------|---------------:|
| 新 CsCloudCallDataConnection | 建立 online 数据收集器 online cmdlet。|
| Get CsCloudCallDataConnection | 检索现有 online 数据收集器 online cmdlet。|  
| Get CsCloudCallDataConnector | 在本地 cmdlet 检索通过新建 CsCloudCallDataConnection cmdlet 创建的连接信息。 |
| 设置 CsCloudCallDataConnector | 保存通过新建 CsCloudCallDataConnection cmdlet 创建的连接信息的本地副本的本地 cmdlet。 |  
| 设置 CsCloudCallDataConnectorConfiguration | 在本地 cmdlet，使您能够启用或禁用连接器和自定义作用域级别。|

### <a name="configure-your-environment"></a>配置环境 

若要配置您的环境以启用联机数据收集器，您必须首先以登录到 Skype 业务 Online PowerShell 中的管理员。 有关详细信息，请参阅[管理业务 online 与 Office 365 PowerShell 中的 Skype](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)。

有两种方法，用于登录到 Skype 并业务 Online PowerShell 中：

- 从业务服务器 2019年命令行管理程序 （推荐方法） 的 Skype
- 从另一个 PowerShell 会话

#### <a name="log-in-to-skype-for-business-online-powershell-from-the-skype-for-business-server-management-shell-recommended-method"></a>登录到 Skype 的业务 Online PowerShell 从 Business Server 命令行管理程序 （推荐方法） 的 Skype

1. 如果第一次启用连接器，请运行以下命令：

   ```
   New-CsCloudCallDataConnection | Set-CsCloudCallDataConnector -TenantId <tenant_id>
   ```

2. 如果您收到一条错误，连接已存在，这意味着调用数据连接已存在租户。 在这种情况下，运行命令： 

   ```
   Get-CsCloudCallDataConnection | Set-CsCloudCallDataConnector -TenantId <tenant_id>
   ```


#### <a name="log-in-to-skype-for-business-online-powershell-from-another-powershell-session-optional-method"></a>登录到 Skype 的业务 Online PowerShell 从另一个 PowerShell 会话 （可选方法）

1.  如果第一次启用连接器，请运行以下命令： 

    ``` 
    New-CsCloudCallDataConnection 
    ```

2.  如果您收到一条错误，连接已存在，这意味着调用数据连接已存在租户。 在这种情况下，运行命令： 

    ```
    Get-CsCloudCallDataConnection  
    ```

上述命令的输出包含一个令牌值，该值，如下所示配置您的本地环境时，您将需要：

从业务 Server 命令行管理程序 Skype 中指定以下命令：

```
Set-CsCloudCallDataConnector -Identity Global -TenantId <tenant_id> -Token <token-copied-from-online>
```

### <a name="configure-the-scope"></a>配置作用域

使用 for Business Server 命令行管理程序中 Skype 集 CsCloudCallDataConnectorConfiguration cmdlet，可以为特定站点或业务服务器部署在整个 Skype 启用呼叫数据连接器。 例如，以下命令可使呼叫在全局范围内的数据连接器：

```
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $True
```

除了全局设置中，调用数据连接器配置设置可分配给站点作用域。 当谈到监控，这可以提供额外的管理灵活性。 例如，管理员可以启用为 Redmond 站点的呼叫数据连接器转发，但禁用都柏林网站中，调用数据连接器转发，如下面的示例中所示：

```
Set-CsCloudCallDataConnectorConfiguration -Identity "site:Redmond" -EnableCallDataConnector $True
```

```
Set-CsCloudCallDataConnectorConfiguration -Identity "site:Dublin" -EnableCallDataConnector $False
```

在 site 作用域配置的设置的优先于在 global 作用域配置的设置。 例如，假设调用数据连接器转接已启用在全局范围内，但是禁用在站点范围 （对于 Redmond 站点）。 不会为 Redmond 站点中的用户转发呼叫详细信息记录和 QoE 信息的方法。 但是，在其他网站 （即，由全局设置而非雷德蒙德站点设置管理的用户） 中的用户将有其呼叫详细信息记录和 QoE 信息转发。

下表中所示使用调用数据连接器的最常用设置的值：  

|属性|描述|默认值|
|:-----|:-----|:-----|
|EnableCallDataConnector  <br/> |指示是否启用呼叫数据连接器。 如果为 True，则会向联机监视转接监控记录。  <br/> |$False  <br/> |
| Identity  | 确定该命令的作用域级别： 全局或站点。   | 全局  |

## <a name="disable-call-data-connector"></a>禁用呼叫数据连接器

禁用呼叫数据连接器不解除关联监控存储与前端池，也不会卸载或否则影响监控后端数据库。 禁用呼叫数据连接器时，您停止 Skype 业务服务器从呼叫数据上载到云。 

使用适用于 Business Server 命令行管理程序中 Skype 集 CsCloudCallDataConnectorConfiguration cmdlet 禁用呼叫数据连接器。 例如，下面的命令通过 EnableCallDataConnector 属性设置为 $False 禁用呼叫在全局范围内的数据连接器：

```
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $False
```

如果您想要恢复呼叫数据上载到云，将设置回 $True，EnableCallDataConnector 属性，如下面的示例中所示：

```
Set-CsCloudCallDataConnectorConfiguration -Identity "global" -EnableCallDataConnector $True
```

## <a name="view-on-premises-data-through-the-online-dashboard"></a>查看本地通过联机仪表板的数据

 启用呼叫数据连接器后，您可以查看您的本地呼叫数据上调用分析仪表板[使用调用分析解决质量不佳](https://docs.microsoft.com/skypeforbusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality)中所述。


## <a name="for-more-information"></a>有关详细信息

有关这些 cmdlet 的详细信息，可用于业务 Server 命令行管理程序 Skype Get-help 命令。 例如：

获取帮助 Get CsCloudCallDataConnector |更多

获取帮助设置 CsCloudCallDataConnector |更多

获取帮助设置 CsCloudCallDataConnectorConfiguration |更多