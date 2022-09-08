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
description: 了解如何在 Teams 教育版 中的 Microsoft Teams 管理中心管理工作分配。
ms.localizationpriority: medium
appliesto:
- Microsoft Teams
ms.openlocfilehash: 91afcd8036cddfae2550aaddad776958ca413a78
ms.sourcegitcommit: 8b33cc2c2e8f43e6ab4b17715d6a42692351ccad
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/08/2022
ms.locfileid: "67624292"
---
# <a name="assignments-in-teams-for-education"></a>Teams 教育版中的分配

Teams 教育版中的作业和成绩功能允许教师向学生分配任务、工作或测验。 教师可以管理作业时间线、说明、添加要上交的资源、使用 rubric 评分等。 他们还可以在“成绩”选项卡中跟踪课堂和个人学生的进度。

[详细了解Teams 教育版中的作业和成绩](https://support.office.com/article/microsoft-teams-5aa4431a-8a3c-4aa5-87a6-b6401abea114?ui=en-US&rs=en-IE&ad=IE#ID0EAABAAA=Assignments)。

> [!Note]
> 有关不同平台上的 Teams 分配的详细信息，请 [参阅 Teams 功能（按平台）](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)。

## <a name="assignments-integrations-in-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理中心中的分配集成

使用 Microsoft Teams 管理中心中的管理员设置，可以为组织内的教师及其学生打开或关闭功能。 下面是与工作分配相关的设置：

<a name="#bkemaildigest"> </a>

### <a name="weekly-guardian-email-digest"></a>每周监护人电子邮件摘要

每个周末都会向父母或监护人发送监护人电子邮件。 电子邮件包含有关前一周和未来一周的工作分配的信息。 可以使用 [学校数据同步](/schooldatasync/parent-contact-sync)设置家长同步和保护者同步。

1. 通过 SDS 中的父级和监护人同步导入父联系人信息。 有关如何启用父级和监护人同步的说明，请参阅 [“启用父级和监护人同步](/schooldatasync/parent-contact-sync#enabling-parent-and-guardian-sync)”。

2. 在 Microsoft Teams 管理中心打开“保护者设置”，因为默认情况下，设置已关闭。 这将使教师能够发送每周摘要。

   > [!NOTE]
   > 教师可以选择退出摘要，方法是取消选择自己的个人课堂团队中的设置 (**分配设置>家长/监护人电子邮件**) 。

若要验证家长是否将收到电子邮件，以下三项必须为 true：

- Email附加到 SDS 中的学生配置文件并标记为 _“家长_”或 _“监护人”_ 的地址。 有关详细信息，请参阅 [父级和保护者同步文件格式](/schooldatasync/parent-contact-sync-file-format)。

- 学生属于至少一个班级，教师在 [作业设置](https://support.microsoft.com/office/adjust-assignment-settings-in-your-class-team-05bb3b89-1cdf-415a-b6c7-44add0376a77)中不禁用电子邮件。

- 电子邮件将包含有关具有上一周或未来一周截止日期的作业的信息。

此功能的默认设置为 - **关闭**。

<a name="bkmakecode"> </a>

### <a name="makecode"></a>MakeCode

Microsoft MakeCode 是基于块的编码平台，为所有学生带来计算机科学的生命。

MakeCode 是受 Microsoft [使用条款](https://go.microsoft.com/fwlink/?LinkID=206977) 和 [隐私](https://go.microsoft.com/fwlink/?LinkId=521839) 策略约束的 Microsoft 产品。

此功能的默认设置为 - **关闭**。

若要在 Teams 中启用 MakeCode 分配，请转到 **Teams 管理员中心**，导航到 **“分配”** 部分，然后将 MakeCode 切换选项切换为 **“打开**”。 选择“**保存**”。 允许几个小时让这些设置生效。

有关此功能的工作原理的详细信息，请观看此 [视频演示](https://makecode.com/blog/teams/teams-assignments)。

[详细了解 MakeCode](https://aka.ms/makecode)。

<a name="#turnitin"> </a>

### <a name="turnitin"></a>Turnitin

[Turnitin](https://www.turnitin.com/) 是一项学术诚信服务。 这是一个受其自己的条款和隐私策略约束的第三方服务。 你负责使用任何第三方产品和服务。

此功能的默认设置为 - **关闭**。

若要为组织启用 Turnitin，需要一个 Turnitin 订阅。 然后，可以输入以下信息，可在 Turnitin 管理控制台中找到：

- **TurnitinApiKey**：这是在“集成”下的管理控制台中找到的 32 个字符的 GUID。
- **TurnitinApiUrl**：这是 Turnitin 管理控制台的 HTTPS URL。

下面是一些帮助你获取此信息的说明。

**TurnitinApiUrl** 是管理控制台的主机地址。
示例：`https://your-tenant-name.turnitin.com`

在管理控制台中，可以创建与集成关联的集成和 API 密钥。

从侧面菜单 **中选择“集成** ”，然后选择 **“添加集成** ”并为集成命名。

![显示添加新集成的屏幕截图。](./educationImages/Assignments_mopo_turnitin2.png)

按照提示操作后，将向你提供 **TurnitinApiKey** 。
复制 API 密钥并将其粘贴到 Microsoft Teams 管理中心。  这是唯一一次可以查看密钥。

![显示复制 API 密钥的屏幕截图。](./educationImages/Assignments_mopo_turnitin3.png)

单击此设置的管理中心中的 **“保存** ”按钮后，请允许几个小时让这些设置生效。

## <a name="assignments-data"></a>工作分配数据

作业存储由教师和学生生成的信息。 所有数据在教师和特定学生之间共同共享，这些学生的信息应在课堂上使用。 此数据有两个存储，即 SharePoint 和 SharePoint 外部。

>[!NOTE]
>相同的规则也适用于第一方集成，如阅读进度。

### <a name="assignments-data-in-sharepoint-document-libraries"></a>在 SharePoint 文档库中分配数据

与提交作业相关联的学生文件存储在名为“ *学生工作*) ” (文档库中。 与教师创建且学生可访问的作业相关联的文件存储在另一个文档库中， (名为： *类文件*) 相应的课堂团队 SharePoint 网站中。 第一方集成还可以将工作分配数据存储在同一个对应的类团队 SharePoint 站点中， (命名为： *工作分配标题 + 时间戳*) 。

#### <a name="files-associated-with-the-student"></a>与学生关联的文件

IT 管理员可以使用内容搜索工具搜索学生文件 (*学生工作*、 *课堂文件* 或其他第一方集成文件) 与作业提交和与作业相关的文件。 例如，管理员可以搜索组织中的所有 SharePoint 网站，并在搜索查询中使用学生的姓名、班级或作业名称查找与数据主体请求 (DSR) 相关的数据。

#### <a name="files-associated-with-the-teacher"></a>与教师关联的文件

IT 管理员可以使用内容搜索工具搜索教师文件 (*学生工作*、 *课堂文件* 或其他第一方集成文件) ，这些文件与教师在作业上分配给学生的作业和文件相关。 例如，管理员可以搜索组织中的所有 SharePoint 网站，并在搜索查询中使用教师的姓名、班级或作业名称来查找与 DSR 相关的数据。

### <a name="assignments-data-outside-of-sharepoint-document-libraries"></a>分配 SharePoint 文档库外部的数据

一些与工作分配相关的数据不会存储在类团队 SharePoint 网站中，这意味着无法通过内容搜索发现。 这包括：

- 来自教师的学生成绩和反馈
- 每个学生提交作业的文档列表
- 分配详细信息，如截止日期等。
- 第一方集成数据，如阅读进度段落或学生发音数据

对于此类数据，IT 管理员或数据所有者（例如教师）可能必须进入课堂团队中的作业，以查找与 DSR 相关的数据。 管理员可以将自己添加为类的所有者，并查看该类团队的所有分配。

>[!NOTE]
>如果学生不再是班级的一部分，则其数据可能仍显示在课堂中，因为 *不再注册*。 学生必须向租户管理员提供他们曾经参与过的此类类的列表。

### <a name="bulk-export-assignment-data-outside-of-sharepoint-document-libraries"></a>在 SharePoint 文档库外部批量导出分配数据

#### <a name="for-a-student"></a>对于学生

若要批量导出单个学生的数据，在将学生从其所属的班级中删除之前， [请运行脚本](/microsoft-365/education/deploy/configure-assignments-for-teams) 并提供该 ``userId``脚本。 如果已从网站中删除学生，管理员可以在运行脚本之前将学生添加回课堂，或者管理员可以提供``userId````classId``该学生曾经属于该学生的一部分。

将导出有关学生提交的数据。

#### <a name="for-a-teacher"></a>对于教师

批量导出作业数据对学生的工作方式相同，但教师有权访问的所有提交都将导出。

### <a name="bulk-delete-assignment-data-outside-of-sharepoint-document-libraries"></a>批量删除 SharePoint 文档库外部的分配数据

#### <a name="for-a-student"></a>对于学生

若要批量删除单个学生的数据，在将学生从其所属的班级中删除之前， [请运行脚本](/microsoft-365/education/deploy/configure-assignments-for-teams) 并提供该 ``userId``脚本。 如果已从网站中删除学生，管理员可以在运行脚本之前将学生添加回课堂，或者管理员可以提供``userId````classId``该学生曾经属于该学生的一部分。

提供一个 ``ClassId`` 允许管理员只从特定类中删除有关学生的信息。

#### <a name="for-a-teacher"></a>对于教师

由于教师的作业数据在全班共享，因此没有批量删除选项。 相反，管理员可以将自己添加到类中，转到应用并删除分配。

有关详细信息，请参阅 [为 Teams 配置分配](/microsoft-365/education/deploy/configure-assignments-for-teams)。

## <a name="removing-assignments-and-grades"></a>删除作业和成绩

还可以使用 Teams 策略删除特定用户或整个租户的分配和等级。

若要删除单个用户的分配和成绩，请转到 **Teams 管理员 中心** 并导航到 **Teams 应用>权限策略**，以创建新的应用权限策略定义。  创建新策略定义时，请将 **Microsoft 应用** 策略设置为 _阻止特定应用，并允许所有其他应用_ ，并将 **分配** 和 **成绩** 添加到被阻止的应用程序列表。 保存新策略定义后，将其分配给相应的用户。

若要删除整个租户的作业和成绩，请转到 **Teams 管理员 中心**，导航到 **Teams 应用>管理应用**，然后从应用程序列表中搜索和选择 **“分配** 和 **成绩**”。 将应用程序设置页中的状态设置更改为 _“已阻止_”。

## <a name="assignments-diagnostic-tool-for-users"></a>用户分配诊断工具

Microsoft 支持部门创建了一个工具，用于收集 Microsoft 工程团队的诊断数据，以调查与工作分配功能相关的问题。

可以在用户遇到问题的任意屏幕上的“分配”内部访问此工具。

若要在 Teams 中拉取诊断工具，用户可以：

- **在桌面和 Web 上：**
  - 选择 Ctrl+/
- **在移动设备上：**
  - 用两根手指触摸屏幕，旋转手指 45 度，或
  - 用三根手指点击屏幕 15 秒

诊断工具弹出后，用户将看到 Microsoft 技术支持部门可能需要的数据列表。

拉取的数据可能包括：

- 组 ID
- 租户 ID
- 会话 ID
- 分配 ID
- 提交 ID
- 用户 ID

此数据不会自动发送到 Microsoft。 用户需要将数据复制并粘贴到有关支持票证的 Microsoft 支持代理。

如果用户拉取诊断工具，然后将其关闭，则不会发送任何数据。

将数据发送到 Microsoft 支持代理时，会根据组织的 Microsoft 365 服务协议将其作为支持数据进行处理。

有关使用可与教师和学生共享的诊断工具的说明， [请参阅获取诊断数据以排查作业问题](https://support.microsoft.com/topic/b40793f5-dbae-4c8a-841a-6baa7f232e2e)。
