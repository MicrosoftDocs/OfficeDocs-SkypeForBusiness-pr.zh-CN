---
title: Lync Server 2013：验证架构复制
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verifying schema replication
ms:assetid: ad01a7cf-aa79-4648-ba5a-a7a09172db36
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412822(v=OCS.15)
ms:contentKeyID: 48185124
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 41cb48da1711cfa6eb29a90f19a9b6e42b110c52
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007291"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verifying-active-directory-schema-replication-in-lync-server-2013"></a>在 Lync Server 2013 中验证 Active Directory 架构复制

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-29_

在运行林准备之前，请手动验证架构分区是否已复制。

<div>

## <a name="to-manually-verify-schema-replication"></a>手动验证架构复制

1.  以 Enterprise Admins 组成员的身份登录到域控制器。

2.  依次单击 **“开始”**、**“管理工具”**、**“ADSI Edit”** 以打开 ADSI Edit。
    
    <div>
    

    > [!TIP]  
    > 此外，还可以从命令行运行 <STRONG>adsiedit.msc</STRONG>。

    
    </div>

3.  在 Microsoft 管理控制台 (MMC) 树中，单击 **“ADSI Edit”**（如果尚未选中）。

4.  在 **“操作”** 菜单上，单击 **“连接到”**。

5.  在 **“连接设置”** 对话框中的 **“选择一个已知命名上下文”** 下，选择 **“架构”**，然后单击 **“确定”**。

6.  在架构容器下，搜索“CN=ms-RTC-SIP-SchemaVersion”。 如果此对象存在，并且 **rangeUpper** 属性的值为 1150，**rangeLower** 属性的值为 3，则说明架构更新和复制成功。 如果此对象不存在，或 **rangeUpper** 和 **rangeLower** 属性的值不是指定的值，则说明架构未经过修改或尚未复制。

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中运行 Active Directory 架构准备](lync-server-2013-running-schema-preparation.md)  


[在 Lync Server 2013 中准备 Active Directory 架构](lync-server-2013-preparing-the-active-directory-schema.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

