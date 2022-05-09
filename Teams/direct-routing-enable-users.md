---
title: 为用户启用直接路由
ms.reviewer: filippse
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: 了解如何为用户启用直接路由Microsoft Teams 电话。
ms.openlocfilehash: edf02077bf5c15da56fe7894d1faec2a9b87b0d5
ms.sourcegitcommit: 9968ef7d58c526e35cb58174db3535fd6b2bd1db
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/09/2022
ms.locfileid: "65284077"
---
# <a name="enable-users-for-direct-routing"></a>为用户启用直接路由

本文介绍如何为用户启用直接路由。 这是配置直接路由的以下步骤的第 2 步：

- 第 1 步 [使用电话系统连接 SBC 并验证连接](direct-routing-connect-the-sbc.md) 
- **步骤 2.为用户启用直接路由**   (本文) 
- 第 3 步 [配置语音路由](direct-routing-voice-routing.md)
- 第 4 步 [将数字转换为备用格式](direct-routing-translate-numbers.md) 


有关设置直接路由所需的所有步骤的信息，请参阅 [配置直接路由](direct-routing-configure.md)。

准备好为用户启用直接路由后，请执行以下步骤： 

1. 在Microsoft 365中创建用户并分配电话系统许可证。  
2. 确保用户处于联机状态。
3. 配置电话号码并启用企业语音。 
4. 将Teams仅限模式分配给用户。

## <a name="create-a-user-and-assign-the-license"></a>创建用户并分配许可证

在Microsoft 365中创建新用户有两个选项。 但是，Microsoft 建议组织选择一个选项以避免路由问题： 

- 在本地 Active Directory中创建用户，并将用户同步到云。 请参阅[将本地目录与Azure Active Directory集成](/azure/active-directory/connect/active-directory-aadconnect)。
- 直接在Microsoft 365 管理中心中创建用户。 请参阅[单独或批量添加用户以Microsoft 365或Office 365 - 管理员帮助](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec)。 

如果Skype for Business联机部署与Skype for Business 2015 或 Lync 2010 或 2013 本地共存，唯一支持的选项是在本地 Active Directory中创建用户并将用户同步到云 (选项 1) 。 

