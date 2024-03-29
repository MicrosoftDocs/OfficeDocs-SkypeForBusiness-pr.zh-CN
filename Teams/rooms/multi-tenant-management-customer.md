---
title: 客户的合作伙伴管理
author: altsou
ms.author: altsou
manager: serdars
ms.reviewer: altsou
ms.date: 06/09/2022
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_MTRP
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: 客户的合作伙伴管理。
f1keywords: ''
ms.openlocfilehash: 56aaf61092dd1bbd61c2734be6da1732f4882e49
ms.sourcegitcommit: baf29d244b428712052553f9e4484e72e727247e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/17/2022
ms.locfileid: "69046861"
---
# <a name="partner-management-for-customers"></a>客户的合作伙伴管理

Teams 会议室专业版管理服务中的合作伙伴管理使客户能够无缝地将访问权限和职责委派给一个或多个合作伙伴组织。 合作伙伴只能管理他们分配要管理的会议室。

## <a name="on-boarding-partners"></a>加入合作伙伴
   通过专业管理门户邀请合作伙伴在组织与合作伙伴组织的租户之间建立关系。
   
> [!NOTE]
> 合作伙伴需要满足 [合作伙伴的多租户管理](multi-tenant-management-partner.md)中的先决条件。

### <a name="invitation-to-partner"></a>合作伙伴邀请

   在此方法中，应知道合作伙伴 (的域名，例如 Contoso.com) 。

**启动邀请** 

1. 以托管服务管理员身份登录到 Teams 会议室专业版 管理门户。
1. 转到 **“合作伙伴>设置”** **，然后选择**“ **添加合作伙伴”。**
1. 在第一行中输入域名。
1. 通过输入 1-30 的整数来配置邀请过期之前的天数。
1. 配置需要更改控制审批的事件。 默认情况下，所有控件都设置为 **“自动审批”。**

   > [!NOTE]
   > *目前只有自动批准可用。*
   > 
   >  1.  *手动审批：* 合作伙伴执行操作时，将生成审批请求，供客户查看和批准。 在请求获得批准之前，不会实施该操作。
   >  
   >  1. *自动审批：* 当合作伙伴执行操作时，不会生成任何审批请求，并且会立即实施该操作。
     
1. 选择“ **下一步”。**
1. 分配合作伙伴将管理的房间，然后选择“ **下一步”。**
1. 若要继续，请查看条款并选择“ **我同意”。**
1. 查看邀请的详细信息。
1. 选择 **“添加合作伙伴** ”以发送邀请。

邀请将发送给合作伙伴实例中的租户经理进行评审。 接受邀请的第一个合作伙伴用户将在合作伙伴和租户之间建立链接，并分配主管理员。 与建立链接的用户没有特殊关联，这样在重新分配用户时可以灵活地进行关联。 主管理员角色中必须始终至少有一个用户。

若要以主管理员角色管理用户，请参阅 [合作伙伴的多租户管理](multi-tenant-management-partner.md)。

## <a name="off-boarding-partners"></a>退出合作伙伴

**删除合作伙伴**

1. 以托管服务管理员身份登录到 Pro Management-Multi-tenant Management (MTM) 门户。
1. 导航到 **“>合作伙伴的设置”。**
1. 选择要删除的合作伙伴。
1. 在“客户详细信息”窗格中，选择“ **删除合作伙伴”。**
1. 选择“**删除**”。 
1. 在终止与客户租户之间的关联的确认提示下，选择“ **删除**”。

## <a name="managing-partner-roles"></a>管理合作伙伴角色

合作伙伴角色允许合作伙伴更精细地将职责委派给其他人员。 这些角色的概念与 [基于角色的访问控制](rooms-pro-rbac.md)中所述相同。 请务必注意，合作伙伴角色不同于自定义角色。 

**主管理员** 角色是添加的每个合作伙伴的唯一内置角色。 此角色拥有你为 TRM 服务分配的合作伙伴的会议室的几乎所有权限 (请参阅 [表 1](#table-1)) 。 例如，如果在全球拥有会议室并分配合作伙伴来管理“所有美国会议室”，则主管理员只能管理和委派这些会议室的权限。 在这种情况下，此合作伙伴的主要管理员无法查看美国以外的任何会议室。 

### <a name="adding-primary-admins-to-partner"></a>将主要管理员添加到合作伙伴

如果已向合作伙伴发送邀请并希望委派更多聊天室，则可以将聊天室添加到合作伙伴管理员角色。

**向现有合作伙伴添加新会议室**

1. 以托管服务管理员身份登录到 Pro Management-MTM 门户。
1. 转到 **“设置”>角色。**
1. 选择  **“合作伙伴角色”。** 
1. 为相应的合作伙伴名称选择 **“主管理员** ”角色。
1. 在角色窗格中，选择“ **分配**”。
1. 选择“ **分配的管理员”** 分配。
1. 在“分配的管理员分配”窗格中，选择“ **范围**”。
1. 选择 **“编辑**”。
1. 搜索要添加的会议室，然后选择所需的会议室。
1. 若要确认更改，请选择“ **保存**”。

### <a name="table-1"></a>表 1

|功能|许可|**托管服务管理员**|**网站主管**|**网站技术**|**合作伙伴管理员**|
| :- | :- | :- | :- | :- | :- |
|房间|查看| &#10004;|&#10004;|&#10004;|&#10004;|
||修改|&#10004;|&#10004;|&#10004;|&#10004;|
||重置密钥|&#10004;||||
||下载密钥|&#10004;|&#10004;|&#10004;||
||取消注册|&#10004;|&#10004;|&#10004;||
||创建 |&#10004;|&#10004;|||
|组管理|查看|&#10004;|&#10004;||&#10004;|
||修改|&#10004;|&#10004;|||
||创建 |&#10004;|&#10004;|||
|更新环管理|查看|&#10004;|&#10004;||&#10004;|
||修改|&#10004;|&#10004;||&#10004;|
|报告|查看|&#10004;|&#10004;||&#10004;|
||创建客户事件|&#10004;|&#10004;|&#10004;|&#10004;|
|票证管理|查看|&#10004;|&#10004;|&#10004;|&#10004;|
||更新|&#10004;|&#10004;|&#10004;|&#10004;|
|Pro 管理设置|查看|&#10004;||||
||修改|&#10004;||||
|角色管理|查看 |&#10004;|||&#10004;|
||修改|&#10004;|||&#10004;|

## <a name="security"></a>安全性

作为最终客户，你可以保留对数据访问权限的控制，并且可以随时完全删除合作伙伴。 

使用委派访问功能，合作伙伴不会在 Pro 管理门户之外获得任何其他特权。 但是，Pro Management 服务中派生自其他 Microsoft 产品的任何数据都被视为服务中的数据。 例如，虽然通话质量报告派生自 Teams 通话质量数据，但 Pro 管理门户中的任何数据都在权限范围内。 

不会向 AAD 或 Teams 管理员中心或任何其他 Microsoft 产品授予任何权限。 此外，合作伙伴无权查看或修改未在邀请范围中定义的会议室。 

数据驻留在客户的租户中，不会复制到合作伙伴的租户。 

MTM 门户使用 Azure AD 身份验证来验证合作伙伴的登录凭据。 请注意，目前，客户的身份验证策略不适用于合作伙伴。 例如，如果客户具有多重身份验证策略，则不会转换为合作伙伴。 

若要拉取合作伙伴活动的日志，请参阅 [审核](multi-tenant-auditing.md)。 

> [!NOTE]
> AAD 审核和 O365 审核不会从 Pro Management 门户捕获日志。 
