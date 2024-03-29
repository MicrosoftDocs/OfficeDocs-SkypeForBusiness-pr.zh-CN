---
title: 创建或修改语音策略，并配置 PSTN 用法Skype for Business
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
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
ms.assetid: e6ff27e0-e2d1-4445-840f-08f738200c20
description: 摘要：使用控制面板创建或修改语音策略并配置 PSTN 用法Skype for Business Server记录。
ms.openlocfilehash: 988ce046e3ef5dbbf9020deeb79665b7fda3f9b2
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/05/2022
ms.locfileid: "62386280"
---
# <a name="create-or-modify-a-voice-policy-and-configure-pstn-usage-records-in-skype-for-business"></a>创建或修改语音策略，并配置 PSTN 用法Skype for Business

**摘要：** 使用控制面板创建或修改语音策略和配置 PSTN Skype for Business Server记录。

> [!NOTE]
> 每个语音策略都必须至少有一个关联的公用电话交换网 (PSTN) 用法记录。 若要查看所有 PSTN 用法记录在部署中可用的列表，企业语音查看其属性，请参阅在部署中查看 [PSTN 用法Skype for Business](view-pstn-usage-records.md)。

### <a name="to-create-a-voice-policy"></a>创建语音策略

1. 打开Skype for Business Server控制面板"。

2. 在左侧导航栏中，单击" **语音路由"** ，然后单击" **语音策略"**。

3. 在" **语音策略"** 页上，单击" **新建** "，然后选择新策略的范围：

   - **站点** 策略适用于整个站点，分配给用户策略的任何用户或组除外。 如果选择"站点"作为策略作用域，请从"选择站点" **对话框中选择** 站点。 如果已针对某个站点创建了语音策略，则该网站不会显示在"选择站点 **"** 对话框中。

   - **用户策略** 可应用于指定的用户或组。

4. 如果语音策略作用域为"用户"，请在"名称"字段中输入策略 **的描述性** 名称。

    > [!NOTE]
    > 如果语音策略作用域为"站点"，则"新建语音策略"中的"名称"字段会使用站点名称预先填充，并且无法更改。

5.  (可选) 输入语音策略的其他描述性信息。

6. 选中或清除以下复选框，为此语音策略启用或禁用 **每个呼叫功能** ：

   - **语音邮件转** 义可防止在配置同时响铃、电话关闭、电池不足或范围外时将呼叫立即路由到用户的移动电话语音邮件系统。

     > [!NOTE]
     > 此功能只能通过命令行管理程序Skype for Business Server配置

   - 通过 **呼叫转接**，用户可以将呼叫转接到其他电话或客户端设备。 Skype for Business Server为呼叫转发提供了范围更广的配置选项。 例如，如果组织不允许将传入呼叫外部转接到 PSTN，则管理员可应用特定语音策略来部署此限制。 默认为启用。

   - 通过 **委派**，用户可以指定其他用户代表他们发送和接收呼叫。 在Skype for Business Server中，代理人可以配置同时响铃，从而允许呼叫其经理的传入呼叫拨打代理人的所有同时响铃目标。 这为代理提供了极大地灵活性以响应定向至管理员的呼叫。 默认为启用。

   - 通过 **呼叫转移**，用户可以将呼叫转移到其他用户。默认为启用。

   - **通过呼叫** 保留，用户可以将呼叫保留，然后从其他电话或客户端接听呼叫。 默认为禁用。

   - **同时响铃** 使传入呼叫可以在其他电话（如手机）或其他终结点设备上响铃。 Skype for Business Server为同时响铃提供了范围更广的配置选项。 默认为启用。

   - 通过 **团队呼叫**，指定团队中的用户可以为团队中的其他成员应答呼叫。默认为启用。

   - **PSTN 重新** 路由使分配了此策略的用户向其他企业用户拨打的呼叫可以在 WAN 变得塞或不可用时在 PSTN 上重新路由。 默认为启用。

   - 通过 **带宽策略覆盖**，管理员可以覆盖特定用户的呼叫允许控制策略决策。默认为禁用。

     > [!NOTE]
     > 只能覆盖向用户发出的传入呼叫的策略，而不能覆盖由用户发出的传出呼叫的策略。 建立会话后，将准确记录带宽消耗。 应谨慎使用此设置，且应保留用于相应的呼叫允许控制决策。

   - **通过恶意** 呼叫跟踪，用户可以使用客户端 UI 报告恶意呼叫 (如威胁) ，而客户端 UI 又在呼叫详细信息记录或 CDR (标记) 。 默认情况下处于禁用状态。

   - **忙碌选项** 启用或禁用指定语音策略的忙碌选项。 忙碌选项允许在呼叫的目标用户接听电话时将传入呼叫路由到语音邮件，或者拒绝传入呼叫时显示繁忙信号。 忙碌选项是 2016 年 7 月累积更新中引入的新语音策略。 选中此参数将启用忙碌选项，取消选中将禁用忙碌选项。 有关详细信息，请参阅 Plan [for Busy Options for Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/busy-options.md) [Install and configure Busy Options for Skype for Business Server](install-and-configure-busy-options.md)。

