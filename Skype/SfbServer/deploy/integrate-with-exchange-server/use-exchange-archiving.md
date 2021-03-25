---
title: 配置 Skype for Business Server 以使用Exchange Server存档
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 260346d1-edc8-4a0c-8ad2-6c2401c3c377
description: 摘要：配置 Exchange Server 2016 或 Exchange Server 2013 和 Skype for Business Server 的 IM 脚本。
ms.openlocfilehash: 43a57fc227f7fc0dbcb33b2ecb4808f3e9762ad6
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120311"
---
# <a name="configure-skype-for-business-server-to-use-exchange-server-archiving"></a>配置 Skype for Business Server 以使用Exchange Server存档

**摘要：** 为 2016 Exchange Server 2013 Exchange Server Skype for Business Server 配置 IM 脚本。

Skype for Business Server 使管理员可以选择将即时消息和 Web 会议脚本存档到用户的 Exchange Server 2016 或 Exchange Server 2013 邮箱，而不是 SQL Server 数据库。 如果启用此选项，则会将脚本写入用户邮箱中的“清除”文件夹。 “清除”文件夹是“可恢复邮件”文件夹下的一个隐藏文件夹。 尽管此文件夹对最终用户不可见，但该文件夹由 Exchange 搜索引擎编制索引，并且可以使用 Exchange 邮箱搜索和/或 Microsoft SharePoint Server 2013 来发现。 由于信息存储在 Exchange In-Place 保留功能 (负责存档电子邮件和其他 Exchange 通信) 所使用的同一文件夹中，因此管理员可以使用单个工具来搜索为用户存档的所有电子通信。

> [!IMPORTANT]
> 若要完全禁用对话存档，还必须禁用对话历史记录。 有关详细信息，请参阅以下主题 [：Managing the Archiving of internal and external communications in Skype for Business Server、](/previous-versions/office/lync-server-2013/lync-server-2013-managing-the-archiving-of-internal-and-external-communications) [New-CsClientPolicy](/powershell/module/skype/new-csclientpolicy?view=skype-ps)和 [Set-CsClientPolicy](/powershell/module/skype/set-csclientpolicy?view=skype-ps)。

为了将脚本存档到Exchange Server必须先在 Skype for Business Server 和 Skype for Business Server 之间配置服务器到服务器Exchange Server。 在服务器到服务器身份验证就位后，可以在 Skype for Business Server (中执行以下任务，请注意，根据你的设置和配置，你可能不需要完成所有这些任务) ：

1. 通过修改 Skype for Business Server 存档配置设置启用 Exchange 存档。 此步骤是所有部署必需的。

2. 为用户的内部和/或外部通信启用存档。 此步骤是所有部署必需的。

3. 为每个用户配置 ExchangeArchivingPolicy 属性。 只有当 Skype for Business Server 和 Exchange Server位于不同的林时，才需要执行此步骤。

## <a name="step-1-enabling-exchange-archiving"></a>步骤 1：启用 Exchange 存档

Skype for Business Server 中的存档主要是通过使用存档配置设置进行管理的。 安装 Skype for Business Server 时，系统会自动提供这些设置的单个全局集合。  (管理员可以选择在站点范围创建新的存档设置集合。) 默认情况下，不会在全局设置中启用存档，也不会在这些设置中启用 Exchange 存档。 为了使用 Exchange 存档，管理员必须在这些配置设置中同时配置 EnableArchiving 和 EnableExchangeArchiving 属性。 EnableArchiving 属性可以设置为以下三个可能的值之一：

- **无**。 禁用存档。 这是默认值。 如果 EnableArchiving 设置为 None，则 Skype for Business Server 存档数据库或存档数据库中不会存档任何Exchange Server。

- **ImOnly**。 仅存档即时消息脚本。 如果启用 Exchange 存档，这些脚本将存档在Exchange Server。 如果禁用 Exchange 存档，这些脚本将存档到 Skype for Business Server。

- **ImAndWebConf**。 将存档即时消息脚本和 Web 会议脚本。 如果启用 Exchange 存档，这些脚本将存档在Exchange Server。 如果禁用 Exchange 存档，这些脚本将存档到 Skype for Business Server。

EnableExchangeArchiving 属性是一个布尔值：将 EnableExchangeArchiving 设置为 True ($True) 以启用 Exchange 存档，或将 EnableExchangeArchiving 设置为 False ($False) 禁用 Exchange 存档。 例如，此命令可启用即时消息脚本的存档，还启用 Exchange 存档：

```powershell
Set-CsArchivingConfiguration -Identity "global" -EnableArchiving ImOnly -EnableExchangeArchiving $True
```

若要禁用 Exchange 存档，请使用类似如下的命令，该命令可启用即时消息存档，但禁用 Exchange (换句话说，脚本将存档到 Skype for Business Server) ：

```powershell
Set-CsArchivingConfiguration -Identity "global" -EnableArchiving ImOnly -EnableExchangeArchiving $False
```

> [!NOTE]
> 如果 EnableArchiving 属性设置为 None，则 Skype for Business Server 将完全不存档即时消息和 Web 会议脚本。 在本例中，服务器只会忽略为 EnableExchangeArchiving 配置的值。

通过使用 Skype for Business Server， (Exchange 存档) 或禁用 Exchange 存档。 为此，请完成以下过程：

1. 在控制面板中，单击“监控和存档”，然后单击“存档配置”。

2. 在“存档配置”选项卡上，双击要修改的存档设置集合（例如“全局”集合）。

3. 在“编辑存档设置”窗格中，单击“存档设置”下拉列表并选择“存档 IM 会话”（仅存档即时消息会话）或“存档 IM 和 Web 会议会话”（存档即时消息和 Web 会议会话）。

