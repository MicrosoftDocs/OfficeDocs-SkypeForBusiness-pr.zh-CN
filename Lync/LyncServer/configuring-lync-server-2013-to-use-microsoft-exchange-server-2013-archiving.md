---
title: 配置 Lync Server 2013 以使用 Microsoft Exchange Server 2013 存档
description: 将 Lync Server 2013 配置为使用 Microsoft Exchange Server 2013 存档。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Lync Server 2013 to use Exchange Server 2013 archiving
ms:assetid: 260346d1-edc8-4a0c-8ad2-6c2401c3c377
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ679896(v=OCS.15)
ms:contentKeyID: 49557731
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 80b0673071ec38246e366fe7556b39bd495895d1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542938"
---
# <a name="configuring-microsoft-lync-server-2013-to-use-microsoft-exchange-server-2013-archiving"></a>配置 Microsoft Lync Server 2013 以使用 Microsoft Exchange Server 2013 存档

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2014-06-24_

Microsoft Lync Server 2013 为管理员提供了将即时消息和 Web 会议脚本存档到用户的 Microsoft Exchange Server 2013 邮箱（而不是 SQL Server 数据库）的选项。 如果启用此选项，则会将脚本写入用户邮箱中的“清除”文件夹。 “清除”文件夹是“可恢复邮件”文件夹下的一个隐藏文件夹。 虽然此文件夹对最终用户不可见，但该文件夹由 Exchange 搜索引擎编制索引，并且可以使用 Exchange 邮箱搜索和/或 Microsoft SharePoint Server 2013 进行发现。 由于信息存储在 Exchange In-Place 保留功能所使用的同一文件夹中 (负责存档电子邮件和其他 Exchange 通信) ，因此管理员可以使用单个工具搜索为用户存档的所有电子通信。

<div>


> [!IMPORTANT]  
> 若要完全禁用 Lync 对话的存档，您还必须禁用 Lync 对话历史记录。 有关详细信息，请参阅下列主题：<A href="lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md">在 Lync Server 2013、set-csclientpolicy 和 set-csclientpolicy 中管理内部和外部通信的存档</A>。 <A href="https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy">New-CsClientPolicy</A> <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy">Set-CsClientPolicy</A>



</div>

必须先配置两台服务器之间的服务器到服务器身份验证，然后才能将脚本存档到 Exchange 2013。 在服务器到服务器的身份验证准备就绪后，可以在 Microsoft Lync Server 2013 中执行以下任务 (请注意，根据您的设置和配置，您可能不需要完成所有这些任务) ：

1.  通过修改 Lync Server 存档配置设置来启用 Exchange 存档。 此步骤是所有部署必需的。

2.  为用户的内部和/或外部通信启用存档。 此步骤是所有部署必需的。

3.  为每个用户配置 ExchangeArchivingPolicy 属性。 仅在 Lync Server 和 Exchange 位于不同林中时，才需要执行此步骤。

<div>

## <a name="step-1-enabling-exchange-archiving"></a>步骤1：启用 Exchange 存档

Lync Server 中的存档主要是通过使用存档配置设置进行管理。 在安装 Lync Server 2013 时，系统会自动为您提供这些设置的单个全局集合。  (管理员可以选择在站点范围创建新的存档设置集合。 ) 默认情况下，不会在全局设置中启用存档，也不会在这些设置中启用 Exchange 存档。 为了使用 Exchange 存档管理员，必须在这些配置设置中配置 EnableArchiving 和 EnableExchangeArchiving 属性。 EnableArchiving 属性可以设置为以下三个可能的值之一：

  - **无**。 禁用存档。 这是默认值。 如果将 EnableArchiving 设置为 None，则不会在 Lync Server 存档数据库或 Exchange 2013 中存档任何内容。

  - **ImOnly**。 仅存档即时消息脚本。 如果启用了 Exchange 存档，这些脚本将在 Exchange 2013 中存档。 如果禁用 Exchange 存档，则会将这些脚本存档到 Lync Server。

  - **ImAndWebConf**。 将存档即时消息脚本和 Web 会议脚本。 如果启用了 Exchange 存档，这些脚本将在 Exchange 2013 中存档。 如果禁用 Exchange 存档，则会将这些脚本存档到 Lync Server。

