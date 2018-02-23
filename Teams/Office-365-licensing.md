---
title: "适用于 Microsoft Teams 的 Office 365 许可"
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen, ninadara
description: "了解不同的 Office 365 许可证、哪些许可证支持用户使用 Microsoft Teams 以及如何启用或禁用它。"
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 401788f354ad57bded48d59a54646d6c10235662
ms.sourcegitcommit: 4b69ae91de3f82912eda3513cec65ae12e1ce2b2
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2018
---
<a name="office-365-licensing-for-microsoft-teams"></a>适用于 Microsoft Teams 的 Office 365 许可
========================================

以下 Office 365 订阅支持用户使用 Teams：

|小型企业版计划  |企业版计划  |教育版计划  |
|---------|---------|---------|
|Office 365 商业协作版     |Office 365 企业版 E1         |Office 365 教育版         |
|Office 365 商业高级版     |Office 365 企业版 E3         |Office 365 教育增强版         |
|     |Office 365 企业版 E4（已停用）         |Office 365 教育版 E3（已停用）         |
|     |Office 365 企业版 E5         |Office 365 教育版 E5   
      |Office 365 企业版 F1 |  |

> [!NOTE]
> Teams 也适用于非盈利组织。 当前不支持政府许可，但正在调查以便将来支持。
        


从 Teams **核心**功能方面来看，不同的 Office 365 订阅之间没有区别，合规性功能的可用性依赖于正确的订阅级别。 （有关详细信息，请参阅[信息保护许可](https://support.office.com/en-us/article/Plan-for-Office-365-security-and-information-protection-capabilities-3d4ac4a1-3920-4ff9-918f-011f3ce60408)。）

所有支持的订阅计划都符合访问 Teams 的 Web 客户端、桌面客户端和移动应用的条件。

Teams 不作为独立服务提供。

<a name="teams-license"></a>Teams 许可证
-------------

默认情况下，对于通过符合条件的 Office 365 订阅分配的所有用户，均启用 Teams 许可证。

![Office 365 管理中心中的许可证部分中的设置屏幕截图，显示 Microsoft Teams 为“开启”状态。](media/Understand_Office_365_Licensing__for_Microsoft_Teams_image2.png)


可以在组织中对整个许可证类型开启或关闭 Teams，默认情况下，对所有许可证类型开启 Teams（来宾用户除外）。 **不能通过使用 Office 365 管理中心中的 Teams 切换仅对某个许可证类型的一部分人开启 Teams。** 如果你要对贵组织的一部分人开启 Teams 并对其他人关闭 Teams（例如，如果你计划在一组挑选的用户中进行 Teams 试点），请对所有人开启 Teams 许可证切换，然后对单个用户关闭 Teams。

![Office 365 管理中心中的 Teams 用户/许可证类型设置屏幕截图，显示 Microsoft Teams 为“开启”状态。](media/Understand_Office_365_Licensing__for_Microsoft_Teams_image3.png)


**提示：**   正如任何其他工作负荷一样，通过 PowerShell 以工作负荷许可证方式启用和禁用 Teams。 Microsoft Teams 的服务计划名称为 TEAMS1。 （有关详细信息，请参阅[通过 Office 365 PowerShell 禁用对服务的访问](https://technet.microsoft.com/en-us/library/dn771769.aspx)。）

**示例：** 下面是有关如何在采用特殊许可证类型的情况下对所有人禁用 Microsoft Teams 的快速示例。 你需要先执行此操作，然后单独为应该拥有访问权限的用户启用 Microsoft Teams，以进行试点。

*要显示贵组织中具有的订阅类型，请使用以下命令：*

      Get-MsolAccountSku

*填写计划的名称（包括贵组织名称和学校的计划，例如 ContosoSchool:ENTERPRISEPACK_STUDENT），然后运行以下命令：*

      $acctSKU="<plan name>
      $x = New-MsolLicenseOptions -AccountSkuId $acctSKU -DisabledPlans "TEAMS1"
*要为你的命名计划对具有有效许可证的所有用户禁用 Microsoft Teams，请运行以下命令：*

      Get-MsolUser | Where-Object {$_.licenses[0].AccountSku.SkuPartNumber -eq  ($acctSKU).Substring($acctSKU.IndexOf(":")+1,  $acctSKU.Length-$acctSKU.IndexOf(":")-1) -and $_.IsLicensed -eq $True} |  Set-MsolUserLicense -LicenseOptions $x