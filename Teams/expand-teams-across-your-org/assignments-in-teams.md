---
title: Teams 的分配
author: DaniEASmith
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
description: 了解如何在 Teams 教育版 的 Microsoft Teams 管理中心管理分配。
ms.localizationpriority: medium
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1475406697778080d5e49aae58729e6eb1d1576c
ms.sourcegitcommit: 9504b7a67e593f5575060b09b69817325e2a1f77
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/18/2022
ms.locfileid: "69111139"
---
# <a name="assignments-in-teams-for-education"></a>Teams 教育版中的分配

Teams 教育版 中的作业和成绩功能允许教师为其学生分配任务、工作或测验。 教师可以管理作业时间线、说明、添加要上交的资源、评分评分等。 他们还可以在“成绩”选项卡中跟踪班级和个别学生的进度。

[详细了解 Teams 教育版 中的作业和成绩](https://support.office.com/article/microsoft-teams-5aa4431a-8a3c-4aa5-87a6-b6401abea114?ui=en-US&rs=en-IE&ad=IE#ID0EAABAAA=Assignments)。

> [!Note]
> 有关不同平台上的 Teams 分配的详细信息，请参阅 [按平台显示的 Teams 功能](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)。

## <a name="assignments-integrations-in-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理中心中的分配集成

使用 Microsoft Teams 管理中心中的管理员设置，可以为组织内的教师及其学生打开或关闭功能。

若要查看和管理作业设置，请转到 Teams 管理中心中的 <a href="https://admin.teams.microsoft.com/education/assignments-settings" target="_blank">**“教育** > **作业设置**</a> ”。

以下是与工作分配相关的设置：

<a name="#bkemaildigest"> </a>

### <a name="weekly-guardian-email-digest"></a>每周监护人电子邮件摘要

监护人电子邮件在每个周末发送给家长或监护人。 电子邮件包含有关前一周和下一周的作业的信息。 可以使用 [学校数据](/schooldatasync/parent-contact-sync)同步设置家长和监护人同步。

1. 在 SDS 中通过家长和监护人同步导入家长联系信息。 有关如何启用父级和监护人同步的说明，请参阅 [启用家长和监护人同步](/schooldatasync/parent-contact-sync#enabling-parent-and-guardian-sync)。

2. 在 Microsoft Teams 管理中心中打开“卫报设置”，因为默认情况下，该设置处于关闭状态。 这将使教师能够发送每周摘要。

   > [!NOTE]
   > 教师可以通过取消选择自己的个人课堂团队中的设置来选择退出摘要， (**作业设置>家长/监护人电子邮件**) 。

若要验证 Parents 是否会收到电子邮件，必须满足以下三项条件：

- Email地址附加到 SDS 中学生个人资料，并标记为 _家长_ 或 _监护人_。 有关详细信息，请参阅 [父级和监护人同步文件格式](/schooldatasync/parent-contact-sync-file-format)。

- 学生至少属于一个课堂，教师在 [作业设置](https://support.microsoft.com/office/adjust-assignment-settings-in-your-class-team-05bb3b89-1cdf-415a-b6c7-44add0376a77)中未禁用电子邮件。

- 电子邮件将包含有关具有上一周或下一周截止日期的作业的信息。

此功能的默认设置为 - **关**。

<a name="bkmakecode"> </a>

### <a name="makecode"></a>MakeCode

Microsoft MakeCode 是一个基于块的编码平台，可让计算机科学成为所有学生的生活。

MakeCode 是受 Microsoft 使用条款和[隐私](https://go.microsoft.com/fwlink/?LinkId=521839)策略约束[的](https://go.microsoft.com/fwlink/?LinkID=206977) Microsoft 产品。

此功能的默认设置为 - **关**。

若要在 Teams 中启用 MakeCode 分配，请转到 **Teams 管理员中心**，导航到 **“分配”** 部分，然后将“MakeCode”切换选项更改为 **“开**”。 选择“**保存**”。 等待几个小时，这些设置才会生效。

有关此功能工作原理的详细信息，请观看此 [视频演示](https://makecode.com/blog/teams/teams-assignments)。

[详细了解 MakeCode](https://aka.ms/makecode)。

<a name="#turnitin"> </a>

### <a name="turnitin"></a>Turnitin

[Turnitin](https://www.turnitin.com/) 是一种学术诚信服务。 这是受其自己的条款和隐私策略约束的第三方服务。 你负责使用任何第三方产品和服务。

此功能的默认设置为 - **关**。

若要为组织启用 Turnitin，需要一个 Turnitin 订阅。 然后，可以输入以下信息，这些信息可在 Turnitin 管理控制台中找到：

- **TurnitinApiKey**：这是一个包含 32 个字符的 GUID，位于管理控制台的“集成”下。
- **TurnitinApiUrl**：这是 Turnitin 管理控制台的 HTTPS URL。

下面是帮助你获取此信息的一些说明。

**TurnitinApiUrl** 是管理控制台的主机地址。
示例：`https://your-tenant-name.turnitin.com`

可以在管理控制台中创建集成以及与集成关联的 API 密钥。

从侧边菜单中选择“ **集成** ”，然后选择“ **添加集成** ”，并为集成命名。

![显示添加新集成的屏幕截图。](./educationImages/Assignments_mopo_turnitin2.png)

按照提示操作后，系统会提供 **TurnitinApiKey** 。
复制 API 密钥并将其粘贴到 Microsoft Teams 管理中心。  这是唯一一次可以查看密钥。

![显示复制 API 密钥的屏幕截图。](./educationImages/Assignments_mopo_turnitin3.png)

在管理中心内单击此设置的“ **保存** ”按钮后，等待几个小时，这些设置才会生效。

## <a name="assignments-data"></a>工作分配数据

作业存储由教师和学生生成的信息。 所有数据在教师和特定学生之间共同共享，信息用于课堂。 此数据有两个存储：SharePoint 和 SharePoint 外部。

>[!NOTE]
>相同的规则也适用于第一方集成，例如阅读进度。

### <a name="assignments-data-in-sharepoint-document-libraries"></a>SharePoint 文档库中的分配数据

与作业提交关联的学生文件存储在名为“ *学生工作*) ”的文档库中 (。 与教师创建并由学生访问的作业关联的文件存储在另一个文档库中， (名为： *课堂文件*) 相应的课堂团队 SharePoint 网站。 第一方集成还可以将作业数据存储在同一个相应的课堂团队 SharePoint 网站中， (名为： *作业标题 + 时间戳*) 。

#### <a name="files-associated-with-the-student"></a>与学生关联的文件

IT 管理员可以使用内容搜索工具来搜索学生文件 (*学生作业*、 *课堂文件* 或其他与作业提交相关的第一方集成文件) 以及与作业相关的文件。 例如，管理员可以搜索组织中的所有 SharePoint 网站，并在搜索查询中使用学生的姓名和班级或作业名称来查找与 DSR)  (数据主体请求相关的数据。

#### <a name="files-associated-with-the-teacher"></a>与教师关联的文件

IT 管理员可以使用内容搜索工具搜索教师文件 (*学生作业*、 *课堂文件* 或其他第一方集成文件) ，这些文件与课堂中教师分发给学生的作业和文件相关。 例如，管理员可以搜索组织中的所有 SharePoint 网站，并在搜索查询中使用教师的姓名和班级或作业名称来查找与 DSR 相关的数据。

### <a name="assignments-data-outside-of-sharepoint-document-libraries"></a>在 SharePoint 文档库外部分配数据

与作业相关的某些数据未存储在课堂团队 SharePoint 网站中，这意味着内容搜索无法发现这些数据。 这包括：

- 学生成绩和教师的反馈
- 每个学生为作业提交的文档列表
- 作业详细信息，如截止日期等。
- 第一方集成数据，如阅读进度段落或学生发音数据

对于此类数据，IT 管理员或数据所有者（如教师）可能必须进入课堂团队中的作业，才能查找与 DSR 相关的数据。 管理员可以将自己添加为课堂的所有者，并查看该课堂团队的所有作业。

>[!NOTE]
>如果学生不再是课堂的一员，则他们的数据可能仍存在于课堂中，因为 *不再注册*。 学生必须向租户管理员提供他们曾经所属的此类课程的列表。

### <a name="bulk-export-assignment-data-outside-of-sharepoint-document-libraries"></a>批量导出 SharePoint 文档库外部的分配数据

#### <a name="for-a-student"></a>对于学生

若要批量导出单个学生的数据，请在将学生从所属课堂中删除之前， [请运行脚本](/microsoft-365/education/deploy/configure-assignments-for-teams) 并提供 ``userId``。 如果学生已从网站中删除，则管理员可以在运行脚本之前将学生添加回课堂，或者管理员可以提供 ``userId`` 学生曾经所属的 和 ``classId`` 。

将导出有关学生提交的数据。

#### <a name="for-a-teacher"></a>对于教师

批量导出作业数据的工作方式与学生相同，但将导出教师有权访问的所有提交。

### <a name="bulk-delete-assignment-data-outside-of-sharepoint-document-libraries"></a>批量删除 SharePoint 文档库外部的分配数据

#### <a name="for-a-student"></a>对于学生

若要批量删除单个学生的数据，请在将学生从所属课堂中删除之前， [请运行脚本](/microsoft-365/education/deploy/configure-assignments-for-teams) 并提供 ``userId``。 如果学生已从网站中删除，则管理员可以在运行脚本之前将学生添加回课堂，或者管理员可以提供 ``userId`` 学生曾经所属的 和 ``classId`` 。

``ClassId``提供 将允许管理员仅从特定班级中删除有关学生的信息。

#### <a name="for-a-teacher"></a>对于教师

由于教师作业的数据在课堂上共享，因此没有大容量删除选项。 相反，管理员可以将自己添加到课堂，转到应用，然后删除作业。

有关详细信息，请参阅 [配置 Teams 分配](/microsoft-365/education/deploy/configure-assignments-for-teams)。

## <a name="removing-assignments-and-grades"></a>删除作业和成绩

还可以使用 Teams 策略删除特定用户或整个租户的分配和成绩。

若要删除单个用户的作业和成绩，请转到 **Teams 管理员 中心**，导航到 **Teams 应用>权限策略** 创建新的应用权限策略定义。  创建新策略定义时，将 **Microsoft 应用** 策略设置为 _“阻止特定应用并允许所有其他应用_ ”，并将 **“作业** ”和 **“成绩** ”添加到阻止的应用程序列表。 保存新策略定义后，将其分配给相应的用户。

若要删除整个租户的作业和成绩，请转到 **Teams 管理员中心**，导航到 **Teams 应用>管理应用**，并从应用程序列表中搜索并选择 **“作业** 和 **成绩**”。 将应用程序的设置页中的状态设置更改为 _“已阻止_”。

## <a name="assignments-diagnostic-tool-for-users"></a>用户的分配诊断工具

Microsoft 支持部门创建了一个工具，用于收集 Microsoft 工程团队的诊断数据，以调查与“分配”功能相关的问题。

可以在用户遇到问题的任何屏幕上的“分配”中访问此工具。

若要在 Teams 中拉取诊断工具，用户可以：

- **在桌面和 Web 上：**
  - 选择 Ctrl+/
- **在移动设备上：**
  - 用两根手指触摸屏幕并旋转手指 45 度，或
  - 用三根手指点击屏幕 15 秒

弹出诊断工具后，用户将看到 Microsoft 技术支持可能需要的数据列表。

拉取的数据可能包括：

- 组 ID
- 租户 ID
- 会话 ID
- 分配 ID
- 提交 ID
- 用户 ID

此数据不会自动发送到 Microsoft。 用户需要将有关支持票证的数据复制并粘贴到 Microsoft 支持代理。

如果用户拉取诊断工具，然后将其关闭，则不会发送任何数据。

将数据发送到 Microsoft 支持代理时，会根据组织的 Microsoft 365 服务协议将其作为支持数据进行处理。

有关使用此诊断工具（可与教师和学生共享）的说明，请参阅 [获取诊断数据以排查作业问题](https://support.microsoft.com/topic/b40793f5-dbae-4c8a-841a-6baa7f232e2e)。
