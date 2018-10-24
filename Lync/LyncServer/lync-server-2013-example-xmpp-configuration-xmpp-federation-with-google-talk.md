---
title: Lync Server 2013：示例 XMPP 配置 –  与 Google Talk 的 XMPP 联盟
TOCTitle: 示例 XMPP 配置 –  与 Google Talk 的 XMPP 联盟
ms:assetid: 360a2f7b-015b-4e93-ac67-0f609c21f1a2
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204807(v=OCS.15)
ms:contentKeyID: 49312477
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的示例 XMPP 配置 – 与 Google Talk 的 XMPP 联盟

 

_**上一次修改主题：** 2016-12-08_

用于部署 XMPP 代理的示例配置定义了与 Google Talk 的联盟。

## 示例 XMPP 配置 – 与 Google Talk 的 XMPP 联盟

1.  在前端服务器上，打开 Lync Server 部署向导。单击“安装”或“更新 Lync Server 系统”，然后单击“安装”或“删除 Lync Server 组件”。单击“再次运行”。

2.  在“设置 Lync Server 组件”中，单击“下一步”。摘要屏幕将显示已执行的操作。部署完成后，单击“查看日志”可查看可用日志文件。单击“完成”以完成部署。

3.  在边缘服务器上，打开 Lync Server 部署向导。单击“安装”或“更新 Lync Server 系统”，然后单击“安装”或“删除 Lync Server 组件”。单击“再次运行”。

4.  添加 Google Talk 作为 XMPP 允许的合作伙伴。对于服务器与服务器的 XMPP 联盟，Google Talk 当前仅支持未加密的 TCP 连接，对于身份验证，仅支持 Server Dialback。（请参阅 <http://xmpp.org/extensions/xep-0220.html>）
    
        New-CsXmppAllowedPartner gmail.com -TlsNegotiation NotSupported -SaslNegotiation NotSupported -EnableKeepAlive $false -SupportDialbackNegotiation $true

5.  要启用边缘联盟，请键入以下内容：
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $true

6.  在“设置 Lync Server 组件”中，单击“下一步”。摘要屏幕将显示已执行的操作。部署完成后，单击“查看日志”可查看可用日志文件。单击“完成”以完成部署。

7.  在边缘服务器上的 Lync Server 部署向导中，单击“步骤 3：请求、安装或分配证书”旁边的“再次运行”。
    
    > [!TIP]
    > 如果您第一次部署边缘服务器，您将看到“运行”而不是“再次运行”。


8.  在“可用的证书任务”页上，单击“创建新的证书请求”。

9.  在“证书请求”页上，单击“外部边缘证书”。

10. 在“延迟的请求或即时请求”页上，选中“现在准备请求，但稍后发送”复选框。

11. 在“证书请求文件”页上，键入要向其保存请求的文件的完整路径和文件名（例如，c:\\cert\_exernal\_edge.cer）。

12. 在“指定替代证书模板”页上，要使用除默认 WebServer 模板之外的模板，请选中“使用选定证书颁发机构的备用证书模板”复选框。

13. 在“名称和安全设置”页上，执行以下操作：
    
    1.  在“友好名称”中，键入证书的显示名称
    
    2.  在“位长度”中，指定位长度（通常为默认值“2048”）。
    
    3.  验证是否选中了“将证书私钥标记为可导出”复选框。

14. 在“组织信息”页上，键入组织和组织单位（例如，分部或部门）的名称

15. 在“地理信息”页上，指定位置信息。

16. 在“使用者名称/使用者替代名称”页上，将显示向导自动填充的信息。如果需要其他使用者替代名称，可以在接下来的两个步骤中指定

17. 在“使用者替代名称(SAN)的 SIP 域设置”页上，选中域复选框以向使用者替代名称列表中添加 *\<sipdomain\>* 条目。

18. 在“配置其他使用者替代名称”页上，指定所需的任何其他使用者替代名称。
    
    > [!TIP]
    > 如果安装了 XMPP 代理，则默认情况下域名（如 contoso.com）填充在 SAN 条目中。如果您需要更多条目，请在此步骤中添加它们。


19. 在“请求摘要”页上，检查要用于生成请求的证书信息。

20. 在命令运行完毕后，您可以“查看日志”，或单击“下一步”继续操作。

21. 在“证书请求文件”页上，您可以通过单击“查看”来查看生成的证书签名请求 (CSR) 文件，或通过单击“完成”来退出证书向导。

22. 复制请求文件并提交至公共证书颁发机构。

23. 在接收、导入和分配公共证书后，您必须停止然后重新启动边缘服务器服务。 启动 Lync Server 命令行管理程序：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 命令行管理程序”。在 Lync Server 命令行管理程序中键入：
    
    ```
    Stop-CsWindowsService
    ```
    ```
    Start-CsWindowsService
    ```

24. 要为 XMPP 联盟配置 DNS，需将以下 SRV 记录添加到外部 DNS:\_xmpp-server.\_tcp.*\<domain name\>*。SRV 记录将使用端口值 5269 解析到边缘服务器的访问边缘 FQDN。

25. 配置一个新外部访问策略来启用所有用户，方法是打开 前端服务器上的 Lync Server 命令行管理程序并键入：
    
        New-CsExternalAccessPolicy -Identity FedPic -EnableFederationAccess $true -EnablePublicCloudAccess $true
        Get-CsUser | Grant-CsExternalAccessPolicy -PolicyName FedPic

