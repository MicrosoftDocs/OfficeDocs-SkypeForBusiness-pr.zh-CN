---
title: Lync Server 2013：配置自定义状态
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
ms.openlocfilehash: c69f7a5b32b4ad0dd31f8be118aa2f2173ff3e22
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758192"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-custom-presence-states-in-lync-server-2013"></a>在 Lync Server 2013 中配置自定义状态状态

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2013-01-10_

若要在 Lync 2013 中定义自定义状态，请创建一个 XML 自定义状态配置文件，然后通过将 Lync Server Management Shell cmdlet **set-csclientpolicy**或**set-csclientpolicy**参数 CustomStateURL 指定其位置。

配置文件具有以下属性：

  - 自定义状态状态可以配置为 "可用、忙碌和请勿打扰" 状态指示器。

  - 可用性属性确定哪些状态指示器与自定义状态的状态文本相关联。 在本主题后面的示例中，"开始使用的状态文本" 显示在绿色（可用）状态指示器的右侧。

  - 状态文本的最大长度为64个字符。

  - 最多可以添加四个自定义状态。

  - CustomStateURL 参数指定配置文件的位置。 在 Lync 2013 中，SIP 高安全模式默认情况下处于启用状态，因此你需要将自定义状态配置文件存储在启用了 HTTPS 的 web 服务器上。 否则，Lync 2013 客户端将无法连接到该客户端。 例如，有效的地址将是`https://lspool.corp.contoso.com/ClientConfigFolder/CustomPresence.xml`。

<div>


> [!NOTE]  
> 尽管不推荐在生产环境中使用，但你可以通过使用 EnableSIPHighSecurityMode 注册表设置在客户端上禁用 SIP 高安全模式来测试位于非 HTTPS 文件共享上的配置文件。 然后，你可以使用 CustomStateURL 注册表设置为配置文件指定非 HTTPS 位置。 请注意，Lync 2013 采用 Lync 2010 注册表设置，但注册表配置单元已更新。 您将创建如下所示的注册表设置： 
> <UL>
> <LI>
> <P>HKEY_LOCAL_MACHINE \SOFTWARE\Policies\Microsoft\Office\15.0\Lync\EnableSIPHighSecurityMode</P>
> <P>类型： DWORD</P>
> <P>值数据：0</P>
> <LI>
> <P>HKEY_LOCAL_MACHINE \SOFTWARE\Policies\Microsoft\Office\15.0\Lync\CustomStateURL</P>
> <P>类型： String （REG_SZ）</P>
> <P>值数据（示例）： file://\\lspool com\LSFileShare\ClientConfigFolder\Presence.xml 或 file:///c:/LSFileShare/ClientConfigFolder/Group_1_Pres.xml</P></LI></UL>



</div>

通过在 XML 配置文件中指定一个或多个区域设置 ID （LCID）架构来本地化你的自定义状态。 本主题后面的示例显示英语-美国（1033）、挪威语（1044）、法语-法国（1036）和土耳其语（1055）的本地化。 有关 Lcid 的列表，请参阅 Microsoft 分配的区域设置 Id <http://go.microsoft.com/fwlink/p/?linkid=157331>。

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

2.  将 XML 配置文件保存到启用了 HTTPS 的 web 服务器。 在此示例中，文件命名为 "存在 .xml" 并保存到位置https://lspool.corp.contoso.com/ClientConfigFolder/CustomPresence.xml。

3.  启动 Lync Server 命令行管理程序：依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server Management shell**"。

4.  在 Lync Server Management Shell 中，使用类似于以下内容的命令定义 XML 配置文件的位置：
    
        New-CsClientPolicy -Identity ContosoCustomStates 
        -CustomStateURL "https://lspool.corp.contoso.com/ClientConfigFolder/CustomPresence.xml"

5.  使用**set-csclientpolicy** cmdlet 将此新策略分配给用户。

有关详细信息，请参阅 Lync Server Management Shell 文档中的 "[新建-set-csclientpolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy) " 和 "[授予" set-csclientpolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsClientPolicy) 。

<div>


> [!NOTE]  
> <UL>
> <LI>
> <P>默认情况下，Lync Server&nbsp;2013 每隔3个小时更新客户端策略和设置。</P>
> <LI>
> <P>如果想要继续使用以前版本的组策略设置（如 CustomStateURL），Lync 2013 将识别位于新策略注册表配置单元（HKEY_LOCAL_MACHINE \SOFTWARE\Policies\Microsoft\Office\15.0\Lync）中的设置。 但是，基于服务器的客户端策略优先。</P></LI></UL>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

