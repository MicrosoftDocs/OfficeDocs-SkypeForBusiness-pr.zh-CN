---
title: 为用户启用直接路由
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: 了解如何启用 Microsoft 手机系统直接路由用户。
ms.openlocfilehash: 5fc3955430e5aa441d3c1099a86011d2b0c760f0
ms.sourcegitcommit: 875c854547b5d3ad838ad10c1eada3f0cddc8e66
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/13/2020
ms.locfileid: "46656143"
---
# <a name="enable-users-for-direct-routing-voice-and-voicemail"></a>为用户启用直接路由、语音和语音邮件

本文介绍如何为用户启用电话系统直接路由。  这是用于配置直接路由的以下步骤的步骤2：

- 第 1 步 [将 SBC 连接到 Microsoft Phone 系统并验证连接](direct-routing-connect-the-sbc.md) 
- **步骤2。 (本文中启用直接路由、语音和语音邮件的用户**) 
- 第 3 步 [配置语音路由](direct-routing-voice-routing.md)
- 第 4 步 [将数字转换为备用格式](direct-routing-translate-numbers.md) 


有关设置直接路由所需的所有步骤的信息，请参阅[配置直接路由](direct-routing-configure.md)。

准备好为用户启用直接路由时，请按照下列步骤操作： 

1. 在 Microsoft 365 或 Office 365 中创建用户并分配电话系统许可证。 
2. 确保用户托管在 Skype for Business Online 中。 
3. 配置电话号码并启用企业语音和语音邮件。 
4. 向用户分配 "仅团队" 模式。

## <a name="create-a-user-and-assign-the-license"></a>创建用户并分配许可证 

有两个选项可用于在 Microsoft 365 或 Office 365 中创建新用户。 但是，Microsoft 建议你的组织选择一个选项来避免路由问题： 

- 在本地 Active Directory 中创建用户并将用户同步到云。 请参阅[将本地目录与 Azure Active Directory 集成](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect)。
- 直接在 Microsoft 365 管理中心创建用户。 请参阅[将用户逐个或批量添加到 Microsoft 365 或 Office 365-管理员帮助](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec)。 

如果您的 Skype for Business Online 部署 coexists 使用 Skype for business 2015 或 Lync 2010 或本地2013，则唯一支持的选项是在本地 Active Directory 中创建用户并将用户同步到云 (选项 1) 。 

有关许可证要求的信息，请参阅[计划直接路由](direct-routing-plan.md)中的[许可和其他要求](direct-routing-plan.md#licensing-and-other-requirements)。

## <a name="ensure-that-the-user-is-homed-online"></a>确保用户处于联机状态 

直接路由要求用户在网上托管。 你可以查看 RegistrarPool 参数，该参数需要在 infra.lync.com 域中具有值。

1. 连接到远程 PowerShell。
2. 发出命令： 

    ```PowerShell
    Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool
    ``` 

## <a name="configure-the-phone-number-and-enable-enterprise-voice-and-voicemail"></a>配置电话号码并启用企业语音和语音邮件 

创建用户并分配许可证后，下一步是配置用户的电话号码和语音邮件。 

要为语音邮件添加电话号码和启用，请执行以下操作：
 
1. 连接到远程 PowerShell 会话。 
2. 输入命令： 
 
    ```PowerShell
    Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI tel:<E.164 phone number>
    ```

    例如，若要为用户 "Spencer Low" 添加电话号码，请输入以下内容： 

    ```PowerShell
    Set-CsUser -Identity "spencer.low@contoso.com" -OnPremLineURI tel:+14255388797 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    ```

    使用的电话号码必须配置为完整的 E-164 个国家/地区代码的电话号码。 

      > [!NOTE]
      > 如果用户的电话号码是在本地管理的，请使用本地 Skype for Business Management Shell 或控制面板配置用户的电话号码。 


## <a name="configuring-sending-calls-directly-to-voicemail"></a>配置将呼叫直接发送到语音邮件

直接路由允许您结束呼叫用户并将其直接发送到用户的语音邮件。 如果您想要将呼叫直接发送到语音邮件，请将不透明 = app：语音邮件附加到请求 URI 标题。 例如，"sip： user@yourdomain .com; 不透明 = 应用：语音邮件"。 在这种情况下，团队用户将不会收到呼叫通知，直接将呼叫连接到用户的语音邮件。

## <a name="assign-teams-only-mode-to-users-to-ensure-calls-land-in-microsoft-teams"></a>向用户分配 "仅团队" 模式以确保在 Microsoft 团队中拨打土地

直接路由要求用户仅在 "仅工作组" 模式下，以确保传入呼叫位于团队客户的土地。 若要将用户置于 "仅团队" 模式，请为他们分配 TeamsUpgradePolicy 的 "UpgradeToTeams" 实例。 有关详细信息，请参阅[IT 管理员的升级指南](upgrade-to-teams-on-prem-overview.md)。 如果你的组织使用 Skype for business 服务器或 Skype for business Online，请参阅以下文章了解有关 Skype 和团队之间的互操作性的信息：[迁移和与 skype](migration-interop-guidance-for-teams-with-skype.md)for business 之间的互操作性。

## <a name="see-also"></a>另请参阅

[规划直接路由](direct-routing-plan.md)

[配置直接路由](direct-routing-configure.md)
