---
title: 从 Skype for Business Online 连接器迁移到 Teams PowerShell 模块
author: pupara
ms.author: pupara
ms.reviewer: pupara
manager: bulenteg
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: 了解如何从 Skype for Business Online 连接器移动到 Teams PowerShell 模块以管理Teams。
appliesto:
- Microsoft Teams
ms.openlocfilehash: e788fc8cd31bd6e8754e410132e02829eaa2cad8
ms.sourcegitcommit: 50ec59b454e751d952cde9fd13c8017529d0e1d6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2021
ms.locfileid: "52469714"
---
# <a name="migrating-from-skype-for-business-online-connector-to-the-teams-powershell-module"></a><span data-ttu-id="d8273-103">从 Skype for Business Online 连接器迁移到 Teams PowerShell 模块</span><span class="sxs-lookup"><span data-stu-id="d8273-103">Migrating from Skype for Business Online Connector to the Teams PowerShell module</span></span>

<span data-ttu-id="d8273-104">TeamsPowerShell 模块提供一组完整的 cmdlet，用于Teams PowerShell 命令行管理数据。</span><span class="sxs-lookup"><span data-stu-id="d8273-104">Teams PowerShell Module provides a complete set of cmdlets for managing Teams directly from the PowerShell command line.</span></span> <span data-ttu-id="d8273-105">管理员无需为Skype For Business Online 连接器Teams管理。</span><span class="sxs-lookup"><span data-stu-id="d8273-105">Administrators do not require Skype For Business Online Connector for their Teams administration.</span></span>

> [!NOTE]
> <span data-ttu-id="d8273-106">Teams 2021 年 3 月 16 日 (MC244740 消息中心发布消息通知管理员;MC250940，日期为 2021 年 4 月 16) 此更改。</span><span class="sxs-lookup"><span data-stu-id="d8273-106">Teams administrator were notified through Message center post (MC244740, dated March 16, 2021; MC250940, dated April 16 2021) about this change.</span></span>
>
> <span data-ttu-id="d8273-107">TeamsPowerShell 模块使用新式身份验证，Windows远程管理 (WinRM) 客户端配置为允许基本身份验证。</span><span class="sxs-lookup"><span data-stu-id="d8273-107">Teams PowerShell Module uses modern authentication, but the underlying Windows Remote Management (WinRM) client must be configured to allow Basic authentication.</span></span> <span data-ttu-id="d8273-108">有关如何启用 WinRM for Basic[身份验证的说明](/skypeforbusiness/set-up-your-computer-for-windows-powershell/download-and-install-windows-powershell-5-1)，请参阅下载并安装 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="d8273-108">See [Download and install Windows PowerShell](/skypeforbusiness/set-up-your-computer-for-windows-powershell/download-and-install-windows-powershell-5-1) for instructions on how to enable WinRM for Basic authentication.</span></span>

> [!WARNING]
> <span data-ttu-id="d8273-109">Skype for Business从 2021 年 5 月 17 日开始，将拒绝联机连接器连接。</span><span class="sxs-lookup"><span data-stu-id="d8273-109">Skype for Business Online Connector connections will be rejected starting May 17, 2021.</span></span> <span data-ttu-id="d8273-110">有关迁移到 PowerShell 模块的帮助和支持，请与 Microsoft Teams联系。</span><span class="sxs-lookup"><span data-stu-id="d8273-110">Please contact Microsoft Support for help and support for migrating to Teams PowerShell Module.</span></span>

## <a name="how-to-migrate"></a><span data-ttu-id="d8273-111">如何迁移</span><span class="sxs-lookup"><span data-stu-id="d8273-111">How to Migrate</span></span>

<span data-ttu-id="d8273-112">从使用 Skype for Business Online 连接器迁移到 Teams PowerShell 模块非常简单。</span><span class="sxs-lookup"><span data-stu-id="d8273-112">Migrating from using Skype for Business Online Connector to Teams PowerShell module is easy and simple.</span></span> <span data-ttu-id="d8273-113">以下步骤介绍了如何这样做。</span><span class="sxs-lookup"><span data-stu-id="d8273-113">The below steps explains how to do this.</span></span>