EnableExchangeArchiving 属性是一个布尔值：将 EnableExchangeArchiving 设置为 True ($True) 启用 Exchange 存档或将 EnableExchangeArchiving 设置为 False ($False) 以禁用 Exchange 存档。 例如，此命令启用即时消息脚本的存档，同时还启用 Exchange 存档：

    Set-CsArchivingConfiguration -Identity "global" -EnableArchiving ImOnly -EnableExchangeArchiving $True

若要禁用 Exchange 存档，请使用与以下内容类似的命令，这将启用即时消息存档，但也会禁用对 Exchange (的存档，也就是说，会将脚本存档到 Lync Server) ：

    Set-CsArchivingConfiguration -Identity "global" -EnableArchiving ImOnly -EnableExchangeArchiving $False

<div>


> [!NOTE]  
> 如果将 EnableArchiving 属性设置为 "无"，则 Lync Server 根本不会存档即时消息和 Web 会议脚本。 在本例中，服务器只会忽略为 EnableExchangeArchiving 配置的值。



</div>

还可以使用 Lync Server 控制面板 (或禁用) 启用 Exchange 存档。 为此，请完成以下过程：

1.  在控制面板中，单击“监控和存档”****，然后单击“存档配置”****。

2.  在“存档配置”**** 选项卡上，双击要修改的存档设置集合（例如“全局”**** 集合）。

3.  在“编辑存档设置”**** 窗格中，单击“存档设置”**** 下拉列表并选择“存档 IM 会话”****（仅存档即时消息会话）或“存档 IM 和 Web 会议会话”****（存档即时消息和 Web 会议会话）。

4.  选择要存档的项目后，选中 " **Exchange Server 集成** " 复选框以启用 exchange 存档。 若要禁用 Exchange 存档，请清除此复选框。

<div>


> [!NOTE]  
> 如果“存档设置”<STRONG></STRONG>设置为“禁用存档”<STRONG></STRONG>，则“Exchange Server 集成”<STRONG></STRONG>复选框不可用。 必须先启用存档，然后再启用 Exchange 存档。



</div>

如果 Lync Server 2013 和 Exchange 2013 位于同一个林中，则为单个用户存档 (或至少对在 Exchange 2013 上具有电子邮件帐户的用户) 使用 Exchange In-Place 保留策略进行管理。 如果你的用户驻留在以前版本的 Exchange 中，则将使用 Lync Server 存档策略管理这些用户的存档。 请注意，只有在 Exchange 2013 上具有帐户的用户才可以将其 Lync 脚本存档到 Exchange。

如果 Lync Server 2013 和 Exchange 2013 位于不同的林中，则通过为每个用户帐户配置 ExchangeArchivingPolicy 属性来管理单个用户的存档。 请参阅步骤 3 以了解更多信息。

</div>

<div>

## <a name="step-2-enabling-the-archiving-of-internal-andor-external-communications"></a>步骤 2：启用内部和/或外部通信的存档

在启用存档 (和 Exchange 存档之后) 之后，您必须修改相应的存档策略，以确保实际存档用户会话。 请注意，仅启用存档 (步骤 1) 不会导致 Lync Server 开始存档即时消息和 Web 会议脚本。 相反，您必须使用存档策略启用内部和/或外部存档。 当您安装 Lync Server 2013 时，还安装了一个包含两个属性的全局存档策略：

  - **ArchiveInternal**。当设置为 True ($True) 时，指示将存档仅涉及在贵组织中有 Active Directory 帐户的用户的内部通信会话。

  - **ArchiveExternal**。当设置为 True ($True) 时，指示将存档内部通信会话（涉及至少一个在贵组织中没有 Active Directory 帐户的用户的会话）。

默认情况下，这两个属性的值都设置为 False，意味着既不存档内部通信会话也不存档外部通信会话。 若要修改全局策略，您可以使用 Lync Server 命令行管理程序和 Set-CsArchivingPolicy cmdlet。 此命令可对内部和外部通信会话进行存档：

    Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True -ArchiveExternal $True

