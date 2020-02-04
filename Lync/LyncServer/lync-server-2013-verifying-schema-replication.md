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
ms.openlocfilehash: e7ea90012c116bb66caf16313d930c6f05db4413
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742092"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verifying-active-directory-schema-replication-in-lync-server-2013"></a>在 Lync Server 2013 中验证 Active Directory 架构复制

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-10-29_

在运行林准备之前，手动验证架构分区是否已复制。

<div>

## <a name="to-manually-verify-schema-replication"></a>手动验证架构复制

1.  以企业管理员组的成员身份登录域控制器。

2.  单击 "**开始**"，单击 "**管理工具**"，然后单击 " **adsi 编辑**"，打开 "adsi 编辑"。
    
    <div>
    

    > [!TIP]  
    > 或者，可以从命令行运行<STRONG>adsiedit。</STRONG>

    
    </div>

3.  在 Microsoft 管理控制台（MMC）树中，如果尚未选中它，请单击 " **ADSI 编辑**"。

4.  在“**操作**”菜单上，单击“**连接到**”。

5.  在“**连接设置**”对话框中的“**选择一个已知命名上下文**”下，选择“**架构**”，然后单击“**确定**”。

6.  在架构容器下，搜索“CN=ms-RTC-SIP-SchemaVersion”。 如果此对象存在，并且**rangeUpper**属性的值为1150，并且**rangeLower**属性的值为3，则架构已成功更新和复制。 如果此对象不存在，或者**rangeUpper**和**rangeLower**属性的值不是指定的，则架构未被修改或未复制。

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

