---
title: '为组织停用Microsoft Teams 免费版 (经典) '
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.reviewer: alyake
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-collaboration
- m365initiative-meetings
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
ms.custom:
- Licensing
- admindeeplinkMAC
description: 了解如何删除 Teams 免费 (经典) 许可证，并为组织的用户分配付费 Teams 许可证。
ms.openlocfilehash: 7e9596f631c461e3c1e9134b279c232e384aba6b
ms.sourcegitcommit: ff5411084dc34754462d5fd67b64db7a7e76f1e1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/19/2023
ms.locfileid: "69823291"
---
# <a name="retire-microsoft-teams-free-classic-for-your-organization"></a>为组织停用Microsoft Teams 免费版 (经典) 

> [!NOTE]
> 如果你是 Teams 免费版 (经典) 用户，除非 IT 管理员在本文中执行以下操作，否则你将在 2023 年 4 月中旬失去对 Teams 的访问权限。

2023 年 4 月中旬，Microsoft 将停用 **Microsoft Teams 免费版 (经典)** 许可证。

本文向 IT 管理员提供有关如何停用其组织的 **Microsoft Teams 免费版 (经典)** 许可证和迁移到付费 Teams 许可证的说明。

如果你未在 2023 年 4 月中旬将用户的免费 Teams 许可证移动到付费 Teams 许可证，则你的用户将失去对 Teams 的访问权限。

若要完成此过程，可以选择以下两种方法之一：

