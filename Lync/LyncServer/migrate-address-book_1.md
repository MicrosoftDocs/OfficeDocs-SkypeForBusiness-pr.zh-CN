---
title: 迁移通讯簿
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrate Address Book
ms:assetid: b6e000ce-8b2e-460c-8a8b-000254b9d778
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205198(v=OCS.15)
ms:contentKeyID: 48185218
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 52ca2b4882eec8b34ec07aa4e9365b6f444edd26
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42148941"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrate-address-book"></a>迁移通讯簿

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-02_

**迁移通讯簿自定义规范化规则**

1.  在通讯簿\_共享\_文件夹\_的\_根目录中查找公司电话号码规范化规则 .Txt 文件，并将其复制到 Lync Server 2013 试点池中的通讯簿共享文件夹的根目录中。
    
    <div>
    

    > [!NOTE]  
    > 示例“通讯簿服务”规范化规则已安装在您的 ABS Web 组件文件目录中。 路径为 <STRONG>$installedDriveLetter:\Program Files\Microsoft Lync Server 2013\Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules.txt</STRONG>。 可以将此文件复制并重命名为&nbsp; <STRONG>Company_Phone_Number_Normalization_Rules</STRONG> &nbsp;通讯簿共享文件夹的根目录。 例如， <STRONG>$serverX</STRONG>中共享的通讯簿，&nbsp;该路径将类似于： <STRONG> \\$serverX \LyncFileShare\2-WebServices-1\ABFiles</STRONG>。

    
    </div>

2.  使用文本编辑器（如记事本）打开\_公司电话\_号码\_规范化\_规则 .txt 文件。

3.  在 Lync Server 2013 中，某些类型的条目将无法正常工作。 请在文件中查找该步骤中所述的这些条目类型，根据需要编辑它们，并将更改保存到试点池中的通讯簿共享文件夹。
    
    包含必要空格或标点的字符串会导致规范化规则失败，因为系统会将这些字符从输入到规范化规则的字符串中删除。如果您有包含必要空格或标点的字符串，则需要修改这些字符串。例如，以下字符串将导致规范化规则失败：
    
        \s*\(\s*\d\d\d\s*\)\s*\-\s*\d\d\d\s*\-\s*\d\d\d\d
    
    以下字符串不会导致规范化规则失败：
    
        \s*\(?\s*\d\d\d\s*\)?\s*\-?\s*\d\d\d\s*\-?\s*\d\d\d\d

</div>

<span> </span>

</div>

</div>

</div>

