---
title: Teams 的分配
author: lanachin
ms.author: v-lanac
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
description: 了解如何在 "团队教育版" 的 "Microsoft 团队管理中心" 中管理作业。
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.openlocfilehash: e3a0bf0dd0141679dc89ed1d5ecc0cfc542854c8
ms.sourcegitcommit: 3eb5820b279fc904f34ac4259deeb419e02d832a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/03/2020
ms.locfileid: "49561048"
---
# <a name="assignments-in-teams-for-education"></a>Teams 教育版中的分配

作业是指分配给课程中的学生或团队成员的任务或工作单元，作为其研究的一部分。 可以在团队类中创建作业。

[了解有关作业的详细信息](https://support.office.com/article/microsoft-teams-5aa4431a-8a3c-4aa5-87a6-b6401abea114?ui=en-US&rs=en-IE&ad=IE#ID0EAABAAA=Assignments)。

> [!Note]
> 有关不同平台上的团队工作分配的详细信息，请参阅 [团队功能按平台](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)。

## <a name="assignments-in-the-microsoft-teams-admin-center"></a>Microsoft 团队管理中心中的作业

使用 Microsoft 团队管理中心中的管理员设置，你可以打开或关闭以下功能，以便供你的组织内的学生和教师使用。 以下是与作业相关的设置：

<a name="#bkemaildigest"> </a>
### <a name="weekly-guardian-email-digest"></a>每周监护人电子邮件摘要

该电子邮件将包含有关上一周和未来一周的作业的信息，并将通过周末发送。 可在此处找到有关电子邮件内容的信息。 通过使用 [学校数据同步 (SDS) ](https://docs.microsoft.com/schooldatasync/)，管理员需要设置和更新电子邮件。 此功能会自动从学校的学生信息系统 (SIS) 中为学生海报的团队填充课程。 启用此功能的步骤包括：

1. 通过 SDS 中的家长和监护人同步导入父联系人信息。 有关如何启用家长和监护人同步的说明，请参阅 [启用家长和监护人同步](https://docs.microsoft.com/schooldatasync/parent-contact-sync#enabling-parent-and-guardian-sync)。

2. 在 Microsoft 团队管理中心中启用监护人设置，因为默认情况下该设置处于关闭状态。 这将使教师能够发送每周摘要。

   > [!NOTE]
   > 教师可以通过在其自己的个人课堂团队 (**工作分配设置 > 父/监护人电子邮件**) 中取消摘要，从而选择退出摘要。

若要验证父母是否收到电子邮件，必须满足以下三项条件：

 - 附加到 SDS 中的学生档案并标记为 _家长_ 或 _监护人_ 的电子邮件地址。 有关详细信息，请参阅 [父和监护人同步文件格式](https://docs.microsoft.com/schooldatasync/parent-contact-sync-file-format)。

 - 学生至少属于一个类，其中的电子邮件未由教师在 [作业设置](https://support.microsoft.com/office/adjust-assignment-settings-in-your-class-team-05bb3b89-1cdf-415a-b6c7-44add0376a77)中禁用。

 - 该电子邮件将包含有关前一周或下一周的截止日期的作业的信息。

默认情况下，此设置处于关闭状态。


<a name="bkmakecode"> </a>
### <a name="makecode"></a>MakeCode
Microsoft MakeCode 是一种基于块的编码平台，让所有学生都能使用电脑科学。 

MakeCode 是一种受 Microsoft [使用条款](https://go.microsoft.com/fwlink/?LinkID=206977) 和 [隐私](https://go.microsoft.com/fwlink/?LinkId=521839) 政策制约的 microsoft 产品。

默认情况下，此设置处于关闭状态。 若要启用团队中的 MakeCode 作业，请在 " **团队管理中心**" 中，导航到 " **作业** " 部分，然后将 MakeCode 切换选项转换为 **"开**"。 单击 " **保存** "，并允许几个小时才能使这些设置生效。

有关此功能的工作原理的详细信息，请参阅此 [视频演示](https://makecode.com/blog/teams/teams-assignments)。

[了解有关 MakeCode 的详细信息](https://aka.ms/makecode)。

<a name="#turnitin"> </a>
### <a name="turnitin"></a>Turnitin

Turnitin 是一种 plagiarism 检测服务。 这是由其自身条款和隐私政策制约的第三方产品或服务。 您负责使用第三方产品和服务。

默认情况下，此设置处于关闭状态。

为了成功为你的组织启用 Turnitin，你需要已拥有 Turnitin 订阅。 你将需要输入以下附加信息，这些信息可在 Turnitin 管理控制台中找到：

  * **TurnitinApiKey**：这是在管理控制台中的集成下发现的32字符的 GUID。
  * **TurnitinApiUrl**：这是你的 Turnitin 管理员控制台的 HTTPS URL。

下面是帮助你获取此信息的一些说明。

**TurnitinApiUrl** 是您的管理员控制台的主机地址。
上例 `https://your-tenant-name.turnitin.com`

管理员控制台是你可以在其中创建集成和与集成相关联的 API 密钥。

从侧菜单中选择 " **集成** "，然后选择 " **添加集成** " 并为集成提供名称。

![显示添加新集成的屏幕截图](./educationImages/Assignments_mopo_turnitin2.png)

按照提示操作后，将为您提供 **TurnitinApiKey** 。 复制 API 密钥并将其粘贴到 Microsoft 团队管理中心。  这是唯一可以查看密钥的时候。

![显示复制 API 密钥的屏幕截图](./educationImages/Assignments_mopo_turnitin3.png)

单击管理中心中的 " **保存** " 按钮后，此设置才会生效。

准备好开始使用团队中的 Turnitin 集成？ 注册 [早期访问计划](https://www.turnitin.com/products/feedback-studio/microsoft-teams-integration)。