1. <span data-ttu-id="d8273-114">安装 PowerShell 模块Teams最新版本。</span><span class="sxs-lookup"><span data-stu-id="d8273-114">Install the latest Teams PowerShell module.</span></span> <span data-ttu-id="d8273-115">有关步骤，请参阅[安装 Microsoft Teams Powershell。](teams-powershell-install.md)</span><span class="sxs-lookup"><span data-stu-id="d8273-115">For steps, see [Install Microsoft Teams Powershell](teams-powershell-install.md).</span></span>
2. <span data-ttu-id="d8273-116">卸载 Skype For Business Online 连接器。</span><span class="sxs-lookup"><span data-stu-id="d8273-116">Uninstall Skype For Business Online Connector.</span></span> <span data-ttu-id="d8273-117">为此，请在"控制面板"中转到"程序和功能"，选择"Skype for Business Online"，Windows PowerShell"模块 **"，** 然后选择"卸载 **"。**</span><span class="sxs-lookup"><span data-stu-id="d8273-117">To do this, in Control Panel, go to **Programs and Features**, select **Skype for Business Online, Windows PowerShell Module**, and then select **Uninstall**.</span></span>
3. <span data-ttu-id="d8273-118">在 PowerShell 脚本中，更改 从 中引用的模块 ```Import-Module``` 名称</span><span class="sxs-lookup"><span data-stu-id="d8273-118">In your PowerShell scripts, change the module name that's referenced in ```Import-Module``` from</span></span>

    <span data-ttu-id="d8273-119">`SkypeOnlineConnector` 或 `LyncOnlineConnector` `MicrosoftTeams` 。</span><span class="sxs-lookup"><span data-stu-id="d8273-119">`SkypeOnlineConnector` or `LyncOnlineConnector` to `MicrosoftTeams`.</span></span>

    <span data-ttu-id="d8273-120">例如，将 `Import-Module -Name SkypeOnlineConnector` 更改为 `Import-Module -Name MicrosoftTeams` 。</span><span class="sxs-lookup"><span data-stu-id="d8273-120">For example, change `Import-Module -Name SkypeOnlineConnector` to `Import-Module -Name MicrosoftTeams`.</span></span>

4. <span data-ttu-id="d8273-121">使用 powerShell Teams 2.0 或更高版本时，请更新引用 的 `New-CsOnlineSession` 脚本 `Connect-MicrosoftTeams` 。</span><span class="sxs-lookup"><span data-stu-id="d8273-121">When using Teams PowerShell Module 2.0 or later, update your scripts that refers `New-CsOnlineSession` to `Connect-MicrosoftTeams`.</span></span> <span data-ttu-id="d8273-122">`Import-PsSession`不再需要建立一个Skype for Business远程 PowerShell 会话，因为使用 时，该会话是隐式的 `Connect-MicrosoftTeams` 。</span><span class="sxs-lookup"><span data-stu-id="d8273-122">`Import-PsSession` is no longer required to establish a Skype for Business Online Remote PowerShell Session as that is done implicit when using `Connect-MicrosoftTeams`.</span></span>

    ```powershell
       # When using the Skype for Business online connector
         Import-Module SkypeForBusinessConnector [LyncOnlineConnector]
         $credential = Get-Credential
         $SkypeSession = New-CsOnlineSession -Credential $credential
         Import-Session $SkypeSession
    
       # Example getting tenant details
         Get-csTenant
    
       # When using Teams PowerShell Module 2.0 or later
         Import-Module MicrosoftTeams
         $credential = Get-Credential
         Connect-MicrosoftTeams -Credential $credential
       
       # Example getting tenant details
         Get-csTenant
    
       # Closing the Session when using the Skype for Business online connector
         Get-PsSession $SkypeSession | Remove-PsSession
    
       # Disconnecting from Teams PowerShell Module 
         Disconnect-MicrosoftTeams
    ```

