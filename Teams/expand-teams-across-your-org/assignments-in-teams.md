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
description: 了解如何在 "团队教育版" 的 "Microsoft 团队管理中心" 中管理作业。
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.openlocfilehash: f283a4fb2d49778f4b0e8b31f46dada46f900e6f
ms.sourcegitcommit: 07afc959fec802db583e7111280d0035fdb6e412
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "49616906"
---
# <a name="assignments-in-teams-for-education"></a>Teams 教育版中的分配

"用于教育的团队中的工作分配和成绩" 功能允许教师向学生分配任务、工作或测验。 教师可以管理工作分配日程表、说明、添加要提交的资源、量规的成绩等。 他们还可以在 "成绩" 选项卡中跟踪课堂和单个学生的进度。

[了解有关团队教育版中的作业和成绩的详细信息](https://support.office.com/article/microsoft-teams-5aa4431a-8a3c-4aa5-87a6-b6401abea114?ui=en-US&rs=en-IE&ad=IE#ID0EAABAAA=Assignments)。

> [!Note]
> 有关不同平台上的团队工作分配的详细信息，请参阅 [团队功能按平台](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)。

## <a name="assignments-integrations-in-the-microsoft-teams-admin-center"></a>Microsoft 团队管理中心中的工作分配集成

使用 Microsoft 团队管理中心中的 "管理员" 设置，您可以打开或关闭您的组织及其学生的教育功能。 以下是与作业相关的设置：

<a name="#bkemaildigest"> </a>
### <a name="weekly-guardian-email-digest"></a>每周监护人电子邮件摘要


监护人电子邮件将每个周末发送给家长或监护人。 该电子邮件包含有关上一周和即将到来的周的作业的信息。 可使用 [学校数据同步](https://docs.microsoft.com/schooldatasync/parent-contact-sync)设置父和监护人同步。

1. 通过 SDS 中的家长和监护人同步导入父联系人信息。 有关如何启用家长和监护人同步的说明，请参阅 [启用家长和监护人同步](https://docs.microsoft.com/schooldatasync/parent-contact-sync#enabling-parent-and-guardian-sync)。

2. 在 Microsoft 团队管理中心中启用监护人设置，因为默认情况下该设置处于关闭状态。 这将使教师能够发送每周摘要。

   > [!NOTE]
   > 教师可以通过在其自己的个人课堂团队 (**工作分配设置 > 父/监护人电子邮件**) 中取消摘要，从而选择退出摘要。

若要验证父母是否收到电子邮件，必须满足以下三项条件：

 - 附加到 SDS 中的学生档案并标记为 _家长_ 或 _监护人_ 的电子邮件地址。 有关详细信息，请参阅 [父和监护人同步文件格式](https://docs.microsoft.com/schooldatasync/parent-contact-sync-file-format)。

 - 学生至少属于一个类，其中的电子邮件未由教师在 [作业设置](https://support.microsoft.com/office/adjust-assignment-settings-in-your-class-team-05bb3b89-1cdf-415a-b6c7-44add0376a77)中禁用。

 - 该电子邮件将包含有关前一周或下一周的截止日期的作业的信息。

此功能的默认设置为 " **关闭**"。


<a name="bkmakecode"> </a>
### <a name="makecode"></a>MakeCode
Microsoft MakeCode 是一种基于块的编码平台，让所有学生都能使用电脑科学。 

MakeCode 是一种受 Microsoft [使用条款](https://go.microsoft.com/fwlink/?LinkID=206977) 和 [隐私](https://go.microsoft.com/fwlink/?LinkId=521839) 政策制约的 microsoft 产品。

此功能的默认设置为 " **关闭**"。

若要启用团队中的 MakeCode 作业，请转到 **团队管理中心**，导航到 " **作业** " 部分，然后将 MakeCode 切换选项转换为 **"开**"。 单击“**保存**”。 等待几小时，这些设置生效。

有关此功能的工作原理的详细信息，请参阅此 [视频演示](https://makecode.com/blog/teams/teams-assignments)。

[了解有关 MakeCode 的详细信息](https://aka.ms/makecode)。

<a name="#turnitin"> </a>
### <a name="turnitin"></a>Turnitin

[Turnitin](https://www.turnitin.com/) 是一种学术的完整性服务。 这是由其自身条款和隐私政策制约的第三方产品或服务。 您负责使用第三方产品和服务。

此功能的默认设置为- **关闭**。。

若要为你的组织启用 Turnitin，你将需要 Turnitin 订阅。 然后，你可以输入以下信息，这些信息可以在你的 Turnitin 管理控制台中找到：

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

单击管理中心中的 " **保存** " 按钮以使用此设置时，请等待几个小时，这些设置才会生效。

