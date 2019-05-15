---
title: 使用 Microsoft 团队安装 Moodle 集成
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.date: 05/01/2019
ms.topic: article
ms.service: msteams
ms.reviewer: ''
search.appverid: MET150
description: 了解如何安装和配置 Microsoft 团队 Moodle 集成应用程序。
keywords: 团队 Moodle 应用程序集成插件
localization_priority: Normal
MS.collection: Teams_ITAdmin_Help
appliesto: Microsoft Teams
ms.openlocfilehash: 92259a9ef01232aaeca67089b5d654fe302f1224
ms.sourcegitcommit: 9a99be1365df439f9443f31240aa5311782458df
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2019
ms.locfileid: "34055359"
---
# <a name="install-moodle-integration-with-microsoft-teams"></a>使用 Microsoft 团队安装 Moodle 集成

> [!VIDEO https://www.youtube.com/embed/OHlPt22nKoE]

与 Microsoft 团队现在集成[Moodle](https://moodle.org/)，最受欢迎且打开源学习管理系统 (LMS) 在世界 ！ 此集成有助于教师和教师周围 Moodle 课程协作、 提问有关其薪等级和分配，并保持与通知-团队中的所有更新 ！

为了方便地建立这种集成的 IT 管理员，我们已更新 Office 365 Moodle 插件我们打开源具有以下功能：

- 自动注册 Moodle 服务器与 Azure AD 的
- 一次单击部署到 Azure 您 Moodle 助理自动程序的
- 自动设置的团队和自动同步所有的团队注册或选择 Moodle 课程
- 自动安装 Moodle 选项卡和 Moodle 助手 bot 到每个同步工作组 （即将推出）
- Moodle 应用程序 （即将推出） 私有团队应用程序存储到的一键式发布

## <a name="prerequisites"></a>先决条件

安装和配置此应用程序，您将需要：

- Moodle 管理员凭据
- Azure AD 管理员凭据
- 您可以创建新资源中的 Azure 订阅

## <a name="step-1-install-the-office-365-moodle-plugin"></a>步骤 1： 安装 Office 365 Moodle 插件

> [!VIDEO https://www.youtube.com/embed/SETEC5nzMgk]

中的 Microsoft 团队 Moodle 集成是由开源[Office 365 Moodle 插件](https://github.com/Microsoft/o365-moodle)供电。 Moodle 服务器上安装该插件：

1. 下载[Office 365 插件设置](https://moodle.org/plugins/pluginversions.php?plugin=local_o365)并将其保存在本地计算机上。 您需要使用 3.5 或更高版本。
2. 登录到 Moodle 服务器作为管理员，并从左侧的导航窗格中选择**网站管理**。
3. 选择**插件**选项卡，然后单击**安装插件**。
4. 在**安装插件 ZIP 文件中的**部分单击**选择文件**按钮。
5. 左侧的导航窗格中，选择**上载文件**选项，浏览到上方，下载的文件，然后单击**将此文件上载**。
6. 在左侧的导航窗格中，再次以返回到您的管理员仪表板中选择**网站管理**选项。 向下**本地插件**滚动并单击**Microsoft Office 365 集成**链接。 保留此配置页上的一个单独的浏览器选项卡中打开： 您将使用其此过程的其余。

您可以找到有关如何安装 Moodle 插件[Moodle 文档](https://docs.moodle.org/34/en/Installing_plugins)中的详细信息。

> [!IMPORTANT]
> 保留您的 Office 365 Moodle 插件配置页上的一个单独的浏览器选项卡中打开： 您将返回到此组在此过程中的所有页面。

不会已经 Moodle 网站？ 您可能想要签出我们 Moodle 上 Azure [repo](https://github.com/azure/moodle)您可以快速部署 Azure 上的 Moodle 实例和其自定义您的需要。

## <a name="step-2-configure-the-connection-between-the-office-365-plugin-and-azure-active-directory"></a>步骤 2： 配置 Office 365 插件和 Azure Active Directory 之间的连接

> [!VIDEO https://www.youtube.com/embed/FpGEezaJ3SA]

接下来，您将需要注册 Moodle 为 Azure Active Directory (Azure AD) 中的应用程序。 我们提供了可帮助您完成此过程的 PowerShell 脚本。 PowerShell 脚本设置新的 Azure AD 应用程序的 Office 365 租户，将使用 Office 365 Moodle 插件。 此脚本将设置 O365 租户的应用程序、 设置所有必需回复 Url 和权限设置的应用程序，并返回 AppID 和密钥。 您可以使用生成的 AppID 和键在 O365 Moodle 插件安装程序页面中配置与 Azure AD Moodle 服务器。 如果您希望看到自动 PowerShell 脚本的详细手动步骤，您可以找到这些完整[插件的文档](https://docs.moodle.org/34/en/Office365#Register_your_Moodle_instance_as_an_Application)中。

1. 在 Microsoft Office 365 集成插件页上，选择**安装**选项卡。
2. 单击**下载 PowerShell 脚本**按钮，并将脚本保存在本地计算机上。
3. 您需要准备 ZIP 文件中的 PowerShell 脚本。 若要此操作：
    1. 下载并解压缩 Moodle-AzureAD Powershell.zip 文件。
    2. 打开解压缩的文件夹。
    3. 右键单击 Moodle-AzureAD Script.ps1 文件，然后选择**属性**。
    4. 在属性窗口的**常规**选项卡上，选中在底部的**安全**属性旁边的**取消阻止**框。
    5. 单击“**确定**”。
    6. 将复制解压缩的文件夹的目录的路径。
4. 接下来，您将以管理员身份运行 PowerShell:
    1. 单击“开始”。
    2. 类型**PowerShell**。
    3. 右键单击**Windows PowerShell**。
    4. 单击**以管理员身份运行**。
5. 键入以下命令以导航到解压缩目录`cd ...\...\Moodle-AzureAD-Powershell`其中`...\...`是目录的路径。
6. 执行 PowerShell 脚本：
    1. 输入`Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser`。
    2. 输入`.\Moodle-AzureAD-Script.ps1`。
    3. 登录到您在弹出窗口的 O365 管理员帐户。
    4. 输入 Azure AD 应用程序 （例如， **Moodle/Moodle 插件**） 的名称。
    5. 输入 Moodle 服务器的 URL。
    6. 复制的**应用程序 ID**和**应用程序键**生成脚本，并将其保存。
7. 接下来，您需要将 ID 和密钥添加到 Office 365 Moodle 插件。 返回到插件管理页 (**网站管理** > **插件** > **Microsoft Office 365 集成**)。
8. 在**安装**选项卡中，添加**应用程序 ID**和**应用程序密钥**之前，复制，然后单击**保存所做更改**。
9. 一次页面将刷新，您应看到调用**选择连接方法**的新部分。 单击标记为**默认值**的复选框，然后单击**保存所做更改**。
10. 一次页面将刷新，您将看到新的部分调用**管理 consent & 其他信息**。
    1. 单击**提供管理 Consent**链接，输入 Office3 365 全局管理员凭据，，然后单击**接受**授予权限。
    2. **Azure AD 租户**字段旁边，单击**检测**按钮。
    3. **OneDrive for Business URL**旁边单击**检测**按钮。
    4. 一旦填充字段，单击**保存更改**按钮。
11. 单击**更新**按钮，以确认安装，然后单击**保存所做更改**。
12. 接下来，您将需要同步 Moodle 服务器和 Azure AD 之间的用户。 根据您的环境，您可以在此阶段选择不同的选项。 请注意，此处设置的配置将与 （通常每天运行一次） 以使任何内容同步每个 Moodle cron 一起运行。若要开始：
    1. 切换到**Sync 设置选项卡**。
    2. 在**同步与 Azure AD 的用户**部分中，选择适用于您的环境对应的复选框。 通常，应选择至少：
        - **在 Azure AD 帐户在 Moodle 中创建的用户**
        - **Azure AD 中更新 Moodle 中的用户的所有帐户**
    3. 在**用户创建限制**部分中，您可以设置筛选器以限制将同步到 Moodle 的 Azure AD 用户。
    4. **用户域映射**部分将允许您自定义 Moodle 用户配置文件字段映射到 Azure AD。
    5. 在**团队同步**部分您可以选择自动创建组 （即，团队） 为部分或全部您现有的 Moodle 课程。
13. 若要验证 cron 作业 （并手动运行它们，如果想要对第一个域），请单击**同步与 Azure AD 的用户**部分中的**计划任务管理页**链接。 这会将您导引到**任务计划**页。
    1. 向下滚动和查找作业**同步用户与 Azure AD**作业，然后单击**立即运行**。
    2. 如果您选择创建基于现有的课程的组，您还可以运行**Office 365 中的创建用户组**作业。
14. 返回到插件管理页 (**网站管理** > **插件** > **Microsoft Office 365 集成**)，然后选择**工作组设置**页。 您需要配置某些安全设置，以启用团队应用程序集成。
    1. 要启用 OpenID 连接，请单击**管理身份验证**链接，然后单击**OpenId 连接**行上的眼睛图标，如果它变暗。
    2. 若要启用嵌入的框架，单击**HTTP 安全**链接，然后选择**允许框架嵌入**旁边的复选框。
    3. 启用 web 服务 （这将启用 Moodle API 功能）。 单击**高级功能**链接，并确保选择**启用 web 服务**旁边的复选框。
    4. 启用外部 Office 365 服务。 单击**外部服务**链接，然后：
        1. 在**Moodle Office 365 Webservices**行上，单击**编辑**。
        2. 选择**启用**，旁边的复选框，然后单击**保存更改**
    5. 最后，您需要编辑您允许用户创建 web 服务令牌的身份验证的用户权限。 单击**编辑角色经过身份验证用户**链接。 向下滚动和找到的**创建 web 服务令牌**功能，然后选择**允许**复选框。

## <a name="step-3-deploy-the-moodle-assistant-bot-to-azure"></a>步骤 3： 部署到 Azure Moodle 助理自动程序

> [!VIDEO https://www.youtube.com/embed/gbkJxf8FlfY]

教师和学生回答问题有关其课程、 工作分配、 薪等级和 Moodle 中的其他信息，可帮助 Microsoft 团队免费 Moodle 助手 Bot。 Bot 还 Moodle 将通知发送到学生和教师团队中右。 此自动程序是由 Microsoft 维护的开放源代码项目，并且[GitHub 上可用](https://github.com/microsoft/Moodle-Teams-Bot)。

> [!NOTE]
. 在此部分中，您将部署资源 Azure 订阅，并将使用的免费层配置的所有资源。 根据您自动程序的使用情况，您可能需要扩展这些资源。 如果您想要仅使用不自动程序的情况下的 Moodle 选项卡，则跳到[步骤 4](#step-4-deploy-your-microsoft-teams-app)。

### <a name="moodle-bot-information-flow"></a>Moodle bot 信息流

若要安装自动程序，您将需要在[Microsoft Identity 平台](https://identity.microsoft.com/Landing)上注册它。 这样，您自动程序进行身份验证与您的 Microsoft 终结点。 若要注册您自动程序：

1. 返回到插件管理页 (**网站管理** > **插件** > **Microsoft Office 365 集成**)，然后选择**工作组设置**选项卡。
2. 单击**Microsoft 应用程序注册门户**链接和登录您的 Microsoft id。
3. 输入应用程序 (例如，MoodleBot) 的名称，然后单击**创建**按钮。
4. 复制的**应用程序 ID** ，并将其粘贴到**工作组设置**页上的**自动程序应用程序 ID**字段。
5. 单击**生成新密码**按钮。 复制生成的密码并将其粘贴到**工作组设置**页上的**自动程序应用程序密码**字段。
6. 滚动到窗体的底部，单击**保存更改**。

既然已生成您的应用程序 ID 和密码，就可以部署到 Azure 您自动程序。 单击**部署到 Azure**按钮，并填写表单的必要信息 （自动程序 ID 和密码是否在**工作组设置**页上和**设置**页上的 Azure 信息是）。 填写表单后，单击接受条款和条件，然后单击**购买**按钮 （所有 Azure 资源部署到的免费层） 复选框。

资源已完成后部署到 Azure，您将需要使用其消息的终结点配置 Office 365 Moodle 插件。 首先，您需要从您 bot Azure 中获取终结点。 若要此操作：

1. 如果不已签名，登录到[Azure 门户](https://portal.azure.com)。
2. 在左窗格中，选择**资源组**。
3. 从列表中，选择部署您自动程序时的您只需使用 （或创建） 的资源组。
4. 从组中的资源的列表中选择**WebApp Bot**资源。
5. 从**概述**部分中复制**消息终结点**。
6. 在 Moodle，打开您的 Office 365 Moodle 插件**工作组设置**页。
7. 在**自动程序终结点**字段中，粘贴您刚复制的 URL 和更改为*webhook*的单词*的邮件*。 URL 现在应如下所示： `https://botname.azurewebsites.net/api/webhook`。
8. 单击**保存更改**。
9. 后所做的更改将保存，返回到**工作组设置**选项卡，单击**下载清单文件**按钮和 （将在下一步中使用它） 在计算机上保存清单程序包。

## <a name="step-4-deploy-your-microsoft-teams-app"></a>步骤 4： 部署 Microsoft 团队的应用程序

> [!VIDEO https://www.youtube.com/embed/2rMb7gtM_ZM]

现在，您具有部署 Azure 中的您自动程序，并将其与 Moodle 服务器配置为，就可以部署 Microsoft 团队的应用程序。 若要执行此操作将加载在上一步 Office 365 Moodle 插件**工作组设置**页从您下载的清单文件。

您可以安装应用程序之前，您需要确保已启用外部应用程序和应用程序的 sideloading。 若要执行此操作，请按照[下列步骤](https://docs.microsoft.com/en-us/MicrosoftTeams/admin-settings)。 一次已确保已启用外部应用程序，请按照以下步骤来部署您的应用程序。

1. 打开 Microsoft 团队。
2. 单击左下方的导航栏上的**Store**图标。
3. 单击从选项列表中的**上载自定义应用程序**链接。 
   > [!NOTE]
   > 如果您以全局管理员身份登录，您必须将应用程序上载到组织的应用程序商店; 的选项否则您只将能够加载应用程序后团队 (*sideloading*) 的一部分。
4. 选择您以前，下载的 manifest.zip 包，然后单击**保存**。 如果尚未尚未下载清单包，您可以从 Moodle 插件配置页的**工作组设置**选项卡来完成操作。

既然您已经安装该应用程序，您可以将选项卡添加到有权访问任何通道。 若要执行此操作，导航到该频道，单击**+** 符号，并从列表中选择您的应用程序。 按照提示完成向通道添加您 Moodle 课程的选项卡。

就是这样！ 您和您的团队，现在即可开始使用您直接从 Microsoft 团队的 Moodle 课程。

要与我们共享任何功能请求或提供反馈，请访问我们的[用户语音页](https://microsoftteams.uservoice.com/forums/916759-moodle)。