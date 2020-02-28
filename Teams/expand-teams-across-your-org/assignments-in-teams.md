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
ms.openlocfilehash: ad9e3f8b0f2f3800c7394a9d4dc21fe7a2058426
ms.sourcegitcommit: c16451519e05b47bbb77e09dacd13ff212617e91
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2020
ms.locfileid: "42327994"
---
# <a name="assignments-in-teams-for-education"></a>Teams 教育版中的分配

作业是指分配给课程中的学生或团队成员的任务或工作单元，作为其研究的一部分。 可以在团队类中创建作业。

[了解有关作业的详细信息](https://support.office.com/article/microsoft-teams-5aa4431a-8a3c-4aa5-87a6-b6401abea114?ui=en-US&rs=en-IE&ad=IE#ID0EAABAAA=Assignments)

## <a name="assignments-in-the-microsoft-teams-admin-center"></a>Microsoft 团队管理中心中的作业

使用 Microsoft 团队管理中心中的管理员设置，你可以打开或关闭以下功能，以便供你的组织内的学生和教师使用。 以下是与作业相关的设置：

<a name="#bkemaildigest"> </a>
### <a name="weekly-guardian-email-digest"></a>每周监护人电子邮件摘要

监护人电子邮件是发送给学生的家长或监护人的每周电子邮件。 该电子邮件将包含有关上一周和未来一周的作业的信息，并将通过周末发送。 管理员需要使用学校数据同步功能来更新电子邮件。

默认情况下，此设置处于关闭状态。

<a name="bkmakecode"> </a>
### <a name="makecode"></a>MakeCode
MakeCode 是一种基于块的编码平台，让所有学生都能使用电脑科学。 

这是由其自身条款和隐私政策制约的第三方产品或服务。 您负责使用第三方产品和服务。

默认情况下，此设置处于关闭状态。

[了解有关 MakeCode 的详细信息](https://www.microsoft.com/makecode)

<a name="#turnitin"> </a>
### <a name="turnitin"></a>Turnitin

Turnitin 是一种 plagiarism 检测服务。 这是由其自身条款和隐私政策制约的第三方产品或服务。 您负责使用第三方产品和服务。

默认情况下，此设置处于关闭状态。

为了成功为你的组织启用 Turnitin，你需要已拥有 Turnitin 订阅。 你将需要输入以下附加信息，这些信息可在 Turnitin 管理控制台中找到：

  * _TurnitinApiKey_：这是在管理控制台中的集成下发现的32字符的 GUID。
  * _TurnitinApiUrl_：这是你的 Turnitin 管理员控制台的 HTTPS URL。

下面是帮助你获取此信息的一些说明。

TurnitinApiUrl 是您的管理员控制台的主机地址。
上例. `https://your-tenant-name.turnitin.com`

管理员控制台是你可以在其中创建集成和与集成相关联的 API 密钥。

从侧菜单中选择 "**集成**"，然后选择 "**添加集成**" 并为集成提供名称。
![显示添加新集成的屏幕截图](./educationImages/Assignments_mopo_turnitin2.png)

按照提示操作后，将为您提供 TurnitinApiKey。 复制 API 密钥并将其粘贴到 Microsoft 团队管理中心。  这是唯一可以查看密钥的时候。
![显示复制 API 密钥的屏幕截图](./educationImages/Assignments_mopo_turnitin3.png)

单击管理中心中的 "**保存**" 按钮以使用此设置后，这些设置的生效时间最多为24小时。

准备好开始使用团队中的 Turnitin 集成？ 注册[早期访问计划](https://www.turnitin.com/products/feedback-studio/microsoft-teams-integration)。
