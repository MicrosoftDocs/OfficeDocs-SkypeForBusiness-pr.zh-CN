---
title: 从商务语音移动到 Teams 电话许可证
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.localizationpriority: medium
search.appverid: MET150
description: 了解如何将 Business Voice 许可证更改为 Teams Phone 许可证。
appliesto:
- Microsoft Teams
ms.collection:
- M365-voice
ms.openlocfilehash: 372526a66d4f3a434479c8d4f62e4681b4a39acc
ms.sourcegitcommit: fc87f4300f53abf7a049936944abb21d0cade0d9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2022
ms.locfileid: "68480942"
---
# <a name="move-from-business-voice-to-teams-phone-licenses"></a>从商务语音移动到 Teams 电话许可证

到 2022 年 6 月底，Business Voice 将停用，因此[我们建议企业切换到Microsoft Teams 电话及通话套餐捆绑许可证](https://techcommunity.microsoft.com/t5/small-and-medium-business-blog/teams-phone-with-calling-plan-available-in-33-markets-on-january/ba-p/2967643)。

Business Voice 捆绑了以下三个 Teams 加载项许可证：

- **Microsoft Teams 电话** Microsoft Teams 中基于云的电话系统。
- **用于** 电话拨入式会议和会议拨号会议的音频会议。
- 面向公共交换电话网络的国内呼叫 **的 Microsoft 呼叫计划** (PSTN) 连接。

现有 Business Voice 客户不会自动转换为新的许可模型。

本文适用于需要将商务语音许可证更改为Microsoft Teams 电话和音频会议许可证，同时维护相同功能的 IT 管理员。

> [!WARNING]
> 密切遵循本文的说明。 如果说明指示不要选择 **“保存** ”按钮，请不要选择“ **保存** ”按钮。
>
> 过早保存可能导致失去电话号码分配、拨号计划、自动助理和呼叫队列。

## <a name="acquire-new-licenses"></a>获取新许可证

在替换商务语音许可证之前，首先需要为用户购买替换许可证。

需要许可证才能提供以下功能：

- 音频会议
- 基于云的电话系统
- PSTN 连接

使用下表根据需要确定要购买的许可证：

| 旧的许可证计划 | 建议的许可证计划 | 说明 |
| ---------------- | ------------------------ | ----------- |
| 包含通话套餐的商务语音 | Teams Phone with Calling Plan and Microsoft Teams 音频会议，拨出到美国/CAN | 提供基于云的电话系统功能、以 Microsoft 为 PSTN 提供商的国内呼叫计划，以及拨入和拨入功能，以与许可用户组织的与会者会面。 |
| 不使用通话套餐的业务语音 | Teams 电话标准版和Microsoft Teams 音频会议拨出到美国/CAN | 提供基于云的电话系统功能，这些功能可以 [与第三方呼叫计划与 PSTN 提供商结合使用 Operator Connect 或直接路由](pstn-connectivity.md) ，以及拨入和拨入功能，以便与许可用户组织的与会者会面。 |

## <a name="how-to-update-licenses"></a>如何更新许可证

有四种方法可以更新许可证：

- 通过Microsoft 365 管理中心更新单个用户许可证
- 通过Microsoft 365 管理中心进行批量用户许可证更新
- 使用 PowerShell 脚本进行批量用户许可证更新
- 使用基于 Azure 组的许可进行批量用户许可证更新

# <a name="option-1-single-user-in-admin-center"></a>[选项 1：管理中心中的单个用户](#tab/single-user)

### <a name="option-1-single-user-license-update-via-microsoft-365-admin-center"></a>选项 1：通过Microsoft 365 管理中心进行单个用户许可证更新

若要更新单个用户，可以使用Microsoft 365 管理中心。

1. 转到 [admin.microsoft.com](https://admin.microsoft.com/) 并使用租户管理员凭据登录。
1. 导航到 **用户** > **活动用户** 并选择所需的用户。
1. 在列表工具栏上选择 **“管理产品许可证** ”。
1. 在 **“许可证和应用** ”屏幕上，取消选择商务语音许可证。
    > [!IMPORTANT]
    > 尚不保存更改。 如果在不添加新许可证的情况下保存更改，则将取消预配用户帐户并取消分配电话号码。
1. 取消选择商务语音后，请检查新的 Teams 电话和音频会议许可证。
1. 现在，可以通过选择“保存更改”来安全地 **保存所做的更改**。

用户的许可证将更新，不应影响服务可用性。

# <a name="option-2-bulk-users-in-admin-center"></a>[选项 2：管理中心中的批量用户](#tab/bulk-users-admin-center)

### <a name="option-2-bulk-user-license-update-via-microsoft-365-admin-center"></a>选项 2：通过Microsoft 365 管理中心进行批量用户许可证更新

若要批量更新多个用户的许可证，可以使用Microsoft 365 管理中心。 所选用户将具有相同的许可证计划分配。

1. 转到 [admin.microsoft.com](https://admin.microsoft.com/) 并使用租户管理员凭据登录。
1. 导航到 **用户** > **活动用户** 并选择所有所需的用户。  
1. 在列表工具栏上选择 **“管理产品许可证** ”。
1. 在你 **想要如何处理这些用户的许可证时？** 提示，选择“ **替换：取消分配现有许可证”并分配新许可证** 选项。
    > [!IMPORTANT]
    > “ **替换** ”选项将删除所选用户的所有现有许可证。  因此，必须为用户选择所需的许可状态，包括正在使用的任何其他许可证，如Microsoft 365 商业高级版。
    >
    > 此外，如果所选用户具有不同的基本许可证配置，则它们将被所选许可证覆盖，这可能会影响 Microsoft 365 的其他领域。
    >
    > 对于具有混合许可证设置的租户，建议将 [批量更新选项与 PowerShell 脚本配合](#option-3-bulk-user-license-update-using-a-powershell-script)使用。
1. 在 **“许可证和应用** ”屏幕上，取消选择商务语音许可证。
    > [!IMPORTANT]
    > 尚不保存更改。 如果在不添加新许可证的情况下保存更改，则将取消预配所选用户的帐户，并取消分配电话号码。
1. 取消选择商务语音后，请检查新的 Teams 电话和音频会议许可证。
1. 现在，可以通过选择“保存更改”来安全地 **保存所做的更改**。
  用户的许可证将更新，不应影响服务可用性。

# <a name="option-3-bulk-users-via-powershell"></a>[选项 3：通过 PowerShell 批量用户](#tab/powershell)

### <a name="option-3-bulk-user-license-update-using-a-powershell-script"></a>选项 3：使用 PowerShell 脚本进行批量用户许可证更新

在大多数情况下，使用 PowerShell 脚本替换 Business Voice 许可证计划是一种高效的解决方案。  

若要使用此方法，你将遵循以下常规步骤：

1. 获取当前 Business Voice 许可证的特定于租户的许可证计划标识符。
1. 获取新的 Teams 电话和音频会议许可证计划的租户特定标识符。
1. 验证新许可证计划是否具有与当前商务语音许可证相同的服务计划。
1. 查找获得商业语音许可的租户用户 (或修改脚本以包含筛选器，以便根据需要选择一部分用户) 。
1. 使用 Teams 电话和音频会议计划更新用户的许可证配置。

> [!IMPORTANT]
> 提供的脚本是代码示例。 脚本不应按原样复制并在生产租户中运行，而无需对特定环境进行测试、验证和自定义。

### <a name="how-to-bulk-update-licenses-using-powershell"></a>如何使用 PowerShell 批量更新许可证

1. 安装并导入 AzureAD PowerShell 模块。

    ```powershell
    Install-Module AzureAD
    Import-Module AzureAD
    ```

1. 连接到 Microsoft 365 租户并提供租户管理员凭据。

    ```powershell
    Connect-AzureAD
    ```

1. 使用以下命令包列出租户中的所有许可证包。

    ```powershell
    Get-AzureADSubscribedSku
    ```

1. 使用下表标识将要替换的业务语音加载项许可证计划。

    | SKU 代码 | 许可证类型 |
    | -------- | ------------ |
    | BUSINESS_VOICE_MED | 商务语音通话套餐 - 加拿大 |
    | BUSINESS_VOICE | 商务语音通话套餐 - 英国 |
    | BUSINESS_VOICE_MED2_TELCO | 商务语音通话套餐 - 美国 |
    | BUSINESS_VOICE_DIRECTROUTING | 不使用通话套餐的业务语音 |
    | BUSINESS_VOICE_DIRECTROUTING_MED | 没有呼叫计划的商务语音 - 美国 |

    > [!NOTE]
    > 本文档中提供的脚本假定租户中有一个适用于 Business Voice 的 SKU 代码。  
    >
    > 如果有多个 Business Voice SKU，则需要调整脚本或多次运行脚本，每个 SKU 代码需要一次。

1. Create a PowerShell variable named `$skuSourceBV`.
    1. 请确保将标签替换 `SkuPartNumber` 为租户的业务语音 SKU 代码。
    1. 在此示例中 `BUSINESS_VOICE_MED2_TELCO` ，我们使用 SKU 代码。

    ```powershell
    $skuSourceBV = Get-AzureADSubscribedSku  | where {$_.SkuPartNumber -eq "BUSINESS_VOICE_MED2_TELCO"}
    ```

1. 使用下表标识新的 Teams 电话和音频会议许可证 SKU 代码。

    | SKU 代码 | 许可证类型 |
    | -------- | ------------ |
    | MCOTEAMS_ESSENTIALS | 包含通话套餐的 Teams 电话 |
    | MCOEV | Teams 电话标准版 (无呼叫计划)  |
    | MCOMEETADV | 音频会议 |
    | Microsoft_Teams_Audio_Conferencing_select_dial_out | Microsoft Teams 音频会议选择“拨出” |

1. 创建 PowerShell 变量以存储唯一的 Teams 电话和音频会议 SKU 代码。
    1. 请确保将标签替换 `SkuPartNumber` 为租户中可用的 SKU 代码。
    1. 在此示例中 `MCOTEAM_ESSENTIALS` ，我们使用的是 SKU 代码和 `MCOMEETADV` SKU 代码。

        ```powershell
        $skuTargetTPCP = Get-AzureADSubscribedSku | where {$_.SkuPartNumber -eq "MCOTEAMS_ESSENTIALS"}
        $skuTargetAC = Get-AzureADSubscribedSku | where {$_.SkuPartNumber -eq "MCOMEETADV"} 
        ```

1. 运行此脚本以将所需的服务计划数据从源 SKU 收集到唯一对象中。

     ```powershell
     $servicePlan_Phone = $skuSourceBV.ServicePlans | where {$_.ServicePlanName.ToString() -like "*EV*"}
    $servicePlan_AC = $skuSourceBV.ServicePlans | where {$_.ServicePlanName.ToString() -like "*MEET*"}
    $servicePlan_CP = $skuSourceBV.ServicePlans | where {$_.ServicePlanName.ToString() -like "*PSTN*"}
    ```

1. 继续操作之前，请验证源 SKU (Business Voice) 和目标 SKU (Teams 电话和音频会议) 是否包含相同的服务计划。
    1. 不匹配可能会触发许可证更改，从而中断用户的语音和音频会议服务。
    2. 创建变量以验证源 SKU 中的所有服务计划是否会替换为相同的目标服务计划。

        ```powershell
        $validated_TP = $false
        $validated_AC = $false
        $validated_CP = $false
        ```

    3. 如果源商务语音许可证未包含呼叫计划，请勿检查。

        ```powershell
        if($skuSourceBV.ServicePlans.Count -eq 2) { $validated_CP = $true }
        ```

    4. 验证源 SKU 中的所有服务计划在目标 SKU 中是否有匹配的服务计划。

        ```powershell
        For ($i=0; $i -le $skuSourceBV.ServicePlans.Count ; $i++) {
        if($validated_TP -eq $false) { if($skuTargetTP.ServicePlans.Contains($servicePlan_Phone)) { $validated_TP = $true } }
        if($validated_AC -eq $false) { if($skuTargetAC.ServicePlans.Contains($servicePlan_AC)) { $validated_AC = $true } }
        if($validated_CP -eq $false) { if($skuTargetTP.ServicePlans.Contains($servicePlan_CP)) { $validated_CP = $true } }
        }
        ```

    5. 如果目标 SKU 中缺少服务计划，可能会中断用户的服务可用性，脚本应停止处理。

        ```powershell
        if($validated_TP -eq $false ) { Write-Host "Stop updating users because target SKU does not have the same Service Plan for Teams Phone." ; exit }
        if($validated_AC -eq $false ) { Write-Host "Stop updating users because target SKU does not have the same Service Plan for Audio Conferencing." ; exit }
        if($validated_CP -eq $false ) { Write-Host "Stop updating users because target SKU does not have the same Service Plan for Calling Plan." ; exit }
        ```

1. 如果一切正常，请准备 PowerShell 对象以对用户对象执行更新操作。 为此使用 `AssignedLicenses` 该对象。

    ```powershell
    $LicenseAddTPCP = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
    $LicenseAddTPCP.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $skuTargetTPCP.SkuPartNumber -EQ).SkuID
    $LicenseAddAC = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
    $LicenseAddAC.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $skuTargetAC.SkuPartNumber -EQ).SkuID
    
    $LicensesToUpdate = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
    $LicensesToUpdate.AddLicenses += ($LicenseAddTPCP)
    $LicensesToUpdate.AddLicenses += ($LicenseAddAC)
    $LicensesToUpdate.RemoveLicenses = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $skuSourceBV.SkuPartNumber -EQ).SkuID
    ```

1. 接下来，获取分配了商务语音许可证的用户列表，并将其存储在命名 `$usersLicensedOldSKU`列表中。

    ```powershell
    $usersLicensedOldSKU = New-Object System.Collections.Generic.List[Microsoft.Open.AzureAD.Model.User]
    
    Get-AzureAdUser | ForEach { $BVlicensed=$False ; For ($i=0; $i -le ($_.AssignedLicenses | Measure).Count ; $i++) { If($_.AssignedLicenses[$i].SkuId -eq $skuSourceBV.SkuId) { $BVlicensed=$true } } ; If( $BVlicensed -eq $true) { $usersLicensedOldSKU.Add($_)} }
    ```

1. 现在，使用新的用户列表，使用前面创建的对象执行更新活动以删除 Business Voice 许可证并添加 Teams 电话和音频会议许可证 ``$LicensesToUpdate`` 。

    ```powershell
    $usersLicensedOldSKU | ForEach { Set-AzureADUserLicense -ObjectId $_.ObjectId -AssignedLicenses $LicensesToUpdate; Write-Host "Completed Update of user " $_.UserPrincipalName;  }
    ```

> [!NOTE]
> 如果没有足够的可用 Teams 电话和/或音频会议许可证来替换商务语音，则在用户分配期间，只要许可证池耗尽，就会收到使用 **SKU guid 的订阅没有任何可用许可证** 的错误。

### <a name="full-script"></a>完整脚本

```powershell
#Install the AzureAD module when required
Install-Module AzureAD
#Import the AzureAD module so you can use the commandlets
Import-Module AzureAD

#Connect to your tenant
Connect-AzureAD

#When necessary, uncomment and use this commandlet to list all the licenses in the tenant and identify which license packages are required
#Get-AzureADSubscribedSku

##Replace the SKU codes below to match your desired scenario
$skuSourceBV = Get-AzureADSubscribedSku | where {$_.SkuPartNumber -eq "BUSINESS_VOICE_MED2_TELCO"}
$skuTargetTP = Get-AzureADSubscribedSku | where {$_.SkuPartNumber -eq "MCOTEAMS_ESSENTIALS"}
$skuTargetAC = Get-AzureADSubscribedSku | where {$_.SkuPartNumber -eq "MCOMEETADV"}

##Replace the SKU codes below to match your desired scenario
$servicePlan_Phone = $skuSourceBV.ServicePlans | where {$_.ServicePlanName.ToString() -like "*EV*"}
$servicePlan_AC = $skuSourceBV.ServicePlans | where {$_.ServicePlanName.ToString() -like "*MEET*"}
$servicePlan_CP = $skuSourceBV.ServicePlans | where {$_.ServicePlanName.ToString() -like "*PSTN*"}

##Create variables to validate if all Service Plans in the source SKU will be replaced with the same target service plan
$validated_TP = $false
$validated_AC = $false
$validated_CP = $false

##If source Business Voice has no Calling Plan included, do not check
if($skuSourceBV.ServicePlans.Count -eq 2) { $validated_CP = $true }

##Verify if all service plans in source SKU have a matching service plan in target SKU
For ($i=0; $i -le $skuSourceBV.ServicePlans.Count ; $i++) { 
    if($validated_TP -eq $false) { if($skuTargetTP.ServicePlans.Contains($servicePlan_Phone)) { $validated_TP = $true } }
    if($validated_AC -eq $false) { if($skuTargetAC.ServicePlans.Contains($servicePlan_AC)) { $validated_AC = $true } }
    if($validated_CP -eq $false) { if($skuTargetTP.ServicePlans.Contains($servicePlan_CP)) { $validated_CP = $true } }
}

##If there's a missing service plan in the target sku, we might impact service availability for a user and therefore stop processing
if($validated_TP -eq $false ) { Write-Host "Stop updating users because target SKU does not have the same Service Plan for Teams Phone." ; exit } 
if($validated_AC -eq $false ) { Write-Host "Stop updating users because target SKU does not have the same Service Plan for Audio Conferencing." ; exit } 
if($validated_CP -eq $false ) { Write-Host "Stop updating users because target SKU does not have the same Service Plan for Calling Plan." ; exit } 


##Prepare variables and update
$LicenseAddTP = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$LicenseAddTP.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $skuTargetTP.SkuPartNumber -EQ).SkuID
$LicenseAddAC = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$LicenseAddAC.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $skuTargetAC.SkuPartNumber -EQ).SkuID
$LicensesToUpdate = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$LicensesToUpdate.AddLicenses += ($LicenseAddTP)
$LicensesToUpdate.AddLicenses += ($LicenseAddAC)
$LicensesToUpdate.RemoveLicenses = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $skuSourceBV.SkuPartNumber -EQ).SkuID

$usersLicensedOldSKU = New-Object System.Collections.Generic.List[Microsoft.Open.AzureAD.Model.User]
Get-AzureAdUser | ForEach { $BVlicensed=$False ; For ($i=0; $i -le ($_.AssignedLicenses | Measure).Count ; $i++) { If($_.AssignedLicenses[$i].SkuId -eq $skuSourceBV.SkuId) { $BVlicensed=$true } } ; If( $BVlicensed -eq $true) { $usersLicensedOldSKU.Add($_)} }

$usersLicensedOldSKU | ForEach { Set-AzureADUserLicense -ObjectId $_.ObjectId -AssignedLicenses $LicensesToUpdate; Write-Host "Completed Update of user " $_.UserPrincipalName;  }
```

# <a name="option-4-bulk-users-with-azure-group-based-licensing"></a>[选项 4：使用基于 Azure 组的许可批量用户](#tab/azure-licensing)

### <a name="option-4-bulk-user-license-update-using-azure-group-based-licensing"></a>选项 4：使用基于 Azure 组的许可进行批量用户许可证更新

通过基于 Azure 组的许可证管理，可以将订阅和服务计划分配给组。

此方法可确保：

- 许可证分配给组的所有成员。
- 任何加入该组的新成员都获得了相应的许可证。
- 从组中删除成员时，也会删除这些许可证。

必须验证 [基于组的许可的许可证要求](/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal)。

> [!NOTE]
> 对于此方法，许可证更新必须在一个步骤中处理。
>
> 建议编译分配了 Business Voice 许可证的现有组的列表，首先选择小型测试用户组，并将许可证计划分配替换为首选的新许可证计划。

### <a name="how-to-bulk-update-licenses-using-group-based-licensing"></a>如何使用基于组的许可批量更新许可证

1. 转到 [portal.azure.com](https://portal.azure.com) 并使用管理员凭据登录。
1. 转到 **Azure Active Directory** ，然后在左侧菜单中选择 **“许可证**”。
1. 若要验证分配有商务语音许可证的组，请选择 **“所有产品** ”，然后选择“商务语音”计划。
1. 选择 **许可组** 或 **许可用户**。 你将在右侧窗格中找到许可组的列表。
1. 选择组名称以打开组分配详细信息。
1. 选择 **“分配** ”以修改分配给此组的许可证。
1. 选中获取的用于替换 Business Voice 的许可证计划的框。
1. 取消选中Microsoft 365 商务语音许可证计划前面的框。
1. 选择“**保存**”。
1. 通过选择组名称返回到组。 你将看到一个横幅，指出 **许可证更改正在挂起**。
1. 选择 **“重新处理** ”以强制更新许可证分配。

---

## <a name="validate-user-license-updates"></a>验证用户许可证更新

完成所选方法后，验证用户许可证是否已正确更新。

1. 转到[Microsoft 365 管理中心](https://admin.microsoft.com)并使用管理员凭据登录。
1. 导航到 **用户** > **活动用户** 并选择测试用户。
1. 在工具栏上选择 **“管理产品许可证** ”。
1. 在 **“许可证和应用** ”屏幕上，查看他们分配给他们的许可证。

如果所有目标用户都分配了正确的许可证，则你已完成将商务语音许可证更新到 Teams 电话和音频会议许可证。
