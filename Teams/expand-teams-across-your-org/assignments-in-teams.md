---
title: Teams 的分配
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
search.appverid: MET150
ms.reviewer: jastark
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.assignments.overview
- ms.teamsadmincenter.assignments.tooltip.emaildigest
- ms.teamsadmincenter.assignments.tooltip.makecode
- ms.teamsadmincenter.assignments.tooltip.turnitin
description: 了解如何在 Teams 教育Microsoft Teams管理中心内管理作业。
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.openlocfilehash: 410f5d32dd8af4775639a080725cd5680b6a70c2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51121370"
---
# <a name="assignments-in-teams-for-education"></a>Teams 教育版中的分配

教育Teams中的作业和成绩功能允许教师为其学生分配任务、工作或测验。 教师可以管理作业时间表、说明、添加要上交的资源、使用标准评分等。 他们还可以在"成绩"选项卡中跟踪班级和单个学生的进度。

[了解有关教育Teams作业和成绩。](https://support.office.com/article/microsoft-teams-5aa4431a-8a3c-4aa5-87a6-b6401abea114?ui=en-US&rs=en-IE&ad=IE#ID0EAABAAA=Assignments)

> [!Note]
> 有关不同平台上Teams分配的详细信息，请参阅Teams[平台提供的功能](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)。

## <a name="assignments-integrations-in-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理中心中的作业集成

使用管理中心内的Microsoft Teams设置，您可以为您的组织内的教师及其学生打开或关闭功能。 下面是与分配相关的设置：

<a name="#bkemaildigest"> </a>
### <a name="weekly-guardian-email-digest"></a>每周监护人电子邮件摘要


每个周末向家长或监护人发送监护人电子邮件。 电子邮件包含有关前一周和即将到来的一周的作业的信息。 可以使用 以下方法设置家长和监护人[学校数据同步。](/schooldatasync/parent-contact-sync)

1. 在 SDS 中通过家长和监护人同步导入家长联系信息。 有关如何启用家长和监护人同步的说明，请参阅 [启用家长和监护人同步](/schooldatasync/parent-contact-sync#enabling-parent-and-guardian-sync)。

2. 在管理中心Microsoft Teams"守护者设置"，因为默认情况下该设置已关闭。 这样，教师可以每周发送摘要。

   > [!NOTE]
   > 教师可以通过取消选择他们自己的个人课堂团队中的设置来选择退出摘要 ("设置 >**家长/监护人** 电子邮件) 。

若要验证家长是否收到电子邮件，以下三项必须为 true：

 - 附加到 SDS 中学生个人资料并标记为家长 _或_ 监护人 _的电子邮件地址_。 有关详细信息，请参阅 [家长和监护人同步文件格式](/schooldatasync/parent-contact-sync-file-format)。

 - 学生属于至少一个课堂，教师在作业设置 中未禁用 [电子邮件](https://support.microsoft.com/office/adjust-assignment-settings-in-your-class-team-05bb3b89-1cdf-415a-b6c7-44add0376a77)。

 - 电子邮件将包含有关在上一周或即将到来的一周具有截止日期的作业的信息。

此功能的默认设置为 **-Off。**


<a name="bkmakecode"> </a>
### <a name="makecode"></a>MakeCode
Microsoft MakeCode 是一个基于块的编码平台，它使所有学生都了解计算机科学。 

MakeCode 是一种 Microsoft 产品，受 Microsoft[使用条款和](https://go.microsoft.com/fwlink/?LinkID=206977)[隐私策略](https://go.microsoft.com/fwlink/?LinkId=521839)的约束。

此功能的默认设置为 **-Off。**

若要在 Teams中启用 MakeCode 分配，请转到 Teams 管理中心，导航到"分配"部分，将 MakeCode 切换选项切换到 **"****打开"。** 单击“**保存**”。 为这些设置留出几个小时才能生效。

有关此功能工作原理的信息，请参阅此 [视频演示](https://makecode.com/blog/teams/teams-assignments)。

[详细了解 MakeCode。](https://aka.ms/makecode)

<a name="#turnitin"> </a>
### <a name="turnitin"></a>Turnitin

[Turnitin](https://www.turnitin.com/) 是一项学术完整性服务。 这是第三方产品或服务，受其自己的条款和隐私策略的约束。 你有责任使用任何第三方产品和服务。

此功能的默认设置为 - **关闭**。

若要为组织启用 Turnitin，需要 Turnitin 订阅。 然后，可以输入以下信息，这些信息可在 Turnitin 管理控制台中找到：

  * **TurnitinApiKey：** 这是一个 32 个字符的 GUID，位于管理控制台的"集成"下。
  * **TurnitinApiUrl：** 这是 Turnitin 管理控制台的 HTTPS URL。

下面是一些可帮助你获取此信息的说明。

**TurnitinApiUrl** 是管理员控制台的主机地址。
示例：`https://your-tenant-name.turnitin.com`

可以在管理控制台中创建集成和与集成关联的 API 密钥。

从 **侧菜单中** 选择"集成"，然后选择" **添加集成** "并命名集成。

![显示添加新集成的屏幕截图](./educationImages/Assignments_mopo_turnitin2.png)

按照提示后，系统将会提供 **TurnitinApiKey。** 复制 API 密钥并将其粘贴到Microsoft Teams中心。  这是查看密钥的唯一时间。

![显示复制 API 密钥的屏幕截图](./educationImages/Assignments_mopo_turnitin3.png)

在管理 **中心** 中单击此设置的"保存"按钮后，请等待几个小时让这些设置生效。