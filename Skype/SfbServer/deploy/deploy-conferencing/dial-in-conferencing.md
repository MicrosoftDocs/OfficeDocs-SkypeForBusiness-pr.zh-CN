---
title: 在 Skype for Business Server 中配置电话拨入式会议
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 38d9f168-80b8-46f2-a1c0-becd84e58e73
description: 摘要： 阅读本主题可了解如何在 Skype for Business Server 中配置电话拨入式会议。
ms.openlocfilehash: a0ac408fbdf221d565f17c2d714d7aa1765d5097
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "20982004"
---
# <a name="configure-dial-in-conferencing-in-skype-for-business-server"></a>在 Skype for Business Server 中配置电话拨入式会议
 
**摘要：** 阅读本主题可了解如何在 Skype for Business Server 中配置电话拨入式会议。
  
创建包含会议工作负荷和所选电话拨入式会议的拓扑后，您必须执行额外的步骤配置电话拨入式会议。 阅读本主题中，确保之前您已阅读[规划中的业务服务器的 Skype 电话拨入式会议](../../plan-your-deployment/conferencing/dial-in-conferencing.md)、[会议中的业务服务器 Skype 的硬件和软件要求](../../plan-your-deployment/conferencing/hardware-and-software-requirements.md)和[部署流程图和清单电话拨入式会议](deploy-conferencing.md#deployment-flowchart-and-checklist-for-dial-in-conferencing)。 
  
为了配置电话拨入式会议，必须执行以下任务：
  
- [Configure dial plans](dial-in-conferencing.md#BKMK_ConfigureDialPlans)
    
- [Configure dial-in conferencing regions](dial-in-conferencing.md#BKMK_ConfigureDialInRegions)
    
- [Configure dial-in access numbers](dial-in-conferencing.md#BKMK_ConfigureDialInAccessNumbers)
    
- [Configure conferencing policies](dial-in-conferencing.md#BKMK_ConfigureConferencingPolicies)
    
- [Assign a Line URI to a user account](dial-in-conferencing.md#BKMK_AssignaLineURI)
    
此外，可以执行以下可选任务。 有关这些可选任务的详细信息，请参阅[Skype 业务服务器中的电话拨入式会议管理](../../manage/conferencing/dial-in-conferencing.md)。
  
- 管理电话拨入式会议的 PIN 策略
    
- 管理 DTMF 命令的键映射
    
- 创建会议目录
    
- 管理会议加入和离开通知
    
- 测试电话拨入式会议设置
    
- 给电话拨入用户发送欢迎邮件
    
## <a name="configure-dial-plans"></a>配置拨号计划
<a name="BKMK_ConfigureDialPlans"> </a>

部署电话拨入式会议时，需要创建或修改用于路由拨入访问电话号码的一个或多个拨号计划。 您还必须确保每个拨号计划都包含至少一个规范化规则-电话分机转换为 E.164 格式的完整电话号码的规则。 
  
电话拨入式会议的用户作为通过身份验证的企业用户，输入其个人标识号 (PIN) 和电话号码来加入会议。你需要规范化规则来将分机号转换为完整电话号码，这样用户只要输入电话分机号，就可通过身份验证。
  
若要设置电话拨入式会议的拨号计划：
  
- 无论是否部署企业语音，都需修改全局拨号计划，以添加电话拨入式会议区域，并确保规范化规则准确转换拨入访问号码。 有关详细说明，请参阅[创建或修改拨号计划中 Skype Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md)。
    
- 如果不部署企业语音，请创建电话拨入式会议访问号码的拨号计划。 确保其中包含电话拨入式会议区域。 有关详细说明，请参阅[创建或修改拨号计划中 Skype Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md)。
    
- 如果已部署企业语音，请根据需要修改企业语音拨号计划以纳入区域，并对拨入访问号码使用相应的规范化规则。 还可以创建仅用于拨入访问号码的专用拨号计划。 有关详细说明，请参阅[创建或修改拨号计划中 Skype Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md)。
    
有关创建规范化规则的详细信息，请参阅[创建或修改规范化规则中的业务的 Skype](../../deploy/deploy-enterprise-voice/normalization-rules.md)。
  
## <a name="configure-dial-in-conferencing-regions"></a>配置拨入式会议区域
<a name="BKMK_ConfigureDialInRegions"> </a>

创建拨号计划时，要指定适用于该拨号计划的电话拨入式会议区域。电话拨入式会议区域将电话拨入式会议访问号码与相应的拨号计划相关联。创建拨入访问号码时，要选择将访问号码与相应的拨号计划相关联的区域。 
  
因为为所有拨号计划指定区域非常重要，我们建议你验证是否所有拨号计划均有会议区域。 
  
若要验证是否为所有电话拨入式会议拨号计划设置了区域，请使用 **Get-CsDialPlan** cmdlet。 如果拨号计划中缺少区域，可使用 **Set-CsDialPlan** cmdlet 设置区域。 您可以使用 Skype 的业务 Server Control Panel 中现有的拨号计划更新该区域。 有关使用的业务 Server Control Panel Skype 的详细信息，请参阅[创建或修改拨号计划中 Skype Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md)。
  
### <a name="to-verify-whether-dial-plans-have-the-region-property-set"></a>验证拨号计划是否设置了 region 属性

1. 以 RTCUniversalServerAdmins 组成员或 **Cs-VoiceAdministrator**、**Cs-ServerAdministrator** 或 **CsAdministrator** 角色成员的身份登录计算机。
    
2. 启动 Skype for Business Server 命令行管理程序：依次单击“**开始**”、“**所有程序**”和“**Skype for Business 2015**”，然后单击“**Skype for Business Server 命令行管理程序**”。
    
3. 在命令提示符下，运行以下内容：
    
   ```
   Get-CsDialPlan [-Identity <Identifier of the dial plans to be retrieved>]
   ```

   例如：
    
   ```
   Get-CsDialPlan
   ```

   在此例中，返回为组织配置的所有拨号计划。
    
4. 查看返回的拨号计划，标识缺少电话拨入式会议区域的任何拨号计划。 
    
有关详细信息，请参阅[Get-csdialplan](https://docs.microsoft.com/powershell/module/skype/get-csdialplan?view=skype-ps)。
  
### <a name="to-set-the-region-property-for-a-dial-plan"></a>设置拨号计划的 region 属性

1. 以 RTCUniversalServerAdmins 组成员或 **Cs-VoiceAdministrator**、**Cs-ServerAdministrator** 或 **CsAdministrator** 角色成员的身份登录计算机。
    
2. 启动 Skype for Business Server 命令行管理程序：依次单击“**开始**”、“**所有程序**”和“**Skype for Business 2015**”，然后单击“**Skype for Business Server 命令行管理程序**”。
    
3. 对于缺少电话拨入式会议区域的任何拨号计划，请运行：
    
   ```
   Set-CsDialPlan [-Identity <Identity of the dial plan to be modified>] -DialinConferencingRegion "<new region>"
   ```

   例如：
    
   ```
   Set-CsDialPlan -Identity Redmond -DialinConferencingRegion "US West Coast"
   ```

   在此例中，对 Identity 为 Redmond 的拨号计划进行修改，将 DialinConferencingRegion 属性设置为“US West Coast”。 
    
有关详细信息，请参阅[Set-csdialplan](https://docs.microsoft.com/powershell/module/skype/set-csdialplan?view=skype-ps)。
  
## <a name="configure-dial-in-access-numbers"></a>配置拨入访问号码
<a name="BKMK_ConfigureDialInAccessNumbers"> </a>

部署电话拨入式会议时，需要设置用户可以从公用电话交换网 (PSTN) 拨打以加入会议的音频部分的电话号码。这些拨入访问号码显示在会议邀请和“电话拨入式会议设置”网页上。
  
创建拨入访问号码前，必须首先规划电话拨入式会议区域，然后配置区域的拨号计划。 有关区域的详细信息，请参阅[Plan for Business Server 的 Skype 中电话拨入式会议](../../plan-your-deployment/conferencing/dial-in-conferencing.md)。 有关详细信息配置拨号计划的电话拨入式会议，请参阅[创建或修改拨号计划中 Skype Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md)。
  
> [!NOTE]
> 在 Active Directory 域服务 (AD DS) 完成对一个新拨入访问号码的复制前，无法使用该拨入访问号码。复制可能需要几个小时才能完成。 
  
> [!NOTE]
> 创建拨入访问号码后，可以修改 Active Directory 联系人对象的显示名，以便用户可以更轻松地识别正确的访问号码。 若要修改的显示名称，请使用[Set-csdialinconferencingaccessnumber](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps) cmdlet。 不应手动修改 Active Directory 对象。
  
### <a name="to-create-a-dial-in-access-number"></a>创建拨入访问号码

1. 使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。
    
2.  打开 Skype 业务 Server Control Panel。
    
3. 在左侧导航栏中，单击“会议”****，然后单击“拨入访问号码”****。
    
4. 在“拨入访问号码”**** 页上，执行下列某个操作：
    
   - 单击“新建”**** 打开“新建拨入访问号码”****。
    
   - 单击列表中的一个拨入访问号码，再单击“编辑”****，然后单击“显示详细信息”****。
    
    > [!NOTE]
    > 使用搜索字段搜索拨入访问号码列表中某一列的内容时，可能得不到预期结果。此时，可以按照列的关注度对列表进行排序，以识别要查看或更改的拨入访问号码。 
  
5. 在“显示号码”**** 中，键入公用电话交换网 (PSTN) 电话用户为加入会议而拨打的电话号码。该号码会显示在会议邀请和电话拨入式会议设置网页中。
    
6. 在“显示名称”**** 中，键入拨入访问号码的说明。 这是与业务搜索结果中 Skype 的拨入访问号码相关联的名称。 用户呼叫访问号码时，此名称会显示在客户端上。 
    
7. 在“线路 URI”**** 中，使用 TEL URI 格式键入拨入访问号码的 E.164 号码，请在此号码前添加 + 符号，不要添加空格。例如：tel:+14255550200。
    
    > [!NOTE]
    > 同一线路 URI 不能由其他电话拨入式会议访问号码重复使用。 
  
8. 在“SIP URI”**** 中，执行下列操作：
    
   - 在文本框中，为此电话拨入式会议访问号码键入唯一的 SIP URI。 此 SIP URI 是显示在各种的位置，包括但不是限于呼叫通知消息和早期版本的 Lync 客户端。
    
    > [!NOTE]
    > 同一 SIP URI 不能由其他电话拨入式会议访问号码重复使用。创建访问号码之后，将不能修改 SIP URI。更改 SIP URI 的唯一方法是删除并重新创建访问号码。 
  
   - 在下拉列表框中，单击支持此拨入访问号码的会议助理应用程序的域。
    
9. 在“池”**** 中，单击运行支持此拨入访问号码的会议助理实例的池。
    
    > [!NOTE]
    > 如果您需要更改池创建访问号码后，您必须使用[Move-csapplicationendpoint](https://docs.microsoft.com/powershell/module/skype/move-csapplicationendpoint?view=skype-ps) cmdlet 或删除并重新创建访问号码。
  
10. 在“主要语言”**** 中，单击针对此拨入访问号码播放提示时使用的语言。 
    
    主要语言是会议助理应答呼叫时使用的语言。支持的语言显示在电话拨入式会议设置网页上的每个访问电话号码旁边。
    
11. （可选）在“辅助语言（最多 4 个）”**** 中，单击“添加”****，选择一个或多个要为此拨入访问号码的呼叫者提供支持的其他语言，然后单击“确定”****。 
    
    最多可以为每个拨入访问号码选择四种辅助语言。用户通过电话拨入加入会议时，在输入会议 ID 之前可以选择一种辅助语言。
    
12. 若要添加区域的拨入访问号码，在**关联区域**，下单击**添加**，单击一个或多个区域，与拨号计划针对此拨入访问号码，然后单击**确定**。
    
13. 要从拨入访问号码中删除某个区域，请在“关联区域”**** 下，单击要删除的区域，然后单击“删除”****。
    
14. 单击“**提交**”。
    
## <a name="configure-conferencing-policies"></a>配置会议策略
<a name="BKMK_ConfigureConferencingPolicies"> </a>

会议策略是一种用户帐户设置，用于指定参与者的会议体验。您可以创建具有站点作用域或用户作用域的会议策略。会议策略设置包含会议安排和参与会议的多个方面。一些会议策略设置支持参与者参加电话拨入式会议。当您配置电话拨入式会议时，应该确认已针对组织正确设置了这些字段，并根据需要进行修改。 
  
有关配置会议策略的详细信息，请参阅[管理中的业务服务器 Skype 的会议策略](../../manage/conferencing/conferencing-policies.md)。
  
## <a name="assign-a-line-uri-to-a-user-account"></a>Assign a Line URI to a user account
<a name="BKMK_AssignaLineURI"> </a>

拨入用户输入其电话号码或分机号和 PIN，即可以经过身份验证的用户身份加入会议。 将电话**线路 URI**指定上 Skype Business Server 用户帐户，则需要进行身份验证。
  
本主题中的过程介绍如何为单个用户帐户分配“**线路 URI**”。 如果需要为多个用户帐户分配“**线路 URI**”，则可以创建使用 **Set-CsUser** cmdlet 的脚本。 有关使用一个示例脚本将**线路 URI**分配给多个用户帐户的详细信息，请参阅[分配给多个用户的线路 Uri](https://go.microsoft.com/fwlink/p/?linkId=196945)。
  
1. 以 RTCUniversalServerAdmins 组成员或者 **Cs-UserAdministrator** 或 **CsAdministrator** 角色成员的身份登录计算机。
    
2.  打开 Skype 业务 Server Control Panel。
    
3. 在左导航栏中，单击“用户”****。
    
4. 在搜索字段中，键入要为其配置电话拨入式会议的用户的名称，或单击“**添加筛选器**”以指定搜索字段，然后单击“**查找**”。
    
5. 双击用户名打开“**编辑 Skype for Business Server 用户**”对话框。
    
6. 在“**电话**”下的“**线路 URI**”字段中，键入唯一的规范化电话号码（例如，tel:+14255550200）。
    
    > [!NOTE]
    > 仅当将“**电话**”设置为“**仅限 PC 到 PC**”、“**企业语音**”、“**远程呼叫控制**”或“**仅远程呼叫控制**”时，才可以指定“**线路 URI**”。 
  
7. 单击“**提交**”。
    

