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
ms.openlocfilehash: ee0dc4d50fb3b60d4f6a9581d497df11da630122
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/16/2020
ms.locfileid: "44757033"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrate-address-book"></a>迁移通讯簿

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-09_

通常情况下，会将 Lync Server 2010 通讯簿与拓扑的其余部分一起迁移。 但是，如果您在 Lync Server 2010 环境中自定义了以下各项，则可能需要执行某些迁移后步骤：

  - 将 **PartitionbyOU** WMI 属性设置为按组织单位 (OU) 对通讯簿条目进行分组。

  - 自定义了通讯簿规范化规则。

  - 将**UseNormalizationRules**参数的默认值更改为 False。

**分组的通讯簿条目**

If you set the **PartitionbyOU** WMI property to True to create address books for each OU, you need to set the **msRTCSIP-GroupingId** Active Directory attribute on users and contacts if you want to continue grouping address book entries. You might want to group address book entries to limit the scope of Address Book searches. To use the **msRTCSIP-GroupingId** attribute, write a script to populate the attribute, assigning the same value for all of the users that you want to group together. For example, assign a single value for all the users in an OU.

**通讯簿规范化规则**

如果您在 Lync Server 2010 环境中自定义了通讯簿规范化规则，则必须将自定义规则迁移到您的引导池。 如果未自定义通讯簿规范化规则，则通讯簿服务没有要迁移的内容。 Lync Server 2013 的默认规范化规则与 Lync Server 2010 的默认规则相同。 按照本节后面的过程操作，迁移自定义的规范化规则。

<div>


> [!NOTE]  
> If your organization uses remote call control and you customized Address Book normalization rules, you must perform the procedure in this topic before you can use remote call control. The procedure requires membership in the RTCUniversalServerAdmins group or equivalent rights.



</div>

**UseNormalizationRules 设置为 False**

如果将**UseNormalizationRules**的值设置为 False，以便用户可以使用在 Active Directory 域服务中定义的电话号码，而不使用 Lync Server 2013 应用规范化规则，则需要将**UseNormalizationRules**和**IgnoreGenericRules**参数设置为 True。 按照本节后面的过程操作，将这些参数设置为 True。

<div>

## <a name="to-migrate-address-book-customized-normalization-rules"></a>迁移通讯簿自定义规范化规则

1.  \_ \_ \_ \_ 在通讯簿共享文件夹的根目录中查找公司电话号码规范化Rules.txt 文件，并将其复制到 Lync Server 2013 试点池中的通讯簿共享文件夹的根目录中。
    
    <div>
    

    > [!NOTE]  
    > 示例“通讯簿服务”规范化规则已安装在您的 ABS Web 组件文件目录中。 路径为 <STRONG>$installedDriveLetter:\Program Files\Microsoft Lync Server 2013\Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules.txt</STRONG>。 可以将此文件作为Company_Phone_Number_Normalization_Rules.txt复制和重命名为 &nbsp; <STRONG>Company_Phone_Number_Normalization_Rules.txt</STRONG> &nbsp; 通讯簿共享文件夹的根目录。 例如， <STRONG>$serverX</STRONG>中共享的通讯簿， &nbsp; 该路径将类似于： <STRONG> \\ $serverX \LyncFileShare\2-WebServices-1\ABFiles</STRONG>。

    
    </div>

2.  使用文本编辑器（如记事本）打开公司 \_ 电话 \_ 号码 \_ 规范化 \_Rules.txt 文件。

3.  在 Lync Server 2013 中，某些类型的条目将无法正常工作。 请在文件中查找该步骤中所述的这些条目类型，根据需要编辑它们，并将更改保存到试点池中的通讯簿共享文件夹。
    
    Strings that include required whitespace or punctuation cause normalization rules to fail because these characters are stripped out of the string that is input to the normalization rules. If you have strings that include required whitespace or punctuation, you need to modify the strings. For example, the following string would cause the normalization rule to fail:
    
        \s*\(\s*\d\d\d\s*\)\s*\-\s*\d\d\d\s*\-\s*\d\d\d\d
    
    以下字符串不会导致规范化规则失败：
    
        \s*\(?\s*\d\d\d\s*\)?\s*\-?\s*\d\d\d\s*\-?\s*\d\d\d\d

</div>

<div>

## <a name="to-set-usenormalizationrules-and-ignoregenericrules-to-true"></a>将 UseNormalizationRules 和 IgnoreGenericRules 设置为 true

1.  启动 Lync Server 命令行管理程序：依次单击“开始”****、“所有程序”****、“Microsoft Lync Server 2013”**** 和“Lync Server 命令行管理程序”****。

2.  执行下列操作之一：
    
      - 如果您的部署仅包括 Lync Server 2013，请在全局级别运行以下 cmdlet，以将**UseNormalizationRules**和**IgnoreGenericRules**的值更改为 True：
        
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

