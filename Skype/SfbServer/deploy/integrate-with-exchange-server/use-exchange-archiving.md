---
title: Skype 的业务服务器 2015 使用 Exchange Server 存档配置
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
description: 摘要： 为业务服务器 2015 Exchange Server 2016年或 Exchange Server 2013年和 Skype 配置 IM 聊天记录。
ms.openlocfilehash: 280b86d223cc1dd90eb7fe7bc17e4ab3499e7f5d
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="configure-skype-for-business-server-2015-to-use-exchange-server-archiving"></a>Skype 的业务服务器 2015 使用 Exchange Server 存档配置
 
**摘要：**配置 Exchange Server 2016年或 Exchange Server 2013年和 Skype 的业务服务器 2015 IM 聊天记录。
  
Skype 的业务服务器 2015年使管理员拥有即时消息和 Web 会议记录存档到用户的 Exchange Server 2016年或 Exchange Server 2013年邮箱，而不是 SQL Server 数据库的选项。 如果启用此选项，则会将脚本写入用户邮箱中的“清除”文件夹。 “清除”文件夹是“可恢复邮件”文件夹下的一个隐藏文件夹。 此文件夹，但不是最终用户可见文件夹通过 Exchange 搜索引擎索引，可以通过使用 Exchange 邮箱搜索和/或 Microsoft SharePoint Server 2013 发现。 因为 Exchange 就地保存功能 （负责归档电子邮件和其他 Exchange 通信） 使用相同的文件夹中存储信息，管理员可以使用单个工具搜索所有电子通信存档用户。
  
