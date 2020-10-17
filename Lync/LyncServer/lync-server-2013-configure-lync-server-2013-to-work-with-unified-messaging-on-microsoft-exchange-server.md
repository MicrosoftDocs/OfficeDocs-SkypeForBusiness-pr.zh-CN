---
title: Lync Server 2013：将 Lync Server 2013 配置为在 Microsoft Exchange Server 上使用统一消息
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure Lync Server 2013 to work with Unified Messaging on Microsoft Exchange Server
ms:assetid: 1098ae4d-f57f-44f3-804e-39889d9fc14e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398193(v=OCS.15)
ms:contentKeyID: 48183430
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b297a505b1a12335e545895e0203ffc0e29c7354
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48507629"
---
# <a name="configure-lync-server-2013-to-work-with-unified-messaging-on-microsoft-exchange-server"></a>配置 Lync Server 2013 以使用 Microsoft Exchange Server 上的统一消息

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

_**上次修改的主题：** 2013-04-03_

此步骤需要使用 Exchange UM 集成实用程序 (OcsUmUtil.exe)。 此工具位于中的 Lync Server 2013 服务器上。。 \\程序文件 \\ \\ ： Microsoft Lync Server 2013 \\ 支持文件夹的常见文件。

<div>

## <a name="running-the-exchange-um-integration-utility"></a>运行 Exchange UM 集成实用程序

必须通过具有以下特征的用户帐户运行 Exchange UM 集成实用程序：

  - RTCUniversalServerAdmins 和 RtcUniversalUserAdmins 组中的成员身份（包含读取 Exchange Server 统一消息设置的权限）。

  - 域中的用户权限，用于在指定的组织单位 (OU) 容器中创建联系人对象。

运行 Exchange UM 集成实用程序时，该实用程序将执行以下任务：

  - 为要由企业语音用户使用的每个自动助理和订阅者访问号码创建联系人对象。

  - 验证每个企业语音拨号计划的名称是否都与其对应的统一消息 (UM) 拨号计划电话上下文相匹配。 只有在 UM 拨号计划运行在低于 Exchange 2010 Service Pack 1 (SP1) 的 *exchange 版本* 上时，此匹配才是必需的。

> [!IMPORTANT]
> 在运行 Exchange UM 集成实用工具之前，请确保已完成以下操作：
> <ul>
> <li><p>创建一个或多个 Exchange UM 拨号计划，如 Exchange 产品文档中所述。</p>
> <p>有关 Microsoft Exchange Server 2010，请参阅 &quot; 在上创建 UM 拨号计划 &quot; <a href="https://go.microsoft.com/fwlink/p/?linkid=186177">https://go.microsoft.com/fwlink/p/?linkId=186177</a> 。</p>
> <p>有关 Microsoft Exchange Server 2007 Service Pack 1 (SP1) ，请参阅 &quot; 如何在中创建统一消息 SIP URI 拨号 &quot; 计划 <a href="https://go.microsoft.com/fwlink/p/?linkid=185771">https://go.microsoft.com/fwlink/p/?linkId=185771</a> 。</p></li>
> <li><p>按照在 <a href="lync-server-2013-create-a-dial-plan.md">Lync server 2013 中创建拨号计划</a>中所述，创建一个或多个相应的 Lync server 拨号计划。</p></li>
> <ul><li>如果使用的是早于 Microsoft Exchange Server 2010 SP1 的 Exchange 版本，则必须在 "Lync Server 2013 拨号计划 <STRONG>简单名称</STRONG> " 字段中输入相应 Exchange 统一消息 () UM 拨号计划的完全限定的域名 (FQDN) 。 如果使用的是 Microsoft Exchange Server 2010 SP1 或最新的 service pack，则不需要此拨号计划名称匹配。</li></ul>
> <li>创建自动助理，并确保订阅者访问号码和自动助理号码的格式为 E.164。</li></ul>


<div>

## <a name="to-run-the-exchange-um-integration-utility"></a>运行 Exchange UM 集成实用程序

1.  在前端服务器上，打开命令提示符并键入 **cd% CommonProgramFiles% \\ Microsoft Lync Server 2013 \\ 支持**，然后按 ENTER。

2.  键入 **OcsUmUtil.exe**，然后按 Enter。

3.  单击 **“加载数据”** 以查找所有受信任的 Exchange 林。

4.  在 **“SIP 拨号计划”** 列表中，选择要为其创建联系人对象的 UM SIP 拨号计划，然后单击 **“添加”**。

5.  在 **“联系人”** 框中接受默认的组织单位，或单击 **“浏览”**，从而启动 **“OU 选取器”**。在 **“OU 选取器”** 框中，可以选择 OU 并单击 **“确定”**，也可以单击 **“新建 OU”**，在域中的根或任何其他 OU 下创建新的组织单位（例如“OU=RTC Special Accounts,DC=fourthcoffee,DC=com”），然后单击 **“确定”**。
    
    <div>
    

    > [!NOTE]  
    > 已选择或创建的 OU 的可分辨名称 (DN) 此时将显示在<STRONG>“组织单位”</STRONG>框中。

    
    </div>

6.  在 **“名称”** 框中接受默认的拨号计划名称，或为要创建的联系人对象键入新的显示名称。
    
    <div>
    

    > [!NOTE]  
    > 例如，如果要创建订阅者访问联系人对象，则可能只需简单地将其命名为“订阅者访问”。

    
    </div>

7.  在 **“SIP 地址”** 框中，接受默认 SIP 地址或键入新的 SIP 地址。
    
    <div>
    

    > [!NOTE]  
    > 如果键入新的 SIP 地址，该地址必须以 <STRONG>SIP:</STRONG> 开头（即“SIP:”，包括冒号）。

    
    </div>

8.  在 " **服务器或池** " 列表中，选择要在其中启用 contact 对象的 Standard Edition Server 或前端池。
    
    <div>
    

    > [!NOTE]  
    > 选择的池最好是部署启用了企业语音和 Exchange UM 的用户的同一个池。

    
    </div>

9.  在 **“电话号码”** 列表中，选择 **“输入电话号码”** 或 **“从 Exchange UM 中使用此引导号”**，然后输入电话号码。

10. 在 **“联系人类型”** 列表中，选择要创建的联系人类型，然后单击 **“确定”**。

11. 对于要创建的其他联系人对象，重复步骤 1 到 10。
    
    <div>
    

    > [!NOTE]  
    > 为每个自动助理应至少创建一个联系人。如果希望允许外部访问，还需要一个订阅者访问联系人并指定外线直拨分机 (DID) 号码。

    
    </div>

</div>

要验证是否已创建联系人对象，请打开“Active Directory 用户和计算机”，并选择在其中创建对象的 OU。联系人对象应在详细信息窗格中出现。

</div>

</div>

<span> </span>

</div>

</div>

</div>

