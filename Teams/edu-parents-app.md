---
title: EDU Microsoft Parents 应用的管理员设置
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: Microsoft Teams EDU 文章文档先决条件和针对家长应用的 PowerShell 设置。
ms.localizationpriority: Normal
ROBOTS: NOINDEX, NOFOLLOW
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9ca2c252964f610ee13924f25f5d4ca8e31b9d59
ms.sourcegitcommit: 4a9ea18808d17e2eb6e4e2e7e3894e33c14e8631
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/22/2021
ms.locfileid: "59475903"
---
# <a name="deploying-the-parents-app-in-microsoft-teams"></a>在应用程序中部署父Microsoft Teams

[!INCLUDE [preview-feature](includes/preview-feature.md)]

在 Microsoft Teams 中启用家长应用是管理员的一个简单过程，为教师提供一种安全的方法，以便与仍保留在租户中的学生及其联系人进行通信，这将在教师组织中进行扩展。

## <a name="requirements"></a>要求

- SDS (学校数据同步) - 您需要使用 CSV 选项将与学生关联的相关联系人上传到 SDS。 有关详细信息，请参阅配置 [CSV for SDS](/schooldatasync/set-up-your-sds-flow) 和更新 [相关](/graph/api/relatedcontact-update) 内容。
- 在Teams管理中心中，课堂所有者必须启用聊天，并且必须与组织Teams帐户进行 **联合聊天**。

如果需要基于每个用户启用联合聊天，请执行以下步骤。

## <a name="enabling-federated-chat-on-a-per-user-basis"></a>基于每个用户启用联合聊天

1. 安装最新的 powerShell Microsoft Teams预览版。

    ```powershell
    Install-Module -Name PowerShellGet -Force -AllowClobber
    Install-Module -Name MicrosoftTeams -AllowPrerelease -Force -AllowClobber
    ```
    
2. 使用具有管理员权限的凭据在命令窗口中运行。

    ```powershell
    $credential = Get-Credential
    Connect-MicrosoftTeams -Credential $credential
    ```
    
3. 在全局组/用户级别配置或租户级别配置中关闭和打开。

    ```powershell
    #Retrieves tenant level configuration
    Get-CsTenantFederationConfiguration
    #Turn OFF tenant level configuration
    Set-CsTenantFederationConfiguration -AllowTeamsConsumer $false
    #Turn ON tenant level configuration
    Set-CsTenantFederationConfiguration -AllowTeamsConsumer $true
    #Turn OFF Global GROUP/USER level configuration
    Set-CsExternalAccessPolicy -EnableTeamsConsumerAccess $false
    #Turn ON Global GROUP/USER level configuration
    Set-CsExternalAccessPolicy -EnableTeamsConsumerAccess $false
    ```
        
    > [!NOTE]
    > 运行此 PowerShell 时，更改可能需要一小时或更小时才能完成。
    
## <a name="more-information"></a>更多信息

- [CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy)
- [将策略分配给用户](/powershell/module/skype/grant-csexternalaccesspolicy)
