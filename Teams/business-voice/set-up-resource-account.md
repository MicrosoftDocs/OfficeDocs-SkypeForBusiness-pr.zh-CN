---
title: 设置Microsoft 365 商务语音资源帐户
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- Teams_Business_Voice
search.appverid: MET150
description: 了解如何设置一个Microsoft 365 商务语音自动助理使用的资源帐户。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 76e91a650e9e72c21a39d292e32fe5ff8ecbf80b
ms.sourcegitcommit: 49cdcf344c63c805bcb6365804c6f5d1393e926a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2021
ms.locfileid: "52130326"
---
# <a name="step-4-set-up-a-business-voice-resource-account"></a>步骤 4：设置 Business Voice 资源帐户

在Microsoft Teams，每个自动助理或呼叫队列都需要一个资源帐户。 还可以为资源帐户分配服务电话号码。 这是将电话号码分配给自动助理和呼叫队列，允许来自外部呼叫Teams呼叫者进入自动助理或呼叫队列。

## <a name="obtain-virtual-user-licenses"></a>获取虚拟用户许可证

资源帐户需要许可证才能使用自动助理和呼叫队列。 可以使用免费的虚拟Microsoft 365 电话系统 *- 虚拟用户* 许可证。

1. 登录到 Microsoft 365 管理中心。
2. 转到 **计费**  >  **购买服务**  >  **附加内容**  >  **查看所有附加内容产品**
3. 滚动到末尾，找到 **"Microsoft 365 电话系统 – 虚拟用户"** 许可证。 选择"**详细信息"，** 然后选择"**购买"。**
4. 在许可证购买页上，选择想要的虚拟用户许可证数。 需要为计划设置的每个自动助理和呼叫队列提供一个虚拟许可证。 我们建议选择至少五个许可证，以便将来可以轻松设置更多自动助理和呼叫队列，而无需立即购买更多许可证。
5. 取消 **选中"自动分配给没有许可证的所有用户"。**
6. 选择 **"现在签出"。**
7. 确认订单，选择"下一 **步**"，然后选择"**下订单"。**

> [!NOTE]
> 请记住，即使许可证的成本  **为零** ，仍必须购买许可证。

## <a name="create-a-resource-account"></a>创建资源帐户

收到"虚拟 *用户Microsoft 365 电话系统后*，可以创建资源帐户。

![添加资源帐户用户界面的屏幕截图](../media/resource-account-add.png)

1. 在Teams管理中心，展开 **"组织范围的设置**"，然后单击"**资源帐户"。**
2. 选择“**添加**”。
3. 在"**添加资源帐户"** 窗格中，填写 **"显示名称"，** 然后填写"**用户名"。** 选择描述性显示名称例如"主行自动助理"来描述资源帐户的用途。
4. 在 **"资源帐户类型"中**，选择 **"自动助理"。**
5. 选择“**保存**”。

![资源帐户列表的屏幕截图](../media/resource-accounts-page.png)

## <a name="assign-a-license"></a>分配许可证

创建资源帐户后，需要分配一个 Microsoft 365 电话系统 *-* 虚拟用户 *许可证或电话系统* 许可证。

![在管理中心内分配许可证Microsoft 365屏幕截图](../media/resource-account-assign-virtual-user-license.png)

1. 在Microsoft 365中心，转到"用户  >  **""活动用户"。**
2. 选择资源帐户。
1. 在"**许可证和应用"选项卡上的**"许可证 **"下**，选择 **"Microsoft 365 电话系统 - 虚拟用户"。**
1. 选择 **"保存更改"，** 然后选择"**关闭"。**

## <a name="assign-a-service-number"></a>分配服务编号

![分配服务编号用户界面的屏幕截图](../media/resource-account-assign-phone-number.png)

1. 在Teams管理中心，转到 **"组织范围的** 设置"，然后转到"**资源帐户"。** 
1. 选择刚刚创建的资源帐户，然后单击"**分配/取消分配"。**
1. 在 **"电话类型**"下拉列表中，选择"联机 **"。**
1. 在 **"分配的电话号码"** 框中，搜索想要使用的号码，然后单击"添加 **"。** 请务必包括国家/地区代码 (例如 **，+1** 250 555 0012) 
1. 单击“**保存**”。
    > [!NOTE]
    > 无需在"分配对象"下选择自动助理，因为已选中要添加号码的自动助理。

> [!div class="nextstepaction"]
> [下一步：向用户分配电话号码](set-up-assign-numbers.md)
