---
title: 迁移通讯簿
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrate Address Book
ms:assetid: ac7f0f39-4c6d-4702-8e25-93a73e3d800f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205160(v=OCS.15)
ms:contentKeyID: 48185064
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b678dea3e8ad7f05f82d28dfdd23ad9e45b38e92
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765280"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-address-book"></a>迁移通讯簿

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-10-09_

通常情况下，Lync Server 2010 通讯簿与拓扑的其余部分一起迁移。 但是，如果您在 Lync Server 2010 环境中自定义以下迁移步骤，则可能需要执行一些迁移后步骤：

  - 将**PartitionbyOU** WMI 属性设置为按组织单位（OU）对通讯簿条目分组。

  - 自定义通讯簿规范化规则。

  - 将**UseNormalizationRules**参数的默认值更改为 False。

**分组通讯簿条目**

如果将**PartitionbyOU** WMI 属性设置为 True 以为每个 OU 创建通讯簿，则需要在用户和联系人上设置**msRTCSIP-GroupingId** Active Directory 属性（如果要继续分组通讯簿条目）。 您可能希望对通讯簿条目进行分组以限制通讯簿搜索的范围。 若要使用**msRTCSIP-GroupingId**属性，请编写脚本来填充该属性，为要组合在一起的所有用户分配相同的值。 例如，为 OU 中的所有用户分配单个值。

**通讯簿规范化规则**

如果你在 Lync Server 2010 环境中自定义了通讯簿规范化规则，则必须将自定义规则迁移到你的试点池。 如果您没有自定义通讯簿规范化规则，则不能为通讯簿服务迁移任何内容。 Lync Server 2013 的默认规范化规则与 Lync Server 2010 的默认规则相同。 按照本部分后面的过程迁移自定义的规范化规则。

<div>


> [!NOTE]  
> 如果您的组织使用远程呼叫控制，并且您自定义了通讯簿规范化规则，则必须先执行本主题中的过程，然后才能使用远程呼叫控制。 该过程需要 RTCUniversalServerAdmins 组或等效权限中的成员身份。



</div>

**UseNormalizationRules 设置为 False**

如果将**UseNormalizationRules**的值设置为 False，以便用户可以使用在 Active Directory 域服务中定义的电话号码，而无需使用 Lync Server 2013 应用规范化规则，则需要将**UseNormalizationRules**和**IgnoreGenericRules**参数设置为 True。 按照本部分后面的过程将这些参数设置为 True。

<div>

## <a name="to-migrate-address-book-customized-normalization-rules"></a>迁移通讯簿自定义规范化规则

1.  在 "通讯\_簿\_"\_共享\_文件夹的根中查找公司电话号码规范化规则 .Txt 文件，并将其复制到 Lync Server 2013 试验池中的 "通讯簿" 共享文件夹的根。
    
    <div>
    

    > [!NOTE]  
    > 示例通讯簿规范化规则已安装在你的 ABS Web 组件文件目录中。 路径为<STRONG>$installedDriveLetter： \Program Files\Microsoft Lync Server 2013 \ Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules .txt</STRONG>。 可以将此文件作为&nbsp; <STRONG>Company_Phone_Number_Normalization_Rules</STRONG> &nbsp;复制和重命名为通讯簿共享文件夹的根目录。 例如， <STRONG>$serverX</STRONG>中共享的通讯簿，&nbsp;路径将类似于： <STRONG> \\$serverX \LyncFileShare\2-WebServices-1\ABFiles</STRONG>。

    
    </div>

2.  使用文本编辑器（如记事本）打开\_公司电话\_号码\_规范化\_规则 .txt 文件。

3.  某些类型的条目在 Lync Server 2013 中将无法正常工作。 查看该文件以了解本步骤中所述的条目类型，根据需要对其进行编辑，并将更改保存到你的试点池中的 "通讯簿" 共享文件夹中。
    
    包含所需的空格或标点的字符串将导致规范化规则失败，因为这些字符将从输入到规范化规则的字符串中去除。 如果你有包含必需的空格或标点的字符串，则需要修改这些字符串。 例如，以下字符串将导致规范化规则失败：
    
        \s*\(\s*\d\d\d\s*\)\s*\-\s*\d\d\d\s*\-\s*\d\d\d\d
    
    以下字符串不会导致规范化规则失败：
    
        \s*\(?\s*\d\d\d\s*\)?\s*\-?\s*\d\d\d\s*\-?\s*\d\d\d\d

</div>

<div>

## <a name="to-set-usenormalizationrules-and-ignoregenericrules-to-true"></a>将 UseNormalizationRules 和 IgnoreGenericRules 设置为 true

1.  启动 Lync Server 命令行管理程序：依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server Management shell**"。

2.  请执行下列操作之一：
    
      - 如果你的部署仅包括 Lync Server 2013，请在全局级别上运行以下 cmdlet，将**UseNormalizationRules**和**IgnoreGenericRules**的值更改为 True：
        
            Set-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
    
      - 如果你的部署包括 Lync Server 2013 和 Lync Server 2010 或 Office 通信服务器 2007 R2 的组合，请运行以下 cmdlet，并将其分配给拓扑中的每个 Lync Server 2013 池：
        
            New-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true

3.  等待中央管理存储复制在所有池上发生。

4.  修改电话规范化规则文件 "\_公司电话\_号码\_规范化\_规则 .txt"，以供你的部署清除内容。 该文件位于每个 Lync Server 2013 池的文件共享中。 如果文件不存在，则创建一个名为 "\_公司电话\_号码\_规范化\_规则 .txt" 的空文件。

5.  请等待几分钟，让所有前端池读取新文件。

6.  在部署中的每个 Lync Server 2013 池中运行以下 cmdlet：
    
        Update-CsAddressBook

</div>

</div>

<span> </span>

</div>

</div>

</div>

