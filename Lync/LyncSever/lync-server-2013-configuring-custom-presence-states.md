---
title: 配置自定义显示状态
TOCTitle: 配置自定义显示状态
ms:assetid: e17364a8-8b93-45fc-a614-c80e45435d42
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398997(v=OCS.15)
ms:contentKeyID: 52061146
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 配置自定义显示状态

 

_**上一次修改主题：** 2016-12-08_

若要在 Lync 2013 中定义自定义状态，请创建一个 XML 自定义状态配置文件，然后使用带有 CustomStateURL 参数的 Lync Server 命令行管理程序 cmdlet **New-CSClientPolicy** 或 **Set-CSClientPolicy** 来指定文件位置。

配置文件具有以下属性：

  - 可使用“有空”、“忙碌”和“请勿打扰”等状态指示符配置自定义状态。

  - 空闲状态属性确定将哪个状态指示符与自定义状态的状态文本相关联。本主题后面的示例中，会在绿色（“有空”）状态指示符的右侧显示状态文本“在家中工作”。

  - 状态文本的最大长度是 64 个字符。

  - 最多可添加四个自定义状态。

  - CustomStateURL 参数指定配置文件的位置。在 Lync 2013 中，SIP 高安全性模式默认为启用状态，因此您需要将自定义状态配置文件存储在已启用 HTTPS 的 Web 服务器上。否则，Lync 2013 客户端将无法连接到该文件。例如，有效地址将为 `https://lspool.corp.contoso.com/ClientConfigFolder/CustomPresence.xml`。

> [!NOTE]  
> 然而在生产环境中不建议使用它，您可使用 EnableSIPHighSecurityMode 注册表设置在客户端中禁用 SIP 高安全性模式，从而测试位于非 HTTPS 文件共享中的配置文件。然后，您可使用 CustomStateURL 注册表设置为配置文件指定一个非 HTTPS 位置。请注意，Lync 2013 服从 Lync 2010 注册表设置，但注册表配置单元已更新。您将按如下方式创建注册表设置：
<ul>
<li><p>HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync\EnableSIPHighSecurityMode</p>
<p>类型：DWORD</p>
<p>值数据：0</p></li>
<li><p>HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync\CustomStateURL</p>
<p>类型：String (REG_SZ)</p>
<p>值数据（示例）：file://\\lspool.corp.contoso.com\LSFileShare\ClientConfigFolder\Presence.xml 或 file:///c:/LSFileShare/ClientConfigFolder/Group_1_Pres.xml</p></li>
</ul>



通过在 XML 配置文件中指定一个或多个区域设置 ID (LCID) 架构来本地化自定义状态。本主题后面会显示本地化为英语 - 美国 (1033)、挪威语 - 博克马尔语 (1044)、法语 - 法国 (1036) 和土耳其语 (1055) 的示例。有关 LCID 列表，请参阅由 Microsoft 指定的区域设置 ID，网址为 <http://go.microsoft.com/fwlink/?linkid=157331>。

## 将自定义状态添加到 Lync 2013

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

2.  将 XML 配置文件保存到已启用 HTTPS 的 Web 服务器上。在此示例中，文件命名为 Presence.xml，并保存到位置 https://lspool.corp.contoso.com/ClientConfigFolder/CustomPresence.xml。

3.  启动 Lync Server 命令行管理程序：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 命令行管理程序”。

4.  在 Lync Server 命令行管理程序中，使用类似如下的命令定义 XML 配置文件的位置：
    
        New-CsClientPolicy -Identity ContosoCustomStates 
        -CustomStateURL "https://lspool.corp.contoso.com/ClientConfigFolder/CustomPresence.xml"

5.  使用 **Grant-CSClientPolicy** cmdlet 将此新策略分配给用户。

有关详细信息，请参阅 Lync Server 命令行管理程序文档中的 [New-CsClientPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsClientPolicy) 和 [Grant-CsClientPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsClientPolicy)。

> [!NOTE]  
> <ul><li><p>默认情况下，Lync Server 2013 每三个小时更新一次客户端策略和设置。</p></li>
< <li><p>如果您希望继续从早期版本中使用组策略设置，例如 CustomStateURL，则当这些设置位于新的策略注册表配置单元 (HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync) 中时，Lync 2013 将对这些设置进行识别。但是，基于服务器的客户端策略优先。</p></li></ul>


