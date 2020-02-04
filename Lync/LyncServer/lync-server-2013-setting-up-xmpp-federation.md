---
title: Lync Server 2013：设置 XMPP 联盟
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
ms.openlocfilehash: fd61aded33d37e4a1f5f58e9050f3cd62794f9b6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732042"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-xmpp-federation-in-lync-server-2013"></a>在 Lync Server 2013 中设置 XMPP 联盟

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-12-03_

若要在 Edge 服务器上部署 XMPP 代理，必须为 XMPP 联盟配置边缘服务器。 若要执行此操作，请执行以下步骤。

<div>

## <a name="setting-up-xmpp-federation"></a>设置 XMPP 联合身份验证

1.  登录到安装了 Lync Server 部署向导的计算机，作为 "域管理员" 组和 "RTCUniversalServerAdmins" 组的成员。

2.  在前端服务器上，打开 "Lync Server 部署向导"。 单击 "安装或更新 Lync 服务器系统"，然后单击 "设置" 或 "删除 Lync Server 组件"。 再次单击 "运行"。

3.  在 "安装 Lync 服务器组件" 中，单击 "下一步"。 "摘要" 屏幕将显示执行时的操作。 部署完成后，单击 "查看日志" 以查看可用的日志文件。 单击 "完成" 以完成部署。

4.  在边缘服务器上，打开 "Lync Server 部署向导"。 单击 "安装或更新 Lync 服务器系统"，然后单击 "设置" 或 "删除 Lync Server 组件"。 再次单击 "运行"。

5.  在 "安装 Lync 服务器组件" 中，单击 "下一步"。 "摘要" 屏幕将显示执行时的操作。 部署完成后，单击 "查看日志" 以查看可用的日志文件。 单击 "完成" 以完成部署。

6.  在边缘服务器上的 "部署向导" 中，在 "步骤3：请求、安装或分配证书" 旁边，再次单击 "运行"。
    
    <div class=" ">
    

    > [!TIP]  
    > 如果你是首次部署 Edge 服务器，你将看到 "运行"，而不是再次运行。

    
    </div>

7.  在“可用的证书任务”页上，单击“创建新的证书请求”。

8.  在 "证书请求" 页面上，单击 "外部边缘证书"。

9.  在 "延迟或立即请求" 页面上，选中 "立即准备请求，但稍后发送" 复选框。

10. 在 "证书请求文件" 页面上，键入要保存请求的文件的完整路径和文件名（例如，c：\\cert\_外部\_edge）。

11. 在 "指定备用证书模板" 页面上，若要使用默认 Web 台模板之外的模板，请选中 "为所选证书颁发机构使用备用证书模板" 复选框。

12. 在“名称和安全设置”页上，执行以下操作：
    
    1.  在 "友好名称" 中，键入证书的显示名称
    
    2.  在 "位长度" 中，指定位长（通常为默认值2048）
    
    3.  验证已选中 "将证书私钥标记为可导出" 复选框

13. 在 "组织信息" 页面上，键入组织和组织单位的名称（例如，"部门" 或 "部门"）

14. 在 "地理信息" 页面上，指定位置信息

15. 在 "主题名称/主题备用名称" 页面上，将显示要由向导自动填充的信息。 如果需要其他主题备用名称，请在接下来的两个步骤中进行指定

16. 在 "主题备用名称（San）" 页面上的 "SIP 域设置" 中，选中 "域" 复选框以添加 SIP。\<sipdomain\>条目到 "主题备用名称" 列表。

17. 在 "配置其他主题备用名称" 页面上，指定所需的任何其他主题备用名称
    
    <div class=" ">
    

    > [!TIP]  
    > 如果 XMPP 代理已安装，则默认情况下会在 SAN 条目中填充域名（如 contoso.com）。 如果需要更多条目，请在此步骤中添加这些条目。

    
    </div>

18. 在 "请求摘要" 页面上，查看要用于生成请求的证书信息。

19. 命令完成运行后，您可以查看日志，或单击 "下一步" 继续。

20. 在 "证书请求文件" 页面上，您可以通过单击 "查看或退出证书向导" 查看生成的证书签名请求（CSR）文件，方法是单击 "完成"。

21. 将请求文件复制并提交到公共证书颁发机构。

22. 接收、导入和分配公共证书后，必须停止并重新启动 Edge 服务器服务。 可通过在 Lync Server 管理控制台中键入以下内容来执行此操作：
    
       ```PowerShell
        Stop-CsWindowsService
       ```
    
       ```PowerShell
        Start-CsWindowsService
       ```

