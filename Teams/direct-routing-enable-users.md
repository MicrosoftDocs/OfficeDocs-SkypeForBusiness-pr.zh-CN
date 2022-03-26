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
description: 了解如何为用户启用 Microsoft Teams 电话直接路由。
ms.openlocfilehash: e82865abcc7bb37835009fb9ab7f93e11c423d66
ms.sourcegitcommit: b91d83739a078b175770c797c17d602eb5c83a4f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2022
ms.locfileid: "63774091"
---
# <a name="enable-users-for-direct-routing"></a>为用户启用直接路由

本文介绍如何为用户启用直接路由。 这是配置直接路由的以下步骤的步骤 2：

- 第 1 步 [连接 SBC 电话系统并验证连接](direct-routing-connect-the-sbc.md) 
- **步骤 2.为用户启用直接路由 (**   本文) 
- 第 3 步 [配置语音路由](direct-routing-voice-routing.md)
- 第 4 步 [将数字转换为备用格式](direct-routing-translate-numbers.md) 


有关设置直接路由所需的所有步骤的信息，请参阅 [配置直接路由](direct-routing-configure.md)。

准备好为用户启用直接路由时，请执行以下步骤： 

1. 在许可证中Microsoft 365用户，并分配电话系统许可证。  
2. 确保用户已联机进行家庭管理。
3. 配置电话号码并启用企业语音。 
4. 将Teams模式分配给用户。

## <a name="create-a-user-and-assign-the-license"></a>创建用户并分配许可证

有两个选项用于在 Microsoft 365 中创建新用户。 但是，Microsoft 建议组织选择一个选项以避免路由问题： 

- 在本地 Active Directory 创建用户，将该用户同步到云。 请参阅[将本地目录与 Azure Active Directory](/azure/active-directory/connect/active-directory-aadconnect)。
- 直接在用户Microsoft 365 管理中心。 请参阅[将用户单独或批量添加到Microsoft 365或Office 365 - 管理员帮助](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec)。 

如果您的 Skype for Business Online 部署与本地 Skype for Business 2015 或 Lync 2010 或 2013 共存，则唯一支持的选项是在本地 Active Directory 中创建用户，将用户同步到云 (选项 1) 。 

