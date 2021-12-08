---
title: 客户的合作伙伴管理
author: donnah007
ms.author: v-donnahill
manager: serdars
ms.reviewer: dstrome
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: 客户的合作伙伴管理。
f1keywords: ''
ms.openlocfilehash: 84d15f43ff49565dbba915470ea618a69ff74ee8
ms.sourcegitcommit: c8951fe3504c1776d7aec14b79605aaf5d317e7f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/08/2021
ms.locfileid: "61331210"
---
# <a name="partner-management-for-customers"></a>客户的合作伙伴管理


使用 TRM Teams 会议室 托管 (服务) 合作伙伴管理，客户能够无缝地将访问权限和责任委托给一个或多个合作伙伴组织。 合作伙伴只能管理分配给他们管理的会议室。 

## <a name="on-boarding-partners"></a>登记合作伙伴
   通过 TRM 门户邀请合作伙伴在组织与合作伙伴组织的租户之间建立关系。 

### <a name="invitation-to-partner"></a>合作伙伴邀请

   在此方法中，合作伙伴应提供用户 *（* 将成为分配给 (的主要) UPN）。 

**启动邀请** 

1. 以 MMR Teams 会议室登录到托管门户。
1. 转到 **"设置 >"，** 然后选择"**添加合作伙伴"。**
1. 在首行中输入主要管理员的姓名和 UPN。
1. 选择 **"添加联系人** "进行确认。
1. 执行下列操作之一：
   - 若要添加其他用户，请重复步骤 4。
   - 若要删除用户，请选择用户右边的 bin 图标。

    > [!NOTE]
    > 由于邀请已绑定到 UPN，因此不能使用组或通讯组列表。

1. 选择"下 **一步"。**
1. 配置需要更改控制审批的事件。 默认情况下，所有控件都设置为" **自动审批"。**

   > [!NOTE]
   > *目前仅自动批准可用。*
   > 
   >  1.  *手动审批：* 合作伙伴执行该操作时，将生成一个审批请求，供客户审阅和批准。 在请求获得批准之前，不会执行该操作。
   >  
   >  1. *自动审批：* 合作伙伴执行该操作时，不会生成审批请求，并且会立即执行该操作。
     
1. 选择"下 **一步"。**
1. 分配合作伙伴将管理的会议室，然后选择"下一 **步"。**
1. 若要继续，请查看条款并选择" **我同意"。**
1. 查看邀请的详细信息。
1. 选择 **"添加合作伙伴** "以发送邀请。

邀请对于每个用户都是唯一的，并且是独立的。 接受邀请的第一个合作伙伴用户将建立合作伙伴与租户之间的链接。 与建立此链接的用户没有特殊关联，这样，在重新分配用户时可以灵活操作。 要接受的后续用户将自动分配到"主要管理员"角色。 主管理员角色中必须始终至少有一个用户。

若要管理主要管理员角色中的用户，请参阅 [合作伙伴的多租户管理](multi-tenant-management-partner.md)。


## <a name="off-boarding-partners"></a>下台合作伙伴

**删除合作伙伴**

1. 以 MMR 管理员角色登录到 TRM-MTM 门户。
1. 导航到"设置 >**合作伙伴"。**
1. 选择要删除的合作伙伴。
1. 在客户详细信息窗格中，选择" **删除合作伙伴"。**
1. 选择“**删除**”。 
1. 在确认提示终止你与客户租户之间的关联时，选择"删除 **"。**

## <a name="managing-partner-roles"></a>管理合作伙伴角色

合作伙伴角色允许合作伙伴更细致地将责任委托给其他人员。 这些角色的概念与基于角色的访问控制 [中所述相同](microsoft-teams-rooms-premium-rbac.md)。 必须注意，合作伙伴角色不同于自定义角色。 

" **主要管理员** "角色是添加的每个合作伙伴的唯一内置角色。 此角色几乎拥有分配给 TRM 服务合作伙伴的聊天室的所有权限， (表 [1](#table-1)) 。 例如，如果你在全球拥有聊天室，并分配合作伙伴来管理"所有美国"聊天室，则主要管理员只能管理和委派这些聊天室的权限。 在这种情况下，此合作伙伴的主要管理员无法查看美国以外的任何聊天室。 

### <a name="adding-primary-admins-to-partner"></a>将主要管理员添加到合作伙伴

如果已向合作伙伴发送邀请，并且希望向该管理员添加更多用户，可以将其添加到合作伙伴管理员角色。 这会有效地向添加的用户发送邀请。

**将新用户添加到现有合作伙伴**

1. 以 MMR 管理员角色登录到 TRM-MTM 门户。
1. 转到 **"设置 >角色"。**
1. 选择  **"合作伙伴角色"。** 
1. 为相应的 **合作伙伴名称** 选择"主要管理员"角色。
1. 在角色窗格中，选择"分配 **"。**
1. 选择" **受邀管理员"** 分配。 
1. 在"受邀管理员"工作窗格，选择"**成员"。**
1. 选择"**编辑"。**
1. 输入新用户的 UPN，然后选择" **添加联系人"。**
1. 若要确认更改，请选择"保存 **"。**

<!--To remove users for an existing partner~~

1. ~~Login to the TRM-MTM portal as a MMR administrator~~
1. ~~Navigate to **Settings > Roles**~~
1. ~~Select the **Partner roles** tab~~
1. ~~Select the **Primary admin** role for the corresponding Partner name~~
1. ~~In the role pane, select the **Assignments** tab~~
1. ~~Select the **Invited admins** assignment~~ 
1. ~~In the Invited admins assignment pane, select the **Members** tab~~
1. ~~Select the **Edit** icon~~
1. ~~Enter the UPN of the new user and select **Add contact**~~
1. ~~Click **Save** to confirm the changes-->




### <a name="table-1"></a>表 1

|功能|权限|**MMR 管理员**|**网站潜在顾客**|**网站技术**|**合作伙伴管理员**|
| :- | :- | :- | :- | :- | :- |
|会议室|查看|||||
||修改|||||
||重置密钥|||||
||下载密钥|||||
||取消注册|||||
|组管理|创建 |||||
||查看|||||
||修改|||||
|更新环管理|创建 |||||
||查看|||||
||修改|||||
|报表|查看|||||
|票证管理|创建客户事件|||||
||查看|||||
||更新|||||
|MMR 设置|查看|||||
||修改|||||
|角色管理|查看 |||||
||修改|||||





## <a name="security"></a>安全性

作为最终客户，您可以保留对数据访问权限的控制，并随时完全删除合作伙伴。 

使用委派访问功能，合作伙伴不会在 TRM 服务门户之外获得任何其他权限。 但是，TRM 服务中派生自其他 Microsoft 产品的任何数据都被视为 TRM 服务中的数据。 例如，虽然呼叫质量报告派生自 Teams质量数据，但 TRM 门户中任何数据都位于权限范围内。 

不授予用户或AAD管理Teams任何其他 Microsoft 产品的权限。 此外，合作伙伴没有任何权限查看或修改邀请范围中未定义的聊天室。 

数据驻留在客户的租户中，不会复制到合作伙伴的租户。 

MTM 门户Azure AD身份验证来验证合作伙伴的登录凭据。 请注意，目前客户的身份验证策略不适用于合作伙伴。 例如，如果客户具有多重身份验证策略，该策略不会转换到合作伙伴。 

若要拉取合作伙伴活动的日志，请参阅 [审核](multi-tenant-auditing.md)。 

> [!NOTE]
> AAD审核和 O365 审核不会从 TRM 门户捕获日志。 
