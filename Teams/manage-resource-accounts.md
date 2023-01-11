---
title: 在 Teams 中管理资源帐户
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.reviewer: jastark, wasseemh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
- highpri
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.orgwidesettings.resourceaccounts.overview
- seo-marvel-apr2020
description: 本文介绍如何在 Microsoft Teams 中创建、编辑和管理资源帐户。
ms.openlocfilehash: 2bc0642f20341b9818b1c407fa0294127ee44d6a
ms.sourcegitcommit: ae687f530d5505b96df7cb7ef4da3a36bd9afd29
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/10/2023
ms.locfileid: "69763573"
---
# <a name="manage-resource-accounts-in-microsoft-teams"></a>在 Microsoft Teams 中管理资源帐户

[!INCLUDE [set-up-resource-account-steps](./includes/set-up-resource-account-steps.md)]

## <a name="next-steps"></a>后续步骤

完成资源帐户设置并根据需要分配电话号码后，即可将资源帐户与自动助理或呼叫队列配合使用。

有关详细信息，请参阅以下参考：

- [云自动助理](create-a-phone-system-auto-attendant.md)
- [云呼叫队列](create-a-phone-system-call-queue.md)

可以使用“**编辑**”选项编辑资源帐户 **的“显示名称****”和资源帐户** 类型。 完成后，选择“ **保存** ”。

## <a name="change-an-existing-resource-account-to-use-a-microsoft-teams-phone-resource-account-license"></a>更改现有资源帐户以使用Microsoft Teams 电话资源帐户许可证