有关许可证要求的信息，请参阅 [计划直接路由中的](direct-routing-plan.md#licensing-and-other-requirements) 许可 [和其他要求](direct-routing-plan.md)。

## <a name="ensure-that-the-user-is-homed-online"></a>确保用户已联机进行家庭管理 

此步骤适用于Skype for Business Server 企业语音直接路由的已启用Teams的用户。

直接路由要求用户联机进行归居。 可以通过查看 RegistrarPool 参数来检查，该参数需要在 infra.lync.com 中。 Microsoft 建议（但不要求）在将用户迁移到直接路由时将 LineURI 从本地更改为Teams联机。 

1. 连接 PowerShell Microsoft Teams会话。

2. 发出命令： 

    ```PowerShell
    Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool,OnPremLineUri,LineUri
    ``` 
    如果 OnPremLineUri 中填充了 <E.164>，则电话号码已在本地分配并同步到Microsoft 365。 如果要联机管理电话号码，在使用 Microsoft 365 PowerShell 配置电话号码之前，使用本地 Skype for Business 命令行管理程序清理参数Teams同步到 Teams。 

1. 从 Skype for Business命令行管理程序发出命令： 

   ```PowerShell
   Set-CsUser -Identity "<User name>" -LineUri $null
    ``` 
 > [!NOTE]
 > 请勿将 EnterpriseVoiceEnabled 设置为 False，因为不需要这样做，如果使用旧版 Skype for Business 手机并使用 UseOnPremDialPlan $True 设置租户混合配置，则可能会导致拨号计划规范化问题。 
    
   将更改同步到 Microsoft 365预期输出`Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool,OnPremLineUriManuallySet,OnPremLineUri,LineUri`为：

   ```console
   RegistrarPool                        : pool.infra.lync.com
   OnPremLineURIManuallySet             : True
   OnPremLineURI                        : 
   LineURI                              : 
   ```
 > [!NOTE]
 > 必须先联机管理用户的手机属性，然后才能将本地Skype for Business[环境](/skypeforbusiness/hybrid/decommission-on-prem-overview)。 

## <a name="configure-the-phone-number-and-enable-enterprise-voice"></a>配置电话号码并启用企业语音 

创建用户并分配许可证后，必须配置用户的联机电话设置。 请注意，云语音邮件自动配置;无需执行其他配置。

可以使用管理中心或 PowerShell Teams配置Teams电话号码。

### <a name="use-teams-admin-center"></a>使用Teams管理中心

1. 转到" **用户"** -> **"管理用户"**。

2. 选择用户。

2. 在"**帐户****常规信息"下**，选择"**编辑"**。

3. 在 **"分配电话号码"** 下，**电话**"号码类型"下拉菜单中，选择"直接 **路由"**。

4. 如果可请求，请输入分配的电话号码和电话号码分机号。

5. 选择" **应用"。**

帐户常规信息现在将显示分配的电话号码和直接路由作为电话号码类型。


### <a name="use-powershell"></a>使用 PowerShell

1. 连接 PowerShell Microsoft Teams会话。 

2. 接下来的步骤取决于是在本地还是在线管理用户的电话号码。 如果在本地管理电话号码，则必须使用本地 Skype for Business 命令行管理程序、控制面板或决定在提交后如何管理属性中介绍的方法之[一。](/skypeforbusiness/hybrid/cloud-consolidation-managing-attributes)

   - 如果在本地管理用户的电话号码，则需要确保通过以下命令企业语音启用用户：

       ```PowerShell
       Set-CsPhoneNumberAssignment -Identity "<User name>" -EnterpriseVoiceEnabled $true
       ```
       
   - 如果联机管理用户的电话号码，则需要在 PowerShell 中通过以下命令Teams电话号码。 用户会自动企业语音以下命令启用： 
 
       ```PowerShell
       Set-CsPhoneNumberAssignment -Identity "<User name>" -PhoneNumber <phone number> -PhoneNumberType DirectRouting
       ```
    
       例如，若要为用户"Spencer Low"添加电话号码，请输入以下内容： 

       ```PowerShell
       Set-CsPhoneNumberAssignment -Identity "spencer.low@contoso.com" -PhoneNumber "+14255388797" -PhoneNumberType DirectRouting
       ```
       如果用户"Spencer Low"和"Stacy Quinn"共享同一个具有唯一扩展名的基号，请输入以下内容
    
       ```PowerShell
       Set-CsPhoneNumberAssignment -Identity "spencer.low@contoso.com" -PhoneNumber "+14255388701;ext=1001" -PhoneNumberType DirectRouting
       Set-CsPhoneNumberAssignment -Identity "stacy.quinn@contoso.com" -PhoneNumber "+14255388701;ext=1002" -PhoneNumberType DirectRouting
       ```

    Microsoft 建议但不要求将电话号码配置为包含国家/地区代码的完整 E.164 电话号码。 可以使用分机号配置电话号码。 当针对基数的查找返回多个结果时，这些扩展将用于查找用户。 此功能允许公司配置相同基本号码和唯一分机的电话号码。 若要成功查找，邀请必须包含扩展名的完整号码，如下所示：
    
    ```PowerShell
    To: <sip:+14255388701;ext=1001@sbc1.adatum.biz
    ```


## <a name="configure-sending-calls-directly-to-voicemail"></a>配置将呼叫直接发送到语音邮件

直接路由允许你结束对用户的呼叫，并将其直接发送到用户的语音邮件。 如果要将呼叫直接发送到语音邮件，请将 opaque=app：voicemail 附加到请求 URI 标头。 例如，"sip：user@yourdomain.com;opaque=app：voicemail"。 Teams不会收到呼叫通知，呼叫将直接连接到用户的语音邮件。

## <a name="assign-teams-only-mode-to-users-to-ensure-calls-land-in-microsoft-teams"></a>将Teams仅模式分配给用户，以确保呼叫进入Microsoft Teams

直接路由要求用户进入"仅Teams模式，以确保传入的呼叫进入Teams客户端。 若要将用户置于Teams模式，请为其分配 TeamsUpgradePolicy 的"UpgradeToTeams"实例。 有关详细信息，请参阅适用于 [IT 管理员的升级策略](upgrade-to-teams-on-prem-implement.md)。 如果组织使用Skype for Business Server，请参阅以下文章，了解 Skype 与 Teams 之间的互操作性：迁移和[Skype for Business。](migration-interop-guidance-for-teams-with-skype.md)

## <a name="see-also"></a>另请参阅

[规划直接路由](direct-routing-plan.md)

[配置直接路由](direct-routing-configure.md)
