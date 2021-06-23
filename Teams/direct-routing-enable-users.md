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
description: 了解如何为用户启用Microsoft 电话直接路由。
ms.openlocfilehash: 7d2b7c4b5d6268d1498a47537e0edbbf892198aa
ms.sourcegitcommit: cae94cd5761baafde51aea1137e6d164722eead9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/23/2021
ms.locfileid: "53075365"
---
# <a name="enable-users-for-direct-routing-voice-and-voicemail"></a>为用户启用直接路由、语音和语音邮件

本文介绍如何为用户启用 电话系统直接路由。  这是配置直接路由的以下步骤的步骤 2：

- 第 1 步 [连接系统Microsoft 电话 SBC 并验证连接](direct-routing-connect-the-sbc.md) 
- **步骤 2.为用户启用直接路由、语音和语音邮件 (**   本文) 
- 第 3 步 [配置语音路由](direct-routing-voice-routing.md)
- 第 4 步 [将数字转换为备用格式](direct-routing-translate-numbers.md) 


有关设置直接路由所需的所有步骤的信息，请参阅 [配置直接路由](direct-routing-configure.md)。

准备好为用户启用直接路由时，请执行以下步骤： 

1. 在用户或Microsoft 365 Office 365用户，并分配电话系统许可证。 
2. 确保用户位于 Skype for Business Online 中。 
3. 配置电话号码并启用企业语音和语音邮件。 
4. 将Teams模式分配给用户。

## <a name="create-a-user-and-assign-the-license"></a>创建用户并分配许可证 

有两个选项用于创建新用户或Microsoft 365 Office 365。 但是，Microsoft 建议组织选择一个选项以避免路由问题： 

- 在本地 Active Directory 创建用户，将该用户同步到云。 请参阅[将本地目录与 Azure Active Directory。](/azure/active-directory/connect/active-directory-aadconnect)
- 直接在用户Microsoft 365 管理中心。 请参阅[将用户单独或批量添加到Microsoft 365或Office 365 - 管理员帮助](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec)。 

如果您的 Skype for Business Online 部署与本地 Skype for Business 2015 或 Lync 2010 或 2013 共存，则唯一支持的选项是在本地 Active Directory 中创建用户，将用户同步到云 (选项 1) 。 

有关许可证要求的信息，请参阅计划 [直接路由](direct-routing-plan.md#licensing-and-other-requirements) 中的许可 [和其他要求](direct-routing-plan.md)。

## <a name="ensure-that-the-user-is-homed-online-and-phone-number-is-not-being-synced-from-on-premises-applicable-for-skype-for-business-server-enterprise-voice-enabled-users-being-migrated-to-teams-direct-routing"></a>确保用户是联机家庭用户，并且电话号码未从本地 (同步，Skype for Business Server 企业语音迁移到 Teams 直接路由) 

直接路由要求用户联机进行归居。 可以通过查看 RegistrarPool 参数来检查，该参数需要在 infra.lync.com 中。 OnPremLineUriManuallySet 参数也应设置为 True。 这可以通过配置电话号码和使用 Skype for Business PowerShell 启用企业语音和语音邮件。

1. 连接 Skype for Business PowerShell 会话。

2. 发出命令： 

    ```PowerShell
    Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool,OnPremLineUriManuallySet,OnPremLineUri,LineUri
    ``` 
    如果 OnPremLineUriManuallySet 设置为 False 且 LineUri 中填充了 <E.164 电话号码>，请在使用 Skype for Business Online PowerShell 配置电话号码之前，使用本地 Skype for Business 命令行管理程序清理参数。 

1. 从 Skype for Business 命令行管理程序发出命令： 

   ```PowerShell
   Set-CsUser -Identity "<User name>" -LineUri $null -EnterpriseVoiceEnabled $False -HostedVoiceMail $False
    ``` 
   将更改同步到 Office 365 预期 `Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool,OnPremLineUriManuallySet,OnPremLineUri,LineUri` 输出为：

   ```console
   RegistrarPool                        : pool.infra.lync.com
   OnPremLineURIManuallySet             : True
   OnPremLineURI                        : 
   LineURI                              : 
   ```

## <a name="configure-the-phone-number-and-enable-enterprise-voice-and-voicemail"></a>配置电话号码并启用企业语音和语音邮件 

创建用户并分配许可证后，下一步是配置用户的电话号码和语音邮件。 

添加电话号码并启用语音邮件：
 
1. 连接 Skype for Business PowerShell 会话。 

2. 发出命令： 
 
    ```PowerShell
    Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI tel:<phone number>
    ```
    
    例如，若要为用户"Spencer Low"添加电话号码，请输入以下内容： 

    ```PowerShell
    Set-CsUser -Identity "spencer.low@contoso.com" -OnPremLineURI tel:+14255388797 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    ```
    如果用户"Spencer Low"和"Stacy Quinn"共享同一个具有唯一扩展名的基号，请输入以下代码
    
    ```PowerShell
    Set-CsUser -Identity "spencer.low@contoso.com" -OnPremLineURI "tel:+14255388701;ext=1001" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    Set-CsUser -Identity "stacy.quinn@contoso.com" -OnPremLineURI "tel:+14255388701;ext=1002" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    ```

    建议但不要求将使用的电话号码配置为包含国家/地区代码的完整 E.164 电话号码。 支持使用分机配置电话号码，当针对基本号码的查找返回多个结果时，将用来查找用户。 这允许公司配置相同基本号码和唯一分机的电话号码。 若要成功查找，邀请必须包含扩展名的完整号码，如下所示：
    ```PowerShell
    To: <sip:+14255388701;ext=1001@sbc1.adatum.biz
    ```
    
    > [!NOTE]
    > 如果用户的电话号码在本地管理，请使用本地 Skype for Business命令行管理程序或控制面板来配置用户的电话号码。 


## <a name="configuring-sending-calls-directly-to-voicemail"></a>配置直接向语音邮件发送呼叫

直接路由允许你结束对用户的呼叫，并将其直接发送到用户的语音邮件。 如果要将呼叫直接发送到语音邮件，请将 opaque=app：voicemail 附加到请求 URI 标头。 例如，"sip：user@yourdomain.com;opaque=app：voicemail"。 在这种情况下，Teams不会收到呼叫通知，呼叫将直接连接到用户的语音邮件。

## <a name="assign-teams-only-mode-to-users-to-ensure-calls-land-in-microsoft-teams"></a>为Teams分配"仅通话"模式，确保呼叫进入Microsoft Teams

直接路由要求用户进入"仅Teams模式，以确保传入呼叫进入Teams客户端。 若要将用户置于Teams模式，请为其分配 TeamsUpgradePolicy 的"UpgradeToTeams"实例。 有关详细信息，请参阅 IT [管理员的升级策略](upgrade-to-teams-on-prem-implement.md)。 如果你的组织使用 Skype for Business Server 或 Skype for Business Online，请参阅以下文章，了解 Skype 与 Teams 之间的互操作性：迁移和与 Skype for Business[的互操作性](migration-interop-guidance-for-teams-with-skype.md)。

## <a name="see-also"></a>另请参阅

[规划直接路由](direct-routing-plan.md)

[配置直接路由](direct-routing-configure.md)
