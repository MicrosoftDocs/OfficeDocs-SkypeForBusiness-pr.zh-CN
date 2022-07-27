---
title: Microsoft Teams 中的共享频道错误
author: MikePlumleyMSFT
ms.author: mikeplum
manager: serdars
ms.reviewer: jasonlewis
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.localizationpriority: normal
search.appverid: MET150
description: 了解如何在 Microsoft Teams 中的共享通道中使用修复错误。
ms.openlocfilehash: ecd05f1593817ed03d6e516e8915cd15694b6315
ms.sourcegitcommit: 3266fde54b92a18865d666b98e4e7e8322b9dedc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/26/2022
ms.locfileid: "67024132"
---
# <a name="shared-channels-errors-in-microsoft-teams"></a>Microsoft Teams 中的共享频道错误

如果用户尝试将组织外部的人员添加到共享频道时看到错误消息，请查看本文中的设置。 

## <a name="due-to-admin-policy-you-cant-add-external-people-to-the-channel-for-more-info-talk-to-your-admin"></a>由于管理策略，无法将外部人员添加到频道。 有关详细信息，请与管理员联系。

Teams 使用Microsoft 365 组作为团队成员身份。 必须打开Microsoft 365 组来宾设置，才能将组织外部的人员添加到共享频道。 如果用户看到此错误，请检查组织外部人员的Microsoft 365 组设置。

为组织外部人员设置Microsoft 365 组设置
1. 在Microsoft 365 管理中心的左侧导航窗格中，展开 **“设置**”。
1. 单击 **组织设置**。
1. 在列表中，单击 **Microsoft 365 组**。
1. 确保 **让组所有者将组织外部的人员添加到Microsoft 365 组作为来宾**，同时选中 **“让来宾组成员访问组内容**”复选框。
1. 如果进行了更改，请单击 **“保存”更改**。

## <a name="due-to-admin-policy-you-cant-add-external-people-to-the-channel"></a>由于管理策略，无法将外部人员添加到频道

Teams 频道策略决定了用户如何与共享频道交互。 如果用户看到此错误消息，请检查该用户的频道策略。

设置邀请组织外部人员共享频道的策略
1. 在 Microsoft Teams 管理中心的左侧导航中，转到 Teams > Teams 策略。
1. 选择用户分配给的策略。
1. 确保 **“邀请外部用户访问共享频道****”已启用**。
1. 如果进行了更改，请选择 **“应用**”。

有关 Teams 频道策略的详细信息，请参阅 [Microsoft Teams 中的“管理频道策略](teams-policies.md)”。

## <a name="you-cant-share-this-channel-with-people-from-this-org"></a>无法与此组织中的人员共享此频道

如果用户看到此错误，则 Azure Active Directory 跨租户访问设置会阻止他们与其他组织中的人员共享频道。 这可能是由于组织中的入站设置或其他组织中的出站设置。

检查组织的入站设置
1. 在 [Azure Active Directory 中](https://aad.portal.azure.com)，选择 **“外部标识**”，然后选择 **跨租户访问设置**。
1. 选择要检查的组织的入站访问链接。
1. 在 **“B2B 直接连接** ”选项卡上，选择 **“自定义设置**”。
1. 在 **“外部用户和组** ”选项卡上，确保选择“ **允许访问** ”和 **“所有外部用户和组** ”，或者选择“ **选择外部用户和组**”，确保受邀的用户是所选组的成员。
1. 如果进行了更改，请选择 **“保存** ”并关闭“ **入站访问设置”边** 栏选项卡。

如果用户继续看到错误，请与正在协作的组织核实。 该组织的出站设置可能会禁止与组织共享。 有关在组织之间设置共享频道的信息，请参阅 [与共享频道中的外部参与者协作](/microsoft-365/solutions/collaborate-teams-direct-connect)。

## <a name="we-couldnt-find-any-matches-make-sure-the-email-address-is-correct-or-talk-to-your-admin"></a>我们找不到任何匹配项。 确保电子邮件地址正确，或与管理员交谈

如果用户看到此错误，则 Microsoft 365 无法在外部组织中找到指定的电子邮件地址。 需要向外部组织确认地址。

