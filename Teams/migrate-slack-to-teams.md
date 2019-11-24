---
title: 从 Slack 迁移到 Microsoft Teams
author: lolajacobsen
ms.author: lolaj
ms.reviewer: brandber
manager: serdars
ms.topic: article
ms.service: msteams
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Priority
ms.custom: ''
description: 从 Slack 迁移到 Microsoft Teams 的完整指南。
ms.openlocfilehash: c723df62c3b8811b8d520c66d81e59aa5f96c3bb
ms.sourcegitcommit: 1d230336c0ab48a2914906dc8f4b6b3d996f46fb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2019
ms.locfileid: "38756792"
---
# <a name="migrate-from-slack-to-microsoft-teams"></a>从 Slack 迁移到 Microsoft Teams

本文介绍了从 Slack 迁移到 Microsoft Teams 的步骤。

当为组织制定从 Slack 迁移到 Teams 的计划时，请务必确定你需要保留的内容（如有）。 我们首先介绍可以迁移的数据类型，然后说明如何评估需求、制定迁移计划以及完成迁移。

下图简单展示了 Slack 架构。

![简单展示 Slack 架构的图像](media/migrate-slack-to-teams-image1.png)

## <a name="plan-your-migration-from-slack"></a>制定从 Slack 迁移的计划
### <a name="what-you-can-and-cant-migrate"></a>可以迁移和无法迁移的内容
Slack 服务计划将明确可以迁移和无法迁移的内容。 例如，某些 Slack 服务计划只允许你导出公共频道历史记录和文件，而其他计划则必须通过 DocuSign 请求将专用频道和直接消息纳入导出内容。 

若要确定你的 Slack 工作区服务级别，请登录 Slack 并记下**关于此工作区**页面上的计划类型。

若要详细了解 Slack 导出选项，请转至 Slack 网站：https://get.slack.help/hc/articles/204897248-Guide-to-Slack-import-and-export-tools 

下图概略描述了 Slack 迁移过程，我们将在本文中对此过程进行说明。 

:::image type="content" source="media/migrate-slack-to-teams-image2.png" alt-text="展示 Slack 导出过程的图表。":::

完成本部分后，你应该会了解以下内容：
- 你的 Slack 工作区的服务级别
- 可以导出和无法导出的内容
- 常见的导出方法

### <a name="assess-your-slack-workspaces"></a>评估你的 Slack 工作区
在制定组织迁移计划之前，你需要综合分析 Slack 工作区的某些信息。 了解 Slack 工作区的使用方式有助于确定迁移的范围。 例如，你要迁移多少个工作区？ 这些工作区由某个特定部门、多个部门还是整个组织使用？

如果你是要迁移的 Slack 工作区的成员，可以转至 *<your Slack workspace>.slack.com/stats* 自行分析使用情况。查看“频道”和“成员”选项卡，了解使用模式。 确定要迁移的工作区（和要保留的工作区）。 

> [!NOTE]
> 如果你无权访问统计信息页面，则说明你不是管理员或所有者。 

### <a name="export-channels"></a>导出频道

在 Slack 中，用户会加入作为 Slack 工作区的一部分的频道，而在 Teams 中，用户则是加入作为频道集合的团队。 我们建议你使用 Slack 分析功能了解每个频道的活动量，以确定要迁移的频道。 你可以根据生成的列表确定如何将 Slack 频道划分成 Teams 中的团队，并确定每个团队的成员。

