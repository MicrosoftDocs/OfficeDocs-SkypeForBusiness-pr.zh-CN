---
title: Microsoft Teams 职业教练疑难解答
author: SerdarSoysal
ms.author: serdars
ms.reviewer: alaina.creager
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 了解如何排查 Microsoft Teams 职业教练中的常见问题。
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- m365initiative-edu
appliesto:
- Microsoft Teams
ms.openlocfilehash: a5ebda4324f7cc46d69b882a53684b21b4fa2932
ms.sourcegitcommit: 3266fde54b92a18865d666b98e4e7e8322b9dedc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/26/2022
ms.locfileid: "67024134"
---
# <a name="troubleshoot-career-coach-for-microsoft-teams"></a>Microsoft Teams 职业教练疑难解答

本文适用于需要为 Microsoft Teams 的职业教练进行故障排除的高等教育 IT 管理员。

以下是 IT 管理员在职业教练中可能采取的常见问题和解决步骤。

## <a name="missing-required-configuration-data"></a>缺少所需的配置数据

如果在职业教练体验中看到“职业教练当前正在设置以供你很快使用”， **则尚未添加所有必需的配置数据**。

在使用职业教练之前 **，必须完成以下部分** ：

- [品牌和首选项](career-coach-set-up-steps.md#brand-and-preferences)
- [LinkedIn连接](career-coach-set-up-steps.md#linkedin-connection)
- [课程目录](career-coach-set-up-steps.md#course-catalog)
- [研究领域](career-coach-set-up-steps.md#fields-of-study)

参考 [职业教练配置状态](career-coach-set-up-steps.md#configuration-status) ，查看需要完成哪些设置。

## <a name="incorrect-formatting-of-course-catalog-or-fields-of-study-data"></a>课程目录或研究数据字段格式不正确

课程目录和研究领域的 CSV 具有必需格式，最大大小为 18 MB。

参考学习文档架构的职业教练 [课程目录文档架构](career-coach-set-up-steps.md#course-catalog-document-format-and-schema) 和职业教练 [字段](career-coach-set-up-steps.md#fields-of-study-document-format-and-schema) ，以确保正确配置。

此外，课程目录文件不应超过 15，000 行，以确保成功处理。

## <a name="missing-fields-in-career-coach-settings-pages"></a>职业教练设置页中缺少字段

职业教练设置页面具有必需字段。 如果必要字段未完成，页面将不会提交。

你可能看不到警告消息，并且页面不会提交。

当你在页面顶部看到绿色横幅时，提交会成功。

## <a name="setup-policy-changes-arent-complete"></a>安装策略更改未完成

如果职业教练未在 Microsoft Teams 中为用户显示，则设置策略更改可能尚未生效。 在设置策略更改生效之前，不会为 Microsoft Teams 中的用户安装和固定职业教练。 策略更改可能需要几个小时才能生效。

但是，职业教练可以直接从 Microsoft Teams 应用商店安装。

- 如果用户在 Microsoft Teams 应用商店中找不到职业教练，请查看应用权限策略，并确保职业教练不是受阻止的应用。
- 职业教练是 Microsoft 应用，最佳做法是按权限策略允许 Microsoft 应用。 详细了解如何 [配置权限策略](teams-app-permission-policies.md)。

## <a name="career-coach-initialization-isnt-complete"></a>职业教练初始化未完成

你可能会遇到以下错误：“无法检索应用的设置。 再试一次。 如果仍遇到问题，请联系 Microsoft 客户支持人员。

在“[职业教练设置”页](career-coach-set-up-steps.md#career-coach-settings-status)上检查 **服务预配状态**。

如果租户仍在初始化，请等待 15 分钟，然后重试。 如果仍收到错误，请打开支持票证。
