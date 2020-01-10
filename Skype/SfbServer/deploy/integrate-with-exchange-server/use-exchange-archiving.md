---
title: 配置 Skype for Business 服务器以使用 Exchange Server 存档
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 260346d1-edc8-4a0c-8ad2-6c2401c3c377
description: 摘要：配置 Exchange Server 2016 或 Exchange Server 2013 和 Skype for business 服务器的 IM 脚本。
ms.openlocfilehash: f3ada031b6dc2175ff3241b809a6288daf043010
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003562"
---
# <a name="configure-skype-for-business-server-to-use-exchange-server-archiving"></a>配置 Skype for Business 服务器以使用 Exchange Server 存档

**摘要：** 配置 Exchange Server 2016 或 Exchange Server 2013 和 Skype for business 服务器的 IM 脚本。

Skype for Business 服务器使管理员可以选择将即时消息和 Web 会议脚本存档到用户的 Exchange Server 2016 或 Exchange Server 2013 邮箱，而不是 SQL Server 数据库。 如果启用此选项，则会将脚本写入用户邮箱中的“清除”文件夹。 “清除”文件夹是“可恢复邮件”文件夹下的一个隐藏文件夹。 虽然最终用户看不到此文件夹，但文件夹由 Exchange 搜索引擎编制索引，并且可以使用 Exchange 邮箱搜索和/或 Microsoft SharePoint Server 2013 进行发现。 由于信息存储在 Exchange 就地保留功能所使用的同一个文件夹中（负责存档电子邮件和其他 Exchange 通信），因此管理员可以使用单个工具搜索已存档的所有电子通信user.

