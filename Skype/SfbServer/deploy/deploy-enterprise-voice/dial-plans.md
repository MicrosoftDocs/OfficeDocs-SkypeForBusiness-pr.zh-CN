---
title: 在拨号计划中创建或修改Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d2fef3d0-7e78-4591-b712-d62ac71d71a5
description: 摘要：了解如何使用控制面板创建或修改Skype for Business Server拨号计划。
ms.openlocfilehash: c5c4a819c21708f31fbe0bf4801900143d0d4538
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/08/2021
ms.locfileid: "60864359"
---
# <a name="create-or-modify-a-dial-plan-in-skype-for-business-server"></a>在拨号计划中创建或修改Skype for Business Server

**摘要：** 了解如何使用控制面板创建或修改拨号Skype for Business Server拨号计划。

### <a name="to-create-a-dial-plan"></a>创建拨号计划

1. 打开Skype for Business Server控制面板"。

2. 在左侧导航栏中，单击“语音路由”，然后单击“拨号计划”。

3. 在“拨号计划”页上，单击“新建”，然后为拨号计划选择作用域：

   - “站点拨号计划”将应用于整个站点，分配给用户拨号计划的用户或组除外。 如果选择" **站点** "作为拨号计划的作用域，则必须从"选择站点"对话框中 **选择** 站点。 如果已经为站点创建了拨号计划，则该站点不会显示在“选择站点”对话框中。

   - “池拨号计划”可以应用于公用电话交换网 (PSTN) 网关或注册器。 如果选择" **池** "作为拨号计划的作用域，请从"选择服务"对话框中选择 PSTN 网关 **或** 注册器。 如果已经为服务（PSTN 网关或注册器）创建了拨号计划，则该服务不会显示在列表中。

   - “用户拨号计划”可以应用于指定的用户或组。

     > [!NOTE]
     > 选择拨号计划作用域后，就无法更改。

4. 如果要创建用户拨号计划，请在“新建拨号计划”对话框的“名称”字段中输入描述性名称。保存此名称后，就无法更改。

    > [!NOTE]
    > 对于站点拨号计划，"名称"字段会使用站点名称预先填充，并且不能更改。> 对于池拨号计划，"名称"字段会使用PSTN 网关或注册器名称预先填充，并且不能更改。