- [使用Microsoft 365 管理中心。](#use-microsoft-365-admin-center-to-replace-licenses)
- [使用 Microsoft PowerShell。](#use-microsoft-powershell-to-replace-licenses)

如果你的组织决定不迁移到付费的 Teams 许可证，你可以从 Teams 导出组织的内容。 有关如何导出 Teams 内容的说明，请参阅 [使用 Microsoft Teams 导出 API 导出内容](/microsoftteams/export-teams-content)。

## <a name="use-microsoft-365-admin-center-to-replace-licenses"></a>使用 Microsoft 365 管理中心 替换许可证

如果你的组织没有几个用户分配 **Teams 免费 (经典)** 许可证，我们建议使用Microsoft 365 管理中心来删除和分配许可证。

### <a name="check-users-current-teams-licensing"></a>检查用户的当前 Teams 许可

1. 登录到[Microsoft 365 管理中心](https://go.microsoft.com/fwlink/p/?linkid=2024339)。
1. 在左侧菜单中，转到 **“用户** >并选择” [**活动用户**](https://go.microsoft.com/fwlink/p/?linkid=834822) “以查看分配给用户的许可证。
    1. “**许可证”** 列将在分配该许可证的用户旁边显示 **Microsoft Teams 免费版 (经典)**。
1. 在左侧菜单中，转到 **“计费** >并选择” [**许可证**](https://go.microsoft.com/fwlink/p/?linkid=842264) “，查看是否有可用的付费 Teams 许可证。
    1. 如果组织有可用的许可证，请跳到 [分配付费 Teams 许可证](#assign-paid-teams-licenses) ，将这些许可证分配给具有 **Teams 免费 (经典)** 许可证的用户。
1. 确定需要购买的付费 Teams 许可证数（如果有）。

### <a name="purchase-paid-teams-licenses"></a>购买付费 Teams 许可证

1. 在 [Microsoft 365 管理中心](https://go.microsoft.com/fwlink/p/?linkid=2024339)中，转到 **“计费**>”，然后选择“**购买服务**”。
1. 选择“ **查看产品** ”，查看所有可用的许可证。
1. 选择“ **通信和协作** ”类别筛选器以查看 Teams 许可证。
1. 选择要替换 **Teams 免费 (经典)** 的付费 Teams 许可证。
    1. 建议使用 [**Teams Essentials** 许可证](https://admin.microsoft.com/adminportal/home#/catalog/offer-details/microsoft-teams-essentials-aad-identity-/2D7C59AC-F814-43E0-8E8E-E4EA91A09CAF)，该许可证最多提供 300 个席位。
    1. 如果需要超过 300 个席位，建议购买 [Microsoft 365 E1 许可证](https://admin.microsoft.com/Adminportal/Home#/catalog/offer-details/office-365-e1/CF4A479A-2119-4EF2-83D1-37CF8460EADA)。
1. 输入要购买的许可证数，然后选择计费频率。
1. 选择“ **购买** ”按钮以完成购买过程。

#### <a name="purchase-licenses-in-the-admin-center-marketplace"></a>在管理中心市场中购买许可证

某些租户有权访问Microsoft 365 管理中心市场。 对于这些租户，你将在市场中购买许可证。

1. 在 [Microsoft 365 管理中心](https://go.microsoft.com/fwlink/p/?linkid=2024339)，从左侧菜单中选择“**市场**”。
1. 选择“ **所有产品** ”选项卡。
1. 选择“ **通信和协作** ”类别筛选器以查看 Teams 许可证。
1. 选择要替换 **Teams 免费 (经典)** 的付费 Teams 许可证。
1. 输入要购买的许可证数，然后选择计费频率。
1. 选择“ **购买** ”按钮以完成购买过程。

### <a name="assign-paid-teams-licenses"></a>分配付费 Teams 许可证

1. 准备好替换 **Teams 免费版 (经典)** 许可证时，请在Microsoft 365 管理中心转到 **“用户** > [**活动用户**](https://admin.microsoft.com/adminportal/home#/users)”。
1. 选择“**许可证**”列中列出了 **Teams 免费 (经典)** 许可证的所有用户。
1. 在管理中心顶部，选择“ **管理产品许可证** ”选项。
1. 在右侧窗格中，选择“ **替换**”。
    1. 选择“ **替换”** 选项需要重新选择希望为这些用户分配的所有许可证。 如果仅选择新的付费 Teams 许可证，这些用户分配的其他许可证将从用户中删除，并替换为 Teams 许可证。
    1. 如果用户有不同的许可需求，请批量完成此过程，以防止错误地为用户授予许可。
1. 在“旁路”窗格中，选择新的付费 Teams 许可证和应为用户分配的任何其他许可证，然后选择“ **保存更改** ”按钮。

## <a name="use-microsoft-powershell-to-replace-licenses"></a>使用 Microsoft PowerShell 替换许可证

如果你的组织有大量用户分配了 **Teams 免费 (经典)** 许可证，我们建议使用 PowerShell 批量取消分配许可证并将其分配给用户。

在完成此过程之前，需要为分配有 Teams **免费版 (经典)** 许可证的用户提供付费 Teams 许可证。 若要为这些用户购买许可证，请参阅 [购买付费 Teams 许可证](#purchase-paid-teams-licenses)。

1. 将 Microsoft 365 租户连接到 [Microsoft Graph PowerShell SDK](/powershell/microsoftgraph/get-started)。
1. 打开 Microsoft PowerShell 桌面应用。
1. [设置图形 API的用户和组织权限](/microsoft-365/enterprise/remove-licenses-from-user-accounts-with-microsoft-365-powershell#use-the-microsoft-graph-powershell-sdk)。
1. [从用户帐户中删除 **Teams 免费 (经典)** 许可证](/microsoft-365/enterprise/remove-licenses-from-user-accounts-with-microsoft-365-powershell#removing-licenses-from-user-accounts)。
1. [向用户分配付费 Teams 许可证](/microsoft-365/enterprise/assign-licenses-to-user-accounts-with-microsoft-365-powershell#assigning-licenses-to-user-accounts)。

有关 Graph PowerShell SDK 过程的详细信息，请参阅 [使用 Microsoft Graph PowerShell SDK](/microsoft-365/enterprise/view-licenses-and-services-with-microsoft-365-powershell)。