若要将现有资源帐户上的许可证从 **Teams 电话标准版** 许可证切换到 **Microsoft Teams 电话资源帐户** 许可证，需要获取 **Microsoft Teams 电话资源帐户** 许可证，然后按照 中的步骤操作Microsoft 365 管理中心 [将用户移动到其他订阅](/microsoft-365/admin/manage/assign-licenses-to-users#move-users-to-a-different-subscription)。

> [!WARNING]
> 始终删除 **Teams 电话标准版** 许可证，并在同一许可证活动中分配 **Microsoft Teams 电话资源帐户** 许可证。 如果删除旧许可证，保存帐户更改，添加新许可证，然后再次保存帐户设置，资源帐户可能不再按预期运行。 如果发生这种情况，我们建议为 **Microsoft Teams 电话资源帐户许可证创建新的资源帐户**，并删除损坏的资源帐户。

## <a name="skype-for-business-server-2019"></a>Skype For Business Server 2019

对于驻留在 Skype For Business Server 2019 上且可与云呼叫队列和云自动助理配合使用的资源帐户，请参阅 [计划云呼叫队列](/SkypeforBusiness/hybrid/plan-call-queue) 或 [计划云自动助理](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)。 在本地 (Skype for Business Server 2019 服务器上使用 [New-CsHybridApplicationEndpoint](/powershell/module/skype/new-cshybridapplicationendpoint) cmdlet 配置驻留在直接路由) 上的混合实现。

创建应用程序实例时需要使用的应用程序 ID 包括：

- **自动助理：** ce933385-9390-45d1-9512-c8d228074e07
- **呼叫队列：** 11cd3e2e-fccb-42ad-ad00-878b93575e07

> [!NOTE]
> 如果希望 Skype For Business Server 2019 用户可搜索呼叫队列或自动助理，则应在 Skype For Business Server 2019 上创建资源帐户，因为联机资源帐户不会同步到 Active Directory。 当 sipfederationtls 的 DNS SRV 记录解析为 Skype for Business Server 2019 时，**必须使用** SfB Management shell 在 Skype For Business Server 2019 上创建资源帐户，并将其同步到 Azure AD。

对于具有 Skype for Business Server 的混合实现：

- [计划云自动助理](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)。
- [规划云呼叫队列](/SkypeforBusiness/hybrid/plan-call-queue)。
- [配置本地资源帐户](/SkypeForBusiness/hybrid/configure-onprem-ra)。

## <a name="delete-a-resource-account"></a>删除资源帐户

删除之前，请确保将电话号码与资源帐户取消关联，以避免电话号码停滞在挂起模式。

执行此操作后，可以在“**用户**”选项卡下的Microsoft 365 管理中心中删除资源帐户。

若要取消关联资源帐户的直接路由电话号码，请使用以下 cmdlet：

```powershell
Remove-CsPhoneNumberAssignment -Identity <Resource Account Object ID> -PhoneNumber <assigned phone number> -PhoneNumberType DirectRouting
```

## <a name="hide-resource-accounts-from-teams-users"></a>隐藏 Teams 用户的资源帐户

你可能希望对 Teams 用户隐藏某些资源帐户。 例如，你可能希望阻止 Teams 用户直接调用呼叫队列并绕过配置操作时间的自动助理。

[信息屏障](information-barriers-in-teams.md) 用于隐藏资源帐户。  在继续执行以下步骤之前，请查看信息屏障文档以了解可能的影响。

### <a name="required-subscriptions-and-permissions"></a>所需的订阅和权限 

若要访问和使用信息屏障，你的组织必须具有以下订阅之一或添加： 

-   Microsoft 365 E5/A5 订阅 (付费版或试用版) 。
-   Office 365 E5/A5/A3/A1 订阅 (付费版或试用版) 。
-   Office 365 高级合规版加载项。
-   Microsoft 365 E3/A3/A1 订阅 + Microsoft 365 E5/A5 合规性加载项。
- Microsoft 365 E3/A3/A1 订阅 + Microsoft 365 E5/A5 Insider Risk Management 加载项。

> [!NOTE]
> 如果已配置[Exchange Online](/exchange/address-books/address-book-policies/address-book-policies)通讯簿策略，则必须在继续执行以下步骤之前将其删除。   
> 
> 以下所有步骤均由租户全局管理员执行。 
>   
> 这些说明假定没有配置其他信息屏障。

#### <a name="teams-admin-center"></a>Teams 管理中心

1. 登录到 [Teams 管理中心](https://go.microsoft.com/fwlink/p/?linkid=2066851)。
2. 在左侧菜单中，展开 **“Teams**”。
3. 选择 **“Teams 设置**”。 
4. 向下滚动到 **“按名称搜索**”。
5. 打开开关并保存更改。

有关此选项的详细信息，请参阅 [限制用户在 Teams 中搜索目录时可以看到的用户](teams-scoped-directory-search.md)。

#### <a name="compliance---auditing"></a>合规性 - 审核

1. 登录到[Microsoft Purview 合规门户](https://compliance.microsoft.com/)。
2. 在左侧导航窗格中，选择“ **审核**”。
3. 如果关闭审核，将显示以下横幅： 
 
     :::image type="content" source="/microsoft-365/media/AuditingBanner.png" alt-text="显示审核横幅（如果未启用审核）的屏幕截图":::
  
4. 选择 **“开始录制用户和管理员”活动**。 

有关审核的详细信息，请参阅 [在 Microsoft 365 中设置审核 (标准) ](/microsoft-365/compliance/audit-standard-setup)。

#### <a name="segmenting-data"></a>对数据进行分段

不应直接调用的资源帐户需要分段且易于识别。  这可以通过使他们成为特定组的成员，或通过其用户配置文件中的某些唯一信息来完成，例如： 

-   公司
-   用户主体名称
-   位置
-   部门
-   使用位置
-   邮件昵称 (别名) 
-   Office)  (实体交付办公室名称
-   邮政编码
-   代理地址 (Email 地址) 
-   街道地址
-   目标地址 (ExternalEmailAddress) 
-   邮件 (WindowsEmailAddress) 
-   说明

在下面的示例步骤中， `Department` 将使用 字段。 

有关对用户进行分段的详细信息，请参阅  [标识段](/microsoft-365/compliance/information-barriers-policies)。

#### <a name="microsoft-admin-center"></a>Microsoft 管理中心

1. 登录到 [Microsoft 365 管理 中心](https://go.microsoft.com/fwlink/p/?linkid=2024339)。
2. 在左侧导航窗格中，选择“ **活动用户**”。
3. 选择要阻止直接调用的第一个资源帐户。
4. 在右窗格中 **选择“管理联系人信息** ”。
5. 将字段的内容 `Department` 替换为不用作部门名称的唯一字词或首字母缩略词。 例如， `DNC`。
6. 保存更改。
7. 对需要阻止接收直接调用的每个资源帐户重复此操作。

#### <a name="compliance---information-barriers"></a>合规性 - 信息屏障

1. 登录到[Microsoft Purview 合规门户](https://compliance.microsoft.com/)。
2. 在左侧导航窗格中，选择“**信息屏障段** > ”。
3. 选择“ **新建段**”。
4. 输入段的名称，然后选择“ **下一步**”。 例如， `Uncallable Resource Accounts`。
5. 选择“ **+ 添加**”，然后选择“ **部门**”。
6. 输入在上面的 Microsoft 管理中心步骤 5 中使用的唯一字词或首字母缩略词。 例如， `DNC`。
7. 选择“ **下一步**”，然后选择“ **提交**”。
8. 选择“ **新建段**”。
9. 输入段的名称，然后选择“ **下一步**”。 例如， `Callable Users`。
10. 选择“ **+ 添加**”，然后选择“ **部门**”。
11. 选择“ **等于** ”下拉列表，然后选择“ **不等于**”。
12. 输入在上面的 Microsoft 管理中心步骤 5 中使用的唯一字词或首字母缩略词。 例如， `DNC`。
13. 选择“ **下一步**”，然后选择“ **提交**”。 
14. 在左侧导航窗格中，选择“ **信息屏障** > **策略**”。
15. 选择“ **创建策略**”。
16. 输入策略的名称，然后选择“ **下一步**”。 例如， `Uncallable Resource Accounts`。
17. 选择“ **+ 选择段**”，添加在上述步骤 9 中创建的段，然后选择“ **下一步**”。 例如， `Callable Users`。
18. 从 **“通信和协作**”下拉列表中选择“**阻止**”。
19. 选择“ **+ 选择段**”，添加在上述步骤 4 中创建的段，然后选择“ **下一步**”。 例如， `Uncallable Resource Accounts`。
20. 将策略设置为 **“开”**，选择“ **下一步**”，然后选择“ **提交**”。
21. 选择“ **创建策略**”。
22. 输入策略的名称，然后选择“ **下一步**”。 例如， `Callable Users`。
23. 选择“ **+ 选择段**”，添加在步骤 4 中创建的段，然后选择“ **下一步**”。
24. 从 **“通信和协作**”下拉列表中选择“**阻止**”。 
25. 选择“ **+ 选择段**”，添加在上述步骤 9 中创建的段，然后选择“ **下一步**”。
26. 将策略设置为 **“开”**，选择“ **下一步**”，然后选择“ **提交**”。
27. 在左侧导航窗格中，选择“ **信息屏障** > **策略应用程序**”。
28. 选择 **“应用所有策略**”。

> [!NOTE]
> 应用策略可能需要 30 分钟或更长的时间。  
> 
> 状态显示“已完成”后，转到 Teams 客户端并尝试搜索已阻止的资源帐户。 可能需要清除 Teams 缓存。  
> 
> 如果 Teams 用户已将资源帐户保存为联系人，则他们将无法再调用它。
