---
title: Lync Server 2013：设置 XMPP 联合
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up XMPP federation
ms:assetid: 5fda6cb7-8d4d-495d-90c7-601f1036e085
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204939(v=OCS.15)
ms:contentKeyID: 48184270
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4cb6b2904ee2a8883c492e570173e73bc001cc03
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48497519"
---
# <a name="setting-up-xmpp-federation-in-lync-server-2013"></a>在 Lync Server 2013 中设置 XMPP 联盟

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-12-03_

若要在边缘服务器上部署 XMPP 代理，您必须为 XMPP 联盟配置边缘服务器。 为此，请执行以下步骤。

<div>

## <a name="setting-up-xmpp-federation"></a>设置 XMPP 联合

1.  以 Domain Admins 组和 RTCUniversalServerAdmins 组成员的身份登录到安装了 Lync Server 部署向导的计算机。

2.  在前端服务器上，打开 "Lync Server 部署向导"。 单击“安装或更新 Lync Server 系统”，然后单击“安装或删除 Lync Server 组件”。 单击“再次运行”。

3.  在“设置 Lync Server 组件”中，单击“下一步”。摘要屏幕将显示已执行的操作。部署完成后，单击“查看日志”可查看可用日志文件。单击“完成”以完成部署。

4.  在边缘服务器上，打开 Lync Server 部署向导。单击“安装或更新 Lync Server 系统”，然后单击“安装或删除 Lync Server 组件”。单击“再次运行”。

5.  在“设置 Lync Server 组件”中，单击“下一步”。摘要屏幕将显示已执行的操作。部署完成后，单击“查看日志”可查看可用日志文件。单击“完成”以完成部署。

6.  在边缘服务器上，单击部署向导中“步骤 3：请求、安装或分配证书”旁边的“再次运行”。
    
    <div class=" ">
    

    > [!TIP]  
    > 如果您是首次部署边缘服务器，您将看到“运行”而非“再次运行”。

    
    </div>

7.  在“可用的证书任务”页上，单击“创建新的证书请求”。

8.  在“证书请求”页上，单击“外部边缘证书”。

9.  在“延迟的请求或即时请求”页上，选中“立即准备请求，但是稍后发送”复选框。

10. 在 "证书请求文件" 页上，键入要将请求保存到的文件的完整路径和文件名 (例如，c： \\ cert \_ 外部 \_ edge) 。

11. 在“指定替代证书模板”页上，要使用除默认 WebServer 模板之外的模板，请选中“对选定的证书颁发机构使用替代证书模板”复选框。

12. 在“名称和安全设置”页上，执行以下操作：
    
    1.  在“友好名称”中，键入证书的显示名称
    
    2.  在“位长度”中，指定位长度（通常为默认值“2048”）。
    
    3.  验证是否选中了“将证书私钥标记为可导出”复选框。

13. 在“组织信息”页上，键入组织和组织单位（例如，分部或部门）的名称

14. 在“地理信息”页上，指定位置信息。

15. 在“使用者名称/使用者替代名称”页上，将显示向导自动填充的信息。 如果需要其他使用者替代名称，可以在接下来的两个步骤中指定

16. 在 "使用者替代名称 (SANs) " 页上的 "SIP 域设置" 中，选中 "域" 复选框以添加 SIP。\<sipdomain\> "主题备用名称" 列表中的条目。

17. 在 "配置其他使用者替换名称" 页上，指定所需的其他任何其他主题替代名称
    
    <div class=" ">
    

    > [!TIP]  
    > 如果安装了 XMPP 代理，则默认情况下域名（如 contoso.com）填充在 SAN 条目中。如果您需要更多条目，请在此步骤中添加它们。

    
    </div>

18. 在“请求摘要”页上，检查要用于生成请求的证书信息。

19. 在命令运行完后，您可以“查看日志”，或单击“下一步”继续操作。

20. 在“证书请求文件”页上，您可以通过单击“查看”来查看生成的证书签名请求 (CSR) 文件，或通过单击“完成”退出证书向导。

21. 复制请求文件并提交至公共证书颁发机构。

22. 在接收、导入和分配公共证书后，您必须停止边缘服务器服务，然后重新启动它。为此，请在 Lync Server 管理控制台中键入：
    
       ```PowerShell
        Stop-CsWindowsService
       ```
    
       ```PowerShell
        Start-CsWindowsService
       ```

23. 若要为 XMPP 联盟配置 DNS，请将以下 SRV 记录添加到外部 DNS： \_ XMPP-server。 \_rdp-tcp.\<domain name\> SRV 记录将解析为边缘服务器的访问边缘 FQDN，端口值为5269。 此外，还可以配置 "A" 主机记录 (例如，指向访问边缘服务器的 IP 地址的 xmpp.contoso.com) 。
    
    <div class=" ">
    

    > [!IMPORTANT]  
    > 如果您在多个站点中有边缘池，我们建议您为 XMPP 联合添加多个 SRV 记录。 为组织中的每个边缘池添加一条 SRV 记录，并为每个 SRV 记录指定不同的优先级。 在运行所有边缘池时，XMPP 请求将由具有第一个优先级的边缘池进行处理，但如果该边缘池处于关闭状态，则不必添加新的 SRV 记录以重新获得 XMPP 联合功能。

    
    </div>

