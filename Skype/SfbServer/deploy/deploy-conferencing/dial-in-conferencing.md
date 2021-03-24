---
title: 在 Skype for Business Server 中配置电话拨入式会议
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 38d9f168-80b8-46f2-a1c0-becd84e58e73
description: 摘要：阅读本主题，了解如何在 Skype for Business Server 中配置电话拨入式会议。
ms.openlocfilehash: 5f618e22cc45585baddf1e8d6090b9e211dc5681
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103848"
---
# <a name="configure-dial-in-conferencing-in-skype-for-business-server"></a>在 Skype for Business Server 中配置电话拨入式会议
 
**摘要：** 阅读本主题，了解如何在 Skype for Business Server 中配置电话拨入式会议。
  
创建包含会议工作负荷和所选电话拨入式会议拓扑后，必须执行其他步骤来配置电话拨入式会议。 在阅读本主题之前，请确保已阅读 Plan [for dial-in conferencing in Skype for Business Server、Hardware](../../plan-your-deployment/conferencing/dial-in-conferencing.md)and software requirements for [](deploy-conferencing.md#deployment-flowchart-and-checklist-for-dial-in-conferencing) [conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/hardware-and-software-requirements.md)以及部署流程图和电话拨入式会议清单。 
  
若要配置电话拨入式会议，必须执行以下任务：
  
- [配置拨号计划](dial-in-conferencing.md#BKMK_ConfigureDialPlans)
    
- [配置电话拨入式会议区域](dial-in-conferencing.md#BKMK_ConfigureDialInRegions)
    
- [配置拨入访问号码](dial-in-conferencing.md#BKMK_ConfigureDialInAccessNumbers)
    
- [配置会议策略](dial-in-conferencing.md#BKMK_ConfigureConferencingPolicies)
    
- [为用户帐户分配线路 URI](dial-in-conferencing.md#BKMK_AssignaLineURI)
    
此外，您还可以执行以下可选任务。 有关这些可选任务的信息，请参阅在 [Skype for Business Server](../../manage/conferencing/dial-in-conferencing.md)中管理电话拨入式会议。
  
- 管理电话拨入式会议 PIN 策略
    
- 管理 DTMF 命令的键映射
    
- 创建会议目录
    
- 管理会议加入和离开通知
    
- 测试电话拨入式会议设置
    
- 向拨入用户发送欢迎邮件
    
## <a name="configure-dial-plans"></a>配置拨号计划
<a name="BKMK_ConfigureDialPlans"> </a>

部署电话拨入式会议时，需要创建或修改一个或多个用于路由拨入访问电话号码的拨号计划。 您还必须确保每个拨号计划包含至少一个规范化规则，即将电话分机号转换为 E.164 格式的完整电话号码的规则。 
  
电话拨入式会议的用户通过输入其个人标识号 (PIN) 及其电话号码，可以作为经过身份验证的企业用户加入会议。 需要使用规范化规则将分机号转换为完整的电话号码，以便在用户只输入电话分机号时可以对其进行身份验证。
  
设置电话拨入式会议拨号计划：
  
- 不论您是否企业语音，修改全局拨号计划以添加电话拨入式会议区域，并确保规范化规则准确转换您的拨入访问号码。 有关详细说明，请参阅[Create or modify a dial plan in Skype for Business Server。](../../deploy/deploy-enterprise-voice/dial-plans.md)
    
- 如果未部署企业语音，请为电话拨入式会议访问号码创建拨号计划。 确保其中包含电话拨入式会议区域。 有关详细说明，请参阅[Create or modify a dial plan in Skype for Business Server。](../../deploy/deploy-enterprise-voice/dial-plans.md)
    
- 如果已部署企业语音，企业语音修改拨号计划以包含区域，并针对拨入访问号码使用相应的规范化规则。 还可以创建仅用于拨入访问号码的专用拨号计划。 有关详细说明，请参阅[Create or modify a dial plan in Skype for Business Server。](../../deploy/deploy-enterprise-voice/dial-plans.md)
    
有关创建规范化规则的详细信息，请参阅在 Skype for Business 中创建或修改 [规范化规则](../../deploy/deploy-enterprise-voice/normalization-rules.md)。
  
## <a name="configure-dial-in-conferencing-regions"></a>配置电话拨入式会议区域
<a name="BKMK_ConfigureDialInRegions"> </a>

设置拨号计划时，指定应用于拨号计划的电话拨入式会议区域。 电话拨入式会议区域将电话拨入式会议访问号码与相应的拨号计划关联。 在创建拨入访问号码时，选择将该访问号码与相应拨号计划关联的区域。 
  
由于必须指定所有拨号计划的区域，因此建议您验证所有拨号计划是否都有会议区域。 
  
若要验证是否针对所有电话拨入式会议拨号计划设置了区域，请使用 **Get-CsDialPlan** cmdlet。 如果拨号计划中缺少区域，可使用 **Set-CsDialPlan** cmdlet 设置区域。 您还可以使用 Skype for Business Server 控制面板更新现有拨号计划中的区域。 有关使用 Skype for Business Server 控制面板的详细信息，请参阅 Create [or modify a dial plan in Skype for Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md)。
  
### <a name="to-verify-whether-dial-plans-have-the-region-property-set"></a>验证拨号计划是否设置了 region 属性

1. 以 RTCUniversalServerAdmins 组成员或 **Cs-VoiceAdministrator**、**Cs-ServerAdministrator** 或 **CsAdministrator** 角色成员的身份登录计算机。
    
2. 启动 Skype for Business Server命令行管理程序：单击"开始"，单击"所有程序"，单击 **"Skype for Business 2015"，** 然后单击 **"Skype for Business Server 命令行管理程序"。**
    
3. 在命令提示符下，运行以下内容：
    
   ```powershell
   Get-CsDialPlan [-Identity <Identifier of the dial plans to be retrieved>]
   ```

   例如：
    
   ```powershell
   Get-CsDialPlan
   ```

   在此例中，返回为组织配置的所有拨号计划。
    
4. 查看返回的拨号计划，标识缺少电话拨入式会议区域的任何拨号计划。 
    
有关详细信息，请参阅 [Get-CsDialPlan](/powershell/module/skype/get-csdialplan?view=skype-ps)。
  
### <a name="to-set-the-region-property-for-a-dial-plan"></a>设置拨号计划的 region 属性

1. 以 RTCUniversalServerAdmins 组成员或 **Cs-VoiceAdministrator**、**Cs-ServerAdministrator** 或 **CsAdministrator** 角色成员的身份登录计算机。
    
2. 启动 Skype for Business Server命令行管理程序：单击"开始"，单击"所有程序"，单击 **"Skype for Business 2015"，** 然后单击 **"Skype for Business Server 命令行管理程序"。**
    
3. 对于缺少电话拨入式会议区域的任何拨号计划，请运行：
    
   ```powershell
   Set-CsDialPlan [-Identity <Identity of the dial plan to be modified>] -DialinConferencingRegion "<new region>"
   ```

   例如：
    
   ```powershell
   Set-CsDialPlan -Identity Redmond -DialinConferencingRegion "US West Coast"
   ```

   在此例中，对 Identity 为 Redmond 的拨号计划进行修改，将 DialinConferencingRegion 属性设置为“US West Coast”。 
    
有关详细信息，请参阅 [Set-CsDialPlan](/powershell/module/skype/set-csdialplan?view=skype-ps)。
  
## <a name="configure-dial-in-access-numbers"></a>配置拨入访问号码
<a name="BKMK_ConfigureDialInAccessNumbers"> </a>

部署电话拨入式会议时，需要设置用户可从公用电话交换网 (PSTN) 拨打的电话号码，以加入会议的音频部分。 这些拨入访问号码显示在会议邀请和"电话拨入式会议设置"网页中。
  
必须先规划电话拨入式会议区域，然后使用区域配置拨号计划，然后才能创建拨入访问号码。 有关区域的详细信息，请参阅在 Skype for Business Server 中 [规划电话拨入式会议](../../plan-your-deployment/conferencing/dial-in-conferencing.md)。 有关配置电话拨入式会议拨号计划的详细信息，请参阅在 Skype for Business Server 中 [创建或修改拨号计划](../../deploy/deploy-enterprise-voice/dial-plans.md)。
  
> [!NOTE]
> 在 Active Directory 域服务 (AD DS) 完成该访问号码的复制之前，不能使用新的拨入访问号码。 复制可能需要几个小时才能完成。 
  
> [!NOTE]
> 创建拨入访问号码后，可以修改 Active Directory 显示名称对象的号码，以便用户更轻松地识别正确的访问号码。 若要修改显示名称，请使用 [Set-CsDialInConferencingAccessNumber](/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps) cmdlet。 不应手动修改 Active Directory 对象。
  
### <a name="to-create-a-dial-in-access-number"></a>创建拨入访问号码

1. 使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。
    
2. 打开 Skype for Business Server 控制面板。
    
3. 在左侧导航栏中，单击“会议”，然后单击“拨入访问号码”。
    
4. 在 **"拨入访问号码"** 页上，执行下列操作之一：
    
   - 单击 **"新建**"打开 **"新建拨入访问号码"。**
    
   - 单击列表中的某个拨入访问号码，再单击"编辑"，然后单击"显示 **详细信息"。**
    
     > [!NOTE]
     > 使用搜索字段搜索拨入访问号码列表中列的内容可能不会获得预期的结果。 相反，按关注列对列表进行排序，以标识要查看或更改的拨入访问号码。 
  
5. 在 **"显示** 号码"中，键入公用电话交换网 (PSTN) 电话用户为加入会议而拨打的电话号码。 此号码显示在会议邀请和电话拨入式会议设置网页中。
    
6. 在 **"显示** 名称"中，键入拨入访问号码的说明。 这是与 Skype for Business 搜索结果中的拨入访问号码相关联的名称。 当用户呼叫访问号码时，此名称将显示在客户端中。 
    
7. 在 **"线路 URI"** 中，以 TEL URI 格式键入拨入访问号码的 E.164 号码，包括号码前的 + 符号和不包括空格。 例如，tel：+14255550200。
    
    > [!NOTE]
    > 同一线路 URI 不能由另一个电话拨入式会议访问号码重复使用。 
  
8. 在 **SIP URI** 中，执行以下操作：
    
   - 在文本框中，为此电话拨入式会议访问号码键入唯一的 SIP URI。 此 SIP URI 显示在各种位置，包括但不限于呼叫通知消息和早期版本的 Lync 客户端。
    
     > [!NOTE]
     > 同一 SIP URI 不能由另一个电话拨入式会议访问号码重复使用。 创建访问号码后，不能修改 SIP URI。 更改 SIP URI 的唯一方法就是删除并重新创建访问号码。 
  
   - 在下拉列表框中，单击支持此拨入访问号码的会议助理应用程序的域。
    
9. 在 **"** 池"中，单击运行支持此拨入访问号码的会议助理实例的池。
    
    > [!NOTE]
    > 如果在创建访问号码后需要更改池，则必须使用 [Move-CsApplicationEndpoint](/powershell/module/skype/move-csapplicationendpoint?view=skype-ps) cmdlet 或删除并重新创建访问号码。
  
10. 在 **"主要** 语言"中，单击为此拨入访问号码播放提示的语言。 
    
    主要语言是会议助理用于应答呼叫的语言。 支持的语言显示在"电话拨入式会议设置"网页上的每个访问电话号码旁边。
    
11.  (可选) 在辅助语言 (最多四) 中，单击"添加 **"，** 选择要为此拨入访问号码的呼叫者支持的一种或多种语言，然后单击"确定 **"。** 
    
    对于每个拨入访问号码，你最多可以选择四种辅助语言。 用户在拨入会议时，可以在输入会议 ID 之前选择辅助语言。
    
12. 若要为拨入访问号码添加区域，请在"关联区域"下，单击"添加"，单击与此拨入访问号码的拨号计划关联的一个或多个区域，然后单击"确定 **"。**
    
13. 若要从拨入访问号码中删除某个区域，请在"关联区域"下，单击要删除的区域，然后单击"删除 **"。**
    
14. 单击“提交”。
    
## <a name="configure-conferencing-policies"></a>配置会议策略
<a name="BKMK_ConfigureConferencingPolicies"> </a>

会议策略是一种用户帐户设置，用于指定参与者的会议体验。您可以创建具有站点作用域或用户作用域的会议策略。会议策略设置包含会议安排和参与会议的多个方面。一些会议策略设置支持参与者参加电话拨入式会议。当您配置电话拨入式会议时，应该确认已针对组织正确设置了这些字段，并根据需要进行修改。 
  
有关配置会议策略的信息，请参阅在 Skype [for Business Server](../../manage/conferencing/conferencing-policies.md)中管理会议策略。
  
## <a name="assign-a-line-uri-to-a-user-account"></a>为用户帐户分配线路 URI
<a name="BKMK_AssignaLineURI"> </a>

拨入用户输入其电话号码或分机号和 PIN，即可以经过身份验证的用户身份加入会议。 身份验证需要 Skype for Business Server 用户帐户上指定的电话线路 **URI。**
  
本主题中的过程介绍如何为单个用户帐户分配“线路 URI”。 如果需要为多个用户帐户分配“线路 URI”，则可以创建使用 **Set-CsUser** cmdlet 的脚本。 有关使用示例脚本将线路 **URI** 分配给多个用户帐户的详细信息，请参阅将线路 [URI 分配给多个用户](https://go.microsoft.com/fwlink/p/?linkId=196945)。
  
1. 以 RTCUniversalServerAdmins 组成员或者 **Cs-UserAdministrator** 或 **CsAdministrator** 角色成员的身份登录计算机。
    
2.  打开 Skype for Business Server 控制面板。
    
3. 在左侧导航栏中，单击 **“用户”**。
    
4. 在搜索字段中，键入要为其配置电话拨入式会议的用户的名称，或单击 **“添加筛选器”** 以指定搜索字段，然后单击 **“查找”**。
    
5. 双击用户名以打开"编辑 Skype **for Business Server 用户"** 对话框。
    
6. 在 **“电话”** 下的 **“线路 URI”** 字段中，键入唯一的规范化电话号码（例如，tel:+14255550200）。
    
    > [!NOTE]
    > 只有当电话设置为仅 PC 到PC、企业语音、远程呼叫控制或远程呼叫控制 **时，你** 才能指定线路 **URI。**  
  
7. 单击“提交”。
