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

# <a name="migrate-address-book"></a><span data-ttu-id="263b1-102">迁移通讯簿</span><span class="sxs-lookup"><span data-stu-id="263b1-102">Migrate Address Book</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="263b1-103">_**主题上次修改时间:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="263b1-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="263b1-104">**迁移通讯簿自定义规范化规则**</span><span class="sxs-lookup"><span data-stu-id="263b1-104">**To migrate Address Book customized normalization rules**</span></span>

1.  <span data-ttu-id="263b1-105">在 "通讯\_簿\_"\_共享\_文件夹的根中查找公司电话号码规范化规则 .Txt 文件, 并将其复制到 Lync Server 2013 试验池中的 "通讯簿" 共享文件夹的根。</span><span class="sxs-lookup"><span data-stu-id="263b1-105">Find the Company\_Phone\_Number\_Normalization\_Rules.txt file in the root of the Address Book shared folder, and copy it to the root of the Address Book shared folder in your Lync Server 2013 pilot pool.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="263b1-106">示例通讯簿规范化规则已安装在你的 ABS Web 组件文件目录中。</span><span class="sxs-lookup"><span data-stu-id="263b1-106">The sample Address Book normalization rules have been installed in your ABS Web component file directory.</span></span> <span data-ttu-id="263b1-107">路径为<STRONG>$installedDriveLetter: \Program Files\Microsoft Lync Server 2013 \ Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules。</STRONG></span><span class="sxs-lookup"><span data-stu-id="263b1-107">The path is <STRONG>$installedDriveLetter:\Program Files\Microsoft Lync Server 2013\Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules.txt,</STRONG>.</span></span> <span data-ttu-id="263b1-108">可以将此文件作为&nbsp; <STRONG>Company_Phone_Number_Normalization_Rules</STRONG> &nbsp;复制和重命名为通讯簿共享文件夹的根目录。</span><span class="sxs-lookup"><span data-stu-id="263b1-108">This file can be copied and renamed as &nbsp;<STRONG>Company_Phone_Number_Normalization_Rules.txt</STRONG> &nbsp;to the address book shared folder’s root directory.</span></span> <span data-ttu-id="263b1-109">例如, <STRONG>$serverX</STRONG>中共享的通讯簿,&nbsp;路径将类似于: <STRONG> \\$serverX \LyncFileShare\2-WebServices-1\ABFiles</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="263b1-109">For example, the address book shared in <STRONG>$serverX</STRONG>,&nbsp;the path will be similar to: <STRONG>\\$serverX \LyncFileShare\2-WebServices-1\ABFiles</STRONG>.</span></span>

    
    </div>

2.  <span data-ttu-id="263b1-110">使用文本编辑器 (如记事本) 打开\_公司电话\_号码\_规范化\_规则 .txt 文件。</span><span class="sxs-lookup"><span data-stu-id="263b1-110">Use a text editor, such as Notepad, to open the Company\_Phone\_Number\_Normalization\_Rules.txt file.</span></span>

3.  <span data-ttu-id="263b1-111">某些类型的条目在 Lync Server 2013 中将无法正常工作。</span><span class="sxs-lookup"><span data-stu-id="263b1-111">Certain types of entries will not work correctly in Lync Server 2013.</span></span> <span data-ttu-id="263b1-112">查看该文件以了解本步骤中所述的条目类型, 根据需要对其进行编辑, 并将更改保存到你的试点池中的 "通讯簿" 共享文件夹中。</span><span class="sxs-lookup"><span data-stu-id="263b1-112">Look through the file for the types of entries described in this step, edit them as necessary, and save the changes to the Address Book shared folder in your pilot pool.</span></span>
    
    <span data-ttu-id="263b1-113">包含所需的空格或标点的字符串将导致规范化规则失败, 因为这些字符将从输入到规范化规则的字符串中去除。</span><span class="sxs-lookup"><span data-stu-id="263b1-113">Strings that include required whitespace or punctuation cause normalization rules to fail because these characters are stripped out of the string that is input to the normalization rules.</span></span> <span data-ttu-id="263b1-114">如果你有包含必需的空格或标点的字符串, 则需要修改这些字符串。</span><span class="sxs-lookup"><span data-stu-id="263b1-114">If you have strings that include required whitespace or punctuation, you need to modify the strings.</span></span> <span data-ttu-id="263b1-115">例如, 以下字符串将导致规范化规则失败:</span><span class="sxs-lookup"><span data-stu-id="263b1-115">For example, the following string would cause the normalization rule to fail:</span></span>
    
        \s*\(\s*\d\d\d\s*\)\s*\-\s*\d\d\d\s*\-\s*\d\d\d\d
    
    <span data-ttu-id="263b1-116">以下字符串不会导致规范化规则失败:</span><span class="sxs-lookup"><span data-stu-id="263b1-116">The following string would not cause the normalization rule to fail:</span></span>
    
        \s*\(?\s*\d\d\d\s*\)?\s*\-?\s*\d\d\d\s*\-?\s*\d\d\d\d

</div>

<span> </span>

</div>

</div>

</div>

