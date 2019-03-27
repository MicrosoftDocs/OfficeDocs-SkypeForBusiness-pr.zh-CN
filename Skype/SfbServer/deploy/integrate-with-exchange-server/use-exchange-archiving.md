---
title: 配置 Business Server 使用 Exchange Server 存档的 Skype
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 260346d1-edc8-4a0c-8ad2-6c2401c3c377
description: 摘要： 配置 IM 脚本 Exchange Server 2016 或 Exchange Server 2013 和 Skype 业务服务器。
ms.openlocfilehash: 5db51f1206fee5ef3f87f16e73836a32c460234b
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30873484"
---
# <a name="configure-skype-for-business-server-to-use-exchange-server-archiving"></a>配置 Business Server 使用 Exchange Server 存档的 Skype

**摘要：** 配置 Exchange Server 2016 或 Exchange Server 2013 和 Skype 业务服务器 IM 脚本。

Skype 业务服务器为管理员提供了无即时消息和 Web 会议脚本存档到用户的 Exchange Server 2016 或 Exchange Server 2013 的邮箱，而不是 SQL Server 数据库的选项。 如果启用此选项，则会将脚本写入用户邮箱中的“清除”文件夹。 “清除”文件夹是“可恢复邮件”文件夹下的一个隐藏文件夹。 尽管此文件夹不是最终用户可见的文件夹由 Exchange 搜索引擎编制索引，并可以发现使用 Exchange 邮箱搜索和/或 Microsoft SharePoint Server 2013。 因为由 Exchange 就地保留功能 (存档电子邮件和其他 Exchange 通信 responsible) 的同一文件夹中存储的信息，管理员可以使用单一的工具可以搜索所有电子通信的存档用户。

