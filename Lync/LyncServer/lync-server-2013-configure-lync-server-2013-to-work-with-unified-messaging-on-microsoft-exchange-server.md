---
title: Lync Server 2013：配置 Lync Server 2013 以使用 Microsoft Exchange Server 统一消息
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure Lync Server 2013 to work with Unified Messaging on Microsoft Exchange Server
ms:assetid: 1098ae4d-f57f-44f3-804e-39889d9fc14e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398193(v=OCS.15)
ms:contentKeyID: 48183430
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 27909f4ae6231b1452cbfefdd82e0a0eb107c6fa
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837361"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-lync-server-2013-to-work-with-unified-messaging-on-microsoft-exchange-server"></a>配置 Lync Server 2013 以使用 Microsoft Exchange Server 统一消息

</div>

<div id="mainSection">

<div id="mainBody">

_**主题上次修改时间:** 2013-04-03_

此步骤需要 Exchange UM 集成实用工具 (OcsUmUtil)。 此工具位于 Lync Server 2013 服务器的 "..."\\程序文件\\常见文件\\Microsoft Lync Server 2013\\支持文件夹。

<div>

## <a name="running-the-exchange-um-integration-utility"></a>运行 Exchange UM 集成实用工具

Exchange UM 集成实用工具必须从具有以下特征的用户帐户运行:

  - RTCUniversalServerAdmins 和 RtcUniversalUserAdmins 组中的成员身份 (包括读取 Exchange Server 统一消息设置的权限)。

  - 域内的用户权限, 用于在指定的组织单位 (OU) 容器中创建联系人对象。

运行 Exchange UM 集成实用工具时, 它将执行以下任务:

  - 为企业语音用户使用的每个自动助理和订阅者访问号码创建联系人对象。

  - 验证每个企业语音拨号计划的名称是否与其对应的统一消息 (UM) 拨号计划电话上下文相匹配。 只有当 UM 拨号计划运行于 Exchange 2010 Service Pack 1 (SP1)*之前*的 exchange 版本上时, 此匹配才是必需的。

> [!IMPORTANT]
> 在运行 Exchange UM 集成实用程序之前, 请确保已完成以下操作:
> <ul>
> <li><p>如 Exchange 产品文档中所述, 创建一个或多个 Exchange UM 拨号计划。</p>
> <p>对于 Microsoft Exchange Server 2010, 请&quot;参阅在上<a href="http://go.microsoft.com/fwlink/p/?linkid=186177">http://go.microsoft.com/fwlink/p/?linkId=186177</a>创建 UM&quot;拨号计划。</p>
> <p>对于 Microsoft Exchange Server 2007 Service Pack 1 (SP1), 请&quot;参阅如何在<a href="http://go.microsoft.com/fwlink/p/?linkid=185771">http://go.microsoft.com/fwlink/p/?linkId=185771</a>创建统一消息 SIP URI 拨号计划&quot; 。</p></li>
> <li><p>如在<a href="lync-server-2013-create-a-dial-plan.md">Lync server 2013 中创建拨号计划</a>中所述, 创建一个或多个相应的 Lync server 拨号计划。</p></li>
> <ul><li>如果你使用的是早于 Microsoft Exchange Server 2010 SP1 的 Exchange 版本, 则必须在 Lync Server 2013 拨号计划简单名称中输入相应 Exchange 统一消息 (UM) SIP 拨号计划的完全限定域名 (FQDN) <STRONG></STRONG>字段。 如果您使用的是 Microsoft Exchange Server 2010 SP1 或最新的 service pack, 则不需要此拨号计划名称匹配。</li></ul>
> <li>创建自动助理, 并确保订阅者访问号码和自动助理号码都采用的是电子164格式。</li></ul>


<div>

## <a name="to-run-the-exchange-um-integration-utility"></a>运行 Exchange UM 集成实用工具

1.  在前端服务器上, 打开命令提示符并键入 " **cd% CommonProgramFiles%\\Microsoft Lync Server 2013\\支持**", 然后按 ENTER。

2.  键入**OcsUmUtil**, 然后按 ENTER。

3.  单击 "**加载数据**" 以查找所有受信任的 Exchange 林。

4.  在 " **SIP 拨号计划**" 列表中, 选择要为其创建联系人对象的 UM SIP 拨号计划, 然后单击 "**添加**"。

5.  在 "**联系人**" 框中, 接受默认组织单位, 或单击 "**浏览**" 以启动**OU 选取器**。 在 " **OU 选取器**" 框中, 可以选择一个 OU 并单击 **"确定**", 也可以单击 "创建**新 ou** " 以在域的根或任何其他 OU 下 (例如, "OU = RTC 特殊帐户, dc = fourthcoffee, dc = com") 中创建新的组织单位。, 然后单击 **"确定"**。
    
    <div>
    

    > [!NOTE]  
    > 您已选择或创建的 OU 的可分辨名称 (DN) 现在将显示在 "<STRONG>组织单位</STRONG>" 框中。

    
    </div>

6.  在 "**名称**" 框中, 接受默认的拨号计划名称, 或为要创建的联系人对象键入新的显示名称。
    
    <div>
    

    > [!NOTE]  
    > 例如, 如果你要创建订阅者访问联系人对象, 你可能只是将其命名为订阅者访问。

    
    </div>

7.  在 " **SIP 地址**" 框中, 接受默认 sip 地址或键入新的 sip 地址。
    
    <div>
    

    > [!NOTE]  
    > 如果键入新的 SIP 地址, 它必须以 SIP 开头<STRONG>:</STRONG> (即, "SIP:" 包含冒号)。

    
    </div>

8.  在 "**服务器" 或 "池**" 列表中, 选择要在其中启用 contact 对象的标准版服务器或前端池。
    
    <div>
    

    > [!NOTE]  
    > 您选择的池最好是在其中部署了用户启用企业语音和 Exchange UM 的池。

    
    </div>

9.  在 "**电话号码**" 列表中, 选择 "**输入电话号码**" 或 "**使用 Exchange UM 中的此试点号码**", 然后输入电话号码。

10. 在 "**联系人类型**" 列表中, 选择要创建的联系人类型, 然后单击 **"确定"**。

11. 对要创建的其他联系人对象重复步骤1到10。
    
    <div>
    

    > [!NOTE]  
    > 您至少应为每个自动助理创建一个联系人。 如果需要外部访问, 还需要订阅者访问联系人并指定直接向内拨号 (已连接) 号码。

    
    </div>

</div>

若要验证是否已创建联系人对象, 请打开 "Active Directory 用户和计算机", 并选择创建这些对象的 OU。 联系人对象应显示在详细信息窗格中。

</div>

</div>

<span> </span>

</div>

</div>

</div>

