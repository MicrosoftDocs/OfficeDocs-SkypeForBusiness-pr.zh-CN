---
title: 使用 Lync Connectivity Analyzer
TOCTitle: 使用 Lync Connectivity Analyzer
ms:assetid: 954953fb-0c7a-4fd5-8acd-68ecb59b20af
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ907302(v=OCS.15)
ms:contentKeyID: 52061078
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 使用 Lync Connectivity Analyzer

 

_**上一次修改主题：** 2016-12-08_

Microsoft Lync Connectivity Analyzer 可帮助 Lync 管理员确定他们的 Office 365 或内部部署 Lync Server 环境的部署和配置是否满足要求，以便支持来自移动设备上的 Lync Windows 应用商店应用 和 Lync 应用的连接。

Lync Connectivity Analyzer 试图使用与 Lync Windows 应用商店应用 和 Lync 移动应用所用的服务和协议相同的服务和协议连接到本地 Lync Server 或 Skype for Business Online。您可以通过您的内部网络或连接到 Lync Server 或 Skype for Business Online 的外部网络执行连接测试。Lync Connectivity Analyzer 提供包含有关各个连接步骤的详细信息的报告，可帮助您验证您的配置并解决连接问题。

Lync Connectivity Analyzer 测试下列 Lync Server 组件：

  - 自动发现服务

  - Authentication Broker (Reach) 服务

  - Mobility (MCX) 服务

  - Mobility (UCWA) 服务

  - WebTicket 服务

Lync Connectivity Analyzer 测试下列其他组件的配置：

  - 自动发现 URL 的 DNS 记录发布

  - 证书

  - 代理服务器

您可以从 Microsoft 下载中心下载 Lync Connectivity Analyzer，网址为 <http://go.microsoft.com/fwlink/?linkid=277056>。

## 连接性分析

1.  输入工具将用于测试连接的有效 Lync 帐户（内部部署 Lync 帐户或 Office 365Lync 帐户）的凭据：
    
      - 在“Lync 帐户类型”中，选择“Office 365”或“内部部署”。
    
      - 在“SIP URI”中，输入 Lync 连接的 SIP 登录地址，格式为 <strong>user@domain.com</strong>。
    
      - 在“密码”中，输入与此帐户关联的密码。
    
      - 在“用户名(可选)”中，输入用户名（如适用）。用户名又称用户主体名称 (UPN)。如果用户名和 SIP URI 相同，则不需要输入用户名。如果不同，则输入格式为 <strong>user@domain.com</strong> 或 **domain\\user** 的用户名。
    
      - 如果您是从连接到您的内部网络的计算机运行 Lync Connectivity Analyzer，请在“网络访问”下选择“从我的组织内”。否则，选择“外部 (Internet)”。Lync Connectivity Analyzer 始终同时执行内部和外部测试，但指定您是处于自己的网络之内还是之外将有助于此工具解释某些故障是否为预期的。
    
      - 在“客户端”下，选择是为“Lync Windows 应用商店应用”、“Lync Mobile 2010 应用”还是“Lync Mobile 2013 应用”执行连接性测试。
    
      - 在“服务器发现”下，选择要执行的测试类型：
        
          - 如果希望此工具自动发现 Lync 服务器，请选择“自动”。
        
          - 如果希望此工具绕过自动发现测试，或者您知道想要连接的服务器的名称，请选择“使用地址手动：”，然后指定 Lync 服务器的完全限定域名 (FQDN)，例如，**lync.company.com**。

2.  （可选）在“日志文件”下，如果您希望在指定路径处创建日志文件，请选择该复选框。如果日志记录已启用，请单击“清除”以清除日志文件，单击“打开”以打开并查看日志文件，单击“电子邮件”以打开一封电子邮件并将结果发送给您的支持团队（您必须从指定的路径手动附加日志文件）。

3.  单击“开始”。

下图显示来自 Lync Connectivity Analyzer 的示例结果。

**Lync Connectivity Analyzer**

![Lync Connectivity Analyzer 的屏幕截图](images/JJ907302.a7cc0abe-fac2-4691-a7d8-9ffef59cdee5(OCS.15).png "Lync Connectivity Analyzer 的屏幕截图")

