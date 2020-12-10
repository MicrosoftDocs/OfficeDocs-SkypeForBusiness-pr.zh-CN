---
title: 直接路由 SBA
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/28/2019
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
description: 了解有关直接路由的详细信息，如配置、必要的核心部署决策和语音路由注意事项。
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5b30f8a435f256edc816ebeea075425fddeaf8bb
ms.sourcegitcommit: 4386f4b89331112e0d54943dc3133791d5dca3fb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "49611786"
---
# <a name="survivable-branch-appliance-sba-for-direct-routing---public-preview"></a>Survivable 分支装置 (SBA) 用于直接路由-公共预览


> [!NOTE]
> 这是公开预览版本。

有时，使用直接路由连接到 Microsoft Phone 系统的客户网站可能会遇到网络中断。

假设客户网站（称为分支）暂时无法通过直接路由连接到 Microsoft 云。 但是，分支内的 intranet 仍能完全正常工作，并且用户可以连接到提供 PSTN 连接的 SBC) 的会话边界控制器 (。

本文介绍了如何使用 Survivable 分支装置 (SBA) 启用 Microsoft Phone 系统，以便在发生中断时，继续拨打和接收公共交换电话网络 (PSTN) 呼叫。

## <a name="prerequisites"></a>先决条件

SBA 是由 Microsoft 向 SBC 供应商提供的可分发代码，这些供应商将代码嵌入到 SBCs 的固件中。 

若要使用嵌入式 Survivable 分支装置获取最新的会话边框控制器固件，请与 SBC 供应商联系。 此外，还需要以下内容：

- 需要为媒体旁路配置 SBC，以确保分支网站中的 Microsoft 团队客户可以直接使用 SBC 进行媒体流。 

- 应在 SBA VM 操作系统上启用 TLS 1.2。

## <a name="supported-teams-clients"></a>支持的团队客户端

以下 Microsoft 团队客户端支持 SBA 功能： 

- Microsoft 团队 Windows 桌面版 

- Microsoft 团队 macOS 桌面版 

## <a name="how-it-works"></a>运作方式

在 internet 中断期间，团队客户端应自动切换到 SBA，并且持续通话应继续不中断。 用户不需要执行任何操作。 一旦团队客户端检测到 internet 已启动且所有传出调用均已完成，客户端将回退到正常操作模式并连接到其他团队服务。 SBA 将向云上载收集的调用数据记录，并且将更新通话记录，以便租户管理员可以查看此信息。 

当 Microsoft 团队客户端处于脱机模式时，以下与调用相关的功能可用： 

- 通过本地 SBA/SBC 进行 PSTN 呼叫，并将媒体流过 SBC。

- 通过本地 SBA/SBC 接收 PSTN 呼叫，并通过 SBC 进行媒体流。 

- 保留和继续 PSTN 呼叫。

## <a name="configuration"></a>配置

为使 SBA 功能正常工作，团队客户需要了解每个分支站点中提供哪些 SBAs，以及将哪些 SBAs 分配给该网站中的用户。 配置步骤如下所示：

1. 创建 SBAs。
2. 创建团队分支留存策略。
3. 为用户分配策略。
4. 向 Azure Active Directory 注册 SBA 应用程序。

所有配置均通过使用 Skype for Business Online PowerShell cmdlet 完成。  (团队管理中心尚不支持直接路由 SBA 功能。 )  

 (有关配置 SBC 以及指向 SBC 供应商文档的链接的信息，请参阅本文末尾的会话边框控制器配置。 ) 

### <a name="create-the-sbas"></a>创建 SBAs

若要创建 SBAs，你将使用 New-CsTeamsSurvivableBranchAppliance cmdlet。 此 cmdlet 具有以下参数：

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

### <a name="create-the-teams-branch-survivability-policy"></a>创建团队分支留存策略 

若要创建策略，请使用 New-CsTeamsSurvivableBranchAppliancePolicy cmdlet。 此 cmdlet 具有下列参数。 请注意，该策略可以包含一个或多个 SBAs。

| 参数| 说明 |
| :------------|:-------|
| Identity | 策略的标识 |
| BranchApplianceFqdns  | 网站中的 SBA (s 的 FQDN)  |
||

例如：

``` powershell
C:\> new-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns "sba1.contoso.com","sba2.contoso.com" 
Identity             : Tag:CPH 
BranchApplianceFqdns : {sba1.contoso.com, sba2.contoso.com} 
```

你可以使用 Set-CsTeamsSurvivableBranchAppliancePolicy cmdlet 在策略中添加或删除 SBAs。 例如： 

``` powershell
Set-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns @{remove="sba1.contoso.com"} 
Set-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns @{add="sba1.contoso.com"} 
```

### <a name="assign-a-policy-to-a-user"></a>为用户分配策略

若要将策略分配给单个用户，您将使用 Grant-CsTeamsSurvivableBranchAppliancePolicy cmdlet。 此 cmdlet 具有以下参数：

| 参数| 说明 |
| :------------|:-------|
| Identity | 用户的标识 |
| PolicyName | 策略的标识 |
||

例如：

``` powershell
C:\> Grant-CsTeamsSurvivableBranchAppliancePolicy -PolicyName CPH -Identity user@contoso.com 
```

你可以通过授予 $Null 策略来删除用户的策略，如下例中所示：

``` powershell
C:\> Grant-CsTeamsSurvivableBranchAppliancePolicy -PolicyName $Null -Identity user@contoso.com 
```

### <a name="register-an-application-for-the-sba-with-azure-active-directory"></a>向 Azure Active Directory 注册 SBA 应用程序

若要允许租户内使用的不同 SBAs 从 Microsoft 365 中读取所需的数据，你需要使用 Azure Active Directory 为 SBA 注册应用程序。 

有关应用程序注册的详细信息，请参阅以下内容：

- [开发适用于 Azure Active Directory 的业务线应用](https://docs.microsoft.com/azure/active-directory/manage-apps/developer-guidance-for-integrating-applications)

- [使用 Microsoft 标识平台注册应用程序](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app)。  

您只需注册一个应用程序，即可供租户中的所有 SBAs 使用。 

对于 SBA 注册，你需要由注册创建的以下值： 

- 应用程序 (客户端) ID 
- 客户端密码 

对于 SBA 应用程序，请记住以下几点： 

- 名称可以是您决定的任何内容。  
- 受支持的帐户类型 = 仅限此组织目录中的帐户。 
- Web 重定向 Uri = https://login.microsoftonline.com/common/oauth2/nativeclient 。
- 隐式授予令牌 = 访问令牌和 ID 令牌。 
- API 权限 = Skype 和团队租户管理员访问-> 应用程序权限-> application_access_custom_sba_appliance。
- 客户端密码：你可以使用任何描述和到期。 
- 请记住在创建客户端密码后立即将其复制。 
-  (客户端) ID 的应用程序显示在 "概述" 选项卡上。

然后按照以下步骤操作：

1. 注册应用程序。
2. 设置隐式授予令牌。
3. 设置 API 权限。
4. 创建客户端密码。


## <a name="session-border-controller-configuration"></a>会话边框控制器配置 

有关如何使用嵌入式 Survivable 分支设备配置会话边框控制器的分步指导，请参阅 SBC 供应商提供的文档： 

- [AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-survivable-branch-appliances)

- [带](https://support.sonus.net/pages/viewpage.action?pageId=248644034)

- [Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html#Link-MicrosoftTeams) 

- [TE-系统](https://www.anynode.de/microsoft-teams-sba/)

## <a name="reporting-issues"></a>报告问题

向 SBC 供应商的支持组织报告任何问题。 报告问题时，请指明你拥有已配置的 Survivable 分支装置。

## <a name="known-issues"></a>已知问题

- 添加新的 Survivable 分支设备时，可能需要一些时间才能在 Survivable 分支装置策略中使用它们。

- 向用户分配 Survivable 分支装置策略时，可能需要一段时间才能在 CsOnlineUser 的输出中显示 SBA。 

- 不执行对 Azure AD 联系人的反向号码查找。 

- SBA 不支持呼叫转接设置。 

- 不支持 (E911) 为动态紧急呼叫配置的紧急电话号码进行紧急通话。

- Get-CsOnlineUser 的输出显示 TeamsBranchSurvivabilityPolicy。
