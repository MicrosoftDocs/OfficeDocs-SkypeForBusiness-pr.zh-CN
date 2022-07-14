---
title: 安装 Moodle 与 Microsoft Teams 的集成
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: ''
search.appverid: MET150
description: 了解如何为 Microsoft Teams 安装和配置 Moodle 开源学习管理系统 (LMS) 应用。
keywords: Teams Moodle 应用集成插件
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
ms.custom:
- seo-marvel-apr2020
- seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: f7f0078be9f9077966fbba1a91fd569e1c4e11ec
ms.sourcegitcommit: 0dda332951df3b946097d90a4923eb191fd86b4c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/14/2022
ms.locfileid: "66789537"
---
# <a name="installing-the-moodle-integration-with-microsoft-teams"></a>安装 Moodle 与 Microsoft Teams 的集成

> [!VIDEO https://www.youtube.com/embed/OHlPt22nKoE]

[Moodle](https://moodle.org/) 是全球最受欢迎的开放源代码学习管理系统 (LMS) ，现已与 Microsoft Teams 集成！ 此集成可帮助教师和学生围绕 Moodle 课程进行协作，询问有关其成绩和作业的问题，并随时更新通知 - 就在 Teams 中！

为了帮助 IT 管理员轻松设置此集成，我们更新了具有以下功能的开源 Moodle 插件：

* 将 Moodle 服务器自动注册到 Azure AD。
* 将 Moodle 助手机器人一键式部署到 Azure。
* 为所有或选择 Moodle 课程自动预配团队和自动同步团队注册。
* 将 Moodle 选项卡和 Moodle 助手机器人自动安装到每个同步团队中。  (即将) 
* 单击将 Moodle 应用发布到专用 Teams App Store。  (即将) 

若要详细了解此集成提供的功能，请 [参阅安装 Moodle 与 Microsoft Teams 的集成](/microsoftteams/platform/resources/moodleinstructions)。

## <a name="prerequisites"></a>先决条件

若要安装和配置此应用程序，需要：

1. Moodle 管理员凭据
2. Azure AD 管理员凭据
3. 可在其中创建新资源的 Azure 订阅

## <a name="step-1-install-the-moodle-plugin"></a>步骤 1：安装 Moodle 插件

> [!VIDEO https://www.youtube.com/embed/SETEC5nzMgk]

Microsoft Teams 中的 Moodle 集成由 开放源代码 [Moodle 插件集](https://github.com/Microsoft/o365-moodle)提供支持。 若要在 Moodle 服务器中安装插件，请执行以下操作：

1. 首先，下载 [Moodle 插件集](https://moodle.org/plugins/pluginversions.php?plugin=local_o365) 并将其保存到本地计算机。 需要使用版本 3.5 或更高版本。
    * 安装local_o365插件还将安装 [auth_oidc](https://moodle.org/plugins/auth_oidc) 和 [boost_o365Teams](https://moodle.org/plugins/pluginversions.php?plugin=theme_boost_o365teams) 插件。
1. 以管理员身份登录到 Moodle 服务器，然后从左侧导航面板中选择 **“站点管理** ”。
1. 选择 **“插件** ”选项卡，然后单击 **“安装插件**”。
1. 在 **ZIP 文件部分的“安装插件** ”下，单击“ **选择文件** ”按钮。
1. 从左侧导航栏中选择“ **上传文件** ”选项，浏览上面下载的文件，然后单击 **“上传此文件**”。
1. 再次从左侧导航面板中选择 **“站点管理** ”选项以返回到管理员仪表板。 向下滚动到 **本地插件**，然后单击 **Microsoft Office 365集成** 链接。 将此配置页保持在单独的浏览器选项卡中打开，因为在此过程中的其余部分将使用它。

可以在 [Moodle 文档](https://docs.moodle.org/34/en/Installing_plugins)中找到有关如何安装 Moodle 插件的详细信息。

**重要说明：** 让 Microsoft 365 或 Office 365 Moodle 插件配置页在单独的浏览器选项卡中打开，因为在整个过程中，你将返回到这组页面。

*没有穆德尔网站吗？* 你可能想要查看 Azure 存储 [库](https://github.com/azure/moodle) 上的 Moodle，可在 Azure 上快速部署 Moodle 实例并根据需要自定义它。

## <a name="step-2-configure-the-connection-between-the-microsoft-365-or-office-365-plugin-and-azure-active-directory"></a>步骤 2：配置 Microsoft 365 或Office 365插件与 Azure Active Directory 之间的连接

> [!VIDEO https://www.youtube.com/embed/FpGEezaJ3SA]

接下来，需要在 Azure Active Directory 中将 Moodle 注册为应用程序。 我们提供了一个 PowerShell 脚本来帮助你完成此过程。 PowerShell 脚本为 Microsoft 365 或Office 365组织预配新的 Azure AD 应用程序，该应用程序将由 Moodle 插件使用。 该脚本将为 Microsoft 365 或Office 365租户预配应用，为预配的应用设置所有必需的回复 URL 和权限，并返回 AppID 和密钥。 可以使用 Moodle 插件安装页中生成的 AppID 和密钥，使用 Azure AD 配置 Moodle 服务器。 如果想要查看 PowerShell 脚本自动执行的详细手动步骤，可以在 [插件的完整文档](https://docs.moodle.org/34/en/Office365#Register_your_Moodle_instance_as_an_Application)中找到这些步骤。

### <a name="moodle-tab-for-microsoft-teams-information-flow"></a>Microsoft Teams 信息流的 Moodle 选项卡

<img width="530px" src="media/MoodleTabInformationFlow.png" alt="Illustration of Moodle tab for Microsoft Teams information flow" title="Microsoft Teams 信息流的 Moodle 选项卡插图" />

1. 在 Microsoft 365 或Office 365集成插件页中，选择 **“设置”** 选项卡。
1. 单击 **“下载 PowerShell 脚本”** 按钮并将其保存到本地计算机。
1. 需要从 ZIP 文件准备 PowerShell 脚本。 为此：
    * 下载并提取 `Moodle-AzureAD-Powershell.zip` 文件。
    * 打开提取的文件夹。
    * 右键单击该 `Moodle-AzureAD-Script.ps1` 文件并选择 **“属性**”。
    * 在属性窗口的“**常规**”选项卡下，选中`Unblock`底部 **安全** 属性旁边的框。
    * 单击“**确定**”。
    * 复制提取的文件夹的目录路径。
1. 接下来，你将以管理员身份运行 PowerShell：
    * 单击“开始”。
    * 键入 PowerShell。
    * 右键单击Windows PowerShell。
    * 单击“以管理员身份运行”。
1. 通过键入 `cd ...\...\Moodle-AzureAD-Powershell` 目录路径的位置 `...\...` ，导航到解压缩的目录。
1. 通过以下方式执行 PowerShell 脚本：
    * 输入 `Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser`。
    * 输入 `.\Moodle-AzureAD-Script.ps1`。
    * 在弹出窗口中登录到 Microsoft 365 或Office 365管理员帐户。
    * 输入 Azure AD 应用程序 (Ex 的名称。 Moodle/Moodle 插件) 。
    * 输入 Moodle 服务器的 URL。
    * 复制脚本生成的应用程序 **ID** 和 **应用程序密钥** 并保存它们。
1. 接下来，需要将 ID 和密钥添加到 Moodle 插件。 返回到站点管理>插件> Microsoft 365 集成)  (插件管理页。
1. 在 **“设置”** 选项卡上添加之前复制的应用程序 **ID** 和 **应用程序密钥** ，然后单击 **“保存更改**”。
1. 页面刷新后，现在应会看到新的“ **选择连接方法**”部分。 单击标记为 **“默认** ”的复选框，然后再次单击 **“保存更改** ”。
1. 页面刷新后，你将看到另一个新部分 **管理员同意&其他信息**。
    * 单击 **“提供管理员许可**”链接，输入 Microsoft 365 或Office 365全局管理员凭据，然后 **接受** 以授予权限。
    * 在 **Azure AD 租户** 字段旁边，单击“ **检测”** 按钮。
    * 在 **OneDrive for Business URL** 旁边，单击“**检测”** 按钮。
    * 填充字段后，再次单击 **“保存更改** ”按钮。
1. 单击 **“更新”** 按钮验证安装，然后 **保存更改**。
1. 接下来，需要在 Moodle 服务器和 Azure Active Directory 之间同步用户。 根据环境，在此阶段可以选择不同的选项。 请注意，此处设置的配置将运行，每个 Moodle cron 运行 (通常每天) 一次，以保持一切同步。若要开始，
    * 切换到“ **同步设置”选项卡**
    * 在 **“使用 Azure AD 同步用户** ”部分中，选择适用于环境的复选框。 通常，你至少会选择：
        * 在 Moodle 中为 Azure AD 中的用户创建帐户
        * 为 Azure AD 中的用户更新 Moodle 中的所有帐户
    * 在 **“用户创建限制** ”部分中，可以设置筛选器以限制将同步到 Moodle 的 Azure AD 用户。
    * 使用 **“用户字段映射** ”部分，可以自定义 Azure AD 到 Moodle 用户配置文件字段映射。
    * 在 **“Teams 同步** ”部分中，可以选择自动创建组 (，即团队) 某些或全部现有 Moodle 课程。
1. 若要验证 cron 作业 (，如果要进行首次运行，请手动运行这些作业) 单击 **“使用 Azure AD 同步用户**”部分中的 **“计划任务管理”页** 链接。 这会转到 **“计划任务** ”页。
    * 向下滚动并找到 **使用 Azure AD 作业同步用户** 的作业，然后单击 **“立即运行**”。
    * 如果选择基于现有课程创建组，也可以 **在Office 365作业中运行“创建用户组**”。
1. 返回到插件管理页 (站点管理>插件> Microsoft 365 集成) 并选择 **“Teams 设置”** 页。 需要配置一些安全设置以启用 Teams 应用集成。
    * 若要启用 OpenID Connect，请单击 **“管理身份验证** ”链接，然后单击 **OpenId Connect** 行上的眼睛图标（如果已灰显）。
    * 接下来，需要启用帧嵌入。 单击 **HTTP 安全** 链接，然后单击“ **允许嵌入帧**”旁边的复选框。
    * 下一步是启用将启用 Moodle API 功能的 Web 服务。 单击 **“高级功能** ”链接，然后确保选中 **“启用 Web 服务”** 旁边的复选框。
    * 最后，需要为 Microsoft 365 或 Office 365 启用外部服务。 然后单击 **“外部服务** ”链接：
        * 单击“**在** **Moodle Office 365 Webservices 行上编辑**”。
        * 标记 **“已启用”** 旁边的复选框，然后单击 **“保存更改”**
    * 接下来，需要编辑经过身份验证的用户权限，以允许他们创建 Web 服务令牌。 单击 **编辑角色“经过身份验证的用户”** 链接。 向下滚动并找到 **“创建 Web 服务令牌** ”功能并标记 **“允许** ”复选框。

## <a name="step-3-deploy-the-moodle-assistant-bot-to-azure"></a>步骤 3：将 Moodle 助手机器人部署到 Azure

> [!VIDEO https://www.youtube.com/embed/gbkJxf8FlfY]

免费的 Moodle Assistant Bot for Microsoft Teams 可帮助教师和学生回答有关他们在 Moodle 中的课程、作业、成绩和其他信息的问题。 机器人还会直接在 Teams 中向学生和教师发送 Moodle 通知。 此机器人是 Microsoft 维护的开放源代码项目，[可在 GitHub 上使用](https://github.com/microsoft/Moodle-Teams-Bot)。

> [!NOTE]
> 在本部分中，你将将资源部署到 Azure 订阅，所有资源都将使用 **免费** 层进行配置。 根据机器人的使用情况，可能需要缩放这些资源。
> 如果只想使用没有机器人的 Moodle 选项卡，请跳到 [步骤 4](#step-4-deploy-your-microsoft-teams-app)。

### <a name="moodle-bot-information-flow"></a>Moodle 机器人信息流

<img width="530px" src="media/MoodleBotInformationFlow.png" alt="llustration of Moodle bot for Microsoft Teams information flow" title="Microsoft Teams 信息流的 Moodle 机器人图示" />


若要安装机器人，首先需要在 [Microsoft 标识平台](https://identity.microsoft.com/Landing)上注册它。 这样机器人就可以对 Microsoft 终结点进行身份验证。 注册机器人：

1. 返回到站点管理 (插件>插件> Microsoft 365 集成) 的插件管理页，然后选择 **“Teams 设置”** 选项卡。
1. 单击 **Microsoft 应用程序注册门户** 链接并使用 Microsoft ID 登录。
1. 输入应用 (Eg 的名称。 MoodleBot) ，然后单击 **“创建”** 按钮。
1. 复制 **应用程序 ID** 并将其粘贴到 **“团队设置”** 页上的 **机器人应用程序 ID** 字段中。
1. 单击“ **生成新密码”** 按钮。 复制生成的密码，并将其粘贴到“**团队设置”** 页上的 **“机器人应用程序密码**”字段中。
1. 滚动到窗体底部，然后单击 **“保存更改**”。

现在，你已生成应用程序 ID 和密码，现在可以将机器人部署到 Azure 了。 单击“ **部署到 Azure** ”按钮，并在“ **团队设置”** 页上填写“机器人应用程序 ID”、“机器人应用程序密码”和“Moodle 机密”所需的 (信息，Azure 信息位于 **“安装** ”页) 。 填写完窗体后，单击复选框以同意条款和条件，然后单击“ **购买** ”按钮 (所有 Azure 资源都部署到免费层) 。

资源完成部署到 Azure 后，需要使用其消息传送终结点配置 Moodle 插件。 首先，需要从 Azure 中的机器人获取终结点。 要执行此操作：

1. 如果尚未登录[到Azure 门户](https://portal.azure.com)。
2. 在左窗格中选择 **“资源组**”。
3. 从列表中选择刚才在部署机器人时 (或创建) 的资源组。
4. 从组中的资源列表中选择 **WebApp 机器人** 资源。
5. 从“**概述**”部分复制 **消息传送终结点**。
6. 在 Moodle 中，打开 Moodle 插件的“ **团队设置”** 页。
7. 在 **Bot Endpoint** 字段中粘贴刚复制的 URL，并将单词 *消息* 更改为 *Webhook*。 URL 现在应如下所示 `https://botname.azurewebsites.net/api/webhook`
8. 单击 **“保存更改”**
9. 保存更改后，返回到“ **团队设置”** 选项卡，单击 **“下载清单文件** ”按钮并将清单包保存到计算机 (你将在下一部分) 中使用它。

## <a name="step-4-deploy-your-microsoft-teams-app"></a>步骤 4：部署 Microsoft Teams 应用

> [!VIDEO https://www.youtube.com/embed/2rMb7gtM_ZM]

现在，机器人已部署到 Azure 并配置为与 Moodle 服务器通信，现在可以部署 Microsoft Teams 应用了。 为此，你将加载上一步中从 Moodle 插件团队设置页下载的清单文件。

安装应用之前，需要确保已启用外部应用和旁加载应用。 为此，可以执行 [以下步骤](./admin-settings.md)。 确保启用外部应用后，可以按照以下步骤部署应用。

1. 打开 Microsoft Teams。
2. 单击导航栏左下角的 **“应用商店** ”图标。
3. 单击选项列表中的 **“上传自定义应用** ”链接。 *注意：* 如果以全局管理员身份登录，则可以选择将应用上传到组织的应用商店，否则你只能为 Teams 加载应用，而你是 (“旁加载”) 的一部分。
4. 选择之前下载的 `manifest.zip` 包，然后单击 **“保存**”。 如果尚未下载清单包，则可以从 Moodle 插件配置页的“ **团队设置”** 选项卡执行此操作。

安装应用后，可以将选项卡添加到有权访问的任何通道。 为此，请导航到通道，单击该 **+** 符号并从列表中选择应用。 按照提示完成将 Moodle 课程选项卡添加到频道。

就是这样！ 现在，你和你的团队可以直接从 Microsoft Teams 开始使用 Moodle 课程。

若要与我们共享任何功能请求或反馈，请访问我们的 [反馈门户](https://feedbackportal.microsoft.com)。

[!INCLUDE [uservoice-disclaimer-note](includes/uservoice-disclaimer-note.md)]
