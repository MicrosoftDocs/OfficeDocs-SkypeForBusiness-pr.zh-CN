---
title: 安装与 Microsoft 团队的 Moodle 集成
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: ''
search.appverid: MET150
description: 了解如何安装和配置 Microsoft 团队的 Moodle 集成应用
keywords: Moodle 应用集成插件的团队
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3a3ee51fdbbda7c3d49ac5a7b2a65b977f8fb245
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/03/2020
ms.locfileid: "43137132"
---
# <a name="installing-the-moodle-integration-with-microsoft-teams"></a>安装与 Microsoft 团队的 Moodle 集成

> [!VIDEO https://www.youtube.com/embed/OHlPt22nKoE]

[Moodle](https://moodle.org/)是世界上最常用和开放源代码的学习管理系统（LMS）现已与 Microsoft 团队集成！ 此集成可帮助教师和教师在 Moodle 课程中进行协作，询问有关其成绩和作业的问题，并在团队内部及时更新通知！

为了帮助 IT 管理员轻松地设置此集成，我们已使用以下功能更新了我们的开放源代码 Office 365 Moodle 插件：

* 通过 Azure AD 自动注册 Moodle 服务器。
* 将 Moodle 助手机器人的一次单击部署到 Azure。
* 自动预配团队并自动同步团队注册的所有或选择 Moodle 课程。
* 将 Moodle 选项卡和 Moodle 助手机器人自动安装到每个同步团队。 （即将推出）
* 单击 "将 Moodle 应用发布到专用团队应用商店"。 （即将推出）

若要了解有关此集成提供的功能的详细信息，请访问[此处](https://education.microsoft.com/courses-and-resources/resources/microsoft-teams-moodle)。

## <a name="prerequisites"></a>先决条件

为了安装和配置此应用程序，你需要：

1. Moodle 管理员凭据
2. Azure AD 管理员凭据
3. Azure 订阅可在中创建新资源

## <a name="step-1-install-the-office-365-moodle-plugin"></a>步骤1：安装 Office 365 Moodle 插件

> [!VIDEO https://www.youtube.com/embed/SETEC5nzMgk]

Microsoft 团队中的 Moodle 集成由开放源[Office 365 Moodle 插件设置](https://github.com/Microsoft/o365-moodle)。 要在 Moodle server 中安装插件，请执行以下操作：

1. 首先，下载[Office 365 插件集](https://moodle.org/plugins/pluginversions.php?plugin=local_o365)并将其保存到本地计算机。 您需要使用版本3.5 或更高版本。
    * 安装 local_o365 插件还将安装[auth_oidc](https://moodle.org/plugins/auth_oidc)和[boost_o365Teams](https://moodle.org/plugins/pluginversions.php?plugin=theme_boost_o365teams)插件。
1. 以管理员身份登录到 Moodle 服务器，然后从左侧导航面板中选择 "**网站管理**"。
1. 选择 "**插件**" 选项卡，然后单击 "**安装插件**"。
1. 在 " **ZIP 文件安装插件**" 部分下，单击 "**选择文件**" 按钮。
1. 从左侧导航中选择 "**上传文件**" 选项，通过浏览找到上面下载的文件，然后单击 "**上载此文件**"。
1. 再次从左侧导航面板中选择 "**网站管理**" 选项，返回到您的 "管理员" 仪表板。 向下滚动到**本地插件**，然后单击 " **Microsoft Office 365 集成**" 链接。 将此配置页在单独的浏览器选项卡中打开，因为您将在整个过程的其余部分中使用它。

你可以在[Moodle 文档](https://docs.moodle.org/34/en/Installing_plugins)中找到有关如何安装 Moodle 插件的详细信息。

**重要说明：** 保留 Office 365 的 Moodle 插件配置页在单独的浏览器选项卡中打开，因为你将在整个过程中返回到此页面集。

*尚未有 Moodle 网站？* 你可能希望查看 Azure 存储库上的 Moodle [，你](https://github.com/azure/moodle)可以在其中快速部署 azure 上的 Moodle 实例并根据你的需要对其进行自定义。

## <a name="step-2-configure-the-connection-between-the-office-365-plugin-and-azure-active-directory"></a>步骤2：配置 Office 365 插件与 Azure Active Directory 之间的连接

> [!VIDEO https://www.youtube.com/embed/FpGEezaJ3SA]

接下来，你需要在 Azure Active Directory 中将 Moodle 注册为应用程序。 我们提供了一个 PowerShell 脚本来帮助你完成此过程。 PowerShell 脚本为 Office 365 租户预配新的 Azure AD 应用程序，该应用程序将由 Office 365 Moodle 插件使用。 该脚本将为 O365 租户设置应用，为预配的应用设置所有所需的答复 Url 和权限，并返回 AppID 和 Key。 你可以在 O365 Moodle 插件设置页面中使用生成的 AppID 和 Key，使用 Azure AD 配置 Moodle 服务器。 如果你想要查看 PowerShell 脚本自动化的详细手动步骤，你可以在插件的完整[文档](https://docs.moodle.org/34/en/Office365#Register_your_Moodle_instance_as_an_Application)中找到它们。

### <a name="moodle-tab-for-microsoft-teams-information-flow"></a>Microsoft 团队信息流的 Moodle 选项卡

<img width="530px" src="media/MoodleTabInformationFlow.png" alt="Illustration of Moodle tab for Microsoft Teams information flow" title="Microsoft 团队信息流的 Moodle 选项卡的插图" />

1. 从 "Microsoft Office 365 集成插件" 页面 slect "**设置**" 选项卡。
1. 单击 "**下载 PowerShell 脚本**" 按钮并将其保存到本地计算机。
1. 你需要从 ZIP 文件准备 PowerShell 脚本。 为此：
    * 下载并解压缩该`Moodle-AzureAD-Powershell.zip`文件。
    * 打开提取的文件夹。
    * 右键单击该`Moodle-AzureAD-Script.ps1`文件，然后选择 "**属性**"。
    * 在 "属性" 窗口的 "**常规**" 选项卡`Unblock`下，选中底部的 "**安全**" 属性旁边的框。
    * 单击“**确定**”。
    * 复制提取的文件夹的目录路径。
1. 接下来，你将以管理员身份运行 PowerShell：
    * 单击“开始”。
    * 键入 PowerShell。
    * 右键单击 "Windows PowerShell"。
    * 单击 "以管理员身份运行"。
1. 通过键入`cd ...\...\Moodle-AzureAD-Powershell`目录路径的位置`...\...` ，导航到解压缩目录。
1. 通过以下方式执行 PowerShell 脚本：
    * Enter `Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser`。
    * Enter `.\Moodle-AzureAD-Script.ps1`。
    * 在弹出窗口中登录到 O365 管理员帐户。
    * 输入 Azure AD 应用程序的名称（例如 Moodle/Moodle 插件）。
    * 输入 Moodle 服务器的 URL。
    * 复制脚本生成的**应用程序 ID**和**应用程序密钥**并保存。
1. 接下来，你需要将 Id 和密钥添加到 Office 365 Moodle 插件。 返回到插件管理页面（网站管理 > 插件 > Microsoft Office 365 集成）。
1. 在 "**设置**" 选项卡上，添加您之前复制的**应用程序 Id**和**应用程序键**，然后单击 "**保存更改**"。
1. 页面刷新后，您现在应该可以看到一个新分区**选择连接方法**。 单击标记为 "**默认**" 的复选框，然后再次单击 "**保存更改**"。
1. 页面刷新后，您将看到另一个新部分**管理员同意 & 其他信息**。
    * 单击 "**提供管理员同意**" 链接，输入您的 Office3 365 全局管理员凭据，然后按 "**接受**" 授予权限。
    * 在 " **AZURE AD 租户**" 字段旁边，单击 "**检测**" 按钮。
    * 在**OneDrive for BUSINESS URL**旁边，单击 "**检测**" 按钮。
    * 填写域后，再次单击 "**保存更改**" 按钮。
1. 单击 "**更新**" 按钮以验证安装，然后单击 "**保存更改**"。
1. 接下来，你需要在 Moodle server 和 Azure Active Directory 之间同步用户。 根据你的环境，你可以在此阶段中选择不同的选项。 请注意，你在此处设置的配置将与每个 Moodle cron 运行（通常是每天一次）一起运行，以使所有内容保持同步。要开始使用，请执行以下操作：
    * 切换到 "**同步设置" 选项卡**
    * 在 "将**用户与 AZURE AD 同步**" 部分中，选择适用于你的环境的复选框。 通常情况下，您至少要选择：
        * 在 Moodle 中为 Azure AD 中的用户创建帐户
        * 在 Moodle for Azure AD 中的用户更新所有帐户
    * 在 "**用户创建限制**" 部分中，你可以设置筛选器以限制将同步到 Moodle 的 Azure AD 用户。
    * **用户字段映射**部分将允许你将 Azure AD 自定义为 Moodle 用户配置文件字段映射。
    * 在 "**团队同步**" 部分中，你可以选择为你的现有 Moodle 课程自动创建组（如团队）。
1. 若要验证 cron 作业（并在首次运行时手动运行它们），请单击 "**同步用户和 AZURE AD** " 部分中的 "**计划任务管理页面**" 链接。 这将转到 "**计划任务**" 页面。
    * 向下滚动并找到 "**与 AZURE AD 作业同步用户**"，然后单击 "**立即运行**"。
    * 如果您选择基于现有课程创建组，也可以**在 Office 365 作业中运行 "创建用户组**"。
1. 返回到插件管理页面（网站管理 > 插件 > Microsoft Office 365 集成），然后选择 "**团队设置**" 页面。 你需要配置一些安全设置以启用团队应用集成。
    * 若要启用 OpenID Connect，请单击 "**管理身份验证**" 链接，然后在**OpenID 连接线**上单击 "眼睛" 图标（如果它呈灰色）。
    * 接下来，你需要启用框架嵌入。 单击 " **HTTP 安全**" 链接，然后单击 "**允许框架嵌入**" 旁边的复选框。
    * 下一步是启用将启用 Moodle API 功能的 web 服务。 单击 "**高级功能**" 链接，然后确保选中 "**启用 web 服务**" 旁边的复选框。
    * 最后，你需要启用 Office 365 的外部服务。 单击 "**外部服务**" 链接，然后执行以下操作：
        * 单击 " **Moodle Office 365 Webservices** " 行上的 "**编辑**"。
        * 标记 "**启用**" 旁边的复选框，然后单击 "**保存更改**"
    * 接下来，你需要编辑已验证身份的用户权限，以允许他们创建 web 服务令牌。 单击**编辑角色的 "经过身份验证的用户"** 链接。 向下滚动并找到 "**创建 web 服务标记**" 功能，并标记 "**允许**" 复选框。

## <a name="step-3-deploy-the-moodle-assistant-bot-to-azure"></a>步骤3：将 Moodle 助理机器人部署到 Azure

> [!VIDEO https://www.youtube.com/embed/gbkJxf8FlfY]

Microsoft 团队的免费 Moodle 助理机器人可帮助教师和学生在 Moodle 中解答有关其课程、作业、成绩和其他信息的问题。 机器人还会向团队中的学生和教师发送 Moodle 通知。 此 bot 是由 Microsoft 维护的开源项目，[在 GitHub 上提供](https://github.com/microsoft/Moodle-Teams-Bot)。

> [!NOTE]
> 在此部分中，你会将资源部署到你的 Azure 订阅，并且将使用**免费**的层配置所有资源。 根据你的 bot 使用情况，你可能需要缩放这些资源。
> 如果只想在没有机器人的情况下使用 Moodle 选项卡，请跳到[步骤 4](#step-4-deploy-your-microsoft-teams-app)。

### <a name="moodle-bot-information-flow"></a>Moodle 机器人信息流

<img width="530px" src="media/MoodleBotInformationFlow.png" alt="llustration of Moodle bot for Microsoft Teams information flow" title="Microsoft 团队信息流的 Moodle bot 的插图" />


若要安装机器人，首先需要在[Microsoft Identity 平台](https://identity.microsoft.com/Landing)上注册它。 这使你的 Bot 能够针对你的 Microsoft 终结点进行身份验证。 要注册你的 bot，请执行以下操作：

1. 返回到插件管理页面（网站管理 > 插件 > Microsoft Office 365 集成），然后选择 "**团队设置**" 选项卡。
1. 单击 " **Microsoft 应用程序注册门户**" 链接，并通过您的 microsoft Id 登录。
1. 输入你的应用的名称（例如 MoodleBot），然后单击 "**创建**" 按钮。
1. 复制**应用程序 Id**并将其粘贴到 "**团队设置**" 页面上的 " **Bot 应用程序 id** " 字段中。
1. 单击 "**生成新密码**" 按钮。 复制生成的密码，并将其粘贴到 "**团队设置**" 页面上的 " **Bot 应用程序密码**" 字段中。
1. 滚动到窗体底部，然后单击 "**保存更改**"。

既然你已生成你的应用程序 Id 和密码，现在是将机器人部署到 Azure 的时候了。 单击 "**部署到 Azure** " 按钮，并填写包含必要信息的表单（Bot 应用 Id、Bot 应用程序密码和 Moodle 机密位于 "**团队设置**" 页面上，Azure 信息位于 "**设置**" 页面上）。 填写完表单后，单击复选框以接受条款和条件，然后单击 "**购买**" 按钮（所有 Azure 资源都部署到免费层）。

将资源部署到 Azure 后，你需要将 Office 365 Moodle 插件配置为其消息传递终结点。 首先，你需要在 Azure 中从你的 Bot 获取终结点。 为此，请执行以下操作：

1. 如果尚未登录，请登录到[Azure 门户](https://portal.azure.com)。
2. 在左窗格中，选择 "**资源组**"。
3. 从列表中选择在部署你的 Bot 时刚刚使用（或创建）的资源组。
4. 从组资源列表中选择 " **WebApp Bot**资源"。
5. 从 "**概述**" 部分复制**消息终结点**。
6. 在 Moodle 中，打开 Office 365 Moodle 插件的**团队设置**页面。
7. 在 "**机器人终结点**" 字段中，粘贴您刚刚复制的 URL，并将 word*消息*更改为*webhook*。 该 URL 现在应如下所示`https://botname.azurewebsites.net/api/webhook`
8. 单击 "**保存更改**"
9. 保存更改后，返回到 "**团队设置**" 选项卡，单击 "**下载清单文件**" 按钮并将清单程序包保存到您的计算机上（将在下一节中使用）。

## <a name="step-4-deploy-your-microsoft-teams-app"></a>步骤4：部署 Microsoft 团队应用

> [!VIDEO https://www.youtube.com/embed/2rMb7gtM_ZM]

现在，你已将机器人部署到 Azure 并配置为与 Moodle 服务器通话，现在是部署 Microsoft 团队应用的时候了。 若要执行此操作，你将从上一步中的 Office 365 Moodle 插件团队设置页面加载下载的清单文件。

在你可以安装应用之前，你需要确保已启用应用的外部应用和旁加载。 若要执行此操作，您可以执行[以下步骤](https://docs.microsoft.com/MicrosoftTeams/admin-settings)。 确保已启用外部应用后，你可以按照以下步骤部署你的应用。

1. 打开 Microsoft 团队。
2. 单击导航栏左下角的 "**应用商店**" 图标。
3. 从选项列表中单击 "**上载自定义应用程序**" 链接。 *注意：* 如果你作为全局管理员登录，你可以选择将应用上载到你的组织的应用商店，否则你将只能为你所属的团队加载应用（"旁加载"）。
4. 选择之前`manifest.zip`下载的程序包，然后单击 "**保存**"。 如果您尚未下载清单程序包，则可以从 Moodle 中的 "插件配置" 页面的 "**团队设置**" 选项卡执行此操作。

现在已安装应用，你可以将该选项卡添加到你有权访问的任何频道。 若要执行此操作，请导航到该**+** 通道，单击该符号，然后从列表中选择你的应用。 按照提示完成将 Moodle 课程选项卡添加到频道。

就是这样！ 您和您的团队现在可以直接从 Microsoft 团队开始处理 Moodle 课程。

若要与我们共享任何功能请求或反馈，请访问我们的[用户语音页面](https://microsoftteams.uservoice.com/forums/916759-moodle)。