5. “简单名称”字段会使用与“名称”字段中显示的相同名称预先填充。您可以选择编辑该字段来指定描述性更强的名称，以反映应用该拨号计划的站点、服务或用户。

   > [!IMPORTANT]
   > 简单 **名称** 在部署的所有拨号计划中必须是唯一的。 它不能超过 256 个 Unicode 字符，每个 Unicode 字符可以是字母或数字字符、连字符 (-) 、周期 (.) 或下划线字符 (_) .> 不支持的字符包括空格和保留字符，如 RFC 3966 ( <http://www.ietf.org/rfc/rfc3966.txt>) 中的定义。 "简单名称" **中** 不支持的保留字符 **包括** ：>";""/" "?"":" "@" "&amp;" "=" "+" "$" ","

6. （可选）在“说明”字段中，您可以键入有关拨号计划的其他描述性信息。

7. （可选）如果要将此拨号计划用作电话拨入式访问号码的区域，请指定“电话拨入式会议区域”。如果不希望将此拨号计划用于电话拨入式访问号码，请将此字段留空。

    > [!NOTE]
    > 电话拨入式会议区域需要将电话拨入式会议访问号码与一个或多个拨号计划相关联。

8. （可选）在“外部访问前缀”字段中，指定一个值，该值仅在用户需要拨打一个或多个附加的前导数字（例如 9）以拨通外线时使用。键入的前缀值不得超过 4 个字符（#、* 和 0-9）。

    > [!NOTE]
    > 如果指定了外部访问前缀，则不需要创建新的规范化规则来满足前缀。

9. 按如下所示为拨号计划关联并配置规范化规则：

    - 若要从部署中提供的所有规范化规则列表中选择一个或多个企业语音，请单击"选择 **"。** 在“选择规范化规则”中，突出显示要与拨号计划关联的规则，然后单击“确定”。

   - 要定义新的规范化规则并将其与拨号计划相关联，请单击“新建”。 有关定义新规则的详细信息，请参阅 Create [or modify a normalization rule in Skype for Business](normalization-rules.md)。

   - 要编辑已经与拨号计划关联的规范化规则，请突出显示相应的规则名称，然后单击“显示详细信息”。

   - 要复制现有规范化规则以作为定义新规则的起点，请突出显示相应的规则名称，单击“复制”，然后单击“粘贴”。

   - 要从拨号计划中删除某个规范化规则，请突出显示相应的规则名称，然后单击“删除”。

     > [!NOTE]
     > 每个拨号计划都必须至少有一个关联的规范化规则。 若要了解如何确定拨号计划所需的全部规范化规则，请参阅规划文档中的 Plan [for outbound voice routing in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/outbound-voice-routing.md) in the Planning documentation。

10. 验证拨号计划的规范化规则是否按正确的顺序排列。 若要更改规则在列表中的位置，请突出显示规则名称，然后单击向上箭头或向下箭头。

    > [!IMPORTANT]
    > Skype for Business Server从上到下遍历规范化规则列表，并使用第一个匹配拨打号码的规则。 如果要配置拨号计划以使拨打号码可以匹配多个规范化规则，请确保限制较严格的规则排在限制较宽松的规则上方。 >默认的"全部保留 **"** 规范化规则^ (\d) {11} $ 匹配任何 11 位数字。 例如，如果添加与以 1425 开头的 11 位数字相匹配的规范化规则，请确保"全部保留"排序在限制性较严格的^ (1425\d) $ 规则 {7} 下。

11. （可选）输入一个号码来测试拨号计划，然后单击“执行”。测试结果会显示在“输入要测试的号码”下。

12. 单击“确定”。

13. 在“拨号计划”页上，单击“提交”，然后单击“全部提交”。

    > [!NOTE]
    > 任何时候创建拨号计划，都必须运行“全部提交”命令以发布配置更改。 有关详细信息，请参阅操作[文档中的](voice-route-config-changes.md)Publish pending changes to the voice routing configuration in Skype for Business in the Operations documentation。

### <a name="to-modify-a-dial-plan"></a>修改拨号计划

1. 以 RTCUniversalServerAdmins 组成员的身份或者以 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色成员的身份登录计算机。有关详细信息，请参阅 **Delegate Setup Permissions**。

2. 打开浏览器窗口，然后输入管理 URL 以打开Skype for Business Server控制面板。

3. 在左侧导航栏中，单击“语音路由”，然后单击“拨号计划”。

4. 在“拨号计划”页上，双击某个拨号计划名称。

    > [!NOTE]
    > 拨号计划的作用域和名称是在创建该拨号计划时设置的，且不能更改。

5. （可选）在“编辑拨号计划”中，编辑“简单名称”字段，该字段会预填充“名称”字段中显示的相同名称，以指定反映应用该拨号计划的站点、服务或用户的更具描述性的名称。

    > [!IMPORTANT]
    > 简单 **名称在** Lync Server 2013 部署内的所有拨号计划中必须是唯一的。 "简单名称"字段中不允许包含 256 个 Unicode 字符，每个 Unicode 字符可以是字母或数字字符、连字符 (-) 、 (.) 、加号 (+) 或下划线 (_) .>**空格。**

6. （可选）在“说明”字段中，键入有关拨号计划的描述性信息。

7. （可选）如果要将此拨号计划用作电话拨入式访问号码的区域，请指定“电话拨入式会议区域”。如果不希望将此拨号计划用于电话拨入式访问号码，请将此字段留空。

    > [!NOTE]
    > 电话拨入式会议区域需要将电话拨入式会议访问号码与一个或多个拨号计划相关联。

8. （可选）在“外部访问前缀”字段中，指定一个值，该值仅在用户需要拨打一个或多个附加的前导数字（例如 9）以拨通外线时使用。键入的前缀值不得超过 4 个字符（即 #、* 和 0-9）。

    > [!NOTE]
    > 如果指定了外部访问前缀，则不需要创建新的规范化规则来满足前缀。

9. 为拨号计划关联并配置规范化规则：

   - 若要从部署中提供的所有规范化规则列表中选择一个或多个企业语音，请单击"选择 **"。** 在“选择规范化规则”对话框中，突出显示要与拨号计划关联的规则，然后单击“确定”。

   - 要定义新的规范化规则并将其与拨号计划相关联，请单击“新建”。 有关定义新规则的详细信息，请参阅 Create [or modify a normalization rule in Skype for Business](normalization-rules.md)。

   - 要编辑已经与拨号计划关联的规范化规则，请突出显示相应的规则名称，然后单击“显示详细信息”。

   - 要复制现有规范化规则以作为定义新规则的起点，请突出显示相应的规则名称，单击“复制”，然后单击“粘贴”。

   - 要从拨号计划中删除某个规范化规则，请突出显示相应的规则名称，然后单击“删除”。

     > [!NOTE]
     > 每个拨号计划都必须至少有一个关联的规范化规则。 若要详细了解如何确定拨号计划所需的全部规范化规则，请参阅规划文档中的 Plan [for outbound voice routing in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/outbound-voice-routing.md) in the Planning documentation。

10. 验证拨号计划的规范化规则是否按正确的顺序排列。 若要更改规则在列表中的位置，请突出显示规则名称，然后单击向上箭头或向下箭头。

    > [!IMPORTANT]
    > Skype for Business Server从上到下遍历规范化规则列表，并使用第一个匹配拨打号码的规则。 如果要配置拨号计划以使拨打号码可以匹配多个规范化规则，请确保限制较严格的规则排在限制较宽松的规则上方。 >默认的"全部保留 **"** 规范化规则^ (\d) {11} $ 匹配任何 11 位数字。 例如，如果添加与以 1425 开头的 11 位数字相匹配的规范化规则，请确保"全部保留"排序在限制性较严格的^ (1425\d) $ 规则 {7} 下。

11. （可选）输入一个号码来测试拨号计划，然后单击“执行”。测试结果会显示在“输入要测试的号码”下。

    > [!NOTE]
    > 您可以保存尚未通过测试的拨号计划，并在稍后对其进行重新配置。有关详细信息，请参阅[Testing Voice Routing](/previous-versions/office/lync-server-2013/lync-server-2013-test-voice-routing)。

12. 单击“确定”。

13. 在“拨号计划”页上，单击“提交”，然后单击“全部提交”。

    > [!NOTE]
    > 任何时候创建或修改拨号计划，都必须运行“全部提交”命令以发布配置更改。 有关详细信息，请参阅操作[文档中的](voice-route-config-changes.md)Publish pending changes to the voice routing configuration in Skype for Business in the Operations documentation。

## <a name="see-also"></a>另请参阅

[在语音路由配置中发布待处理Skype for Business](voice-route-config-changes.md)