4. 选择要存档的项目后，选中"Exchange Server **集成"复选框** 以启用 Exchange 存档。 若要禁用 Exchange 存档，请清除此复选框。

> [!NOTE]
> 如果“存档设置”设置为“禁用存档”，则“Exchange Server 集成”复选框不可用。 必须先启用存档，然后再启用 Exchange 存档。

如果 Skype for Business Server 和 Exchange Server 位于同一个林中，则使用 Exchange In-Place 保留策略管理单个用户的存档 (或至少在 Exchange Server) 上拥有电子邮件帐户的用户的存档。 如果你有用户托管在以前版本的 Exchange 上，则这些用户的存档将通过使用 Skype for Business Server 存档策略进行管理。 请注意，只有拥有 2016 Exchange Server 2013 Exchange Server帐户的用户才能将其 Skype for Business 脚本存档到 Exchange。

如果 Skype for Business Server Exchange Server位于不同的林中，则通过为各个用户帐户配置 ExchangeArchivingPolicy 属性管理单个用户的存档。 请参阅步骤 3 以了解更多信息。

## <a name="step-2-enabling-the-archiving-of-internal-andor-external-communications"></a>步骤 2：启用内部和/或外部通信的存档

在启用存档策略 (Exchange 存档) 您必须修改相应的存档策略以确保实际存档用户会话。 请注意，仅启用 (步骤 1) 不会导致 Skype for Business Server 开始存档即时消息和 Web 会议脚本。 相反，您必须使用存档策略启用内部和/或外部存档。 安装 Skype for Business Server 时，还会安装一个包含两个属性的全局存档策略：

- **ArchiveInternal**。当设置为 True ($True) 时，指示将存档仅涉及在贵组织中有 Active Directory 帐户的用户的内部通信会话。

- **ArchiveExternal**。当设置为 True ($True) 时，指示将存档内部通信会话（涉及至少一个在贵组织中没有 Active Directory 帐户的用户的会话）。

默认情况下，这两个属性的值都设置为 False，意味着既不存档内部通信会话也不存档外部通信会话。 若要修改全局策略，可以使用 Skype for Business Server 命令行管理程序和 Set-CsArchivingPolicy cmdlet。 此命令可对内部和外部通信会话进行存档：

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

存档策略也可使用 Skype for Business Server 控制面板进行管理。 在控制面板中，单击“监控和存档”，然后单击“存档策略”。 若要修改现有策略，请双击该策略（例如“全局”），然后在“编辑存档策略”窗格中，根据需要选中或清除“存档内部通信”和“存档外部通信”复选框。 若要创建新的存档策略，请单击"**新建**"，然后选择"站点策略"**或**"**用户策略"。** 如果您新建用户策略，则必须访问相应的用户帐户（从“用户”选项卡中）并为这些用户分配新策略。

## <a name="step-3-configuring-the-exchangearchivingpolicy-property"></a>步骤 3：配置 ExchangeArchivingPolicy 属性

如果 Skype for Business Server Exchange Server位于不同的林中，则只需在存档配置设置中启用 Exchange 存档是不够的;这不会在 Exchange 中存档即时消息和 Web 会议脚本。 相反，还必须在每个相关的 Skype for Business Server 用户帐户上配置 ExchangeArchivingPolicy 属性。 此属性可设置为以下四个可能的值之一：

1. **未初始化**。 指示存档将基于为In-Place Exchange 邮箱配置的"保留"设置;如果In-Place邮箱上未启用"保留"功能，则用户将在 Skype for Business Server 中存档其消息和 Web 会议脚本。

2. **UseLyncArchivingPolicy**。 指示应在 Skype for Business Server 而非 Exchange 中存档用户的即时消息和 Web 会议脚本。

3. **NoArchiving**。 指示根本不应存档用户的即时消息和 Web 会议脚本。 请注意，此设置会覆盖分配给用户的任何 Skype for Business Server 存档策略。

4. **ArchivingToExchange**。 指示用户即时消息和 Web 会议脚本应存档到 Exchange，而不考虑 (或) 分配给用户邮箱的 In-Place 保留设置。

例如，若要配置用户帐户以便始终将即时消息和 Web 会议脚本存档到 Exchange，可以从 Skype for Business Server 命令行管理程序使用类似以下的命令：

```powershell
Set-CsUser -Identity "Ken Myer" -ExchangeArchivingPolicy ArchivingToExchange
```

如果要为一组用户（例如驻留在指定注册器池中的所有用户）设置同一存档策略，可以使用如下命令：

```powershell
Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.litwareinc.com"} | Set-CsUser -ExchangeArchivingPolicy ArchivingToExchange
```

请注意，必须使用 Skype for Business Server 命令行管理程序 (Windows PowerShell) 才能配置 ExchangeArchivingPolicy 属性的值。 此属性不会向 Skype for Business Server 中的管理员公开。

如果您要查看已向其分配了特定存档策略的所有用户的列表，则可以使用如下命令，此命令返回已将 ExchangeArchivingPolicy 属性设置为“未初始化”的所有用户的 Active Directory 显示名称：

```powershell
Get-CsUser | Where-Object {$_.ExchangeArchivingPolicy -eq "Uninitialized"} | Select-Object DisplayName
```

同样，此命令也返回尚未将 ExchangeArchivingPolicy 属性设置为 UseLyncArchivingPolicy 的用户的显示名称：

```powershell
Get-CsUser | Where-Object {$_.ExchangeArchivingPolicy -ne "UseLyncArchivingPolicy"} | Select-Object DisplayName
```