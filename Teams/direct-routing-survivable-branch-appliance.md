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
ms.openlocfilehash: 976c73aebe698152c4824e3eaedfcc19a13ae525
ms.sourcegitcommit: 1be178dc3b34575e1914e629f004f897c02e0097
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/28/2022
ms.locfileid: "68138485"
---
# <a name="survivable-branch-appliance-sba-for-direct-routing"></a>用于直接路由的 Survivable Branch Appliance (SBA) 


有时，使用直接路由连接到 Microsoft Phone 系统的客户站点可能会遇到 Internet 中断。

假定客户站点（称为分支）暂时无法通过直接路由连接到 Microsoft 云。 但是，分支内的 Intranet 仍然功能齐全，用户可以连接到提供 PSTN 连接的会话边界控制器 (SBC) 。

本文介绍如何使用 Survivable Branch Appliance (SBA) 使 Microsoft 电话系统在发生中断时继续拨打和接收公共交换电话网络 (PSTN) 呼叫。

## <a name="prerequisites"></a>先决条件

SBA 是 Microsoft 提供给 SBC 供应商的可分发代码，这些供应商随后将代码嵌入其固件或单独分发，以便在单独的 VM 或硬件上运行 SBA。 

若要使用嵌入的 Survivable Branch 设备获取最新的会话边框控制器固件，请联系 SBC 供应商。 此外，还需要以下各项：

- 需要为媒体旁路配置 SBC，以确保分支站点中的 Microsoft Teams 客户端可以让媒体直接与 SBC 一起流动。 

- 应在 SBA VM OS 上启用 TLS1.2。
- 端口 3443、4444 和 8443 由 Microsoft SBA Server 用于与 Teams 客户端通信，应允许在防火墙上使用。 
- 端口 5061 (或 SBC) 上配置的端口 5061 由 Microsoft SBA Server 用于与 SBC 通信，应允许在防火墙上使用。 
- UDP 端口 123 由 Microsoft SBA Server 用于与 NTP 服务器通信，应允许在防火墙上使用。
- 端口 443 由 Microsoft SBA Server 用于与 Microsoft 365 通信，应允许在防火墙上使用。
- 公有云的 Azure IP 范围和服务标记应根据如下所述的准则进行定义： https://www.microsoft.com/download/details.aspx?id=56519

## <a name="supported-teams-clients"></a>支持的 Teams 客户端

以下 Microsoft Teams 客户端支持 SBA 功能： 

- Microsoft Teams Windows 桌面 

- Microsoft Teams macOS 桌面
- Teams for Mobile 
- Teams 电话

## <a name="how-it-works"></a>运作方式

在 Internet 中断期间，Teams 客户端应自动切换到 SBA，并且正在进行的调用应继续，不会中断。 用户无需执行任何操作。 一旦 Teams 客户端检测到 Internet 已启动并完成任何传出调用，客户端将恢复到正常操作模式并连接到其他 Teams 服务。 SBA 会将收集的呼叫数据记录上传到云，并更新呼叫历史记录，以便租户管理员可以查看此信息。 

当 Microsoft Teams 客户端处于脱机模式时，可使用以下与呼叫相关的功能： 

- 通过本地 SBA/SBC 进行 PSTN 调用，媒体流经 SBC。

- 通过本地 SBA/SBC 接收 PSTN 呼叫，媒体流经 SBC。 

- 保留和恢复 PSTN 调用。

## <a name="configuration"></a>配置

若要运行 SBA 功能，Teams 客户端需要知道每个分支站点中可用的 SBA，以及向该站点中的用户分配哪些 SBA。 配置步骤如下所示：

1. 创建 SBA。
2. 创建 Teams 分支生存性策略。
3. 将策略分配给用户。
4. 向 Azure Active Directory 注册 SBA 应用程序。

所有配置都是通过使用 Skype for Business Online PowerShell cmdlet 完成的。  (Teams 管理中心尚不支持直接路由 SBA 功能。)  

 (有关使用 SBC 供应商文档链接配置 SBC 的信息，请参阅本文末尾的会话边界控制器配置。) 

### <a name="create-the-sbas"></a>创建 SVA

若要创建 SBA，请使用New-CsTeamsSurvivableBranchAppliance cmdlet。 此 cmdlet 具有以下参数：

| 参数| 说明 |
| :------------|:-------|
| Identity  | SBA 的标识  |
| Fqdn | SBA 的 FQDN |
| 站点 | SBA 所在的 TenantNetworkSite |
| 说明 | 免费格式文本 |
|||

例如：

``` powershell
C:\> New-CsTeamsSurvivableBranchAppliance  -Fqdn sba1.contoso.com -Description "SBA 1" 
Identity    : sba1.contoso.com 
Fqdn        : sba1.contoso.com 
Site        : 
Description : SBA 1 
```