7. 要为此语音策略关联和配置 PSTN 用法记录，请执行以下任意操作：

   - 要从企业语音部署中提供的所有 PSTN 用法记录列表中选择一个或多个记录，请单击“选择”。突出显示要与此语音策略关联的记录，然后单击“确定”。

   - 要删除此语音策略中的某个 PSTN 用法记录，请突出显示相应的记录，然后单击“删除”。

   - 要定义新的 PSTN 用法记录并将其与此语音策略相关联，请执行以下操作：

     a. 单击"新建"。

     b. 在“名称”字段中，输入记录的唯一描述性名称。 例如，您可能需要为 Redmond 的全职员工创建名为Redmond 的 PSTN 用法记录，为临时员工创建另一个名为RedmondTemps 的 PSTN 用法记录。

     > [!NOTE]
     > PSTN 用法记录名称在企业语音部署中必须是唯一的。保存记录后，将无法编辑“名称”字段。

     c. 使用以下任意方法为此 PSTN 用法记录关联和配置路由：

   - 要从企业语音部署中提供的所有路由列表中选择一个或多个路由，请单击“选择”，突出显示要与此 PSTN 用法记录相关联的路由，然后单击“确定”。

   - 若要从 PSTN 用法记录中删除路由，请突出显示该路由，然后单击"删除 **"**。

   - 要定义新路由并将其与此 PSTN 用法记录相关联，请单击“新建”。 有关详细信息，请参阅 Create [or modify a voice route in Skype for Business](create-or-modify-a-voice-route.md)。

   - 要编辑已经与此 PSTN 用法记录相关联的路由，请突出显示相应的路由，然后单击“显示详细信息”。

     d. 单击“确定”。

   - 要编辑已经与此语音策略相关联的 PSTN 用法记录，请执行以下操作：

     a. 突出显示要编辑的 PSTN 用法记录，然后单击"显示 **详细信息"**。

     b. 使用以下任意方法为此 PSTN 用法记录关联和配置路由：

   - 要从企业语音部署中提供的所有路由列表中选择一个或多个路由，请单击“选择”，突出显示要与此 PSTN 用法记录相关联的路由，然后单击“确定”。

   - 若要从此 PSTN 用法记录中删除路由，请突出显示该路由，然后单击"删除 **"**。

   - 要定义新路由并将其与此 PSTN 用法记录相关联，请单击“新建”。 有关详细信息，请参阅 Create [or modify a voice route in Skype for Business](create-or-modify-a-voice-route.md)。

   - 若要编辑已与此 PSTN 用法记录关联的路由，请突出显示相应的路由并单击"显示 **详细信息"**。

     c. 单击“确定”。

8. 排列 PSTN 用法记录以获得最佳性能。 若要更改记录在列表中的位置，请突出显示记录名称，然后单击向上箭头或向下箭头。

    > [!IMPORTANT]
    > PSTN 用法记录在语音策略中的列出顺序十分重要。 Skype for Business Server从上到下遍历列表。 建议按使用频率来组织该列表，例如：RedmondLocal、RedmondLongDist、RedmondInternational 和 RedmondBackup。