## Lync Connectivity Analyzer 测试的组件

Lync Connectivity Analyzer 试图发现 Lync 服务器并使用 Lync Windows 应用商店应用和 Lync 移动应用所用的相同步骤来建立连接。它执行本节所述的测试。

如果选择了“自动发现”，Lync Connectivity Analyzer 会执行以下操作：

  - 查询域名服务 (DNS) 以获得自动发现 URL。

  - 尝试使用安全的内部通道发现。例如 **HTTPS://lyncdiscoverinternal.company.com/**。

  - 尝试使用非安全的内部通道发现。例如 **HTTP://lyncdiscoverinternal.company.com/**。

  - 尝试使用安全的外部通道发现。例如 **HTTPS://lyncdiscover.company.com**。

  - 尝试使用非安全的外部通道发现。例如 **HTTP://lyncdiscover.company.com**。

如果选择了“使用以下服务器发现地址”，则 Lync Connectivity Analyzer 会执行以下操作：

  - 查询 DNS 以获得服务器的 FQDN。

  - 尝试使用安全通道发现。例如 **HTTPS://serverFQDN/**。

  - 尝试使用非安全通道发现。例如 **HTTP://serverFQDN/**。

如果在“测试需求”下选择了“Lync Windows 应用商店应用”，则 Lync Connectivity Analyzer 会执行以下操作：

  - 验证 WebTicket 服务是否可用并测试 Lync 帐户凭据的身份验证。

  - 验证 Authentication Broker (Reach) 服务是否可用。

如果在“客户端”下选择“Lync Mobile 2010 应用”，则 Lync Connectivity Analyzer 会执行以下操作：

  - 验证 WebTicket 服务是否可用并测试 Lync 帐户凭据的身份验证。

  - 验证 Mobility (MCX) 服务是否可用。

如果在“客户端”下选择“Lync Mobile 2013 应用”，则 Lync Connectivity Analyzer 会执行以下操作：

  - 验证 WebTicket 服务是否可用并测试 Lync 帐户凭据的身份验证。

  - 验证 Mobility (UCWA) 服务是否可用。

在执行这些测试时，Lync Connectivity Analyzer 会验证 Lync Server、硬件负载平衡器、代理服务器和您在其上运行测试的计算机上安装的证书。

## 其他资源

Microsoft 还提供 Microsoft Remote Connectivity Analyzer，这是一个基于 Web 的连接性测试工具，可从 <https://testconnectivity.microsoft.com/> 上下载。Lync Connectivity Analyzer 和 Remote Connectivity Analyzer 在以下方面有所不同：

  - 除了为 Microsoft Lync 测试连接性外，Remote Connectivity Analyzer 还可以为 Microsoft Exchange 和 Outlook 测试连接性。

  - Remote Connectivity Analyzer 完成 SIP 登录，而 Lync Connectivity Analyzer 只验证帐户凭据而不登录。

  - 因为 Remote Connectivity Analyzer 从公共 Web 服务器运行，所以它只测试来自您的组织网络之外的连接。

  - Remote Connectivity Analyzer 不测试 Authentication Broker (Reach)、Mobility (MCX) 和 WebTicket 服务的可用性。

  - Lync Connectivity Analyzer 测试自动发现服务。

  - Remote Connectivity Analyzer 可以连接到任何版本的 Lync Server，而 Lync Connectivity Analyzer 只能成功连接到具有 2012 年 2 月版 Lync Server 2010 累积更新（最低要求）的 Lync Server 2010 或连接到最新版本的 Lync Server。

以下文档描述部署和配置 Lync Server 以支持 Lync Windows 应用商店应用和 Lync 移动客户端的需求和过程：

  - [在 Lync Server 2013 中部署客户端和设备](lync-server-2013-deploying-clients-and-devices.md)

  - [在 Lync Server 2013 中规划移动功能](lync-server-2013-planning-for-mobility.md)

  - [在 Lync Server 2013 中部署移动功能](lync-server-2013-deploying-mobility.md)

