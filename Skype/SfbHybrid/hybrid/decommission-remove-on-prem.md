---
title: 停用 Skype for Business Server
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
description: 有关停用 Skype for Business Server 的说明。
ms.openlocfilehash: 668e3d5ebf5dfa03fcfb883adcc3e08fc5924bae
ms.sourcegitcommit: f223b5f3735f165d46bb611a52fcdfb0f4b88f66
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/06/2021
ms.locfileid: "51593878"
---
# <a name="remove-your-on-premises-skype-for-business-deployment"></a>删除本地 Skype for Business 部署

本文介绍了如何删除本地 Skype for Business 部署。 这是停止使用本地环境的以下步骤的第 3 步：

- 步骤 1. [将所有必需的用户和应用程序终结点从本地移动到联机](decommission-move-on-prem-users.md)。 

- 步骤 2. [禁用混合配置](cloud-consolidation-disabling-hybrid.md)。

- **步骤 3.删除本地 Skype for Business 部署。**  (本文) 


> [!IMPORTANT] 
> 本文中的步骤仅在使用方法 2 管理用户属性时适用，如此处 [所述](cloud-consolidation-disabling-hybrid.md#method-2---clear-skype-for-business-attributes-for-all-on-premises-users-in-active-directory)。 如果使用方法 1，请不要使用本文中所述的步骤删除 Skype for Business 服务器。 相反，你可以重新映像服务器。

若要完成本文中的步骤，需要 Schema Admins 组和企业管理员组的权限。 你将需要这些权限来撤消对 Active Directory 域服务的 Skype for Business Server 架构和林级别更改。 您还需要是 RTCUniversalServerAdmins 组的成员。


## <a name="prepare-to-remove-the-skype-for-business-deployment"></a>准备删除 Skype for Business 部署

将所有必需的用户帐户移动到云后，可能仍有一些需要清理的其余本地对象，如联系人和应用程序。

使用以下步骤清理这些对象，并确保你是本地管理员组和 RTCUniversalServerAdmins 组的成员。 请注意，ExUmContacts 和 PersistantChatEndPoints 在 Skype for Business Server 2019 中不可用。 如果你有 Skype for Business Server 2019，应省略以下步骤中的相应 cmdlet。

1. 若要检查是否有与 Skype for Business Server 本地部署关联的联系人或应用程序，请运行以下 Skype for Business Server PowerShell cmdlet。

   ```PowerShell
   Get-CsMeetingRoom
   Get-CsCommonAreaPhone
   Get-CsAnalogDevice
   Get-CsExUmContact
   Get-CsDialInConferencingAccessNumber
   Get-CsRgsWorkflow
   Get-CsTrustedApplicationEndpoint
   Get-CsTrustedApplication
   Get-CsPersistentChatEndpoint
   Get-CsAudioTestServiceApplication
   Get-CsCallParkOrbit
   ```
2. 查看步骤 1 中 cmdlet 的输出列表。 然后，如果可以删除对象，请运行以下 Skype for Business Server PowerShell cmdlet：

   ```PowerShell
   Get-CsMeetingRoom | Disable-CsMeetingRoom
   Get-CsCommonAreaPhone | Remove-CsCommonAreaPhone 
   Get-CsAnalogDevice | Remove-CsAnalogDevice
   Get-CsExUmContact | Remove-CsExUmContact
   Get-CsDialInConferencingAccessNumber | Remove-CsDialInConferencingAccessNumber
   Get-CsRgsWorkflow | Remove-CsRgsWorkflow
   Get-CsTrustedApplicationEndpoint | Remove-CsTrustedApplicationEndpoint
   Get-CsTrustedApplication | Remove-CsTrustedApplication -Force
   Get-CsPersistentChatEndpoint |  Remove-CsPersistentChatEndpoint
   Get-CsCallParkOrbit | Remove-CsCallParkOrbit -Force
   Get-CsVoiceRoute | Remove-CsVoiceRoute -Force
   ```
## <a name="remove-your-on-premises-skype-for-business-deployment"></a>删除本地 Skype for Business 部署

完成所有初步步骤后，可以按照以下步骤删除 Skype for Business 部署：

1. 逻辑删除 Skype for Business Server 部署，单个前端除外，如下所示：

   a. 将 Skype for Business Server 拓扑更新为具有单个前端池：

     - 在拓扑生成器中，下载新副本并导航到前端池。
     - 右键单击该池，然后单击“编辑属性”。
     - 在 **"关联"中****，** 取消选中 (媒体组件关联边缘) 然后单击"确定 **"。**
     - 如果存在多个前端池，请删除其余所有池的关联。
     - 选择 **"删除>操作"。**
     - 选择 **"操作>发布拓扑"。**

    b. 发布拓扑后，完成向导中所述的其他步骤。

2. 通过运行以下 Skype for Business Server PowerShell cmdlet 删除 Skype for Business Server 会议目录：

   ```PowerShell
   Get-CsConferenceDirectory | Remove-CsConferenceDirectory -Force
   ```

3. 通过运行以下 Skype for Business Server PowerShell cmdlet 完成 Skype for Business Server 部署的卸载：

   ```PowerShell
   Publish-CsTopology -FinalizeUninstall
   ```
   > [!NOTE]
   > 如果此步骤返回错误，请打开 Microsoft 支持票证，获取删除其余过时对象的帮助。

4. 通过运行以下 Skype for Business Server PowerShell cmdlet 删除中央管理存储服务控制点：

   ```PowerShell
   Remove-CsConfigurationStoreLocation
   ``` 

5. 通过运行以下 Skype for Business Server PowerShell cmdlet 撤消 Skype for Business Server Active Directory 域林级更改：

   ```PowerShell
   Disable-CsAdDomain
   ```
6. 通过运行以下 Skype for Business Server PowerShell cmdlet 撤消 Skype for Business Server Active Directory 域架构更改：

   ```PowerShell
   Disable-CsAdForest
   ```

## <a name="see-also"></a>另请参阅

- [停用本地 Skype for Business 环境](decommission-on-prem-overview.md)

- [将用户和终结点移动到云](decommission-move-on-prem-users.md)

- [禁用混合配置](cloud-consolidation-disabling-hybrid.md)














