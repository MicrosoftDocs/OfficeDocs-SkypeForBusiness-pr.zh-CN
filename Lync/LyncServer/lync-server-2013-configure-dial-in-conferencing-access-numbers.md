---
title: Lync Server 2013：配置电话拨入式会议访问号码
description: Lync Server 2013：配置电话拨入式会议访问号码。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure dial-in conferencing access numbers
ms:assetid: d8a18030-f318-43dd-834d-70e5014b5e8a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398952(v=OCS.15)
ms:contentKeyID: 48185623
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0edb3492c243b36b69c4b48df8c22adc4ece7999
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565077"
---
# <a name="configure-dial-in-conferencing-access-numbers-in-lync-server-2013"></a>在 Lync Server 2013 中配置电话拨入式会议访问号码

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2011-07-17_

当您部署电话拨入式会议时，您需要设置用户可以从公用电话交换网 (PSTN) 拨号的电话号码，以加入会议的音频部分。 这些拨入访问号码将显示在会议邀请和电话拨入式会议设置网页中。

在创建电话拨入访问号码之前，必须先规划电话拨入式会议区域，然后再配置区域的拨号计划。 有关区域的详细信息，请参阅规划文档中的 [Lync Server 2013 中的电话拨入式会议要求](lync-server-2013-dial-in-conferencing-requirements.md) 。 有关为电话拨入式会议配置拨号计划的详细信息，请参阅 [在 Lync Server 2013 中为电话拨入式会议配置拨号计划](lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md)。

<div>


> [!NOTE]  
> 在 Active Directory 域服务 (AD &nbsp; DS) 此访问号码的复制已完成之前，不能使用新的拨入访问号码。 复制可能需要几个小时才能完成。



</div>

<div>


> [!NOTE]  
> 创建电话拨入访问号码后，可以修改 Active Directory 联系人对象的显示名称，以便用户可以更轻松地识别正确的访问号码。 使用 <STRONG>set-csdialinconferencingaccessnumber</STRONG> cmdlet 可以修改显示名称。 您不应手动修改 Active Directory 对象。 有关修改访问号码的详细信息，请参阅 Lync Server 命令行管理程序文档中的 <STRONG>set-csdialinconferencingaccessnumber</STRONG> cmdlet。



</div>

<div>

## <a name="in-this-section"></a>本部分内容

[在 Lync Server 2013 中创建或修改电话拨入式会议访问号码](lync-server-2013-create-or-modify-a-dial-in-conferencing-access-number.md)

</div>

<div>

## <a name="see-also"></a>另请参阅


[Lync Server 2013 中的电话拨入式会议要求](lync-server-2013-dial-in-conferencing-requirements.md)  


[在 Lync Server 2013 中配置电话拨入式会议的拨号计划](lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

