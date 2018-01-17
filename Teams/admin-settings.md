---
title: "Microsoft Teams 中适用于应用的管理设置"
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "了解如何在 Microsoft Teams 中允许和启用应用，包括侧向加载外部应用。"
ms.openlocfilehash: 4265866bb346da1aa773d337d02fc1c11149f579
ms.sourcegitcommit: ee1c79b6d6d73e5fc702fe55b9e5aee8a7aae793
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/10/2018
---
<a name="admin-settings-for-apps-in-microsoft-teams"></a>Microsoft Teams 中适用于应用的管理设置
==========================================

应用是第三方服务提供的选项卡、连接器或聊天机器人或这三者的任意组合。 可以在 Office 365 管理中心配置管理策略来控制允许哪些外部第三方应用。 通过这些策略可以指定允许和不允许哪些应用、新的外部应用行为以及是否允许侧向加载应用。

> [!NOTE]
> 要管理 Teams 中的应用的管理员设置，请转到 Office 365 管理中心并打开“**设置**” > “**服务和外接程序**”，然后选择“**Microsoft Teams**”。 如果你已使用 Office 365 管理员身份登录，点击此链接应该能实现此操作：
> 
> https://portal.office.com/adminportal/home#/Settings/ServicesAndAddIns 

**在 Microsoft Teams 中允许外部应用**

默认情况下，启用“在 Microsoft Teams 中允许外部应用”，并选中所有应用。 将此策略设置为**“关闭”**后，则禁用所有外部第三方应用。 你可以进行更加精细的控制，先启用允许外部应用，然后单个取消选中你要禁用的特定应用。

**默认启用新的外部应用**

每当新应用提交到 Teams 应用目录时，此开关控制此租户中的用户是否可以使用这些应用。 默认情况下，此策略设置为**“开启”**，表示允许用户在应用添加到 Teams 的应用目录时即可访问这些应用。 如果你更希望先验证应用，再允许在 Teams 中使用它们，则将此策略设置为**“关闭”**。 请注意，如果将此策略设置为**“关闭”**，你应该定期评估新加的应用，以确保你的用户能够从应用的最新创新和增加内容中获益。

**允许侧向加载外部应用**

仅获得权限的 Team 所有者或成员可以向 Microsoft Teams 中侧向加载应用。 向 Microsoft Teams 中侧向加载应用的一些优势如下：

-   能够在向 Microsoft 提交应用之前对其进行测试

-   直接向贵组织中的用户提供应用，而无需向 Office 应用商店提交应用

要详细了解如何向 Microsoft Teams 中侧向加载应用，请参阅：[在团队中侧向加载应用](https://go.microsoft.com/fwlink/?linkid=854631)。

![Microsoft Teams 设置的“应用”部分屏幕截图。](media/Admin_settings_for_apps_in_Microsoft_Teams_image1.png)
