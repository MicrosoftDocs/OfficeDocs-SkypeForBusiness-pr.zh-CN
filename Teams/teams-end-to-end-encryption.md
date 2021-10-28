---
title: Microsoft Teams 的端到端加密
author: kccross
ms.author: krowley
manager: laurawi
ms.date: 10/23/2021
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: ashgupt
description: 了解 Microsoft Teams 中的增强型加密功能、使用 Teams 管理中心和 Microsoft PowerShell 管理端到端加密。
ms.localizationpriority: high
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
ms.custom:
- Security
appliesto:
- Microsoft Teams
ms.openlocfilehash: bdc626510a180185cae699106c1420880ea55e73
ms.sourcegitcommit: b57e19e20900ff02f3196c811bf1dd1acd149c79
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/26/2021
ms.locfileid: "60579694"
---
# <a name="use-end-to-end-encryption-for-one-to-one-microsoft-teams-calls-public-preview"></a>将端到端加密用于一对一 Microsoft Teams 通话（公共预览版）

> [!IMPORTANT]
> 为了改善客户体验，Teams 服务模型及其加密支持可能会发生变化。 例如，该服务会定期弃用不再被视为安全的密码套件。 进行任何此类更改的目的都是为了通过设计保证 Teams 安全可靠。 此外，Microsoft 数据中心中的所有客户内容均已加密。 有关 Microsoft 365 中加密层的信息，请参阅 [Microsoft 365 中的加密](/microsoft-365/compliance/encryption)。

端到端加密（或 E2EE）发生在内容在发送之前进行加密，并且仅由预期收件人解密时。 通过端到端加密，只有两个终结点系统参与到加密和解密通话数据中。 其他任何一方（包括 Microsoft）都无权访问解密的对话。

在此公共预览版中，我们将针对计划外一对一通话推出 E2EE。 只有一对一 Teams 通话的实时媒体流（即视频和语音数据）会进行端到端加密。 双方必须都启用此设置才能启用端到端加密。 [Microsoft 365 中的加密](/microsoft-365/compliance/encryption)保护通话中的聊天、文件共享、状态和其他内容。