有关许可证要求的信息，请参阅[计划直接路由](direct-routing-plan.md)中的[许可和其他要求](direct-routing-plan.md#licensing-and-other-requirements)。

## <a name="ensure-that-the-user-is-homed-online"></a>确保用户处于联机状态 

此步骤适用于Skype for Business Server 企业语音已启用的用户迁移到直接路由Teams。

直接路由要求用户联机托管。 可以通过查看 RegistrarPool 参数进行检查，该参数需要在 infra.lync.com 域中具有值。 Microsoft 建议在将用户迁移到Teams直接路由时，将 LineURI 从本地更改为联机，但不需要这样做。 

1. 连接Microsoft Teams PowerShell 会话。

2. 发出命令： 

    ```PowerShell
    Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool,OnPremLineUri,LineUri
    ``` 
    如果 OnPremLineUri 填充了<E.164 电话号码>，则电话号码已在本地分配并同步到Microsoft 365。 若要联机管理电话号码，请使用本地 Skype for Business Management Shell 清除参数并同步到Microsoft 365，然后再使用 Teams PowerShell 配置电话号码。 

1. 从 Skype for Business Management Shell 发出命令： 

   ```PowerShell
   Set-CsUser -Identity "<User name>" -LineUri $null
    ``` 
 > [!NOTE]
 > 请勿将 EnterpriseVoiceEnabled 设置为 False，因为不需要这样做，如果旧版Skype for Business手机正在使用，并且租户混合配置是使用 UseOnPremDialPlan $True 设置的，这可能会导致拨号计划规范化问题。 
    
   更改同步到Microsoft 365后，预期输出`Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool,OnPremLineUri,LineUri`为：

   ```console
   RegistrarPool                        : pool.infra.lync.com
   OnPremLineURI                        : 
   LineURI                              : 
   ```
 > [!NOTE]
 > 在分离本地Skype for Business[环境](/skypeforbusiness/hybrid/decommission-on-prem-overview)之前，必须联机管理所有用户的电话属性。 

## <a name="configure-the-phone-number-and-enable-enterprise-voice"></a>配置电话号码并启用企业语音 

创建用户并分配许可证后，必须配置用户的联机电话设置。 用户的云语音邮件配置是自动的;无需执行其他配置。

可以使用Teams管理中心或使用 Teams PowerShell 来配置电话号码。

### <a name="use-teams-admin-center"></a>使用Teams管理中心

1. 转到 **UsersManage** ->  用户。

2. 选择用户。

2. 在 **“帐户****常规信息**”下，选择 **“编辑**”。

3. 在 **“分配电话号码**”下，从 **电话号码类型** 下拉菜单中，选择 **“直接路由**”。

4. 输入分配的电话号码和电话号码扩展（如果适用）。

5. 选择 **“应用”。**

帐户一般信息现在将显示分配的电话号码和直接路由作为电话号码类型。


### <a name="use-powershell"></a>使用 PowerShell

1. 连接到 Microsoft Teams PowerShell 会话。 

2. 后续步骤取决于你是在本地还是联机管理用户的电话号码。 如果要在本地管理电话号码，则必须使用本地 Skype for Business Management Shell、控制面板 或在[“决定如何在停用后管理属性](/skypeforbusiness/hybrid/cloud-consolidation-managing-attributes)”中介绍的方法之一。

   - 如果要在本地管理用户的电话号码，则需要使用以下命令确保用户企业语音联机启用：

       ```PowerShell
       Set-CsPhoneNumberAssignment -Identity "<User name>" -EnterpriseVoiceEnabled $true
       ```
       
   - 如果要联机管理用户的电话号码，则需要使用 Teams PowerShell 中的以下命令将电话号码分配给用户。 命令自动启用用户企业语音： 
 
       ```PowerShell
       Set-CsPhoneNumberAssignment -Identity "<User name>" -PhoneNumber <phone number> -PhoneNumberType DirectRouting
       ```
    
       例如，若要为用户“Spencer Low”添加电话号码，请输入以下内容： 

       ```PowerShell
       Set-CsPhoneNumberAssignment -Identity "spencer.low@contoso.com" -PhoneNumber "+14255388797" -PhoneNumberType DirectRouting
       ```
       如果用户“Spencer Low”和“Stacy Quinn”共享具有唯一扩展名的相同基数，请输入以下内容
    
       ```PowerShell
       Set-CsPhoneNumberAssignment -Identity "spencer.low@contoso.com" -PhoneNumber "+14255388701;ext=1001" -PhoneNumberType DirectRouting
       Set-CsPhoneNumberAssignment -Identity "stacy.quinn@contoso.com" -PhoneNumber "+14255388701;ext=1002" -PhoneNumberType DirectRouting
       ```

    Microsoft 建议但不需要将电话号码配置为具有国家/地区代码的完整 E.164 电话号码。 可以使用扩展插件配置电话号码。 当对基数的查找返回多个结果时，这些扩展将用于查找用户。 此功能允许公司配置具有相同基号和唯一扩展名的电话号码。 若要成功查找，邀请必须包含扩展名的完整号码，如下所示：
    
    ```PowerShell
    To: <sip:+14255388701;ext=1001@sbc1.adatum.biz
    ```


## <a name="configure-sending-calls-directly-to-voicemail"></a>配置直接向语音邮件发送呼叫

直接路由允许你结束对用户的呼叫，并将其直接发送到用户的语音邮件。 如果要将呼叫直接发送到语音邮件，请将不透明=app：voicemail 附加到请求 URI 标头。 例如，“sip：user@yourdomain.com;opaque=app：voicemail”。 Teams用户不会收到呼叫通知。 相反，呼叫将直接连接到用户的语音邮件。

## <a name="assign-teams-only-mode-to-users-to-ensure-calls-land-in-microsoft-teams"></a>将Teams仅限模式分配给用户，以确保呼叫在Microsoft Teams

直接路由要求用户处于“仅Teams模式，以确保传入呼叫位于Teams客户端。 若要将用户置于“仅Teams模式”，请为其分配 TeamsUpgradePolicy 的“UpgradeToTeams”实例。 有关详细信息，请参阅 [IT 管理员的升级策略](upgrade-to-teams-on-prem-implement.md)。 如果组织使用Skype for Business Server，请参阅以下文章，了解Skype与Teams之间的互操作[性：迁移和与Skype for Business的互操作性](migration-interop-guidance-for-teams-with-skype.md)。

## <a name="see-also"></a>另请参阅

[规划直接路由](direct-routing-plan.md)

[配置直接路由](direct-routing-configure.md)