9. 要为此语音策略中的呼叫转接和同时响铃关联和配置 PSTN 用法记录，请执行以下任一操作：

   - 若要对呼叫转接和同时响铃使用与此语音策略相同的 PSTN 用法记录，请从下拉菜单中选择“使用呼叫 PSTN 用法进行路由”。

   - 若要仅允许将呼叫转发和同时响铃Skype for Business内部呼叫用户，请从下拉菜单中选择"仅Skype for Business路由到内部呼叫用户"。 呼叫将不会转接到外部 PSTN 号码。

   - 若要为呼叫转发和同时响铃指定与用于此语音策略不同的 PSTN 用法记录，请从下拉菜单中选择"使用自定义 **PSTN** 用法路由"。 此选项显示一个控件，用于选择现有 PSTN 用法记录或专门为呼叫转发和同时响铃创建新的 PSTN 用法记录。

   - 要从呼叫转接和同时响铃的 PSTN 用法记录列表中选择一个或多个记录，请单击“选择”。突出显示要与此呼叫转接和同时响铃策略关联的记录，然后单击“确定”。

   - 要从此呼叫转接和同时响铃策略中删除某个 PSTN 用法记录，请突出显示相应的记录，然后单击“删除”。

   - 要定义新的 PSTN 用法记录并将其与此呼叫转接和同时响铃策略相关联，请执行以下操作：

     a. 单击"新建"。

     b. 在“名称”字段中，输入记录的唯一描述性名称。

     > [!NOTE]
     > PSTN 用法记录名称在企业语音部署中必须是唯一的。保存记录后，将无法编辑“名称”字段。

     c. 使用以下任意方法为此 PSTN 用法记录关联和配置路由：

   - 要从企业语音部署中提供的所有路由列表中选择一个或多个路由，请单击“选择”，突出显示要与此 PSTN 用法记录相关联的路由，然后单击“确定”。

   - 要删除 PSTN 用法记录中的某个路由，请突出显示相应的路由，然后单击“删除”。

   - 要定义新路由并将其与此 PSTN 用法记录相关联，请单击“新建”。 有关详细信息，请参阅 Create [or modify a voice route in Skype for Business](create-or-modify-a-voice-route.md)。

   - 要编辑已经与此 PSTN 用法记录相关联的路由，请突出显示相应的路由，然后单击“显示详细信息”。

     d. 单击“确定”。

   - 要编辑已经与此语音策略相关联的 PSTN 用法记录，请执行以下操作：

     a. 突出显示要编辑的 PSTN 用法记录，然后单击" **显示详细信息"**。

     b. 使用以下任意方法为此 PSTN 用法记录关联和配置路由：

   - 要从企业语音部署中提供的所有路由列表中选择一个或多个路由，请单击“选择”，突出显示要与此 PSTN 用法记录相关联的路由，然后单击“确定”。

   - 要删除此 PSTN 用法记录中的某个路由，请突出显示相应的路由，然后单击“删除”。

   - 要定义新路由并将其与此 PSTN 用法记录相关联，请单击“新建”。 有关详细信息，请参阅 Create [or modify a voice route in Skype for Business](create-or-modify-a-voice-route.md)。

   - 要编辑已经与此 PSTN 用法记录相关联的路由，请突出显示相应的路由，然后单击“显示详细信息”。

     c. 单击“确定”。

10. （可选）输入一个号码来测试语音策略，然后单击“执行”。测试结果会显示在“要测试的转换号码”下。

11. 单击“确定”。