23. 若要为 XMPP 联盟配置 DNS，请将以下 SRV 记录添加到外部 DNS\_： XMPP-server。\_tcp。\<域名 SRV 记录将解析为 edge 服务器的访问边缘 FQDN，其端口值为\> 5269。 此外，您还可以配置一个指向访问边缘服务器的 IP 地址的 "A" 主机记录（例如，xmpp.contoso.com）。
    
    <div class=" ">
    

    > [!IMPORTANT]  
    > 如果你有多个网站中的 Edge 池，我们建议你为 XMPP federation 添加多个 SRV 记录。 为组织中的每个边缘池添加 SRV 记录，并为每个 SRV 记录提供不同的优先级。 当所有边缘池都在运行时，XMPP 请求将由具有第一个优先级的边缘池进行处理，但如果该边缘池停机，则不必添加新的 SRV 记录即可重新获得 XMPP 联合功能。

    
    </div>

24. 通过在前端打开 Lync Server 管理外壳并键入以下内容，将新的外部访问策略配置为启用所有用户：
    
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

25. 在部署 XMPP 代理的边缘服务器上，打开命令提示符或 Windows PowerShell™命令行界面，然后键入以下命令：
    
       ```PowerShell
        Netstat -ano | findstr 5269
       ```
    
       ```PowerShell
        Netstat -ano | findstr 23456
       ```
    
    Command **netstat-ano**是网络统计命令、参数 **-ano**请求 netstat 显示所有连接和侦听端口、地址和端口均以数字形式显示，并且拥有的进程 ID 与每个连接相关联。 该字符**|** 定义管道到下一个命令、" **findstr**" 或 "查找" 字符串。 作为参数传递给 findstr 的数字5269和23456指示 findstr 搜索针对字符串5269和23456的 netstat 的输出。 如果 XMPP 配置正确，则命令的结果应导致侦听和建立的连接在外部（端口5269）和边缘服务器的内部（端口23456）接口上。
    
    如果命令未在5269和23456上返回已建立或侦听端口，请检查以下内容：

</div>

<div>

## <a name="troubleshooting-xmpp-federation"></a>XMPP 联盟疑难解答

1.  若要确定 XMPP 代理是否正在运行，请执行下列操作：

2.  以本地管理员组的成员身份登录运行 XMPP 代理服务的边缘服务器。

3.  依次单击 "**开始**"、"**所有程序**"、"**管理工具**"、"**服务**"

4.  在 "服务" 中，找到 "Lync Server XMPP 转换网关代理"。 服务应处于 "**已启动**" 状态。 如果未启动，请单击工具栏中的 "**开始**" 图标。 图标显示为绿色的右箭头。

5.  确认该服务已更改为 "已**启动**"。 如果它已成功启动，请关闭**服务**并继续。
    
    如果 ther 服务未成功启动，请从 "管理工具" 打开事件查看器，并在 "**应用程序和服务日志**" 下的**Lync Server**部分中参阅错误和警告。

6.  在**Lync SERVER XMPP 转换网关**服务运行后，重新检查以前使用的 netstat 命令。 如果你没有看到已建立或正在侦听的会话，请检查并确保在拓扑结构生成器中正确配置了**XMPP 联合路线**

7.  以 Domain Admins 组和 RTCUniversalServerAdmins 组成员的身份登录安装了拓扑生成器的计算机。

8.  启动拓扑生成器：单击 "**开始**"，单击 "**所有程序**"，单击 " **Microsoft Lync server 2013**"，然后单击 " **Lync server 拓扑生成器**"。

9.  在拓扑生成器中，选择 XMPP 联盟路线的网站并查看以确认**XMPP 联盟**的**站点联盟路由分配**是否将边缘服务器或边缘池显示为所选的 XMPP 联合路由分配。
    
    如果路线分配不正确或未设置，请右键单击该站点，单击 "**编辑属性**"。 选中 "XMPP 联盟" 复选框，然后选择正确的 "边缘服务器" 或 "边缘池"。

10. 发布拓扑。 有关详细信息，请参阅[在 Lync Server 2013 中发布拓扑](lync-server-2013-publish-your-topology.md)
    
    <div class=" ">
    

    > [!TIP]  
    > 虽然不是必需的，并且通常不必要，但你可能需要重新启动边缘服务器

    
    </div>

11. 使用以前使用的 netstat 进程，确认 Edge 服务器正在侦听或已在端口5269和端口23456上建立了会话。

12. 如果仍然看不到预期的会话，请检查事件查看器是否有可能导致通信问题的原因。

</div>

<div>

## <a name="see-also"></a>另请参阅


[Lync Server 2013 中的示例 XMPP 配置 –  与 Google Talk 的 XMPP 联盟](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  


[在 Lync Server 2013 中管理组织的 XMPP 联盟伙伴](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