您也可以使用 New-CsArchivingPolicy 在站点范围或每用户范围创建一个新策略。例如，此命令可新建一个名为 RedmondArchivingPolicy 的每用户存档策略：

    New-CsArchivingPolicy -Identity "RedmondArchivingPolicy" -ArchiveInternal $True -ArchiveExternal $True

如果您创建每用户策略，您将需要将该策略分配给相应的用户。例如：

    Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName  "RedmondArchivingPolicy"

也可以使用 Lync Server 控制面板对存档策略进行管理。 在控制面板中，单击“监控和存档”****，然后单击“存档策略”****。 若要修改现有策略，请双击该策略（例如“全局”），然后在“编辑存档策略”**** 窗格中，根据需要选中或清除“存档内部通信”**** 和“存档外部通信”**** 复选框。 若要创建新的存档策略，请单击 " **新建** "，然后选择 " **站点策略** " 或 " **用户策略**"。 如果您新建用户策略，则必须访问相应的用户帐户（从“用户”**** 选项卡中）并为这些用户分配新策略。

</div>

<div>

## <a name="step-3-configuring-the-exchangearchivingpolicy-property"></a>步骤 3：配置 ExchangeArchivingPolicy 属性

如果 Lync Server 2013 和 Exchange 2013 位于不同的林中，则只需在存档配置设置中启用 Exchange 存档就足够了;这不会导致即时消息和 Web 会议脚本在 Exchange 中进行存档。 相反，您还必须在每个相关的 Lync Server 用户帐户上配置 ExchangeArchivingPolicy 属性。 此属性可设置为以下四个可能的值之一：

1.  即. 指示将基于为用户的 Exchange 邮箱配置的 In-Place 保留设置进行存档;如果未在用户的邮箱上启用 In-Place 保留，则用户将在 Lync Server 中存档其邮件和 Web 会议脚本。

2.  **UseLyncArchivingPolicy**。 指示应将用户的即时消息和 Web 会议脚本存档在 Lync Server 中，而不是在 Exchange 中进行存档。

3.  **NoArchiving**。 指示根本不应存档用户的即时消息和 Web 会议脚本。 请注意，此设置将覆盖分配给用户的任何 Lync Server 存档策略。

4.  **ArchivingToExchange**。 指示应将用户的即时消息和 Web 会议脚本存档到 Exchange，而不考虑 In-Place 保留已 (的设置或尚未将) 分配给用户邮箱的设置。

例如，若要将用户帐户配置为始终将即时消息和 Web 会议脚本存档到 Exchange，您可以在 Lync Server 命令行管理程序中使用类似下面的命令：

    Set-CsUser -Identity "Ken Myer" -ExchangeArchivingPolicy ArchivingToExchange

如果要为一组用户（例如驻留在指定注册器池中的所有用户）设置同一存档策略，可以使用如下命令：

    Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.litwareinc.com"} | Set-CsUser -ExchangeArchivingPolicy ArchivingToExchange

请注意，您必须使用 Lync Server 命令行管理程序 (和 Windows PowerShell) 才能配置 ExchangeArchivingPolicy 属性的值。 此属性不会向 Lync Server 控制面板中的管理员公开。

如果您要查看已向其分配了特定存档策略的所有用户的列表，则可以使用如下命令，此命令返回已将 ExchangeArchivingPolicy 属性设置为“未初始化”的所有用户的 Active Directory 显示名称：

    Get-CsUser | Where-Object {$_.ExchangeArchivingPolicy -eq "Uninitialized"} | Select-Object DisplayName

同样，此命令也返回尚未将 ExchangeArchivingPolicy 属性设置为 UseLyncArchivingPolicy 的用户的显示名称：

    Get-CsUser | Where-Object {$_.ExchangeArchivingPolicy -ne "UseLyncArchivingPolicy"} | Select-Object DisplayName

</div>

</div>

<span> </span>

</div>

</div>

</div>