12. 在“语音策略”页上，单击“提交”，然后单击“全部提交”。

    > [!NOTE]
    > 每次创建或修改语音策略时，都必须运行 **"全部提交** "命令以发布配置更改。 有关详细信息，请参阅操作文档中的 Publish [pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation。

13.  (可选) 语音邮件转义"检测到用户的移动电话语音邮件立即应答了呼叫，并且断开了对移动电话语音邮件的呼叫。 这允许呼叫继续在用户的其他终结点上响铃，从而让用户有机会应答呼叫。 若要详细了解如何配置语音邮件策略，[请参阅配置语音邮件](configure-voice-mail-escape.md)转义Skype for Business。

### <a name="to-modify-a-voice-policy"></a>修改语音策略

1. 打开Skype for Business Server控制面板"。

2. 在左侧导航栏中，单击“语音路由”，然后单击“语音策略”。

3. 在“语音策略”页上，双击某个语音策略名称。

    > [!NOTE]
    > 作用域和名称是在创建语音策略时设置的，且不能更改。

4. （可选）在“编辑语音策略”中，输入语音策略的其他描述性信息。

5. 选中或清除以下复选框以启用或禁用每种“呼叫功能”：

   - **语音邮件转** 义可防止在配置同时响铃、电话关闭、电池不足或范围外时将呼叫立即路由到用户的移动电话语音邮件系统。

     > [!NOTE]
     > 此功能只能通过命令行管理程序Skype for Business Server配置

   - 通过 **呼叫转接**，用户可以将呼叫转接到其他电话或客户端设备。 Skype for Business Server为呼叫转发提供了范围更广的配置选项。 例如，如果组织不允许将传入呼叫外部转接到 PSTN，则管理员可应用特定语音策略来部署此限制。 默认为启用。

   - 通过 **委派**，用户可以指定其他用户代表他们发送和接收呼叫。 在Skype for Business Server中，代理人可以配置同时响铃，从而允许呼叫其经理的传入呼叫拨打代理人的所有同时响铃目标。 这为代理提供了极大地灵活性以响应定向至管理员的呼叫。 默认为启用。

   - 通过 **呼叫转移**，用户可以将呼叫转移到其他用户。默认为启用。

   - 通过 **呼叫寄存**，用户可以寄存呼叫，将其置于保持状态，然后从其他电话或客户端接听呼叫。默认为禁用。

   - **同时响铃** 使传入呼叫可以在其他电话（如手机）或其他终结点设备上响铃。 Skype for Business Server为同时响铃提供了范围更广的配置选项。 默认为启用。

   - 通过 **团队呼叫**，指定团队中的用户可以为团队中的其他成员应答呼叫。默认为启用。

   - **PSTN 重新** 路由使分配了此策略的用户向其他企业用户拨打的呼叫可以在 WAN 变得塞或不可用时在 PSTN 上重新路由。 默认为启用。

   - **通过带宽策略** 覆盖，管理员可以覆盖特定用户的 CAC 策略决策。 默认为禁用。

     > [!NOTE]
     > 只能覆盖向用户发出的传入呼叫的策略，而不能覆盖由用户发出的传出呼叫的策略。建立会话后，将准确记录带宽消耗。应慎用此设置。

   - **通过恶意** 呼叫跟踪，用户可以报告恶意 (，如) UI 发送的威胁，进而标记 CDR 中的呼叫。 默认为禁用。

6. 要为此语音策略关联和配置 PSTN 用法记录，请执行以下任意操作：

   - 要从企业语音部署中提供的所有 PSTN 用法记录列表中选择一个或多个记录，请单击“选择”。突出显示要与此语音策略关联的记录，然后单击“确定”。

   - 要删除此语音策略中的某个 PSTN 用法记录，请突出显示相应的记录，然后单击“删除”。

   - 要定义新的 PSTN 用法记录并将其与此语音策略相关联，请执行以下操作：

     a. 单击"新建"。

     b. 在“名称”字段中，输入记录的唯一描述性名称。 例如，您可能需要为 Redmond 的全职员工创建名为Redmond 的 PSTN 用法记录，为临时员工创建另一个名为RedmondTemps 的 PSTN 用法记录。

     > [!NOTE]
     > PSTN 用法记录名称在企业语音部署中必须是唯一的。保存记录后，将无法编辑“名称”字段。

     c. 使用以下任意方法为此 PSTN 用法记录关联和配置路由：

   - 要从企业语音部署中提供的所有路由列表中选择一个或多个路由，请单击“选择”，突出显示要与此 PSTN 用法记录相关联的路由，然后单击“确定”。

   - 要删除 PSTN 用法记录中的某个路由，请突出显示相应的路由，然后单击“删除”。

   - 要定义新路由并将其与此 PSTN 用法记录相关联，请单击“新建”。 有关详细信息，请参阅 Create [or modify a voice route in Skype for Business](create-or-modify-a-voice-route.md)。

   - 要编辑已经与此 PSTN 用法记录相关联的路由，请突出显示相应的路由，然后单击“显示详细信息”。

     d. 单击“确定”。

   - 要编辑已经与此语音策略相关联的 PSTN 用法记录，请执行以下操作：

     a. 突出显示要编辑的 PSTN 用法记录，然后单击“显示详细信息”。

     b. 使用以下任意方法为此 PSTN 用法记录关联和配置路由：

   - 要从企业语音部署中提供的所有路由列表中选择一个或多个路由，请单击“选择”，突出显示要与此 PSTN 用法记录相关联的路由，然后单击“确定”。

   - 要删除此 PSTN 用法记录中的某个路由，请突出显示相应的路由，然后单击“删除”。

   - 要定义新路由并将其与此 PSTN 用法记录相关联，请单击“新建”。 有关详细信息，请参阅 Create [or modify a voice route in Skype for Business](create-or-modify-a-voice-route.md)。

   - 要编辑已经与此 PSTN 用法记录相关联的路由，请突出显示相应的路由，然后单击“显示详细信息”。

     c. 单击“确定”。

7. 排列 PSTN 用法记录以获得最佳性能。 若要更改记录在列表中的位置，请突出显示记录名称，然后单击向上箭头或向下箭头。

    > [!NOTE]
    > PSTN 用法记录在语音策略中的列出顺序十分重要。 Skype for Business Server从上到下遍历列表。 建议按使用频率来组织该列表，例如：RedmondLocal、RedmondLongDist、RedmondInternational 和 RedmondBackup。

8. 要为此语音策略中的呼叫转接和同时响铃关联和配置 PSTN 用法记录，请执行以下任一操作：

   - 若要对呼叫转接和同时响铃使用与此语音策略相同的 PSTN 用法记录，请从下拉菜单中选择“使用呼叫 PSTN 用法进行路由”。

   - 若要仅允许将呼叫转发和同时响铃Skype for Business内部呼叫用户，请从下拉菜单中选择Skype for Business路由到内部呼叫用户"。 呼叫将不会转接到外部 PSTN 号码。

   - 若要为呼叫转接和同时响铃指定与此语音策略所用的 PSTN 用法记录不同的 PSTN 用法记录，请从下拉菜单中选择“使用自定义 PSTN 用法进行路由”。此选项显示一个控件，此控件专用于为呼叫转接和同时响铃选择现有 PSTN 用法记录或创建新的 PSTN 用法记录。

   - 要从呼叫转接和同时响铃的 PSTN 用法记录列表中选择一个或多个记录，请单击“选择”。突出显示要与此呼叫转接和同时响铃策略关联的记录，然后单击“确定”。

   - 要从此呼叫转接和同时响铃策略中删除某个 PSTN 用法记录，请突出显示相应的记录，然后单击“删除”。

   - 要定义新的 PSTN 用法记录并将其与此呼叫转接和同时响铃策略相关联，请执行以下操作：

     a. 单击"新建"。

     b. 在“名称”字段中，输入记录的唯一描述性名称。

     > [!NOTE]
     > PSTN 用法记录名称在企业语音部署中必须是唯一的。保存记录后，将无法编辑“名称”字段。

     c. 使用以下任意方法为此 PSTN 用法记录关联和配置路由：

   - 要从企业语音部署中提供的所有路由列表中选择一个或多个路由，请单击“选择”，突出显示要与此 PSTN 用法记录相关联的路由，然后单击“确定”。

   - 要删除 PSTN 用法记录中的某个路由，请突出显示相应的路由，然后单击“删除”。

   - 要定义新路由并将其与此 PSTN 用法记录相关联，请单击“新建”。 有关详细信息，请参阅 Create [or modify a voice route in Skype for Business](create-or-modify-a-voice-route.md)。

   - 要编辑已经与此 PSTN 用法记录相关联的路由，请突出显示相应的路由，然后单击“显示详细信息”。有关详细信息，请参阅[Modify a Voice Route](/previous-versions/office/lync-server-2013/lync-server-2013-modify-a-voice-route)。

     d. 单击“确定”。

   - 要编辑已经与此语音策略相关联的 PSTN 用法记录，请执行以下操作：

     a. 突出显示要编辑的 PSTN 用法记录，然后单击“显示详细信息”。

     b. 使用以下任意方法为此 PSTN 用法记录关联和配置路由：

     - 要从企业语音部署中提供的所有路由列表中选择一个或多个路由，请单击“选择”，突出显示要与此 PSTN 用法记录相关联的路由，然后单击“确定”。

     - 要删除此 PSTN 用法记录中的某个路由，请突出显示相应的路由，然后单击“删除”。

     - 要定义新路由并将其与此 PSTN 用法记录相关联，请单击“新建”。 有关详细信息，请参阅 Create [or modify a voice route in Skype for Business](create-or-modify-a-voice-route.md)。

     - 要编辑已经与此 PSTN 用法记录相关联的路由，请突出显示相应的路由，然后单击“显示详细信息”。有关详细信息，请参阅[Modify a Voice Route](/previous-versions/office/lync-server-2013/lync-server-2013-modify-a-voice-route)。

     c. 单击“确定”。

9. （可选）输入一个号码来测试语音策略，然后单击“执行”。测试结果会显示在“要测试的转换号码”下。

10. 单击“确定”。

11. 在“语音策略”页上，单击“提交”，然后单击“全部提交”。

    > [!NOTE]
    > 只要创建或修改语音策略，就必须运行“全部提交”命令以发布配置更改。 有关详细信息，请参阅操作文档中的 Publish [pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation。

12.  (可选) 语音邮件转义"检测到用户的移动电话语音邮件立即应答了呼叫，并且断开了对移动电话语音邮件的呼叫。 这允许呼叫继续在用户的其他终结点上响铃，从而让用户有机会应答呼叫。 若要详细了解如何配置语音邮件策略，[请参阅配置语音邮件](configure-voice-mail-escape.md)转义Skype for Business。

## <a name="see-also"></a>另请参阅

[查看 PSTN 用法记录Skype for Business](view-pstn-usage-records.md)

[Create or modify a voice route in Skype for Business](create-or-modify-a-voice-route.md)

[在语音路由配置中发布待处理Skype for Business](voice-route-config-changes.md)

[配置语音邮件转义Skype for Business](configure-voice-mail-escape.md)