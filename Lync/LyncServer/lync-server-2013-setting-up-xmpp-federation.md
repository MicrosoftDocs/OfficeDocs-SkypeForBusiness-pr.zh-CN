---
title: Lync Server 2013：设置 XMPP 联盟
TOCTitle: 设置 XMPP 联盟
ms:assetid: 5fda6cb7-8d4d-495d-90c7-601f1036e085
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204939(v=OCS.15)
ms:contentKeyID: 49313012
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中设置 XMPP 联盟

 

_**上一次修改主题：** 2012-12-03_

要在边缘服务器上部署 XMPP 代理，您必须为 XMPP 联盟配置边缘服务器。为此，请执行以下步骤。

## 设置 XMPP 联盟

1.  以 Domain Admins 组和 RTCUniversalServerAdmins 组成员的身份登录安装了 Lync Server 部署向导的计算机。

2.  在前端服务器上，打开 Lync Server 部署向导。单击“安装或更新 Lync Server 系统”，然后单击“安装或删除 Lync Server 组件”。单击“再次运行”。

3.  在“设置 Lync Server 组件”中，单击“下一步”。摘要屏幕将显示已执行的操作。部署完成后，单击“查看日志”可查看可用日志文件。单击“完成”以完成部署。

4.  在边缘服务器上，打开 Lync Server 部署向导。单击“安装或更新 Lync Server 系统”，然后单击“安装或删除 Lync Server 组件”。单击“再次运行”。

5.  在“设置 Lync Server 组件”中，单击“下一步”。摘要屏幕将显示已执行的操作。部署完成后，单击“查看日志”可查看可用日志文件。单击“完成”以完成部署。

6.  在边缘服务器上，单击部署向导中“步骤 3：请求、安装或分配证书”旁边的“再次运行”。
    
    > [!TIP]
    > 如果您第一次部署边缘服务器，您将看到“运行”而不是“再次运行”。


7.  在“可用的证书任务”页上，单击“创建新的证书请求”。

8.  在“证书请求”页上，单击“外部边缘证书”。

9.  在“延迟的请求或即时请求”页上，选中“现在准备请求，但稍后发送”复选框。

10. 在“证书请求文件”页上，键入要向其保存请求的文件的完整路径和文件名（例如，c:\\cert\_exernal\_edge.cer）。

11. 在“指定替代证书模板”页上，要使用除默认 WebServer 模板之外的模板，请选中“使用选定证书颁发机构的备用证书模板”复选框。

12. 在“名称和安全设置”页上，执行以下操作：
    
    1.  在“友好名称”中，键入证书的显示名称
    
    2.  在“位长度”中，指定位长度（通常为默认值“2048”）。
    
    3.  验证是否选中了“将证书私钥标记为可导出”复选框。

13. 在“组织信息”页上，键入组织和组织单位（例如，分部或部门）的名称

14. 在“地理信息”页上，指定位置信息。

15. 在“使用者名称/使用者替代名称”页上，将显示向导自动填充的信息。如果需要其他使用者替代名称，可以在接下来的两个步骤中指定

16. 在“使用者替代名称(SAN)的 SIP 域设置”页上，选中域复选框以向使用者替代名称列表中添加 sip.\<sipdomain\> 条目。

17. 在“配置其他使用者替代名称”页上，指定所需的任何其他使用者替代名称
    
    > [!TIP]
    > 如果安装了 XMPP 代理，则默认情况下域名（如 contoso.com）填充在 SAN 条目中。如果您需要更多条目，请在此步骤中添加它们。


18. 在“请求摘要”页上，检查要用于生成请求的证书信息。

19. 在命令运行完毕后，您可以“查看日志”，或单击“下一步”继续操作。

20. 在“证书请求文件”页上，您可以通过单击“查看”来查看生成的证书签名请求 (CSR) 文件，或通过单击“完成”来退出证书向导。

21. 复制请求文件并提交至公共证书颁发机构。

22. 在接收、导入和分配公共证书后，您必须停止边缘服务器服务，然后重新启动它。为此，请在 Lync Server 管理控制台中键入：
    
        Stop-CsWindowsService

       &nbsp;
    
        Start-CsWindowsService

23. 要为 XMPP 联盟配置 DNS，需要将以下 SRV 记录添加到外部 DNS:\_xmpp-server.\_tcp.\<域名\>。SRV 记录将使用端口值 5269 解析到边缘服务器的访问边缘 FQDN。另外，您还可以配置一个指向访问边缘服务器的 IP 地址的 "A" 主机记录（例如，xmpp.contoso.com）。
    
    > [!IMPORTANT]
    > 如果您在多个站点中具有边缘池，则建议为 XMPP 联盟添加多个 SRV 记录。请为您组织中的每个边缘池添加一个 SRV 记录，然后为其中每个 SRV 记录提供不同的优先级。当所有边缘池都在运行时，XMPP 请求将全部由具有第一优先级的边缘池处理，但如果该边缘池关闭，您随后不必添加新 SRV 记录来重新获得 XMPP 联盟功能。


