---
title: 创建 Microsoft 365 用户、添加 Microsoft 365 商务语音许可证，并分配电话号码
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
localization_priority: Priority
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- Teams_Business_Voice
search.appverid: MET150
description: ''
appliesto:
- Microsoft Teams
ms.openlocfilehash: bd00c4baf7958926c2e27e8141630444e7df637c
ms.sourcegitcommit: 30b4b979e20066253e32ab9e44d79c48a97e6211
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/05/2019
ms.locfileid: "37972073"
---
# <a name="create-and-license-users-and-assign-phone-numbers-to-them"></a>创建用户并为其授予许可并分配电话号码

要使用 Microsoft 365 商务语音，用户需要 Microsoft 365 帐户，其中包含带有 SMS 许可证的 Microsoft 365 商务语音。 在创建包含带有 SMS 许可证的 Microsoft 365 商务语音的帐户后，可以向其分配电话号码。

## <a name="create-and-license-users"></a>创建用户并向其授予许可

1. 按照[将用户单独或批量添加到 Office 365](https://docs.microsoft.com/office365/admin/add-users/add-users)中的步骤添加一个或多个用户。
2. 在“**分配产品许可证**”窗格中，确保选择“**具有 SMS 的 Microsoft 365 商务语音**。

## <a name="assign-phone-numbers-to-users"></a>向用户分配电话号码

在创建用户并向其分配带有 SMS 许可证的 Microsoft 365 商务语音后，可以向其分配电话号码。 每个需要电话号码的用户需要一个未分配的电话号码。 如果没有足够的未分配电话号码，请参阅本文后面的[获取更多电话号码](#get-more-phone-numbers)。

1. 转到 https://admin.teams.microsoft.com
2. 输入电话号码请求的名称和说明
3. 选择“**语音**” > “**电话号码**”
4. 选择要分配给用户的电话号码并选择“**编辑**”
5. 在“**编辑**”面板中，在“**分配对象**”中输入要向其分配号码的用户名称，然后选择“**分配**”
6. 在“**紧急位置**”中，输入用户所在的位置，然后选择“**应用**”


## <a name="get-more-phone-numbers"></a>获取更多电话号码

如果没有足够的电话号码分配给新用户，可以获取更多电话号码。 下订单后，可能需要最多 24 小时才可获取这些号码。

1. 转到 https://admin.teams.microsoft.com
2. 输入电话号码请求的名称和说明
3. 选择“**语音**” > “**电话号码**”，然后选择“**添加**”
4. 选择要创建电话号码的国家或地区
5. 在“**号码类型**”中，选择“**用户（订阅者）**”
6. 在“**位置**”中，搜索用户的位置并选中它。 如果需要添加新位置，请选择“**添加位置**”。
7. 选择一个区号，输入要获取的电话号码，然后单击“**下一步**”
8. 等待保留电话号码，查看所选号码，如果所有内容看起来正确，请选择“**下订单**”，然后选择“**完成**”。

