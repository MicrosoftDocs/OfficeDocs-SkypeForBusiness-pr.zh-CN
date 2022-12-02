---
title: 排查Microsoft Teams 职业指导问题
author: DaniEASmith
ms.author: danismith
ms.reviewer: alaina.creager
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 了解如何在适用于 Microsoft Teams 的职业指导中排查常见问题。
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- m365initiative-edu
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4c00837c40fe405ab4d9d608326a12567843c8bb
ms.sourcegitcommit: aef1ab47fb9cb4502cb49bc3c7ffafcd62e54c82
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2022
ms.locfileid: "69242446"
---
# <a name="troubleshoot-career-coach-for-microsoft-teams"></a>排查Microsoft Teams 职业指导问题

本文面向需要排查 Microsoft Teams 职业指导问题的教育 IT 管理员。

以下是 IT 管理员在职业指导中可能采取的常见问题和解决方法步骤。

## <a name="missing-required-configuration-data"></a>缺少所需的配置数据

如果在职业指导体验中看到“当前正在设置职业指导供你使用”，则 **尚未添加所有必需的配置数据**。

你的机构必须完全配置 [LinkedIn连接](career-coach-set-up-steps.md#linkedin-connection-required) 。

参考 [职业指导配置状态](career-coach-set-up-steps.md#configuration-status) ，查看需要完成的设置。

## <a name="incorrect-formatting-of-course-catalog-or-fields-of-study-data"></a>课程目录或学习字段数据的格式不正确

课程目录和研究领域的 CSV 具有所需的格式，最大大小为 18 MB。

参考职业指导 [课程目录文档架构](career-coach-set-up-steps.md#course-catalog-document-format-and-schema) 和职业指导 [字段学习文档架构](career-coach-set-up-steps.md#fields-of-study-document-format-and-schema) ，以确保正确配置。

此外，课程目录文件的行数不应超过 15，000 行，以确保处理成功。

## <a name="missing-fields-in-career-coach-settings-pages"></a>职业指导设置页中缺少字段

职业指导设置页具有必填字段。 如果未完成必要的字段，页面将不会提交。

你可能看不到警告消息，并且页面不会提交。

在页面顶部看到绿色横幅时，提交成功。

## <a name="setup-policy-changes-arent-complete"></a>设置策略更改未完成

如果职业指导未显示在用户的 Microsoft Teams 中，则设置策略更改可能尚未生效。 在设置策略更改生效之前，不会为 Microsoft Teams 中的用户安装并固定职业指导。 策略更改可能需要几个小时才能生效。

但是，职业指导可以直接从 Microsoft Teams 应用商店安装。

- 如果用户在 Microsoft Teams 应用商店中找不到 Career Coach，请查看你的应用权限策略，并确保 Career Coach 不是被阻止的应用。
- 职业指导是一个Microsoft应用，最佳做法是允许按权限策略Microsoft应用。 详细了解 [如何配置权限策略](teams-app-permission-policies.md)。

## <a name="career-coach-initialization-isnt-complete"></a>职业指导初始化未完成

可能会遇到以下错误：“我们无法检索应用的设置。 再试一次。 如果仍然遇到问题，请联系Microsoft客户支持。”

在 [“职业指导”设置页上](career-coach-set-up-steps.md#career-coach-settings-status)查看 **“服务预配”状态**。

如果租户仍在初始化，请等待 15 分钟，然后重试。 如果仍收到错误，请打开支持票证。