24. 配置一个新外部访问策略来启用所有用户，方法是在前端服务器上打开 Lync Server 命令行管理程序并键入：
    
        New-CsExternalAccessPolicy -Identity <name of policy to create.  If site scope, prepend with 'site:'> -EnableFederationAcces $true -EnablePublicCloudAccess $true

       &nbsp;
    
        New-CsExternalAccessPolicy -Identity FedPic -EnableFederationAcces $true -EnablePublicCloudAccess $true

       &nbsp;
    
        Get-CsUser | Grant-CsExternalAccessPolicy -PolicyName FedPic
    
    通过键入以下命令为外部用户启用 XMPP 访问：
    
        Set-CsExternalAccessPolicy -Identity <name of the policy being used> EnableXmppAccess $true

       &nbsp;
    
        Set-CsExternalAccessPolicy -Identity FedPic -EnableXmppAccess $true

25. 在部署 XMPP 代理的 边缘服务器上，打开命令提示符或 Windows PowerShell™ 命令行接口并键入以下命令：
    
        Netstat -ano | findstr 5269

       &nbsp;
    
        Netstat -ano | findstr 23456
    
    命令 **netstat –ano** 是网络统计信息命令，参数 **–ano** 请求 netstat 显示所有连接和侦听端口，请求以数字形式显示地址和端口，并请求拥有进程 ID 与每个连接关联。字符 **|** 定义下一个命令 **findstr**（或称为查找字符串）的管道。数字 5269 和 23456 thaaat 将传递到 findstr 以作为指示 findstr 搜索 netstat 的输出中的字符串 5269 和 23456 的参数。如果 XMPP 配置正确，这些命令的结果应该同时在边缘服务器 的外部（端口 5269）和内部（端口 23456）接口上生成正在侦听的连接和已建立的连接。
    
    如果这些命令没有在 5269 和 23456 上返回已建立的端口或正在侦听的端口，则检查以下项目：

## 对 XMPP 联盟进行故障排除

1.  若要确定 XMPP 代理是否在运行，请执行以下操作：

2.  登以本地管理员组成员身份登录到运行 XMPP 代理服务的边缘服务器。

3.  依次单击“开始”、“所有程序”、“管理工具”和“服务”。

4.  在“服务”中，找到“Lync Server XMPP 转换网关代理”。该服务应处于“已启动”状态。如果未启动，则单击工具栏中的“启动”图标。该图标显示为绿色的向右箭头。

5.  确认该服务已更改为“已启动”。如果已成功启动，则关闭“服务”并继续。
    
    如果该服务未成功启动，则在“管理工具”中打开事件查看器并查看“应用程序和服务日志”下的“Lync Server”部分的错误和警告。

6.  “Lync Server XMPP 转换网关”服务运行后，重新检查之前使用的 netstat 命令。如果没有看到已建立的会话或正在侦听的会话，则检查并确保在拓扑生成器中正确配置了“XMPP 联盟路由”。

7.  以 Domain Admins 组和 RTCUniversalServerAdmins 组成员的身份登录安装了拓扑生成器的计算机。

8.  启动拓扑生成器：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 拓扑生成器”。

9.  在拓扑生成器中，选中 XMPP 联盟路由的站点并检查确认“XMPP 联盟”的“站点联盟路由分配”将边缘服务器或边缘池显示为已选择的 XMPP 联盟路由分配。
    
    如果路由分配不正确或未设置，则右键单击站点，然后单击“编辑属性”。选中“XMPP 联盟”复选框，然后选择正确的边缘服务器或边缘池。

10. 发布拓扑。有关详细信息，请参阅 [在 Lync Server 2013 中发布拓扑](lync-server-2013-publish-your-topology.md)。
    
    > [!TIP]
    > 您可能发现您需要重新启动 边缘服务器，但这不是必需的且通常没有必要。


11. 使用之前使用的 netstat 进程，确认 边缘服务器现在正在端口 5269 和端口 23456 上侦听会话或已在这些端口上建立会话。

12. 如果仍然没有看到所需的会话，则查看事件查看器以了解造成此通信问题的可能原因。

## 另请参阅

#### 任务

[Lync Server 2013 中的示例 XMPP 配置 – 与 Google Talk 的 XMPP 联盟](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  

#### 其他资源

[在 Lync Server 2013 中管理组织的 XMPP 联盟伙伴](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)

