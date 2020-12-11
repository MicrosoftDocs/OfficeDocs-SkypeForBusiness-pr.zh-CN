---
title: 直接路由 SBA
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 12/08/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- m365initiative-voice
ms.reviewer: crowe
search.appverid: MET150
f1.keywords:
- NOCSH
- ms.teamsadmincenter.directrouting.overview
description: 详细了解直接路由，例如配置、必要的核心部署决策和语音路由注意事项。
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3204bc58b083f62feca3f878d2189558b69af6bd
ms.sourcegitcommit: 6b24c82837ca2c11f450a162ca4fab3dfa4ac8d4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "49620723"
---
# <a name="survivable-branch-appliance-sba-for-direct-routing---public-preview"></a>用于直接路由的 SBA (分支) 设备 - 公共预览版


> [!NOTE]
> 这是公共预览版。

有时，使用直接路由连接到 Microsoft Phone System 的客户站点可能会遇到 Internet 中断。

假设客户站点（称为分支）暂时无法通过直接路由连接到 Microsoft 云。 但是，分支内的 Intranet 仍然功能正常，用户可以连接到提供 PSTN 连接的 SBC (SBC) 会话边界控制器。

本文介绍如何使用可生存分支设备 (SBA) 在服务中断时让 Microsoft Phone 系统继续拨打和接听公用电话交换网 (PSTN) 呼叫。

## <a name="prerequisites"></a>先决条件

SBA 是 Microsoft 提供给 SBC 供应商的可分发代码，SBC 供应商随后将代码嵌入其固件或单独分发，让 SBA 在单独的 VM 或硬件上运行。 

若要获取具有嵌入式可代理分支设备的最新会话边界控制器固件，请联系 SBC 供应商。 此外，需要以下各项：

- 需要为"媒体绕过"配置 SBC，以确保分支站点中的 Microsoft Teams 客户端媒体可以直接与 SBC 一起流动。 

- 应在 SBA VM OS 上启用 TLS1.2。

## <a name="supported-teams-clients"></a>支持的 Teams 客户端

以下 Microsoft Teams 客户端支持 SBA 功能： 

- Microsoft Teams Windows 桌面版 

- Microsoft Teams macOS 桌面版 

## <a name="how-it-works"></a>运作方式

在 Internet 中断期间，Teams 客户端应自动切换到 SBA，并且正在进行的调用应继续进行且不会中断。 用户无需任何操作。 一旦 Teams 客户端检测到 Internet 已启动且任何传出调用完成，客户端将回退到正常操作模式并连接到其他 Teams 服务。 SBA 将收集的呼叫数据记录上传到云，并更新呼叫历史记录，以便租户管理员能够查看此信息。 

当 Microsoft Teams 客户端处于脱机模式时，可以使用以下与通话相关的功能： 

- 通过本地 SBA/SBC 进行 PSTN 呼叫，媒体流经 SBC。

- 通过本地 SBA/SBC 接收 PSTN 呼叫，媒体流经 SBC。 

- PSTN 呼叫的保留和恢复。

## <a name="configuration"></a>配置

若要运行 SBA 功能，Teams 客户端需要知道每个分支站点中可用的 SBA，以及将哪些 SBA 分配给该站点中的用户。 配置步骤如下：

1. 创建 SBA。
2. 创建 Teams 分支生存能力策略。
3. 将策略分配给用户。
4. 向 Azure Active Directory 注册 SBA 的应用程序。

所有配置都是使用 Skype for Business Online PowerShell cmdlet 完成。  (Teams 管理中心尚不支持直接路由 SBA 功能。)  

 (有关配置 SBC 的信息以及 SBC 供应商文档的链接，请参阅本文末尾的会话边界控制器配置。) 

### <a name="create-the-sbas"></a>创建 SBA

若要创建 SBA，请使用 New-CsTeamsSurvivableBranchAppliance cmdlet。 此 cmdlet 具有以下参数：

| 参数| 说明 |
| :------------|:-------|
| Identity  | SBA 的标识  |
| Fqdn | SBA 的 FQDN |
| 站点 | SBA 所在的 TenantNetworkSite |
| 说明 | 自由格式文本 |
|||

例如：

``` powershell
C:\> New-CsTeamsSurvivableBranchAppliance  -Fqdn sba1.contoso.com -Description "SBA 1" 
Identity    : sba1.contoso.com 
Fqdn        : sba1.contoso.com 
Site        : 
Description : SBA 1 
```

### <a name="create-the-teams-branch-survivability-policy"></a>创建 Teams 分支生存能力策略 

