---
title: 设置 Microsoft 365 商务语音 资源帐户
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
ms.localizationpriority: medium
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- Teams_Business_Voice
search.appverid: MET150
description: 了解如何设置一个Microsoft 365 商务语音自动助理使用的资源帐户。
appliesto:
- Microsoft Teams
ms.openlocfilehash: afc45df5ecf6336d2ddea86581fde67e85a6ab24
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58630236"
---
# <a name="step-4-set-up-a-business-voice-resource-account"></a>步骤 4：设置 Business Voice 资源帐户

资源帐户不会分配给任何特定用户。 相反，使用免费虚拟用户许可证的资源帐户由虚拟机中的设备和服务Microsoft 365。 在Microsoft Teams，资源帐户分配有电话号码，然后与自动助理和呼叫队列相关联。

通过将资源帐户关联到自动助理和呼叫队列，可以添加一个或多个收费或免费电话号码。 例如，可以将一个资源帐户与收费电话号码关联到本地呼叫者的自动助理。 对于长距离呼叫，可以将另一个资源帐户与免费电话号码关联到同一个自动助理。

本文中的部分介绍了如何设置资源帐户，然后为其分配电话号码。 稍后，你将将资源帐户与自动助理关联。

以下视频演示如何在管理中心内完成Teams步骤。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4OFYG]

## <a name="obtain-virtual-user-licenses"></a>获取虚拟用户许可证

资源帐户需要许可证才能使用自动助理和呼叫队列。 可以使用免费的虚拟Microsoft 365 电话系统 *- 虚拟用户* 许可证。

> [!NOTE]
> 如果已注册 Business Voice 试用期，应只需执行以下步骤。 如果你购买了 Business Voice 许可证，则虚拟许可证应该已应用到你的帐户。 
>
> 若要了解你已有虚拟许可证，Microsoft 365具有全局管理员权限的帐户登录。 然后转到"你的>[计费"。](https://admin.microsoft.com/Adminportal/Home#/subscriptions) 如果有虚拟许可证，它们将显示为"Microsoft 365 电话系统 **- 虚拟用户"。**

1. 打开Microsoft 365 管理中心帐户，使用全局管理员用户登录 (该帐户通常是用于注册帐户的帐户Microsoft 365) 。
2. 在左侧导航窗格中，转到"<a href="https://admin.microsoft.com/Adminportal/Home#/catalog" target="_blank">**计费**  >  **购买服务**</a>  >  **加载项**  >  **""查看所有附加内容产品"。**
3. 滚动到末尾，找到 **"Microsoft 365 电话系统 – 虚拟用户**"许可证。 选择"**详细信息"，** 然后选择"**购买"。**
4. 在许可证购买页上，选择想要的虚拟用户许可证数。 需要为计划设置的每个自动助理和呼叫队列提供一个虚拟许可证。 我们建议选择至少五个许可证，以便将来可以轻松设置更多自动助理和呼叫队列，而无需立即购买更多许可证。
5. 取消 **选中"自动分配给没有许可证的所有用户"。**
6. 选择 **"现在签出"。**
7. 确认订单，选择"下一 **步**"，然后选择"**下订单"。**

> [!NOTE]
> 请记住，即使许可证的成本  **为零** ，仍必须购买许可证。

## <a name="create-a-resource-account"></a>创建资源帐户

收到虚拟用户 *-Microsoft 365 电话系统* 许可证后，可以创建资源帐户。

![添加资源帐户用户界面的屏幕截图](../media/resource-account-add.png)

1. 打开 Microsoft Teams 管理中心，使用全局管理员用户登录 (该帐户通常是用于注册 Microsoft 365) 。
2. 在左侧导航窗格中，转到"<a href="https://admin.teams.microsoft.com/company-wide-settings/resource-accounts" target="_blank">**组织范围的设置""**  >  **资源帐户"。**</a>
3. 选择“**添加**”。
4. 在"**添加资源帐户"** 窗格中，填写 **"显示名称"，** 然后填写"**用户名"。** 选择描述显示名称例如"主行自动助理"来描述资源帐户的用途。
5. 在 **"资源帐户类型"中**，选择 **"自动助理"。**
6. 选择“**保存**”。

![资源帐户列表的屏幕截图](../media/resource-accounts-auto-attendant-only-page.png)

## <a name="assign-a-license"></a>分配许可证

创建资源帐户后，需要分配一个Microsoft 365 电话系统 - 虚拟 *用户**许可证或* 电话系统许可证。

!["许可证分配"用户界面的屏幕截图Microsoft 365 管理中心](../media/resource-account-assign-virtual-user-license.png)

1. 打开Microsoft 365 管理中心帐户，使用全局管理员用户登录 (该帐户通常是用于注册帐户的帐户Microsoft 365) 。
1. 在左侧导航窗格中，转到"用户 <a href="https://admin.microsoft.com/Adminportal/Home#/users" target="_blank">  >  **""活动用户"。**</a>
1. 选择资源帐户。
1. 在"**许可证和应用"选项卡上的**"许可证 **"下**，选择 **"Microsoft 365 电话系统 - 虚拟用户"。**
1. 选择 **"保存更改"，** 然后选择"**关闭"。**

## <a name="assign-a-service-number"></a>分配服务编号

![分配服务编号用户界面的屏幕截图](../media/resource-account-assign-phone-number.png)

1. 打开 Microsoft Teams 管理中心，使用全局管理员用户登录 (该帐户通常是用于注册 Microsoft 365) 。
1. 在左侧导航窗格中，转到"<a href="https://admin.teams.microsoft.com/company-wide-settings/resource-accounts" target="_blank">**组织范围的设置""**  >  **资源帐户"。**</a>
1. 选择刚刚创建的资源帐户，然后单击"**分配/取消分配"。**
1. 在 **"电话类型**"下拉列表中，选择"**联机"。**
1. 在 **"分配的电话号码"** 框中，搜索想要使用的号码，然后单击"添加 **"。** 请务必包含国家/地区代码 (例如 **，+1** 250 555 0012) 
1. 单击“**保存**”。

> [!div class="nextstepaction"]
> [下一步：向用户分配电话号码](set-up-assign-numbers.md)