## <a name="online-support"></a><span data-ttu-id="d8273-123">联机支持</span><span class="sxs-lookup"><span data-stu-id="d8273-123">Online Support</span></span>

<span data-ttu-id="d8273-124">通过联机启动服务请求来节省时间。</span><span class="sxs-lookup"><span data-stu-id="d8273-124">Save time by starting your service request online.</span></span> <span data-ttu-id="d8273-125">我们将帮助你找到解决方案或联系技术支持人员。</span><span class="sxs-lookup"><span data-stu-id="d8273-125">We'll help you find a solution or connect you to technical support.</span></span>
1.  <span data-ttu-id="d8273-126">转到 的管理中心 [https://admin.microsoft.com](https://admin.microsoft.com) 。</span><span class="sxs-lookup"><span data-stu-id="d8273-126">Go to the admin center at [https://admin.microsoft.com](https://admin.microsoft.com).</span></span> <span data-ttu-id="d8273-127">如果你收到一条消息，表明你无权访问此页面或执行此操作，那么你不是管理员。我Who拥有管理员权限？</span><span class="sxs-lookup"><span data-stu-id="d8273-127">If you get a message that says you don't have permission to access this page or perform this action, then you aren't an admin. Who has admin permissions in my business?</span></span>
2.  <span data-ttu-id="d8273-128">选择" **需要帮助？"** 按钮。</span><span class="sxs-lookup"><span data-stu-id="d8273-128">Select the **Need help**? button.</span></span>
3.  <span data-ttu-id="d8273-129">在" **需要帮助？"** 窗格，告诉我们需要帮助的内容，然后按 Enter。</span><span class="sxs-lookup"><span data-stu-id="d8273-129">In the **Need help**? pane, tell us what you need help with, and then press Enter.</span></span>
4.  <span data-ttu-id="d8273-130">如果结果没有帮助，请选择"**联系支持人员"。**</span><span class="sxs-lookup"><span data-stu-id="d8273-130">If the results don't help, select **Contact support**.</span></span>
5.  <span data-ttu-id="d8273-131">输入问题说明，确认联系人号码和电子邮件地址，选择首选联系方式，然后选择"**与我联系"。**</span><span class="sxs-lookup"><span data-stu-id="d8273-131">Enter a description of your issue, confirm your contact number and email address, select your preferred contact method, and then select **Contact me**.</span></span> <span data-ttu-id="d8273-132">"需要帮助？" 中指示了预期的等待时间。窗格。</span><span class="sxs-lookup"><span data-stu-id="d8273-132">The expected wait time is indicated in the Need help? pane.</span></span>

## <a name="related-topics"></a><span data-ttu-id="d8273-133">相关主题</span><span class="sxs-lookup"><span data-stu-id="d8273-133">Related topics</span></span>

[<span data-ttu-id="d8273-134">安装 Microsoft Teams Powershell</span><span class="sxs-lookup"><span data-stu-id="d8273-134">Install Microsoft Teams Powershell</span></span>](teams-powershell-install.md)

[<span data-ttu-id="d8273-135">使用 Teams PowerShell Teams管理资源</span><span class="sxs-lookup"><span data-stu-id="d8273-135">Manage Teams with Teams PowerShell</span></span>](teams-powershell-managing-teams.md)

[<span data-ttu-id="d8273-136">TeamsPowerShell 发行说明</span><span class="sxs-lookup"><span data-stu-id="d8273-136">Teams PowerShell release notes</span></span>](teams-powershell-release-notes.md)

[<span data-ttu-id="d8273-137">Microsoft Teams cmdlet 参考</span><span class="sxs-lookup"><span data-stu-id="d8273-137">Microsoft Teams cmdlet reference</span></span>](/powershell/teams/?view=teams-ps)

[<span data-ttu-id="d8273-138">Skype for Business cmdlet 参考</span><span class="sxs-lookup"><span data-stu-id="d8273-138">Skype for Business cmdlet reference</span></span>](/powershell/skype/intro?view=skype-ps)