若要创建策略，请使用 New-CsTeamsSurvivableBranchAppliancePolicy cmdlet。 此 cmdlet 具有以下参数。 请注意，该策略可以包含一个或多个 SBA。

| 参数| 说明 |
| :------------|:-------|
| Identity | 策略的标识 |
| BranchApplianceFqdns  | 在站点中 (SBA) FQDN |
||

例如：

``` powershell
C:\> new-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns "sba1.contoso.com","sba2.contoso.com" 
Identity             : Tag:CPH 
BranchApplianceFqdns : {sba1.contoso.com, sba2.contoso.com} 
```

可以使用 Set-CsTeamsSurvivableBranchAppliancePolicy cmdlet 在策略中添加或删除 SBA。 例如： 

``` powershell
Set-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns @{remove="sba1.contoso.com"} 
Set-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns @{add="sba1.contoso.com"} 
```

### <a name="assign-a-policy-to-a-user"></a>向用户分配策略

若要将策略分配给单个用户，请使用 Grant-CsTeamsSurvivableBranchAppliancePolicy cmdlet。 此 cmdlet 具有以下参数：

| 参数| 说明 |
| :------------|:-------|
| Identity | 用户的标识 |
| PolicyName | 策略的标识 |
||

例如：

``` powershell
C:\> Grant-CsTeamsSurvivableBranchAppliancePolicy -PolicyName CPH -Identity user@contoso.com 
```

可以通过向用户授予策略$Null删除策略，如下一示例所示：

``` powershell
C:\> Grant-CsTeamsSurvivableBranchAppliancePolicy -PolicyName $Null -Identity user@contoso.com 
```

### <a name="register-an-application-for-the-sba-with-azure-active-directory"></a>向 Azure Active Directory 注册 SBA 的应用程序

若要允许租户中使用的不同 SBA 从 Microsoft 365 读取所需数据，需要向 Azure Active Directory 注册 SBA 应用程序。 

有关应用程序注册详细信息，请参阅以下内容：

- [为 Azure Active Directory 开发业务线应用](https://docs.microsoft.com/azure/active-directory/manage-apps/developer-guidance-for-integrating-applications)

- [将应用程序注册到 Microsoft 标识平台](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app)。  

只需注册一个应用程序，供租户中所有 SBA 使用。 

对于 SBA 注册，需要注册创建的以下值： 

- 应用程序 (客户端) ID 
- 客户端机密 

对于 SBA 应用程序，请记住以下事项： 

- 该名称可以是你决定的任何名称。  
- 支持的帐户类型 = 仅此组织目录中的帐户。 
- Web 重定向 Uri = https://login.microsoftonline.com/common/oauth2/nativeclient 。
- 隐式授予令牌 = 访问令牌和 ID 令牌。 
- API 权限 = Skype 和 Teams 租户管理员访问权限 ->应用程序权限 -> application_access_custom_sba_appliance。
- 客户端机密：可以使用任何说明和过期时间。 
- 请记住在创建客户端机密后立即复制它。 
- 应用程序 (客户端) ID 显示在"概述"选项卡上。

然后执行以下步骤：

1. 注册应用程序。
2. 设置隐式授权令牌。
3. 设置 API 权限。
4. 创建客户端机密。


## <a name="session-border-controller-configuration"></a>会话边界控制器配置 

有关如何使用嵌入式 Survivable 分支设备配置会话边界控制器的分步指南，请参阅 SBC 供应商提供的文档： 

- [AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-survivable-branch-appliances)

- [功能区](https://support.sonus.net/pages/viewpage.action?pageId=248644034)

- [Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html#Link-MicrosoftTeams) 

- [TE-Systems](https://www.anynode.de/microsoft-teams-sba/)

## <a name="reporting-issues"></a>报告问题

向 SBC 供应商的支持组织报告任何问题。 报告问题时，指示已配置了可生存分支设备。

## <a name="known-issues"></a>已知问题

- 添加新的可生存分支设备时，可能需要一些时间才能在"可生存分支设备"策略中使用它们。

- 将可生存分支设备策略分配给用户时，可能需要一些时间，SBA 才能显示在 Get-CsOnlineUser 的输出中。 

- 不针对 Azure AD 联系人执行反向数字查找。 

- SBA 不支持呼叫转发设置。 

- 不支持对为 E911 (动态紧急呼叫配置的紧急) 紧急呼叫。

- 该策略的输出Get-CsOnlineUser TeamsBranchSurvivabilityPolicy。
