---
title: Teams 的分配
author: danieasmith
ms.author: danismith
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
description: 了解如何在 Microsoft Teams 管理中心内管理Teams 教育版。
ms.localizationpriority: medium
appliesto:
- Microsoft Teams
ms.openlocfilehash: 59fb8e0b81195c696b7bd6142ecf031688207917
ms.sourcegitcommit: 115e44f33fc7993f6eb1bc781f83eb02a506e29b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/11/2021
ms.locfileid: "60909593"
---
# <a name="assignments-in-teams-for-education"></a>Teams 教育版中的分配

教师作业和成绩功能Teams 教育版教师向学生分配任务、工作或测验。 教师可以管理作业时间表、说明、添加要上交的资源、使用标准评分等。 他们还可以在"成绩"选项卡中跟踪班级和单个学生的进度。

[详细了解作业和作业Teams 教育版。](https://support.office.com/article/microsoft-teams-5aa4431a-8a3c-4aa5-87a6-b6401abea114?ui=en-US&rs=en-IE&ad=IE#ID0EAABAAA=Assignments)

> [!Note]
> 有关不同平台上Teams分配的详细信息，请参阅Teams[平台提供的功能](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)。

## <a name="assignments-integrations-in-the-microsoft-teams-admin-center"></a>作业管理中心Microsoft Teams集成

使用管理中心中的Microsoft Teams设置，您可以为您的组织内的教师及其学生打开或关闭功能。 下面是与分配相关的设置：

<a name="#bkemaildigest"> </a>

### <a name="weekly-guardian-email-digest"></a>每周监护人电子邮件摘要

每个周末向家长或监护人发送监护人电子邮件。 电子邮件包含有关前一周和即将到来的一周的作业的信息。 可以使用 以下方法设置家长和监护人[学校数据同步。](/schooldatasync/parent-contact-sync)

1. 在 SDS 中通过家长和监护人同步导入家长联系信息。 有关如何启用家长和监护人同步的说明，请参阅 [启用家长和监护人同步](/schooldatasync/parent-contact-sync#enabling-parent-and-guardian-sync)。

2. 在管理中心中Microsoft Teams"守护者设置"，因为此设置默认已关闭。 这样，教师可以每周发送摘要。

   > [!NOTE]
   > 教师可以通过取消选择他们自己的个人课堂团队中的设置来选择退出摘要 (作业设置 >**家长/监护人** 电子邮件) 。

若要验证家长是否收到电子邮件，以下三项必须为 true：

- 附加到 SDS 中学生个人资料并标记为家长 _或_ 监护人 _的电子邮件地址_。 有关详细信息，请参阅 [家长和监护人同步文件格式](/schooldatasync/parent-contact-sync-file-format)。

- 学生属于至少一个课堂，教师在作业设置 中未禁用 [电子邮件](https://support.microsoft.com/office/adjust-assignment-settings-in-your-class-team-05bb3b89-1cdf-415a-b6c7-44add0376a77)。

- 电子邮件将包含有关截止日期为上一周或即将到来的一周的作业的信息。

此功能的默认设置为 **-Off。**

<a name="bkmakecode"> </a>

### <a name="makecode"></a>MakeCode

Microsoft MakeCode 是一个基于块的编码平台，它使所有学生都了解计算机科学。

MakeCode 是 Microsoft 产品，受 Microsoft[使用条款和](https://go.microsoft.com/fwlink/?LinkID=206977)[隐私策略](https://go.microsoft.com/fwlink/?LinkId=521839)的约束。

此功能的默认设置为 **-Off。**

若要在 Teams 中启用 MakeCode 分配，请转到 Teams 管理中心，导航到"分配"部分，将 MakeCode 切换选项切换到 **"****打开"。** 单击“**保存**”。 为这些设置留出几个小时才能生效。

有关此功能工作原理的信息，请观看 [此视频演示](https://makecode.com/blog/teams/teams-assignments)。

[详细了解 MakeCode。](https://aka.ms/makecode)

<a name="#turnitin"> </a>

### <a name="turnitin"></a>Turnitin

[Turnitin](https://www.turnitin.com/) 是一项学术完整性服务。 这是第三方服务，受其自己的条款和隐私策略的约束。 你有责任使用任何第三方产品和服务。

此功能的默认设置为 - **关闭**。

若要为组织启用 Turnitin，需要 Turnitin 订阅。 然后，可以输入以下信息，这些信息可在 Turnitin 管理控制台中找到：

- **TurnitinApiKey：** 这是一个 32 个字符的 GUID，位于管理控制台的"集成"下。
- **TurnitinApiUrl：** 这是 Turnitin 管理控制台的 HTTPS URL。

下面是可帮助你获取此信息的一些说明。

**TurnitinApiUrl** 是管理员控制台的主机地址。
示例：`https://your-tenant-name.turnitin.com`

可以在管理控制台中创建集成和与集成关联的 API 密钥。

从 **侧菜单中** 选择"集成"，然后选择" **添加集成** "并命名集成。

![显示添加新集成的屏幕截图。](./educationImages/Assignments_mopo_turnitin2.png)

按照提示后，系统将会提供 **TurnitinApiKey。**
复制 API 密钥并将其粘贴到Microsoft Teams中心。  这是查看密钥的唯一时间。

![显示复制 API 密钥的屏幕截图。](./educationImages/Assignments_mopo_turnitin3.png)

在管理 **中心** 中单击此设置的"保存"按钮后，请等待几个小时让这些设置生效。

## <a name="assignments-data"></a>分配数据

作业存储教师和学生生成的信息。 所有数据在教师和特定学生之间共同共享，而该信息用于课堂。 有两个存储，SharePoint和外部存储SharePoint。

>[!NOTE]
>相同的规则也适用于第一方集成，例如读取进度。

### <a name="assignments-data-in-sharepoint-document-libraries"></a>文档库中SharePoint分配数据

与作业提交相关联的学生文件存储在名为"学生作业" (的文档库中) 。  与教师创建且学生可访问的作业关联的文件存储在另一个文档库中 (*名为：课堂* 文件) 的相应课堂团队 SharePoint 网站。 第一方集成还可以将作业数据存储在同一相应的课堂团队网站SharePoint网站 (名为：作业标题 *+* 时间戳) 。

#### <a name="files-associated-with-the-student"></a>与学生关联的文件

IT 管理员可以使用内容搜索工具搜索学生文件 (学生作业、课堂文件或其他第一方集成文件) ，这些文件与作业提交和与作业相关的文件相关。 例如，管理员可以搜索组织SharePoint的所有网站，并使用学生的姓名和课堂或作业名称在搜索查询中查找与 DSR (请求) 。

#### <a name="files-associated-with-the-teacher"></a>与教师关联的文件

IT 管理员可以使用内容搜索工具搜索教师文件 (*学生* 作业、 *课堂* 文件或其他第一方集成文件) ，这些文件与作业相关，以及教师在作业中分发给学生的文件。 例如，管理员可以搜索SharePoint的所有网站，并使用教师的姓名和课堂或作业名称在搜索查询中查找与 DSR 相关的数据。

### <a name="assignments-data-outside-of-sharepoint-document-libraries"></a>文档库SharePoint分配数据

与作业相关的某些数据不会存储在课堂团队SharePoint网站中，这意味着内容搜索无法发现。 这包括：

- 学生成绩和来自教师的反馈
- 每个学生提交作业的文档列表
- 作业详细信息，如截止日期等。
- 第一方集成数据，如阅读进度段落或学生发音数据

对于此类数据，IT 管理员或数据所有者（如教师）可能需要转到课堂团队中的作业才能查找与 DSR 相关的数据。 管理员可以将自己添加为课堂所有者，并查看该课堂团队的所有作业。

>[!NOTE]
>如果学生不再是课堂的一部分，其数据可能仍存在于课堂中，因为 *不再注册*。 学生必须向租户管理员提供他们曾经参与的此类课堂的列表。

### <a name="bulk-export-assignment-data-outside-of-sharepoint-document-libraries"></a>批量导出文档库SharePoint作业数据

#### <a name="for-a-student"></a>对于学生

若要批量导出单个学生的数据，在从学生参与的课堂中删除学生之前，请运行脚本并提供 [](/microsoft-365/education/deploy/configure-assignments-for-teams) ``userId`` 。 如果学生已从网站中删除，则管理员可以在运行脚本之前将学生添加回课堂，或者管理员可以提供 和 学生曾经参与的 ``userId`` ``classId`` 。

将导出有关学生提交的数据。

#### <a name="for-a-teacher"></a>对于教师

批量导出作业数据对学生的工作方式相同，但教师有权访问的所有提交都将导出。

### <a name="bulk-delete-assignment-data-outside-of-sharepoint-document-libraries"></a>批量删除文档库SharePoint分配数据

#### <a name="for-a-student"></a>对于学生

若要批量删除单个学生的数据，在从学生参与的课堂中删除学生之前，请运行脚本并提供[](/microsoft-365/education/deploy/configure-assignments-for-teams) ``userId`` 。 如果学生已从网站中删除，则管理员可以在运行脚本之前将学生添加回课堂，或者管理员可以提供 和 学生曾经参与的 ``userId`` ``classId`` 。

提供 ``ClassId`` 将允许管理员仅从特定课堂中删除有关学生的信息。

#### <a name="for-a-teacher"></a>对于教师

由于教师作业的数据在整个课堂中共享，因此没有批量删除选项。 相反，管理员可以将自己添加到课堂，转到应用，然后删除作业。

有关详细信息，请参阅为作业 [配置Teams。](/microsoft-365/education/deploy/configure-assignments-for-teams)

## <a name="removing-assignments-and-grades"></a>删除作业和成绩

还可使用Teams策略删除特定用户或整个租户的作业和成绩。

若要删除单个用户的作业和成绩，请转到 Teams **管理中心并** 导航到"Teams应用 **>"权限策略**"以创建新的应用权限策略定义。  创建新的策略定义时，将 Microsoft **应用** 策略设置为"阻止特定应用"，并允许其他所有应用，将"分配"添加到阻止的应用程序列表。 保存新策略定义后，将其分配给相应的用户。

若要删除整个租户的作业和成绩，请转到 Teams **管理** 中心，导航到 Teams **应用>"管理应用"，** 然后从应用程序列表中搜索并选择"作业"。 将"分配应用程序设置"页中的状态设置更改为 _"已阻止"。_