如果你有 Slack 付费服务计划（任何非免费内容），可以使用 Slack 分析功能 (<your Slack workspace>.slack.com/admin/stats#channels) 了解频道的活跃程度、上次使用时间以及频道成员数量。 这些信息有助于确定是否要迁移相关频道。 默认情况下，可以导出公共频道内容（消息和文件）。 可导出的内容取决于你的 Slack 服务计划，以及你是否请求从 Slack 导出专用频道和直接消息。

若要详细了解 Slack 导出选项，请转至 Slack 网站：https://get.slack.help/hc/articles/204897248-Guide-to-Slack-import-and-export-tools 

> [!IMPORTANT]
> 查看组织在频道数据方面的隐私和合规性要求。 除需遵守最终用户可识别内容 (EUII) 生命周期规定外，你所在的组织可能还对这类数据的控制、存储和处理做出了合规性要求。

### <a name="export-direct-messages"></a>导出直接消息
直接消息与 Teams 中的聊天相同，即 1 对 1 或 1 对多的非频道对话。 “导出”功能取决于你的 Slack 服务计划，以及你是否请求将直接消息纳入 Slack 导出。 目前 Teams 不支持导入直接消息。 请咨询 Microsoft 合作伙伴，了解可通过哪些第三方解决方案将直接消息内容导入 Teams。

若要导出直接消息，请查看 Slack App Store 中的“导出”等工具。

### <a name="apps-and-custom-integrations"></a>应用和自定义集成

Slack 中的应用与 Teams 中的应用相差无几。 获得工作区中的应用及其配置的列表后，你可以在 Teams 应用商店中进行搜索，看看这些应用是否适用于 Teams*。 

转至 <your Slack workspace>.slack.com/apps/manage，获取应用和自定义集成的列表。 此页面还显示了使用每个应用的配置数目。 自定义集成的“迁移能力”各不相同。 如果是 Webhook，你通常可以将其发送到 Office 365 连接器，将工作流转入 Teams。 逐个评估机器人和其他应用，做好将其迁移到 Teams 的规划。

*如果管理员限制了应用使用，则你可能无法查看可用应用的完整列表。

### <a name="users"></a>用户
你在 Slack 中使用的身份方案可能不会直接映射到 Office 365。 例如，Slack 用户的电子邮件地址可能不会映射到 Office 365 的工作或学校帐户。 开始规划 Teams 部署之前，你应创建用户 ID 映射。

如果你使用的是 Slack 付费服务计划，可以转至 *<your Slack workspace>.slack.com/admin/stats#members*，获取每位用户的电子邮件地址和帐户类型等成员详细信息（例如，单频道来宾还是多频道来宾）。

你可以使用下面的脚本，将从 Slack 导出的电子邮件地址与 Azure AD 中的内容进行对比，以解决名称不明确的问题。 此外，它还会报告是否为用户启用了 Teams。 如需 PowerShell 方面的帮助，请参阅 [Azure PowerShell 入门](https://docs.microsoft.com/powershell/azure/get-started-azureps)。

```azurepowershell
Connect-AzureAD
Function Get-TimeStamp {
    return "[{0:MM/dd/yy} {0:HH:mm:ss}]" -f (Get-Date)
}

class User {
    [ValidateNotNullOrEmpty()] $ID
    [ValidateNotNullOrEmpty()] $FullName
    [string] $Email
    [string] $UPN
    [ValidateNotNullOrEmpty()][bool] $ExistsAzureAD
    [ValidateNotNullOrEmpty()][bool] $TeamsEnabled
}

$output = New-Object -type System.Collections.ObjectModel.Collection["User"]

$users = Get-Content -Raw -Path .\slackHistory\users.json | ConvertFrom-Json

Write-Host -ForegroundColor Green "$(Get-Timestamp) User Count: " $users.Count

$i=1
Write-Host "$(Get-Timestamp) Attempting direct email match.. `n"
foreach ($slackUser in $users) {
    $user = New-Object User
    $user.id = $slackUser.id
    $user.FullName = $slackUser.name
    try {
        if ($null -ne $slackUser.profile.email) {
            $user.email = $slackUser.profile.email
            $emailSplit = $slackUser.profile.email.Split('@')
            $mailNickName = $emailSplit[0]
            $result = Get-AzureADUser -Filter "MailNickName eq '$($mailNickName)' or UserPrincipalName eq '$($slackUser.profile.email)' or proxyAddresses/any(c:c eq 'smtp:$($slackUser.profile.email)')"
            if ($null -ne $result) {
                $user.ExistsAzureAD = $true
                $user.UPN = $result.UserPrincipalName
                $assignedPlans = $result.assignedPlans
                foreach ($plan in $assignedPlans) {
                    if ($plan.ServicePlanId -eq "57ff2da0-773e-42df-b2af-ffb7a2317929") {
                        if ($plan.CapabilityStatus -eq "Enabled") {
                            $user.TeamsEnabled = $true
                        }
                        else {
                            $user.TeamsEnabled = $false
                        }
                    }
                }
                Write-Host -ForegroundColor Green "$(Get-Timestamp) Current User $($i) - AzureAD object found:" $result.MailNickName
                Write-Host -ForegroundColor Green "$(Get-Timestamp) Current User $($i) - Teams Enabled:" $user.TeamsEnabled
            }
            else {
                $user.ExistsAzureAD = $false
                Write-Host -ForegroundColor Yellow "$(Get-Timestamp) Current User $($i) - AzureAD object not found: " $slackUser.profile.email
            }
        }
        $i++
    }   
    catch
    {
        $user.ExistsAzureAD = $false
        Write-Host -ForegroundColor Yellow "$(Get-Timestamp) Current User $($i) - AzureAD object not found: $($i)" $user.profile.email
        $i++
    }
    $output.Add($user)
}

$output | Export-Csv -Path .\SlackToAzureADIdentityMapping.csv -NoTypeInformation
Write-Host "`n $(Get-Timestamp) Generated SlackToAzureADIdentityMapping.csv. Exiting..."
$output | Export-Csv -Path .\SlackToAzureADIdentityMapping.csv -NoTypeInformation
Write-Host "`n $(Get-Timestamp) Generated SlackToAzureADIdentityMapping.csv. Exiting..."
```

完成本部分后，你应该拥有以下内容并完成以下事项：
- 包含每个工作区频道及其使用情况统计信息的列表
- 每个频道的 Slack 应用及配置列表
- 确定了要导出的 Slack 消息历史记录类型（如有）
- 包含 Slack 帐户映射到 Microsoft 工作或学校帐户的用户及其拥有的 Teams 许可的列表

## <a name="plan-your-teams-deployment"></a>规划 Teams 部署
你已从 Slack 中导出了所需的内容（并留下了不需要的内容）。 现在可以规划 Teams 部署方式并导入 Slack 数据了。 此时是根据使用情况评估哪些内容适合团队，以及将这些元素纳入 Teams 部署计划的绝佳时机。 本部分结束时，你将获得涉及 Teams 用户、频道和应用的蓝图。 

下图概述了你要在 Teams 部署过程中解决的问题。

:::image type="content" source="media/migrate-slack-to-teams-image3.png" alt-text="从 Slack 迁移到 Teams 的部署规划概述。":::

### <a name="team-and-channel-structure"></a>团队和频道结构

一个 Slack 工作区可能代表一个团队、多个团队或整个组织。 确定结构时，了解工作区的范围非常重要。 Slack 中最接近 Teams 团队的就是工作区，工作区包含频道集合。 下图显示了 3 种不同的 Slack 到 Teams 映射，以及为每个工作区选取适当映射的指南。


|Slack 到 Teams 映射 |  |
|---------|---------|
|1 个 Slack 工作区 :arrow_right: 1 个团队   | 适用于需要 200 个以内频道的较小 Slack 工作区<br>包含针对增长和专用频道规划的缓冲区  |
|1 个 Slack 工作区 :arrow_right: 多个团队     | 使用 Slack 工作区分析数据创建逻辑频道分组，这将成为团队的基础        |
|2 个以上的 Slack 工作区 :arrow_right: 多个团队     | 使用 Slack 工作区分析数据创建逻辑团队和频道分组，这将成为团队的基础        |

第三方解决方案会提供使用情况统计信息，以帮助你评估频道的活跃程度，以及频道的帖子数量。 通常情况下，常用频道将会是团队规划中的候选项。

> [!TIP]
> 只保留你的方法所需的内容，以便确定要在 Teams 中重新创建哪些频道。 若要了解详细信息，请阅读[团队和频道概述](teams-channels-overview.md)。 

#### <a name="team-planning"></a>团队规划
使用你在上面的“规划”部分编译的频道清单，并与 Slack 所有者和管理员共同确定哪些频道应成为团队，以及哪些频道应成为团队中的频道。 利用 Excel 或 PowerBI 来进行这项分析 - 这两种工具都可提供更多见解，帮助推动就要保留哪些频道展开讨论。

> [!TIP]
> Teams 目前规定每个团队不能超过 200 个频道。 如果频道列表接近该限制，则应想办法将其拆分为两个单独的团队。

### <a name="channel-history"></a>频道历史记录

你可以使用 GitHub 上的免费解决方案和付费解决方案，具体取决于你所在的组织在保留公共频道和专用频道历史记录方面的要求。 此外，还可通过编写脚本来将此内容纳入 Teams。

在 Teams 中设置新的团队和频道结构后，可将导出的文件复制到 Teams 频道中的相应文档库。

若要自动导入内容，可考虑采用以下几种方法。 你可以使用 GitHub 上的免费解决方案（[ChannelSurf](https://github.com/tamhinsf/ChannelSurf) 或 [Slack Export Viewer](https://github.com/hfaran/slack-export-viewer)）以及合作伙伴解决方案。 请根据组织需要选择解决方案。 

### <a name="channel-files"></a>频道文件

多数解决方案都会导出文件。 但是，这些文件通常以频道历史记录中的链接的形式提供，需要借助 API 密钥以编程方式取回。

对于 Slack 中存储的文件，当在 Teams 中设置好团队和频道后，你可以以编程方式将其从 Slack 复制到目标 Teams 频道。

以下脚本会从 Slack 取回文件。 这个脚本会在你的计算机上搜索指定的 Slack 导出内容，在每个目标频道中创建一个文件夹，并将所有文件下载到该位置。 此外，还存在可提取数据的第三方解决方案。 如需 PowerShell 方面的帮助，请参阅 [Azure PowerShell 入门](https://docs.microsoft.com/powershell/azure/get-started-azureps)。



```azurepowershell
$ExportPath = ".\slackHistory"
$ExportContents = Get-ChildItem -path $ExportPath -Recurse
Function Get-TimeStamp {
    return "[{0:MM/dd/yy} {0:HH:mm:ss}]" -f (Get-Date)
}

class File {
    [string] $Name
    [string] $Title
    [string] $Channel
    [string] $DownloadURL
    [string] $MimeType
    [double] $Size
    [string] $ParentPath
    [string] $Time
}

$channelList = Get-Content -Raw -Path .\slackHistory\channels.json | ConvertFrom-Json
$Files = New-Object -TypeName System.Collections.ObjectModel.Collection["File"]

Write-Host -ForegroundColor Green "$(Get-TimeStamp) Starting Step 1 (processing channel export for files) of 2. Total Channel Count: $($channelList.Count)"
#Iterate through each Channel listed in the Archive
foreach ($channel in $channelList) {
    #Iterate through Channel folders from the Export
    foreach ($folder in $ExportContents)
    {
        #If Channel Name matches..
        if ($channel.name -eq $folder){
            $channelJsons = Get-ChildItem -Path $folder.FullName -File
            Write-Host -ForegroundColor White "$(Get-TimeStamp) Info: Starting to process $($channelJsons.Count) days of content for #$($channel.name)."
            #Start processing the daily JSON for files
            foreach ($json in $channelJsons){
                $currentJson = Get-Content -Raw -Path $json.FullName | ConvertFrom-Json
                #Write-Host -ForegroundColor Yellow "$(Get-TimeStamp) Info: Processing $($json.Name) in #$($channel.name).."
                #Iterate through every action
                foreach ($entry in $currentJson){
                    #If the action contained file(s)..
                    if($null -ne $entry.files){
                        #Iterate through each file and add it to the List of Files to download
                        foreach ($item in $entry.Files) {
                        $file = New-Object -TypeName File
                            if ($null -ne $item.url_private_download){
                                $file.Name = $item.name
                                $file.Title = $item.Title
                                $file.Channel = $channel.name
                                $file.DownloadURL = $item.url_private_download
                                $file.MimeType = $item.mimetype
                                $file.Size = $item.size
                                $file.ParentPath = $folder.FullName
                                $file.Time = $item.created
                                $files.Add($file)
                            }
                        }
                    }
                }
            }
        }
    }
}
Write-Host -ForegroundColor Green "$(Get-TimeStamp) Step 1 of 2 complete. `n"

Write-Host -ForegroundColor Green "$(Get-TimeStamp) Starting step 2 (creating folders and downloading files) of 2."
#Determine which Files folders need to be created
$FoldersToMake = New-Object System.Collections.ObjectModel.Collection["string"]
foreach ($file in $files){
    if ($FoldersToMake -notcontains $file.Channel){
        $FoldersToMake.Add($file.Channel)
    }
}

#Create Folders
foreach ($folder in $FoldersToMake){
    #$fullFolderPath = $file.ParentPath + "\Files"
    $fullFolderPath = $ExportPath +"\$($folder)"
    $fullFilesPath = $ExportPath +"\$($folder)\Files"
    if (-not (Test-Path $fullFilesPath)){
        New-Item -Path $fullFolderPath  -Name "Files" -ItemType "directory"
    }
}

#Downloading Files
foreach ($file in $files)
{
    Write-Host -ForegroundColor Yellow "$(Get-TimeStamp) Downloading $($file.Name)."
    $fullFilePath = $file.ParentPath + "\Files\" + $file.Name
        if (-not (Test-Path $fullFilePath)){
            try{
                $request = (New-Object System.Net.WebClient).DownloadFile($file.DownloadURL, $fullFilePath)
            }
            catch [System.Net.WebException]{
                Write-Host -ForegroundColor Red "$(Get-TimeStamp) Error: Unable to download $($file.Name) to $($fullFilePath)"
            }   
        }
        else {
            try{
                $extensionPosition = $file.name.LastIndexOf('.')
                $splitFileName = $file.name.Substring(0,$extensionPosition)
                $splitFileExtention = $file.name.Substring($extensionPosition)
                $newFileName = $splitFileName + $file.Time + $splitFileExtention
                $fullFilePath = $file.ParentPath + "\Files\" + $newFileName
                $request = (New-Object System.Net.WebClient).DownloadFile($file.DownloadURL, $fullFilePath)
            }
            catch [System.Net.WebException]{
                Write-Host -ForegroundColor Red "$(Get-TimeStamp) Error: Unable to download $($file.Name) to $($fullFilePath)"
            }   
        }
}
Write-Host -ForegroundColor Green "$(Get-TimeStamp) Step 2 of 2 complete. `n"
Write-Host -ForegroundColor Green "$(Get-TimeStamp) Exiting.."
```


### <a name="apps-and-custom-integrations"></a>应用和自定义集成
查看 Slack 应用和自定义集成（含配置）列表，并确定要将哪些内容迁移到 Teams。 查看 Teams Marketplace，了解某款应用是否可用。 如果不可用，则可能会有备选项。 

若要确定要添加到 Teams 的应用，请务必了解应用的使用方式。 考虑“这个应用可为此频道提供哪些功能？”，了解应用将会造成的结果。 

在许多情况下，应用主要接收来自外部服务（如监控系统）的事件驱动数据，并将消息推送到 Slack。 通过使用可根据事件将消息推送到 Teams 的 Microsoft 365 连接器，也可以实现相同的结果。

下面是 Slack 解决方案示例，其中在 Teams 中使用了 Office 365 连接器进行集成。
- Ansible
  - 可通过 [Ansible Webhook](https://docs.ansible.com/ansible-tower/latest/html/userguide/notifications.html#webhook) 向 Teams 发送警报
- New Relic
  - 请查看这一[向 Teams 发送 New Relic 警报](https://discuss.newrelic.com/t/new-relic-alerts-not-working-with-microsoft-teams/48609/3)的用户解决方案
- Nagios
  - 现在可通过连接器集成警报。 https://github.com/isaac-galvan/nagios-teams-notify
- ZenDesk
  - Teams 商店中拥有该应用
- Jenkins
  - 可使用 [Jenkins 的 Office 365 连接器](https://plugins.jenkins.io/Office-365-Connector)向 Teams 发送警报


### <a name="user-readiness-and-adoption-plan"></a>用户准备情况和采用计划
软件成功部署的基础取决于用户是否已准备好接受变化。 组织中使用 Slack 的用户可以轻松理解 Teams 概念，但仍需为他们提供培训，帮助他们实现平稳过渡。 如需全面的 Teams 采用资源，请转至 [Teams 采用中心](adopt-microsoft-teams-landing-page.md)。

例如，这两种产品均提供频道，但频道在它们中的使用方式各不相同。 例如，Slack 中的频道就像 Teams 中的聊天，通常用于短期事务性对话。 其他明显区别存在于链式/非链式对话和调整通知设置方面。

查看我们内容丰富的[最终用户 Teams 培训](enduser-training.md)库。 

## <a name="move-to-teams"></a>迁移到 Teams 
现在，你已确定了过渡计划，可以开始在 Teams 中创建团队和频道了。 

创建团队和频道后，开始将文件从 Slack 频道复制到 Teams，并配置应用。 如果你要使用某个解决方案来保留历史记录，则现在可以也对其进行配置。 然后，你就可以开始授予用户许可（如果用户尚未获得许可），并将其添加到相应的团队。 为了减少需要额外导出的内容和复制的文件，请考虑在商定的日期（将每个用户添加到团队中的时间）撤销 Slack 访问权限。 这可避免重新导出和导入文件和历史记录的增量更改。

按照下图中的步骤在你所在的组织部署 Teams。 有关详情，请参阅[如何部署 Teams](How-to-roll-out-teams.md)。


:::image type="content" source="media/migrate-slack-to-teams-image4.png" alt-text="列出从 Slack 迁移到 Teams 的步骤的图表。":::