> [!IMPORTANT]
> 要完全禁用对话存档，您还必须禁用对话历史记录。 有关详细信息，请参阅以下主题：[管理 Skype 业务服务器中的内部和外部通信的存档](https://technet.microsoft.com/library/6c2cf941-3204-4f1a-a7e0-416c828056d9.aspx)、 [New-csclientpolicy](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicy?view=skype-ps)和[Set-csclientpolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps)。

若要存档到 Exchange 服务器，必须首先 Skype 业务 server 和 Exchange 服务器之间配置服务器到服务器身份验证的脚本。 服务器到服务器身份验证后，您可以再执行 Skype 中的以下任务的业务服务器 （请注意，具体取决于您的安装和配置，您可能不需要完成这些任务的所有）：

1. 启用 Exchange 存档通过修改您 Skype 业务服务器存档配置设置。 此步骤是所有部署必需的。

2. 为用户的内部和/或外部通信启用存档。 此步骤是所有部署必需的。

3. 为每个用户配置 ExchangeArchivingPolicy 属性。 此步骤即告仅所需的业务 Server 和 Exchange Server 的 Skype 都位于不同的林中。

## <a name="step-1-enabling-exchange-archiving"></a>步骤 1： 启用 Exchange 存档

适用于业务 Server archiving Skype 中主要使用存档配置设置进行管理。 为业务服务器安装 Skype 时将自动授予这些设置的单个、 全局集合。 （管理员可以选择创建新的存档设置集在站点范围。）默认情况下，存档的全局设置中未启用也不 Exchange 存档启用这些设置中。 若要使用 Exchange 存档，管理员必须在这些配置设置中配置 EnableArchiving 和 EnableExchangeArchiving 属性。 EnableArchiving 属性可以设置为以下三个可能的值之一：

- **无**。 禁用存档。 这是默认值。 如果 EnableArchiving 设置为 None，则执行任何操作将在存档您 Skype，存档数据库的业务服务器或 Exchange 服务器中。

- **ImOnly**。 仅存档即时消息脚本。 如果启用 Exchange 存档，则这些脚本将存档在 Exchange 服务器中。 如果禁用 Exchange 存档然后这些脚本将存档到 Skype 业务服务器。

- **ImAndWebConf**。 将存档即时消息脚本和 Web 会议脚本。 如果启用 Exchange 存档，则这些脚本将存档在 Exchange 服务器中。 如果禁用 Exchange 存档然后这些脚本将存档到 Skype 业务服务器。

EnableExchangeArchiving 属性是一个布尔值： 为 False ($False) 若要禁用 Exchange 存档设置为 True ($True) 可启用 Exchange 存档设置 EnableExchangeArchiving EnableExchangeArchiving。 例如，此命令启用存档即时消息脚本，并还允许 Exchange 存档：

```
Set-CsArchivingConfiguration -Identity "global" -EnableArchiving ImOnly -EnableExchangeArchiving $True
```

若要禁用 Exchange 存档，请使用类似于以下内容，它们启用即时消息存档但禁用 exchange 存档命令 （换言之，脚本将存档到 Skype 业务 server）：

```
Set-CsArchivingConfiguration -Identity "global" -EnableArchiving ImOnly -EnableExchangeArchiving $False
```

> [!NOTE]
> 如果 EnableArchiving 属性设置为无，然后 Skype 业务服务器将不存档即时消息和 Web 会议脚本根本。 在本例中，服务器只会忽略为 EnableExchangeArchiving 配置的值。

Exchange 存档可以还启用 （或禁用） 使用 Skype 业务服务器。 为此，请完成以下过程：

1. 在控制面板中，单击“**监控和存档**”，然后单击“**存档配置**”。

2. 在“**存档配置**”选项卡上，双击要修改的存档设置集合（例如“**全局**”集合）。

3. 在“**编辑存档设置**”窗格中，单击“**存档设置**”下拉列表并选择“**存档 IM 会话**”（仅存档即时消息会话）或“**存档 IM 和 Web 会议会话**”（存档即时消息和 Web 会议会话）。

4. 选择后要存档的项目，选择**Exchange Server 集成**复选框以启用 Exchange 存档。 若要禁用 Exchange 存档，请清除此复选框。

> [!NOTE]
> 如果“**存档设置**”设置为“**禁用存档**”，则“**Exchange Server 集成**”复选框不可用。 您必须启用存档的第一，并启用 Exchange 存档。

通过使用 Exchange 就地保留策略管理如果 Business Server 和 Exchange Server 的 Skype 位于同一个林中，然后为各个用户存档 （或至少具有电子邮件的用户帐户的 Exchange 服务器上）。 如果您有用户驻留在以前版本的 Exchange 然后存档这些用户将使用 Skype Business Server 存档策略管理。 请注意，仅使用 Exchange Server 2016 或 Exchange Server 2013 上的帐户的用户可以具有业务脚本存档到 Exchange 其 Skype。

如果业务 Server 和 Exchange Server 的 Skype 位于在不同的林中，然后为各个用户存档所管理的配置 ExchangeArchivingPolicy 属性的每个用户帐户。 请参阅步骤 3 以了解更多信息。

## <a name="step-2-enabling-the-archiving-of-internal-andor-external-communications"></a>步骤 2：启用内部和/或外部通信的存档

在启用了存档 （和 Exchange 存档后） 然后必须修改相应的存档策略以确保用户会话实际已存档。 请注意只启用存档 (第 1 步) 不会导致 Skype 业务服务器开始存档即时消息和 Web 会议脚本。 相反，您必须使用存档策略启用内部和/或外部存档。 为业务服务器安装 Skype 时还会安装包含两个属性的单个、 全局存档策略：

- **ArchiveInternal**。当设置为 True ($True) 时，指示将存档仅涉及在贵组织中有 Active Directory 帐户的用户的内部通信会话。

- **ArchiveExternal**。当设置为 True ($True) 时，指示将存档内部通信会话（涉及至少一个在贵组织中没有 Active Directory 帐户的用户的会话）。

默认情况下，这两个属性的值都设置为 False，意味着既不存档内部通信会话也不存档外部通信会话。 若要修改全局策略，您可用于 Skype 业务 Server 命令行管理程序和 Set-csarchivingpolicy cmdlet。 此命令可对内部和外部通信会话进行存档：

```
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True -ArchiveExternal $True
```

您也可以使用 New-CsArchivingPolicy 在站点范围或每用户范围创建一个新策略。例如，此命令可新建一个名为 RedmondArchivingPolicy 的每用户存档策略：

```
New-CsArchivingPolicy -Identity "RedmondArchivingPolicy" -ArchiveInternal $True -ArchiveExternal $True
```

如果您创建每用户策略，您将需要将该策略分配给相应的用户。例如：

```
Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName  "RedmondArchivingPolicy"
```

也可以使用适用于业务 Server Control Panel Skype 管理存档策略。 在控制面板中，单击“**监控和存档**”，然后单击“**存档策略**”。 若要修改现有策略，请双击该策略（例如“全局”），然后在“**编辑存档策略**”窗格中，根据需要选中或清除“**存档内部通信**”和“**存档外部通信**”复选框。 若要创建新的存档策略，单击**新建**，然后选择**站点策略**或**用户策略**。 如果您新建用户策略，则必须访问相应的用户帐户（从“**用户**”选项卡中）并为这些用户分配新策略。

## <a name="step-3-configuring-the-exchangearchivingpolicy-property"></a>步骤 3：配置 ExchangeArchivingPolicy 属性

如果业务 Server 和 Exchange Server 的 Skype 位于不同的林中，则它不是足够只启用 Exchange 存档的存档配置设置;不会导致即时消息和 Web 会议脚本在 Exchange 存档。 相反，您还必须在每个企业服务器用户帐户相关的 Skype 配置 ExchangeArchivingPolicy 属性。 此属性可设置为以下四个可能的值之一：

1. **未初始化**。 指示将用户的 Exchange 邮箱; 配置的就地保留设置基于存档如果就地保留未然后用户将具有他/她消息和 Web 会议脚本存档中 Skype 业务服务器已启用对用户的邮箱。

2. **UseLyncArchivingPolicy**。 指示应存档用户的即时消息和 Web 会议脚本，Skype 业务服务器而不是 Exchange 中。

3. **NoArchiving**。 指示根本不应存档用户的即时消息和 Web 会议脚本。 请注意，此设置将覆盖的任何 Skype 业务服务器存档策略分配给用户。

4. **ArchivingToExchange**。 指示用户的即时消息和 Web 会议脚本应无论就地保留设置存档到 Exchange （或不具有） 已分配给用户的邮箱。

例如，配置的用户帐户，使即时消息和 Web 会议脚本总是存档到 Exchange 可以为业务 Server 命令行管理程序使用从 Skype 类似于以下命令：

```
Set-CsUser -Identity "Ken Myer" -ExchangeArchivingPolicy ArchivingToExchange
```

如果要为一组用户（例如驻留在指定注册器池中的所有用户）设置同一存档策略，可以使用如下命令：

```
Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.litwareinc.com"} | Set-CsUser -ExchangeArchivingPolicy ArchivingToExchange
```

请注意，您必须使用 Skype 业务 Server Management Shell （和 Windows PowerShell），才能配置 ExchangeArchivingPolicy 属性的值。 此属性不向管理员 Skype 公开业务服务器。

如果您要查看已向其分配了特定存档策略的所有用户的列表，则可以使用如下命令，此命令返回已将 ExchangeArchivingPolicy 属性设置为“未初始化”的所有用户的 Active Directory 显示名称：

```
Get-CsUser | Where-Object {$_.ExchangeArchivingPolicy -eq "Uninitialized"} | Select-Object DisplayName
```

同样，此命令也返回尚未将 ExchangeArchivingPolicy 属性设置为 UseLyncArchivingPolicy 的用户的显示名称：

```
Get-CsUser | Where-Object {$_.ExchangeArchivingPolicy -ne "UseLyncArchivingPolicy"} | Select-Object DisplayName
```


