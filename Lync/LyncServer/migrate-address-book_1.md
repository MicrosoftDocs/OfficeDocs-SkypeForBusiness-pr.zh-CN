---
title: 迁移通讯簿
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migrate Address Book
ms:assetid: b6e000ce-8b2e-460c-8a8b-000254b9d778
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205198(v=OCS.15)
ms:contentKeyID: 48185218
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8dff13c31ecf203d6e6e4b60c22a3792475e403f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845226"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-address-book"></a>迁移通讯簿

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-10-02_

**迁移通讯簿自定义规范化规则**

1.  在 "通讯\_簿\_"\_共享\_文件夹的根中查找公司电话号码规范化规则 .Txt 文件, 并将其复制到 Lync Server 2013 试验池中的 "通讯簿" 共享文件夹的根。
    
    <div>
    

    > [!NOTE]  
    > 示例通讯簿规范化规则已安装在你的 ABS Web 组件文件目录中。 路径为<STRONG>$installedDriveLetter: \Program Files\Microsoft Lync Server 2013 \ Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules。</STRONG> 可以将此文件作为&nbsp; <STRONG>Company_Phone_Number_Normalization_Rules</STRONG> &nbsp;复制和重命名为通讯簿共享文件夹的根目录。 例如, <STRONG>$serverX</STRONG>中共享的通讯簿,&nbsp;路径将类似于: <STRONG> \\$serverX \LyncFileShare\2-WebServices-1\ABFiles</STRONG>。

    
    </div>

2.  使用文本编辑器 (如记事本) 打开\_公司电话\_号码\_规范化\_规则 .txt 文件。

3.  某些类型的条目在 Lync Server 2013 中将无法正常工作。 查看该文件以了解本步骤中所述的条目类型, 根据需要对其进行编辑, 并将更改保存到你的试点池中的 "通讯簿" 共享文件夹中。
    
    包含所需的空格或标点的字符串将导致规范化规则失败, 因为这些字符将从输入到规范化规则的字符串中去除。 如果你有包含必需的空格或标点的字符串, 则需要修改这些字符串。 例如, 以下字符串将导致规范化规则失败:
    
        \s*\(\s*\d\d\d\s*\)\s*\-\s*\d\d\d\s*\-\s*\d\d\d\d
    
    以下字符串不会导致规范化规则失败:
    
        \s*\(?\s*\d\d\d\s*\)?\s*\-?\s*\d\d\d\s*\-?\s*\d\d\d\d

</div>

<span> </span>

</div>

</div>

</div>