如果未启用端到端加密，Teams 仍可使用基于行业标准的加密来保护通话或会议的安全。 在传输过程中和静态时，在通话期间交换的数据将始终是安全的。 有关详细信息，请参阅 [Teams 的媒体加密](teams-security-guide.md#media-encryption)。

在端到端加密通话期间，Teams 会保护以下功能：

- 音频

- 视频

- 屏幕共享

以下高级功能在 E2EE 通话期间不可用：

- 实时字幕和听录

- 呼叫转移

- 呼叫合并

- 呼叫寄存

- 咨询，然后转接

- 呼叫助手并转接到另一台设备

- 添加参与者

- 录制

此外，如果你的组织使用合规性录制，则端到端加密不可用。 有关 Teams 如何支持合规性录制的详细信息，请参阅[基于 Teams 策略的通话和会议录制简介](teams-recording-policy.md)。

## <a name="configure-end-to-end-encryption-for-microsoft-teams"></a>为 Microsoft Teams 配置端到端加密

请完成这些任务，以便用户可以进行端到端加密通话。

- 通过创建一个或多个策略来定义谁可以使用端到端加密，从而为组织启用端到端加密。 在开始之前，请确保你的工作或学校帐户已分配有 Teams 或全局管理员角色。 有关信息，请参阅[使用 Microsoft Teams 管理员角色管理 Teams](using-admin-roles.md)。 准备好设置 E2EE 后，可以使用 Teams 管理中心或 Microsoft PowerShell。

- 在设备上的 Teams 设置中启用端到端加密呼叫。 每个用户都需要完成此任务，但他们只需在一台设备上执行此任务即可。 Teams 将为每个用户跨支持的终结点同步此设置。 有关说明，请参阅[使用面向 Teams 通话的端到端加密](https://support.microsoft.com/office/1274b4d2-b5c5-4b24-a376-606fa6728a90)。

### <a name="use-the-teams-admin-center-to-configure-end-to-end-encryption"></a>使用 Teams 管理中心配置端到端加密

组织范围的全局默认策略指定禁用端到端加密。 除非你创建并分配了自定义策略，你组织中的用户将自动获取全局策略。 如果要启用端到端加密，请创建新的加密策略或修改全局默认策略。 如果要使用 Teams 管理中心来启用端到端加密，请完成以下步骤。

1. 使用已分配有 Teams 或全局管理员角色的工作或学校帐户登录到 [Teams 管理中心](https://go.microsoft.com/fwlink/p/?linkid=2024339)。

2. 转到“**其他设置**” > “**增强型加密策略**”。

3. 选择默认策略，或选择“**添加**”以添加新策略，然后为新策略命名。

4. 如果要为用户启用端到端加密，对于 **端到端呼叫加密**，选择“**用户可以启用**”，然后选择“**保存**”。

   如果要禁用端到端加密，请选择“**为所有人禁用**”。

完成策略设置后，按照管理其他 Teams 策略的相同方式将策略分配给用户、组或整个租户。 有关在 Teams 中使用策略的信息，请参阅[管理具有策略的 Teams](manage-teams-with-policies.md)。

### <a name="use-microsoft-powershell-to-configure-end-to-end-encryption"></a>使用 Microsoft PowerShell 配置端到端加密

可以使用 Microsoft PowerShell 和 Teams 管理中心管理端到端加密策略。 Teams PowerShell 模块中包含多个端到端加密 cmdlet，并记录在 [Microsoft Teams cmdlet 参考](/powershell/teams/?view=teams-ps&preserve-view=true)中。 本文列出了可以使用的 cmdlet，并提供了简单的示例配置。 这些配置使用默认的全局策略。 你的组织可能需要更复杂的策略配置。 cmdlet 参考中提供了有关这些 cmdlet 的完整信息。

端到端加密 PowerShell cmdlet：

- [Get-CsTeamsEnhancedEncryptionPolicy](/powershell/module/teams/Get-CsTeamsEnhancedEncryptionPolicy) 返回有关组织中 Teams 增强型加密策略的信息。

- [Grant-CsTeamsEnhancedEncryptionPolicy](/powershell/module/teams/Grant-CsTeamsEnhancedEncryptionPolicy) 为用户分配和取消分配现有的增强型加密策略。 使用 `$NULL` 来取消分配给用户的所有策略。

- [New-CsTeamsEnhancedEncryptionPolicy](/powershell/module/teams/New-CsTeamsEnhancedEncryptionPolicy) 创建新的 Teams 增强型加密策略。

- [Remove-CsTeamsEnhancedEncryptionPolicy](/powershell/module/teams/Remove-CsTeamsEnhancedEncryptionPolicy) 从组织中删除增强型加密策略。 无法删除全局默认策略。

- [Set-CsTeamsEnhancedEncryptionPolicy](/powershell/module/teams/Set-CsTeamsEnhancedEncryptionPolicy) 更新现有 Teams 增强型加密策略中的值。

工作或学校帐户需要 Teams 或全局管理员角色来配置端到端加密。

#### <a name="to-enable-end-to-end-encryption-for-your-entire-tenant-using-the-global-policy"></a>使用全局策略为整个租户启用端到端加密

默认情况下，端到端加密处于禁用状态。 如果要通过设置默认全局策略为整个租户启用端到端加密，请运行 [Set-CsTeamsEnhancedEncryptionPolicy](/powershell/module/teams/Set-CsTeamsEnhancedEncryptionPolicy) cmdlet，如下所示。

```powershell
Set-CsTeamsEnhancedEncryptionPolicy -Identity Global -CallingEndtoEndEncryptionEnabledType DisabledUserOverride
```

其中：

- `Global` 表示在全局组织范围内的默认策略上设置此配置。

- `DisabledUserOverride` 表示默认情况下在 Teams 中禁用 E2EE，但用户可以在 Teams 设置中替代默认值并启用 E2EE。

#### <a name="to-disable-end-to-end-encryption-for-your-entire-tenant-using-the-global-policy"></a>使用全局策略为整个租户禁用端到端加密

默认情况下，端到端加密处于禁用状态。 如果对全局策略进行了更改，可以通过运行 [Grant-CsTeamsEnhancedEncryptionPolicy](/powershell/module/teams/Grant-CsTeamsEnhancedEncryptionPolicy) cmdlet 将设置改回，如下所示。

```powershell
Grant-CsTeamsEnhancedEncryptionPolicy -Identity Global -CallingEndtoEndEncryptionEnabledType Disabled
```

其中：

- `Global` 表示在全局组织范围内的默认策略上设置此配置。

- `Disabled` 表示已为所有人禁用 E2EE，并且用户无法在其 Teams 设置中启用它。

#### <a name="to-enable-end-to-end-encryption-for-a-single-user"></a>为单个用户启用端到端加密

如果要为某一用户启用端到端加密，请运行 [Grant-CsTeamsEnhancedEncryptionPolicy](/powershell/module/teams/Grant-CsTeamsEnhancedEncryptionPolicy) cmdlet，如下所示。

```powershell
Grant-CsTeamsEnhancedEncryptionPolicy -Identity "username" -PolicyName "policyname"
```

其中：

- *`username`* 是该用户的名称。

- *`policyname`* 是要用于策略的名称。 策略名称不能包含空格，例如 ContosoE2EEUserPolicy。

用户仍需要在其 Teams 设置中打开端到端加密呼叫，然后才能进行端到端加密呼叫。 有关说明，请参阅[使用面向 Teams 通话的端到端加密](https://support.microsoft.com/office/1274b4d2-b5c5-4b24-a376-606fa6728a90)。

例如：

```powershell
Grant-CsTeamsEnhancedEncryptionPolicy -Identity "kenmeyer@contoso.onmicrosoft.com" -PolicyName "ContosoE2EEUserPolicy"
```

#### <a name="to-unassign-an-end-to-end-encryption-policy-from-a-single-user"></a>取消分配给单个用户的端到端加密策略

一次只能向用户分配一项加密策略。 在取消分配给用户的策略时，系统会为用户分配全局、组织范围的默认策略。 无法取消分配默认策略。 如果要取消分配给某个用户的端到端加密策略，请运行 [Grant-CsTeamsEnhancedEncryptionPolicy](/powershell/module/teams/Grant-CsTeamsEnhancedEncryptionPolicy) cmdlet，如下所示。

```powershell
Grant-CsTeamsEnhancedEncryptionPolicy -Identity "kenmeyer@contoso.onmicrosoft.com" -PolicyName $NULL
```

## <a name="switch-on-end-to-end-encryption-on-your-device"></a>在设备上启用端到端加密

有关说明，请参阅[使用面向 Teams 通话的端到端加密](https://support.microsoft.com/office/1274b4d2-b5c5-4b24-a376-606fa6728a90)。

## <a name="related-topics"></a>相关主题

[安全团队为支持在家办公需完成的 12 大任务](/microsoft-365/security/top-security-tasks-for-remote-work)

[在 Microsoft Teams 中管理会议设置](./meeting-settings-in-teams.md)
