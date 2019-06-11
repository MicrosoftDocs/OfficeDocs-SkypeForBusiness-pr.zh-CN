---
title: 迁移拨入访问号码
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migrate dial-in access numbers
ms:assetid: 568a94b7-a697-4ab2-9008-dc9ecc1c87c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204898(v=OCS.15)
ms:contentKeyID: 48184171
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b86db6e669fd5f52827591c25e5bb237bd9ee012
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845217"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-dial-in-access-numbers"></a>迁移拨入访问号码

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-09-26_

迁移拨入访问号码需要两个步骤: 运行**CsLegacyConfiguration** cmdlet (在[导入策略和设置](import-policies-and-settings.md)中完成) 若要迁移拨号计划和其他拨入访问号码设置, 并运行**CsApplicationEndpoint** cmdlet 迁移联系人对象。

<div>

## <a name="to-migrate-dial-in-access-numbers"></a>迁移拨入访问号码

1.  打开 Office 通信服务器 2007 R2 管理工具。

2.  在控制台树中, 右键单击 "林" 节点, 单击 "**属性**", 然后单击 "**会议助理属性**"。

3.  在 "**访问电话号码**" 选项卡上, 单击 "**按池服务**" 以按其关联的池对访问电话号码进行排序, 并确定要从中迁移的池的所有访问号码。

4.  若要标识每个访问号码的 SIP URI, 请双击访问号码以打开 "**编辑会议助理号码**" 对话框, 然后查看 " **SIP URI**" 下的对话框。

5.  打开 Lync Server 命令行管理程序。

6.  若要将每个拨入访问号码移动到 Lync Server 2013 上托管的池, 请运行:
    
        Move-CsApplicationEndpoint -Identity <SIP URI of the access number to be moved> -Target <FQDN of the pool to which the access number is moving>

7.  在 Office 通信服务器 2007 R2 管理工具中的 "**访问电话号码**" 选项卡上, 验证你要从中迁移的 Office 通信服务器 2007 R2 池不保留拨入访问号码。

</div>

</div>

<span> </span>

</div>

</div>

</div>

