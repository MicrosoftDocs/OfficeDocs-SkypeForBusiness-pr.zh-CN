---
title: 迁移通讯簿
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrate Address Book
ms:assetid: b6e000ce-8b2e-460c-8a8b-000254b9d778
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205198(v=OCS.15)
ms:contentKeyID: 48185218
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 937bf9dfff07591ea12a2c78604ab82fa34e97f6
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/16/2020
ms.locfileid: "44757023"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrate-address-book"></a><span data-ttu-id="aa67a-102">迁移通讯簿</span><span class="sxs-lookup"><span data-stu-id="aa67a-102">Migrate Address Book</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aa67a-103">_**上次修改的主题：** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="aa67a-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="aa67a-104">**迁移通讯簿自定义规范化规则**</span><span class="sxs-lookup"><span data-stu-id="aa67a-104">**To migrate Address Book customized normalization rules**</span></span>

1.  <span data-ttu-id="aa67a-105">\_ \_ \_ \_ 在通讯簿共享文件夹的根目录中查找公司电话号码规范化Rules.txt 文件，并将其复制到 Lync Server 2013 试点池中的通讯簿共享文件夹的根目录中。</span><span class="sxs-lookup"><span data-stu-id="aa67a-105">Find the Company\_Phone\_Number\_Normalization\_Rules.txt file in the root of the Address Book shared folder, and copy it to the root of the Address Book shared folder in your Lync Server 2013 pilot pool.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="aa67a-106">示例“通讯簿服务”规范化规则已安装在您的 ABS Web 组件文件目录中。</span><span class="sxs-lookup"><span data-stu-id="aa67a-106">The sample Address Book normalization rules have been installed in your ABS Web component file directory.</span></span> <span data-ttu-id="aa67a-107">路径为 <STRONG>$installedDriveLetter:\Program Files\Microsoft Lync Server 2013\Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules.txt</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="aa67a-107">The path is <STRONG>$installedDriveLetter:\Program Files\Microsoft Lync Server 2013\Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules.txt,</STRONG>.</span></span> <span data-ttu-id="aa67a-108">可以将此文件作为Company_Phone_Number_Normalization_Rules.txt复制和重命名为 &nbsp; <STRONG>Company_Phone_Number_Normalization_Rules.txt</STRONG> &nbsp; 通讯簿共享文件夹的根目录。</span><span class="sxs-lookup"><span data-stu-id="aa67a-108">This file can be copied and renamed as &nbsp;<STRONG>Company_Phone_Number_Normalization_Rules.txt</STRONG> &nbsp;to the address book shared folder’s root directory.</span></span> <span data-ttu-id="aa67a-109">例如， <STRONG>$serverX</STRONG>中共享的通讯簿， &nbsp; 该路径将类似于： <STRONG> \\ $serverX \LyncFileShare\2-WebServices-1\ABFiles</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="aa67a-109">For example, the address book shared in <STRONG>$serverX</STRONG>,&nbsp;the path will be similar to: <STRONG>\\$serverX \LyncFileShare\2-WebServices-1\ABFiles</STRONG>.</span></span>

    
    </div>

2.  <span data-ttu-id="aa67a-110">使用文本编辑器（如记事本）打开公司 \_ 电话 \_ 号码 \_ 规范化 \_Rules.txt 文件。</span><span class="sxs-lookup"><span data-stu-id="aa67a-110">Use a text editor, such as Notepad, to open the Company\_Phone\_Number\_Normalization\_Rules.txt file.</span></span>

3.  <span data-ttu-id="aa67a-111">在 Lync Server 2013 中，某些类型的条目将无法正常工作。</span><span class="sxs-lookup"><span data-stu-id="aa67a-111">Certain types of entries will not work correctly in Lync Server 2013.</span></span> <span data-ttu-id="aa67a-112">请在文件中查找该步骤中所述的这些条目类型，根据需要编辑它们，并将更改保存到试点池中的通讯簿共享文件夹。</span><span class="sxs-lookup"><span data-stu-id="aa67a-112">Look through the file for the types of entries described in this step, edit them as necessary, and save the changes to the Address Book shared folder in your pilot pool.</span></span>
    
    <span data-ttu-id="aa67a-113">Strings that include required whitespace or punctuation cause normalization rules to fail because these characters are stripped out of the string that is input to the normalization rules.</span><span class="sxs-lookup"><span data-stu-id="aa67a-113">Strings that include required whitespace or punctuation cause normalization rules to fail because these characters are stripped out of the string that is input to the normalization rules.</span></span> <span data-ttu-id="aa67a-114">If you have strings that include required whitespace or punctuation, you need to modify the strings.</span><span class="sxs-lookup"><span data-stu-id="aa67a-114">If you have strings that include required whitespace or punctuation, you need to modify the strings.</span></span> <span data-ttu-id="aa67a-115">For example, the following string would cause the normalization rule to fail:</span><span class="sxs-lookup"><span data-stu-id="aa67a-115">For example, the following string would cause the normalization rule to fail:</span></span>
    
        \s*\(\s*\d\d\d\s*\)\s*\-\s*\d\d\d\s*\-\s*\d\d\d\d
    
    <span data-ttu-id="aa67a-116">以下字符串不会导致规范化规则失败：</span><span class="sxs-lookup"><span data-stu-id="aa67a-116">The following string would not cause the normalization rule to fail:</span></span>
    
        \s*\(?\s*\d\d\d\s*\)?\s*\-?\s*\d\d\d\s*\-?\s*\d\d\d\d

</div>

<span> </span>

</div>

</div>

</div>

