---
title: 安装 Moodle 与 Microsoft Teams
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: ''
search.appverid: MET150
description: 了解如何安装和配置适用于 Microsoft Teams 的 Moodle Learning management System (LMS) 应用。
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
ms.openlocfilehash: 95b368bab33818332ca9c2d0eafcb1966fffb3af
ms.sourcegitcommit: 1129841e68e927fe7cc31de3ad63a3e9247253cd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2022
ms.locfileid: "62363038"
---
# <a name="installing-the-moodle-integration-with-microsoft-teams"></a>安装 Moodle 与 Microsoft Teams

> [!VIDEO https://www.youtube.com/embed/OHlPt22nKoE]

[Moodle](https://moodle.org/)（全球最常用的开源 Learning MANAGEMENT System (LMS) ）现在与 Microsoft Teams！ 此集成可帮助教师和教师围绕 Moodle 课程展开协作，提出有关其成绩和作业的问题，并及时了解最新通知 - 就在Teams！

为了帮助 IT 管理员轻松设置此集成，我们已使用以下功能更新了开源 Moodle 插件：

* 将 Moodle 服务器自动注册到 Azure AD。
* 一键式将 Moodle Assistant 机器人部署到 Azure。
* 自动预配团队和自动同步所有或选择 Moodle 课程的团队注册。
* 自动将 Moodle 选项卡和 Moodle Assistant 机器人安装在每个同步的团队中。  (即将推出) 
* 一键式将 Moodle 应用发布到应用商店Teams应用。  (即将推出) 

若要详细了解此集成提供的功能，请参阅[安装 Moodle 与](/microsoftteams/platform/resources/moodleinstructions) Microsoft Teams。

## <a name="prerequisites"></a>先决条件

若要安装和配置此应用程序，需要：

1. Moodle 管理员凭据
2. Azure AD管理员凭据
3. 可以在 中创建新资源的 Azure 订阅

## <a name="step-1-install-the-moodle-plugin"></a>步骤 1：安装 Moodle 插件

> [!VIDEO https://www.youtube.com/embed/SETEC5nzMgk]

Microsoft Teams中的 Moodle 集成由开源 [Moodle 插件集提供。](https://github.com/Microsoft/o365-moodle) 若要在 Moodle 服务器中安装插件，请执行以下操作：

1. 首先，下载 [Moodle 插件集](https://moodle.org/plugins/pluginversions.php?plugin=local_o365) 并将其保存到本地计算机。 需使用 3.5 或更高版本。
    * 安装 local_o365 插件还将安装 [auth_oidc boost_o365Teams 插件](https://moodle.org/plugins/auth_oidc)。[](https://moodle.org/plugins/pluginversions.php?plugin=theme_boost_o365teams)
1. 以管理员角色登录到 Moodle 服务器，然后从左侧导航 **面板** 中选择"网站管理"。
1. 选择" **插件"** 选项卡，并单击" **安装插件"**。
1. 在" **从 ZIP 文件安装插件** "部分下，单击 **"选择文件"** 按钮。
1. 从 **Upload导航栏中** 选择文件选项，浏览到上面下载的文件，然后单击Upload **此文件**。
1. 再次从 **左侧导航** 面板中选择"网站管理"选项，返回到管理员仪表板。 向下滚动到"**本地插件"，** 并单击"Microsoft Office 365 **集成"** 链接。 让此配置页在单独的浏览器选项卡中保持打开状态，因为此过程的余下部分会一直使用。

可以在 Moodle 文档中找到有关如何安装 [Moodle 插件的信息](https://docs.moodle.org/34/en/Installing_plugins)。

**重要说明：** 在单独的浏览器Microsoft 365打开 Office 365 或 Moodle 插件配置页，因为在整个过程中将返回到这组页面。

*还没有 Moodle 网站？* 可能需要查看 Azure 上的 Moodle 存储库，可在其中快速[](https://github.com/azure/moodle)在 Azure 上部署 Moodle 实例，并根据需要对其进行自定义。

## <a name="step-2-configure-the-connection-between-the-microsoft-365-or-office-365-plugin-and-azure-active-directory"></a>步骤 2：配置 Microsoft 365 或 Office 365 插件Azure Active Directory

> [!VIDEO https://www.youtube.com/embed/FpGEezaJ3SA]

接下来，需要将 Moodle 注册为应用程序中Azure Active Directory。 我们提供了 PowerShell 脚本来帮助你完成此过程。 PowerShell 脚本为 Azure AD 或 Microsoft 365 组织Office 365新应用程序，Moodle 插件将使用该应用程序。 该脚本将为租户或Microsoft 365应用Office 365，为预配的应用设置所有必需的回复 URL 和权限，并返回 AppID 和密钥。 可以使用 Moodle 插件设置页中生成的 AppID 和密钥来配置 Moodle 服务器Azure AD。 若要查看 PowerShell 脚本自动执行的详细手动步骤，可以在插件的完整 [文档中找到这些步骤](https://docs.moodle.org/34/en/Office365#Register_your_Moodle_instance_as_an_Application)。

### <a name="moodle-tab-for-microsoft-teams-information-flow"></a>"Moodle"选项卡Microsoft Teams信息流

<img width="530px" src="media/MoodleTabInformationFlow.png" alt="Illustration of Moodle tab for Microsoft Teams information flow" title="用于显示信息流的 Moodle Microsoft Teams插图" />

1. 在"Microsoft 365或Office 365插件"页中，选择"设置 **"** 选项卡。
1. 单击" **下载 PowerShell 脚本"** 按钮，并将其保存到本地计算机。
1. 需要从 ZIP 文件准备 PowerShell 脚本。 为此：
    * 下载并解压缩 `Moodle-AzureAD-Powershell.zip` 文件。
    * 打开提取的文件夹。
    * 右键单击文件并选择 `Moodle-AzureAD-Script.ps1` "属性 **"**。
    * 在" **属性** "窗口的"常规"选项卡下 `Unblock` ，选中底部 **"安全性"** 属性旁边的框。
    * 单击“**确定**”。
    * 复制提取的文件夹的目录路径。
1. 接下来，以管理员角色运行 PowerShell：
    * 单击“开始”。
    * 键入 PowerShell。
    * 右键单击Windows PowerShell。
    * 单击"以管理员角色运行"。
1. 通过键入 ，导航到 `cd ...\...\Moodle-AzureAD-Powershell` 解压缩的目录，其中 `...\...` 是目录的路径。
1. 通过以下方法执行 PowerShell 脚本：
    * 输入 `Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser`。
    * 输入 `.\Moodle-AzureAD-Script.ps1`。
    * 在弹出窗口Microsoft 365 Office 365登录到管理员帐户或管理员帐户。
    * 输入应用程序名称Azure AD应用程序 (例如 Moodle/Moodle 插件) 。
    * 输入 Moodle 服务器的 URL。
    * 复制 **脚本生成的****应用程序** ID 和应用程序密钥，并保存它们。
1. 接下来，需要将 ID 和密钥添加到 Moodle 插件。 返回到"插件管理"页 (">插件"> Microsoft 365集成) 。
1. 在"**设置"** 选项卡上，添加之前复制的应用程序 **ID** 和应用程序密钥，然后单击"保存 **更改"**。
1. 刷新页面后，现在应会看到一个新部分" **选择连接方法"**。 单击标记为"默认" **的复选框** ，然后再次单击" **保存更改** "。
1. 刷新页面后，会看到另一个新分区管理员 **同意&信息**。
    * 单击"**提供管理员许可**"链接，输入Microsoft 365或Office 365全局管理员凭据，并单击"接受"以授予权限。
    * 在"Azure AD **"字段旁边**，单击"**检测"** 按钮。
    * 在 URL 旁边 **OneDrive for Business** 单击"**检测"** 按钮。
    * 填充字段后，再次单击 **"保存更改"** 按钮。
1. 单击" **更新"** 按钮验证安装，并单击" **保存更改"**。
1. 接下来，需要在 Moodle 服务器和客户端之间Azure Active Directory。 根据环境，可以在此阶段选择不同的选项。 请注意，在此处设置的配置将运行每个 Moodle cron (每天运行一次) 以保持所有内容同步。若要开始，请：
    * 切换到"同步 **设置选项卡**
    * 在"**将用户与Azure AD** 同步"部分中，选中适用于环境的复选框。 通常至少选择：
        * 在 Moodle 中为 Azure AD
        * 为用户更新 Moodle 中所有帐户Azure AD
    * 在 **"用户创建限制**"部分中，可以设置筛选器来限制要Azure AD Moodle 的用户数。
    * "**用户字段映射**"部分将允许您自定义Azure AD Moodle 用户配置文件字段映射。
    * 在 **"Teams同步**"部分中，可以选择自动 (组"，Teams) 或所有现有 Moodle 课程创建组。
1. 若要验证 cron 作业 (如果希望首次运行，请手动运行) 请单击"将用户与 Azure AD 同步"部分中的"计划任务 **管理"页** 链接。 这会将你带至 **"计划任务"** 页。
    * 向下滚动并找到作业 **"将用户** 与Azure AD同步"，然后单击"立即 **运行"**。
    * 如果选择基于现有课程创建组，还可以运行在作业中 **Office 365组。**
1. 返回到"插件管理"页 (">插件> Microsoft 365集成) **并选择Teams 设置页**。 需要配置一些安全设置，以启用Teams集成。
    * 若要启用 OpenID 连接，请单击"管理身份验证"链接，如果 **OpenId** 连接显示为灰色，则单击"眼睛"图标。
    * 接下来，你需要启用帧嵌入。 单击" **HTTP 安全性"** 链接，并单击"允许嵌入 **帧"旁边的复选框**。
    * 下一步是启用将启用 Moodle API 功能的 Web 服务。 单击" **高级功能** "链接，确保选中" **启用 Web 服务"旁边的** 复选框。
    * 最后，需要为外部服务启用Microsoft 365 Office 365。 单击" **外部服务"** 链接，然后：
        * 在 **"Moodle** **Office 365 Webservices"行上单击"编辑**"。
        * 标记"已启用"旁边的 **复选框，** 然后单击" **保存更改"**
    * 接下来，需要编辑经过身份验证的用户权限，以允许他们创建 Web 服务令牌。 单击 **"编辑角色""已经过身份验证的用户"** 链接。 向下滚动并找到" **创建 Web 服务令牌** "功能，并标记" **允许"** 复选框。

## <a name="step-3-deploy-the-moodle-assistant-bot-to-azure"></a>步骤 3：将 Moodle Assistant 机器人部署到 Azure

> [!VIDEO https://www.youtube.com/embed/gbkJxf8FlfY]

免费的 Moodle Assistant Bot for Microsoft Teams 可帮助教师和学生回答有关 Moodle 中课程、作业、成绩和其他信息的问题。 机器人还会立即向学生和教师发送 Moodle Teams。 此机器人是由 Microsoft 维护的一个开源项目，[可在 GitHub](https://github.com/microsoft/Moodle-Teams-Bot)。

> [!NOTE]
> 在本部分，我们将资源部署到 Azure 订阅，所有资源都将使用免费 **层进行** 配置。 根据机器人的使用情况，可能需要缩放这些资源。
> 如果只想使用"Moodle"选项卡而不使用机器人，请跳到 [步骤 4](#step-4-deploy-your-microsoft-teams-app)。

### <a name="moodle-bot-information-flow"></a>Moodle 机器人信息流

<img width="530px" src="media/MoodleBotInformationFlow.png" alt="llustration of Moodle bot for Microsoft Teams information flow" title="用于信息流的 Moodle 机器人Microsoft Teams插图" />


若要安装机器人，首先需要在 Microsoft 标识平台上 [注册它](https://identity.microsoft.com/Landing)。 这样机器人可以针对 Microsoft 终结点进行身份验证。 注册机器人：

1. 返回到"插件管理"页 (">插件> Microsoft 365集成) 并选择"**Teams 设置选项卡。**
1. 单击 **"Microsoft 应用程序注册门户"** 链接，使用 Microsoft ID 登录。
1. 输入应用的名称，例如 (名称。 MoodleBot) 单击"创建 **"** 按钮。
1. 复制"**应用程序 ID**"并将其粘贴到"团队"页的"机器人应用程序 **ID**"**设置** 字段中。
1. 单击" **生成新密码"** 按钮。 复制生成的密码，并将其粘贴到"团队密码"页上的"机器人应用程序 **密码设置** 字段中。
1. 滚动到窗体底部，然后单击"保存 **更改"**。

生成应用程序 ID 和密码后，现在可以将机器人部署到 Azure。 单击"**部署到 Azure**"按钮，在表单中填写必要的信息 ("机器人应用程序 ID"、机器人应用程序密码和 Moodle 机密位于 **"团队 设置"** 页上，Azure 信息位于"设置"页) 。 填写表单后，单击该复选框以同意条款和条件，然后单击"购买"按钮 (所有 Azure 资源都部署到免费层) 。

资源部署到 Azure 后，需要配置 Moodle 插件及其消息传送终结点。 首先，需要从 Azure 中的机器人获取终结点。 为此，需要：

1. 如果还没有，请登录到 [Azure 门户](https://portal.azure.com)。
2. 在左窗格中，选择" **资源组"**。
3. 从列表中选择你在部署机器人时刚 (或) 的资源组。
4. 从 **组中资源列表中选择 WebApp** 机器人资源。
5. 从 **"概述"部分** 复制"消息 **传送终结点** "。
6. 在 Moodle 中，打开 **Moodle 设置** 的 Team 设置 页面。
7. 在" **机器人终结点"** 字段中粘贴刚刚复制的 URL，然后将"消息" *一* 词更改为 *webhook*。 URL 现在应如下所示 `https://botname.azurewebsites.net/api/webhook`
8. 单击" **保存更改"**
9. 保存更改后，返回到"团队 设置"选项卡，单击"下载清单文件"按钮，将清单包保存到计算机 (你将在) 的下一部分中使用它。

## <a name="step-4-deploy-your-microsoft-teams-app"></a>步骤 4：部署 Microsoft Teams 应用

> [!VIDEO https://www.youtube.com/embed/2rMb7gtM_ZM]

将机器人部署到 Azure 并配置为与 Moodle 服务器通信后，现在可以将机器人部署到 Microsoft Teams应用。 为此，需要加载在上一步骤中从 Moodle 插件团队设置下载的清单文件。

在安装应用之前，你需要确保启用外部应用和应用旁加载。 为此，可以按照 [以下步骤操作](./admin-settings.md)。 确保启用外部应用后，可以按照以下步骤部署应用。

1. 打开Microsoft Teams。
2. 单击 **导航栏** 左下角的"应用商店"图标。
3. 单击 **Upload选项列表中的自定义** 应用链接。 *注意：* 如果你以全局管理员身份登录，你将可以选择将应用上载到组织的应用商店，否则你只能为 Teams 加载应用 ("旁加载") 。
4. 选择之前 `manifest.zip` 下载的程序包，然后单击"保存 **"**。 如果尚未下载清单包，可以从 Moodle 中插件配置 **设置** 的"团队"选项卡进行下载。

安装应用后，你可以将选项卡添加到你有权访问的任何频道。 为此，请导航到通道，单击 符号 **+** ，然后从列表中选择你的应用。 按照提示完成将 Moodle 课程选项卡添加到频道。

就是这样！ 现在，你和团队可以直接从团队开始Microsoft Teams。

若要与我们共享任何功能请求或反馈，请访问我们的 [User Voice 页面](https://microsoftteams.uservoice.com/forums/916759-moodle)。

[!INCLUDE [uservoice-disclaimer-note](includes/uservoice-disclaimer-note.md)]