> [!IMPORTANT]
> 要完全禁用对话存档，您还必须禁用对话历史记录。 有关详细信息，请参阅以下主题：[在 Skype For Business Server、set-csclientpolicy 和 set-csclientpolicy 中管理内部和外部通信的存档](https://technet.microsoft.com/library/6c2cf941-3204-4f1a-a7e0-416c828056d9.aspx)。 [](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicy?view=skype-ps) [](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps)

为了将脚本存档到 Exchange Server，必须首先在 Skype for Business 服务器和 Exchange Server 之间配置服务器到服务器的身份验证。 在设置服务器到服务器身份验证后，您可以在 Skype for Business 服务器中执行以下任务（请注意，根据您的设置和配置，您可能不需要完成所有这些任务）：

1. 通过修改 Skype for Business 服务器存档配置设置启用 Exchange 存档。 此步骤是所有部署必需的。

2. 为用户的内部和/或外部通信启用存档。 此步骤是所有部署必需的。

3. 为每个用户配置 ExchangeArchivingPolicy 属性。 仅当 Skype for business 服务器和 Exchange Server 位于不同的林中时，才需要执行此步骤。

## <a name="step-1-enabling-exchange-archiving"></a>步骤1：启用 Exchange 存档

Skype for Business 服务器中的存档主要通过使用存档配置设置进行管理。 安装 Skype for Business 服务器时，系统会自动为您提供这些设置的单个全局集合。 （管理员可以选择在网站范围内创建新的存档设置集合。）默认情况下，不会在全局设置中启用存档，也不会在这些设置中启用 Exchange 存档。 为了使用 Exchange 存档，管理员必须在这些配置设置中同时配置 EnableArchiving 和 EnableExchangeArchiving 属性。 EnableArchiving 属性可以设置为以下三个可能的值之一：

- **无**。 禁用存档。 这是默认值。 如果 EnableArchiving 设置为 "无"，则不会在 Skype for Business Server 存档数据库或 Exchange Server 中存档任何内容。

- **ImOnly**。 仅存档即时消息脚本。 如果启用 Exchange 存档，这些脚本将在 Exchange Server 中存档。 如果禁用 Exchange 存档，则会将这些脚本存档到 Skype for business 服务器。

- **ImAndWebConf**。 将存档即时消息脚本和 Web 会议脚本。 如果启用 Exchange 存档，这些脚本将在 Exchange Server 中存档。 如果禁用 Exchange 存档，则会将这些脚本存档到 Skype for business 服务器。

EnableExchangeArchiving 属性是一个布尔值：将 EnableExchangeArchiving 设置为 True （$True）以启用 Exchange 存档，或将 EnableExchangeArchiving 设置为 False （$False）以禁用 Exchange 存档。 例如，此命令启用即时消息脚本的存档，同时启用 Exchange 存档：

```powershell
Set-CsArchivingConfiguration -Identity "global" -EnableArchiving ImOnly -EnableExchangeArchiving $True
```

若要禁用 Exchange 存档，请使用类似于以下内容的命令，这将启用即时消息存档，但禁用对 Exchange 的存档（换句话说，脚本将存档到 Skype for business 服务器）：

```powershell
Set-CsArchivingConfiguration -Identity "global" -EnableArchiving ImOnly -EnableExchangeArchiving $False
```

> [!NOTE]
> 如果 EnableArchiving 属性设置为 "无"，则 Skype for Business 服务器将不会完全存档即时消息和 Web 会议脚本。 在本例中，服务器只会忽略为 EnableExchangeArchiving 配置的值。

也可以通过使用 Skype for Business 服务器启用（或禁用） Exchange 存档。 为此，请完成以下过程：

1. 在控制面板中，单击“**监控和存档**”，然后单击“**存档配置**”。

2. 在“**存档配置**”选项卡上，双击要修改的存档设置集合（例如“**全局**”集合）。

3. 在“**编辑存档设置**”窗格中，单击“**存档设置**”下拉列表并选择“**存档 IM 会话**”（仅存档即时消息会话）或“**存档 IM 和 Web 会议会话**”（存档即时消息和 Web 会议会话）。

4. 选择要存档的项目后，选中 " **Exchange 服务器集成**" 复选框以启用 exchange 存档。 若要禁用 Exchange 存档，请清除此复选框。

> [!NOTE]
> 如果“**存档设置**”设置为“**禁用存档**”，则“**Exchange Server 集成**”复选框不可用。 必须先启用存档，然后启用 Exchange 存档。

如果 Skype for business 服务器和 Exchange Server 位于同一林中，则为单个用户存档（或至少在 Exchange Server 上具有电子邮件帐户的用户）通过使用 Exchange 就地保留策略进行管理。 如果你的用户是托管以前版本的 Exchange 的用户，则将使用 Skype for Business Server 存档策略管理这些用户的存档。 请注意，只有 Exchange Server 2016 或 Exchange Server 2013 帐户的用户才能将其 Skype for Business 脚本存档到 Exchange。

如果 Skype for business 服务器和 Exchange Server 位于不同的林中，则通过为每个单独的用户帐户配置 ExchangeArchivingPolicy 属性来管理对单个用户的存档。 请参阅步骤 3 以了解更多信息。

## <a name="step-2-enabling-the-archiving-of-internal-andor-external-communications"></a>步骤 2：启用内部和/或外部通信的存档

启用存档（和 Exchange 存档）后，必须修改相应的存档策略，以确保实际存档用户会话。 请注意，仅启用存档（步骤1）不会导致 Skype for Business 服务器开始存档即时消息和网络会议脚本。 相反，您必须使用存档策略启用内部和/或外部存档。 安装 Skype for Business 服务器时，还会安装单个全局存档策略，其中包含两个属性：

- **ArchiveInternal**。当设置为 True ($True) 时，指示将存档仅涉及在贵组织中有 Active Directory 帐户的用户的内部通信会话。

- **ArchiveExternal**。当设置为 True ($True) 时，指示将存档内部通信会话（涉及至少一个在贵组织中没有 Active Directory 帐户的用户的会话）。

默认情况下，这两个属性的值都设置为 False，意味着既不存档内部通信会话也不存档外部通信会话。 若要修改全局策略，你可以使用 Skype for Business Server Management Shell 和 CsArchivingPolicy cmdlet。 此命令可对内部和外部通信会话进行存档：

```powershell
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True -ArchiveExternal $True
```

您也可以使用 New-CsArchivingPolicy 在站点范围或每用户范围创建一个新策略。例如，此命令可新建一个名为 RedmondArchivingPolicy 的每用户存档策略：

```powershell
New-CsArchivingPolicy -Identity "RedmondArchivingPolicy" -ArchiveInternal $True -ArchiveExternal $True
```

如果您创建每用户策略，您将需要将该策略分配给相应的用户。例如：

```powershell
Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName  "RedmondArchivingPolicy"
```

还可以使用 Skype for Business 服务器控制面板管理存档策略。 在控制面板中，单击“**监控和存档**”，然后单击“**存档策略**”。 若要修改现有策略，请双击该策略（例如“全局”），然后在“**编辑存档策略**”窗格中，根据需要选中或清除“**存档内部通信**”和“**存档外部通信**”复选框。 若要创建新的存档策略，请单击 "**新建**"，然后选择 "**网站策略**" 或 "**用户策略**"。 如果您新建用户策略，则必须访问相应的用户帐户（从“**用户**”选项卡中）并为这些用户分配新策略。

## <a name="step-3-configuring-the-exchangearchivingpolicy-property"></a>步骤 3：配置 ExchangeArchivingPolicy 属性

如果 Skype for business 服务器和 Exchange Server 位于不同的林中，则只需在存档配置设置中启用 Exchange 存档就够了。这不会导致即时消息和网络会议脚本在 Exchange 中存档。 因此，你还必须在每个相关 Skype for business 服务器用户帐户上配置 ExchangeArchivingPolicy 属性。 此属性可设置为以下四个可能的值之一：

1. **未初始化**。 指示存档将基于为用户的 Exchange 邮箱配置的就地保留设置;如果用户的邮箱尚未启用就地保留，则用户将在 Skype for Business 服务器中将其邮件和网络会议脚本存档。

2. **UseLyncArchivingPolicy**。 指示用户的即时消息和 Web 会议脚本应存档在 Skype for Business 服务器中，而不是在 Exchange 中。

3. **NoArchiving**。 指示根本不应存档用户的即时消息和 Web 会议脚本。 请注意，此设置将替代分配给用户的任何 Skype for Business 服务器存档策略。

4. **ArchivingToExchange**。 指示无论已将（或尚未）分配给用户的邮箱的就地保留设置如何，用户的即时消息和 Web 会议脚本都应存档到 Exchange。

例如，若要配置用户帐户以使即时消息和 Web 会议脚本始终存档到 Exchange，您可以使用 Skype for Business Server Management Shell 中类似的命令：

```powershell
Set-CsUser -Identity "Ken Myer" -ExchangeArchivingPolicy ArchivingToExchange
```

如果要为一组用户（例如驻留在指定注册器池中的所有用户）设置同一存档策略，可以使用如下命令：

```powershell
Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.litwareinc.com"} | Set-CsUser -ExchangeArchivingPolicy ArchivingToExchange
```

请注意，你必须使用 Skype for Business Server Management Shell （和 Windows PowerShell）才能配置 ExchangeArchivingPolicy 属性的值。 此属性不会向 Skype for Business 服务器中的管理员公开。

如果您要查看已向其分配了特定存档策略的所有用户的列表，则可以使用如下命令，此命令返回已将 ExchangeArchivingPolicy 属性设置为“未初始化”的所有用户的 Active Directory 显示名称：

```powershell
Get-CsUser | Where-Object {$_.ExchangeArchivingPolicy -eq "Uninitialized"} | Select-Object DisplayName
```

同样，此命令也返回尚未将 ExchangeArchivingPolicy 属性设置为 UseLyncArchivingPolicy 的用户的显示名称：

```powershell
Get-CsUser | Where-Object {$_.ExchangeArchivingPolicy -ne "UseLyncArchivingPolicy"} | Select-Object DisplayName
```