24. 通过在前端打开 Lync Server 命令行管理程序并键入以下内容，将新的外部访问策略配置为启用所有用户：
    
       ```PowerShell
        New-CsExternalAccessPolicy -Identity <name of policy to create.  If site scope, prepend with 'site:'> -EnableFederationAcces $true -EnablePublicCloudAccess $true
       ```
    
       ```PowerShell
        New-CsExternalAccessPolicy -Identity FedPic -EnableFederationAcces $true -EnablePublicCloudAccess $true
       ```
    
       ```PowerShell
        Get-CsUser | Grant-CsExternalAccessPolicy -PolicyName FedPic
       ```
    
    通过键入以下内容为外部用户启用 XMPP 访问：
    
       ```PowerShell
        Set-CsExternalAccessPolicy -Identity <name of the policy being used> EnableXmppAccess $true
       ```
    
       ```PowerShell
        Set-CsExternalAccessPolicy -Identity FedPic -EnableXmppAccess $true
       ```

25. 在部署 XMPP 代理的边缘服务器上，打开命令提示符或 Windows PowerShell™命令行接口，并键入以下命令：
    
       ```PowerShell
        Netstat -ano | findstr 5269
       ```
    
       ```PowerShell
        Netstat -ano | findstr 23456
       ```
    
    Command **netstat – ano** 是网络统计命令、参数 **– ano** 请求 netstat 显示所有连接和侦听端口、地址和端口均以数字形式显示，并且拥有的进程 ID 与每个连接相关联。 该字符将 **|** 管道定义为下一个命令、 **findstr**或查找字符串。 作为参数传递给 findstr 的数字5269和23456指示 findstr 搜索针对字符串5269和23456的 netstat 的输出。 如果正确配置了 XMPP，则命令的结果应导致侦听和建立的连接，这两个连接都在外部 (端口 5269) 和边缘服务器的内部 (端口 23456) 接口上。
    
    如果命令未在5269和23456上返回已建立或正在侦听的端口，请检查以下各项：

</div>

<div>

## <a name="troubleshooting-xmpp-federation"></a>XMPP 联合身份验证疑难解答

1.  若要确定 XMPP 代理是否正在运行，请执行以下操作：

2.  以本地管理员组成员身份登录到运行 XMPP 代理服务的边缘服务器。

3.  依次单击 " **开始**"、" **所有程序**"、" **管理工具**"、" **服务**

4.  在 "服务" 中，找到 "Lync Server XMPP 转换网关代理"。 服务应处于 " **已启动** " 状态。 如果未启动，请单击工具栏中的 " **开始** " 图标。 图标以绿色的向右箭头形式显示。

5.  确认服务已更改为 " **已启动**"。 如果已成功启动，请关闭 **服务** 并继续。
    
    如果为止服务尚未成功启动，请从 "管理工具" 中打开事件查看器，并在 "**应用程序和服务日志**" 下的**Lync Server**部分中引用错误和警告。

6.  在 **Lync SERVER XMPP 转换网关** 服务运行后，重新检查以前使用的 netstat 命令。 如果你未看到已建立或正在侦听的会话，请检查并确保在拓扑生成器中正确配置了**XMPP 联合路由**

7.  以 Domain Admins 组和 RTCUniversalServerAdmins 组成员的身份登录安装了拓扑生成器的计算机。

8.  启动拓扑生成器：依次单击 " **开始**"、" **所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server 拓扑生成器**"。

9.  在拓扑生成器中，选择 XMPP 联盟路由和审阅的网站，以确认**XMPP 联合**的**站点联合路由分配**将边缘服务器或边缘池显示为选定的 XMPP 联合路由分配。
    
    如果路由分配不正确或未设置，请右键单击网站，然后单击 " **编辑属性**"。 选中 "XMPP 联盟" 复选框，然后选择正确的边缘服务器或边缘池。

10. 发布拓扑。 有关详细信息，请参阅 [在 Lync Server 2013 中发布拓扑](lync-server-2013-publish-your-topology.md)
    
    <div class=" ">
    

    > [!TIP]  
    > 尽管不是必需的且通常不必要，但您可能需要重新启动边缘服务器

    
    </div>

11. 使用之前使用的 netstat 进程，确认边缘服务器正在侦听或已在端口5269和端口23456上建立了会话。

12. 如果仍未看到预期会话，请检查事件查看器是否有可能导致通信问题的原因。

</div>

<div>

## <a name="see-also"></a>另请参阅


[Lync Server 2013 中的示例 XMPP 配置–与 Google 对话的 XMPP 联盟](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  


[在 Lync Server 2013 中管理 XMPP 联盟伙伴](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