> [!IMPORTANT]
> 要完全禁用对话存档，您还必须禁用对话历史记录。 有关详细信息，请参阅下面的主题：[管理内部和外部通信业务服务器 2015年的 Skype 的存档](http://technet.microsoft.com/library/6c2cf941-3204-4f1a-a7e0-416c828056d9.aspx)、[新建 CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicy?view=skype-ps)和[一组 CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps)。 
  
若要存档到 Exchange Server 必须首先配置服务器的身份验证，Skype 业务服务器和 Exchange Server 之间的聊天记录。 服务器到服务器的身份验证的位置后，可以再执行以下任务在 Skype 业务服务器 （请注意，这取决于您的安装和配置，您可能不需要完成所有这些任务）：
  
1. 启用 Exchange 归档通过修改您 Skype 业务服务器存档配置设置。 此步骤是所有部署必需的。
    
2. 为用户的内部和/或外部通信启用存档。此步骤是所有部署必需的。
    
3. 为每个用户配置 ExchangeArchivingPolicy 属性。 此步骤才是必需的业务服务器和 Exchange Server 的 Skype 都位于不同的目录林中。
    
## <a name="step-1-enabling-exchange-archiving"></a>步骤 1： 启用 Exchange 归档

在 Skype 归档业务服务器的主要使用存档配置设置进行管理。 业务服务器安装 Skype 时则自动进行这些设置单一的全球集合。 （管理员可以 （可选） 创建新的存档设置的集合在站点范围内）。默认情况下，不在全局设置中，启用存档也交换存档启用这些设置。 要使用 Exchange 归档，管理员必须配置这些配置设置 EnableArchiving 和 EnableExchangeArchiving 属性。 EnableArchiving 属性可以设置为以下三个可能的值之一：
  
- **无**。 禁用存档。 这是默认值。 如果 EnableArchiving 设置为无，则任何将在存档您的 Skype，业务服务器存档数据库，或者 Exchange Server。
    
- **ImOnly**。 仅存档即时消息脚本。 如果启用 Exchange 归档，则这些记录将在 Exchange Server 存档。 如果禁用了 Exchange 归档然后这些记录将被归档到 Skype 业务服务器。
    
- **ImAndWebConf**。 将存档即时消息脚本和 Web 会议脚本。 如果启用了存档 Exchange 将在 Exchange Server 存档这些抄本。 如果禁用了 Exchange 归档然后这些记录将被归档到 Skype 业务服务器。
    
EnableExchangeArchiving 属性是一个布尔值： False ($False) 以禁用 Exchange 归档到设置为 True 以启用 Exchange 归档或设置 EnableExchangeArchiving ($True) 的 EnableExchangeArchiving。 例如，此命令启用存档即时消息聊天记录，并还可帮助实现 Exchange 归档：
  
```
Set-CsArchivingConfiguration -Identity "global" -EnableArchiving ImOnly -EnableExchangeArchiving $True
```

要禁用 Exchange 归档，请使用类似于以下内容，这使即时消息存档，但禁用存档到 Exchange 的命令 （换句话说，聊天记录将被归档到 Skype 业务服务器）：
  
```
Set-CsArchivingConfiguration -Identity "global" -EnableArchiving ImOnly -EnableExchangeArchiving $False
```

> [!NOTE]
> 如果将 EnableArchiving 属性设置为 None，然后 Skype 业务服务器将不进行存档即时消息和 Web 会议抄本根本。 在本例中，服务器只会忽略为 EnableExchangeArchiving 配置的值。 
  
Exchange 归档可以还启用 （或禁用） 通过 Skype 业务服务器。 为此，请完成以下过程：
  
1. 在控制面板中，单击“**监控和存档**”，然后单击“**存档配置**”。 
    
2. 在“**存档配置**”选项卡上，双击要修改的存档设置集合（例如“**全局**”集合）。
    
3. 在“**编辑存档设置**”窗格中，单击“**存档设置**”下拉列表并选择“**存档 IM 会话**”（仅存档即时消息会话）或“**存档 IM 和 Web 会议会话**”（存档即时消息和 Web 会议会话）。
    
4. 选择要存档的项目之后, 选择**Exchange Server 集成**复选框以启用 Exchange 归档。 若要禁用 Exchange 归档，请清除此复选框。
    
> [!NOTE]
> 如果“**存档设置**”设置为“**禁用存档**”，则“**Exchange Server 集成**”复选框不可用。 必须启用归档的第一个，然后启用 Exchange 归档。 
  
如果 Skype 业务服务器和 Exchange Server 都位于同一个目录林中，然后存档为单个用户 （或至少具有电子邮件的用户的帐户在 Exchange Server） 通过使用 Exchange 的就地保留策略管理。 如果您有穴然后存档的用户的 Exchange 的早期版本的用户将通过 Skype 业务服务器归档策略管理。 请注意，仅在 Exchange Server 2016年或 Exchange Server 2013年帐户的用户可以归档到 Exchange 的业务记录为其 Skype。
  
如果单个用户的存档由配置的 ExchangeArchivingPolicy 属性的每个用户帐户，然后 Skype 业务服务器和 Exchange Server 都位于不同的目录林中。 请参阅步骤 3 以了解更多信息。
  
## <a name="step-2-enabling-the-archiving-of-internal-andor-external-communications"></a>步骤 2：启用内部和/或外部通信的存档

在启用了存档 （并交换归档后） 必须然后修改相应的存档策略，以确保用户会话实际上已存档。 请注意只需启用存档 (步骤 1) 不会导致业务服务器开始存档即时消息和 Web 会议抄本的 Skype。 相反，您必须使用存档策略启用内部和/或外部存档。 当您为业务服务器安装 Skype 也安装单一的、 全局性的存档策略，其中包含两个属性：
  
- **ArchiveInternal**。当设置为 True ($True) 时，指示将存档仅涉及在贵组织中有 Active Directory 帐户的用户的内部通信会话。
    
- **ArchiveExternal**。当设置为 True ($True) 时，指示将存档内部通信会话（涉及至少一个在贵组织中没有 Active Directory 帐户的用户的会话）。
    
默认情况下，这两个属性的值都设置为 False，意味着既不存档内部通信会话也不存档外部通信会话。 要修改全局策略，可以为业务服务器管理外壳程序和一组 CsArchivingPolicy cmdlet 使用 Skype。 此命令可对内部和外部通信会话进行存档：
  
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

也可以通过 Skype 业务服务器控制面板管理归档策略。 在控制面板中，单击“**监控和存档**”，然后单击“**存档策略**”。 若要修改现有策略，请双击该策略（例如“全局”），然后在“**编辑存档策略**”窗格中，根据需要选中或清除“**存档内部通信**”和“**存档外部通信**”复选框。 若要创建新的存档策略，单击**新建**，然后选择**站点策略**或**用户策略**。 如果您新建用户策略，则必须访问相应的用户帐户（从“**用户**”选项卡中）并为这些用户分配新策略。
  
## <a name="step-3-configuring-the-exchangearchivingpolicy-property"></a>步骤 3：配置 ExchangeArchivingPolicy 属性

如果 Skype 业务服务器和 Exchange Server 都位于不同的目录林中，则它不是足够只启用 Exchange 归档中的存档配置设置;它不会导致即时消息和 Web 会议抄本在 Exchange 进行存档。 相反，您必须在每个业务服务器用户帐户相关的 Skype 上配置 ExchangeArchivingPolicy 属性。 此属性可设置为以下四个可能的值之一：
  
1. **未初始化**。 指示，存档将基于用户的 Exchange 邮箱; 配置的适当保存设置如果就地保存尚未启用对用户的邮箱然后用户将拥有他或她邮件和 Web 存档在 Skype 业务服务器的会议记录。 
    
2. **UseLyncArchivingPolicy**。 指示应存档用户的即时消息和 Web 会议抄本，Skype 业务服务器而不是用交换。
    
3. **NoArchiving**。 指示根本不应存档用户的即时消息和 Web 会议脚本。 请注意，该设置将覆盖任何 Skype 业务服务器归档策略分配给该用户。
    
4. **ArchivingToExchange**。 指示用户的即时消息和 Web 会议记录应该无论在适当保存设置归档到 Exchange （或不具有） 已分配给该用户的邮箱。
    
例如，配置用户帐户，以便于交换始终存档即时消息和 Web 会议抄本可以为业务服务器管理外壳程序使用从 Skype 与以下类似的命令：
  
```
Set-CsUser -Identity "Ken Myer" -ExchangeArchivingPolicy ArchivingToExchange
```

如果要为一组用户（例如驻留在指定注册器池中的所有用户）设置同一存档策略，可以使用如下命令：
  
```
Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.litwareinc.com"} | Set-CsUser -ExchangeArchivingPolicy ArchivingToExchange
```

请注意，您必须使用 Skype 业务服务器管理外壳程序 （以及 Windows PowerShell） 为了配置 ExchangeArchivingPolicy 属性的值。 此属性不面临业务服务器管理员在 Skype。
  
如果您要查看已向其分配了特定存档策略的所有用户的列表，则可以使用如下命令，此命令返回已将 ExchangeArchivingPolicy 属性设置为“未初始化”的所有用户的 Active Directory 显示名称：
  
```
Get-CsUser | Where-Object {$_.ExchangeArchivingPolicy -eq "Uninitialized"} | Select-Object DisplayName
```

同样，此命令也返回尚未将 ExchangeArchivingPolicy 属性设置为 UseLyncArchivingPolicy 的用户的显示名称：
  
```
Get-CsUser | Where-Object {$_.ExchangeArchivingPolicy -ne "UseLyncArchivingPolicy"} | Select-Object DisplayName
```