### <a name="create-the-teams-branch-survivability-policy"></a>创建 Teams 分支生存性策略 

若要创建策略，请使用New-CsTeamsSurvivableBranchAppliancePolicy cmdlet。 此 cmdlet 具有以下参数。 请注意，该策略可以包含一个或多个 SVA。

| 参数| 说明 |
| :------------|:-------|
| Identity | 策略的标识 |
| BranchApplianceFqdns  | 站点中 SBA () 的 FQDN |
||

例如：

``` powershell
C:\> new-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns "sba1.contoso.com","sba2.contoso.com" 
Identity             : Tag:CPH 
BranchApplianceFqdns : {sba1.contoso.com, sba2.contoso.com} 
```

可以使用Set-CsTeamsSurvivableBranchAppliancePolicy cmdlet 从策略中添加或删除 SVA。 例如： 

``` powershell
Set-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns @{remove="sba1.contoso.com"} 
Set-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns @{add="sba1.contoso.com"} 
```

### <a name="assign-a-policy-to-a-user"></a>向用户分配策略

若要将策略分配给单个用户，请使用Grant-CsTeamsSurvivableBranchAppliancePolicy cmdlet。 此 cmdlet 具有以下参数：

| 参数| 说明 |
| :------------|:-------|
| Identity | 用户的标识 |
| PolicyName | 策略的标识 |
||

例如：

``` powershell
C:\> Grant-CsTeamsSurvivableBranchAppliancePolicy -PolicyName CPH -Identity user@contoso.com 
```

可以通过授予$Null策略从用户中删除策略，如下一示例所示：

``` powershell
C:\> Grant-CsTeamsSurvivableBranchAppliancePolicy -PolicyName $Null -Identity user@contoso.com 
```

### <a name="register-an-application-for-the-sba-with-azure-active-directory"></a>向 Azure Active Directory 注册 SBA 应用程序

若要允许租户中使用的不同 SBA 从 Microsoft 365 读取所需的数据，需要向 Azure Active Directory 注册 SBA 的应用程序。 

有关应用程序注册的详细信息，请参阅以下内容：

- [为 Azure Active Directory 开发业务线应用](/azure/active-directory/manage-apps/developer-guidance-for-integrating-applications)

- [向Microsoft 标识平台注册](/azure/active-directory/develop/quickstart-register-app)应用程序。  

只需注册一个应用程序即可供租户中的所有 SVA 使用。 

对于 SBA 注册，需要注册创建以下值： 

- 应用程序 (客户端) ID 
- 客户端机密 

对于 SBA 应用程序，请记住以下事项： 

- 名称可以是你决定的。  
- 支持的帐户类型 = 仅此组织目录中的帐户。 
- Web 重定向 Uri = https://login.microsoftonline.com/common/oauth2/nativeclient。
- 隐式授予令牌 = 访问令牌和 ID 令牌。 
- API 权限 = Skype 和 Teams 租户管理员 Access ->应用程序权限 -> application_access_custom_sba_appliance。
- 客户端机密：可以使用任何说明和过期。 
- 请记得在创建客户端机密后立即复制它。 
- “概述”选项卡上显示了应用程序 (客户端) ID。

然后执行以下步骤：

1. 注册应用程序。
2. 设置隐式授予令牌。
3. 设置 API 权限。
4. 创建客户端机密。


## <a name="session-border-controller-configuration"></a>会话边框控制器配置 

有关如何使用嵌入式 Survivable Branch 设备配置会话边界控制器的分步指南，请参阅 SBC 供应商提供的文档： 

- [Audiocodes](https://www.audiocodes.com/library/technical-documents?query=sba)

- [功能区](https://support.sonus.net/pages/viewpage.action?pageId=248644034)

- [Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html#Link-MicrosoftTeams) 

- [TE-Systems](https://www.anynode.de/microsoft-teams-sba/)

## <a name="reporting-issues"></a>报告问题

向 SBC 供应商的支持组织报告任何问题。 报告问题时，指示已配置 Survivable Branch 设备。

## <a name="known-issues"></a>已知问题

- 由于 SBA 依赖于有效期为 24 小时且每天续订的身份验证令牌，因此目前 SBA 可以支持自上次身份验证起长达 24 小时的中断。 这意味着，如果上次身份验证令牌续订后 20 小时发生中断，则 SBA 将仅在剩余的 4 小时内运行。

- 添加新的 Survivable Branch Appliance 时，可能需要一些时间才能在 Survivable Branch Appliance 策略中使用它们。

- 将 Survivable Branch Appliance 策略分配给用户时，可能需要一些时间才能在 Get-CsOnlineUser 的输出中显示 SBA。 

- 不对 Azure AD 联系人执行反向数字查找。 

- SBA 不支持调用转发设置。 

- 不支持对配置为动态紧急呼叫 (E911) 的紧急呼叫进行紧急呼叫。
