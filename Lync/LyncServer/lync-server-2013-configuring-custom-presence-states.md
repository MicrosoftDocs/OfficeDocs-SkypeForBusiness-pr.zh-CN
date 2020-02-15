---
title: Lync Server 2013：配置自定义状态状态
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring custom presence states
ms:assetid: e17364a8-8b93-45fc-a614-c80e45435d42
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398997(v=OCS.15)
ms:contentKeyID: 48185534
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 75e2e47af4951e98f21ea6b26572d39b5eebcb8d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046475"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-custom-presence-states-in-lync-server-2013"></a>在 Lync Server 2013 中配置自定义状态状态

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-01-10_

若要在 Lync 2013 中定义自定义状态状态，请创建 XML 自定义状态配置文件，然后使用 Lync Server 命令行管理程序 cmdlet **set-csclientpolicy**或**set-csclientpolicy**参数 CustomStateURL 指定其位置。

配置文件具有以下属性：

  - 自定义状态状态可配置为 "可用、忙碌和请勿打扰" 状态指示器。

  - Availability 属性确定哪个状态指标与自定义状态的状态文本相关联。 在本主题后面的示例中，"在家中工作的状态文本" 显示在 "绿色（可用）" 状态指示器的右侧。

  - 状态文本的最大长度为64个字符。

  - 最多可以添加四个自定义状态。

  - CustomStateURL 参数指定配置文件的位置。 在 Lync 2013 中，SIP 高安全模式默认处于启用状态，因此您需要将自定义状态配置文件存储在启用了 HTTPS 的 web 服务器上。 否则，Lync 2013 客户端将无法连接到它。 例如，有效的地址为`https://lspool.corp.contoso.com/ClientConfigFolder/CustomPresence.xml`。

<div>


> [!NOTE]  
> 虽然不建议在生产环境中使用，但您可以通过使用 EnableSIPHighSecurityMode 注册表设置在客户端上禁用 SIP 高安全模式来测试位于非 HTTPS 文件共享上的配置文件。 然后，您可以使用 CustomStateURL 注册表设置来指定配置文件的非 HTTPS 位置。 请注意，Lync 2013 采用 Lync 2010 注册表设置，但已更新注册表配置单元。 将创建注册表设置，如下所示： 
> <UL>
> <LI>
> <P>HKEY_LOCAL_MACHINE \SOFTWARE\Policies\Microsoft\Office\15.0\Lync\EnableSIPHighSecurityMode</P>
> <P>类型：DWORD</P>
> <P>值数据：0</P>
> <LI>
> <P>HKEY_LOCAL_MACHINE \SOFTWARE\Policies\Microsoft\Office\15.0\Lync\CustomStateURL</P>
> <P>类型： String （REG_SZ）</P>
> <P>值数据（示例）： file://\\lspool or file:///c:/LSFileShare/ClientConfigFolder/Group_1_Pres.xml</P></LI></UL>



</div>

通过在 XML 配置文件中指定一个或多个区域设置 ID （LCID）架构来本地化您的自定义状态状态。 本主题后面的示例演示如何本地化为英语-美国（1033）、挪威语（1044）、法语-法国（1036）和土耳其语（1055）。 有关 Lcid 的列表，请参阅由 Microsoft 分配的区域设置<http://go.microsoft.com/fwlink/p/?linkid=157331>id。

<div>

## <a name="to-add-custom-presence-states-to-lync-2013"></a>将自定义状态状态添加到 Lync 2013

1.  创建使用以下示例格式的 XML 配置文件：
    
        <?xml version="1.0"?>
        <customStates xmlns="http://schemas.microsoft.com/09/2009/communicator/customStates">
          <customState ID="1" availability="online">
            <activity LCID="1033">Working from Home</activity>
            <activity LCID="1044">activity 2 for 1044</activity>
            <activity LCID="1055">activity 3 for 1055</activity>
          </customState>
          <customState ID="2" availability="busy">
            <activity LCID="1033">In a Live Meeting</activity>
            <activity LCID="1036">Equivalent French String for - In a Live Meeting </activity>
          </customState>
          <customState ID="3" availability="busy">
            <activity LCID="1033">Meeting with Customer</activity>
            <activity LCID="1055">meeting with client</activity>
            <activity LCID="1036">Equivalent French String for - Meeting with Customer</activity>
          </customState>
          <customState ID="4" availability="do-not-disturb">
            <activity LCID="1033">Interviewing</activity>
          </customState>
        </customStates>

2.  将 XML 配置文件保存到启用了 HTTPS 的 web 服务器。 在此示例中，该文件命名为 "web.xml" 并保存到该https://lspool.corp.contoso.com/ClientConfigFolder/CustomPresence.xml位置。

3.  启动 Lync Server 命令行管理程序：依次单击“开始”****、“所有程序”****、“Microsoft Lync Server 2013”**** 和“Lync Server 命令行管理程序”****。

4.  在 Lync Server 命令行管理程序中，使用类似如下的命令定义 XML 配置文件的位置：
    
        New-CsClientPolicy -Identity ContosoCustomStates 
        -CustomStateURL "https://lspool.corp.contoso.com/ClientConfigFolder/CustomPresence.xml"

5.  使用**set-csclientpolicy** cmdlet 可将此新策略分配给用户。

有关详细信息，请参阅 Lync Server 命令行管理程序文档中的[set-csclientpolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy)和[Grant set-csclientpolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsClientPolicy) 。

<div>


> [!NOTE]  
> <UL>
> <LI>
> <P>默认情况下，Lync Server&nbsp;2013 每三个小时更新一次客户端策略和设置。</P>
> <LI>
> <P>如果要继续使用以前版本的组策略设置（如 CustomStateURL），Lync 2013 将识别这些设置（如果它们位于新策略注册表配置单元（HKEY_LOCAL_MACHINE \SOFTWARE\Policies\Microsoft\Office\15.0\Lync）中。 但是，基于服务器的客户端策略优先。</P></LI></UL>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

