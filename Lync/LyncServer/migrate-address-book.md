---
title: 迁移通讯簿
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrate Address Book
ms:assetid: ac7f0f39-4c6d-4702-8e25-93a73e3d800f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205160(v=OCS.15)
ms:contentKeyID: 48185064
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a3282315d50b0a5075afc380487fb9204d4285c8
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529899"
---
# <a name="migrate-address-book"></a>迁移通讯簿

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-09_

通常情况下，会将 Lync Server 2010 通讯簿与拓扑的其余部分一起迁移。 但是，如果您在 Lync Server 2010 环境中自定义了以下各项，则可能需要执行某些迁移后步骤：

  - 将 **PartitionbyOU** WMI 属性设置为按组织单位 (OU) 对通讯簿条目进行分组。

  - 自定义了通讯簿规范化规则。

  - 将 **UseNormalizationRules** 参数的默认值更改为 False。

**分组的通讯簿条目**

如果将 **PartitionbyOU** WMI 属性设置为 True 以针对每个 OU 创建通讯簿，并且您希望继续对通讯簿条目分组，则需要设置用户和联系人的 **msRTCSIP-GroupingId** Active Directory 属性。您可能希望对通讯簿条目分组以限制通讯簿的搜索范围。要使用 **msRTCSIP-GroupingId** 属性，请编写用于填充该属性的脚本，向您希望组合在一起的所有用户分配相同的值。例如，向一个 OU 中的所有用户分配一个值。

**通讯簿规范化规则**

如果您在 Lync Server 2010 环境中自定义了通讯簿规范化规则，则必须将自定义规则迁移到您的引导池。 如果未自定义通讯簿规范化规则，则通讯簿服务没有要迁移的内容。 Lync Server 2013 的默认规范化规则与 Lync Server 2010 的默认规则相同。 按照本节后面的过程操作，迁移自定义的规范化规则。

<div>


> [!NOTE]  
> 如果您的组织使用远程呼叫控制并且您自定义了通讯簿规范化规则，则必须首先执行本主题中的过程，然后才能使用远程呼叫控制。要执行该过程，需要具有 RTCUniversalServerAdmins 组成员的身份或同等权限。



</div>

**UseNormalizationRules 设置为 False**

如果将 **UseNormalizationRules** 的值设置为 False，以便用户可以使用在 Active Directory 域服务中定义的电话号码，而不使用 Lync Server 2013 应用规范化规则，则需要将 **UseNormalizationRules** 和 **IgnoreGenericRules** 参数设置为 True。 按照本节后面的过程操作，将这些参数设置为 True。

<div>

## <a name="to-migrate-address-book-customized-normalization-rules"></a>迁移通讯簿自定义规范化规则

1.  \_ \_ \_ \_ 在通讯簿共享文件夹的根目录中查找公司电话号码规范化Rules.txt 文件，并将其复制到 Lync Server 2013 试点池中的通讯簿共享文件夹的根目录中。
    
    <div>
    

    > [!NOTE]  
    > 示例“通讯簿服务”规范化规则已安装在您的 ABS Web 组件文件目录中。 路径为 <STRONG>$installedDriveLetter:\Program Files\Microsoft Lync Server 2013\Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules.txt</STRONG>。 可以将此文件作为Company_Phone_Number_Normalization_Rules.txt复制和重命名为 &nbsp; <STRONG>Company_Phone_Number_Normalization_Rules.txt</STRONG> &nbsp; 通讯簿共享文件夹的根目录。 例如， <STRONG>$serverX</STRONG>中共享的通讯簿， &nbsp; 该路径将类似于： <STRONG> \\ $serverX \LyncFileShare\2-WebServices-1\ABFiles</STRONG>。

    
    </div>

2.  使用文本编辑器（如记事本）打开公司 \_ 电话 \_ 号码 \_ 规范化 \_Rules.txt 文件。

3.  在 Lync Server 2013 中，某些类型的条目将无法正常工作。 请在文件中查找该步骤中所述的这些条目类型，根据需要编辑它们，并将更改保存到试点池中的通讯簿共享文件夹。
    
    包含必要空格或标点的字符串会导致规范化规则失败，因为系统会将这些字符从输入到规范化规则的字符串中删除。如果您有包含必要空格或标点的字符串，则需要修改这些字符串。例如，以下字符串将导致规范化规则失败：
    
        \s*\(\s*\d\d\d\s*\)\s*\-\s*\d\d\d\s*\-\s*\d\d\d\d
    
    以下字符串不会导致规范化规则失败：
    
        \s*\(?\s*\d\d\d\s*\)?\s*\-?\s*\d\d\d\s*\-?\s*\d\d\d\d

</div>

<div>

## <a name="to-set-usenormalizationrules-and-ignoregenericrules-to-true"></a>将 UseNormalizationRules 和 IgnoreGenericRules 设置为 true

1.  启动 Lync Server 命令行管理程序：依次单击“开始”****、“所有程序”****、“Microsoft Lync Server 2013”**** 和“Lync Server 命令行管理程序”****。

2.  执行下列操作之一：
    
      - 如果您的部署仅包括 Lync Server 2013，请在全局级别运行以下 cmdlet，以将 **UseNormalizationRules** 和 **IgnoreGenericRules** 的值更改为 True：
        
            Set-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
    
      - 如果您的部署包括 Lync Server 2013 和 Lync Server 2010 或 Office 通信服务器 2007 R2 的组合，请运行以下 cmdlet，并将其分配给拓扑中的每个 Lync Server 2013 池：
        
            New-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true

3.  等待中央管理存储复制在所有池上进行。

4.  在您的部署中修改电话规范化规则文件 "公司 \_ 电话 \_ 号码 \_ 规范化 \_Rules.txt" 以清除内容。 文件位于每个 Lync Server 2013 池的文件共享中。 如果该文件不存在，则创建一个名为 "Company \_ Phone \_ Number \_ 正常化 \_Rules.txt" 的空文件。

5.  等待几分钟，让所有前端池都能读取新文件。

6.  在部署中的每个 Lync Server 2013 池中运行以下 cmdlet：
    
        Update-CsAddressBook

</div>

</div>

<span> </span>

</div>

</div>

</div>

