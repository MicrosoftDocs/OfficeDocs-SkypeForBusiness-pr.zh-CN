---
title: Lync Server 2013：为自动发现服务创建 DNS 记录
TOCTitle: 为自动发现服务创建 DNS 记录
ms:assetid: 3756ffe4-c6b1-492d-850e-42a832e06567
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Hh690010(v=OCS.15)
ms:contentKeyID: 49312511
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中为自动发现服务创建 DNS 记录

 

_**上一次修改主题：** 2014-06-20_

您的 Lync Mobile 用户将需要您启用自动发现，部分操作涉及创建一些域名系统 (DNS) 记录。根据您的需要，您需要以下内容：

  - 支持从组织网络内部进行连接的移动用户的内部 DNS 记录。

  - 支持从 Internet 进行连接的移动用户的外部或公共 DNS 记录

为什么？您需要为每个 SIP 域创建一条内部 DNS 记录和一条外部 DNS 记录。

您创建的 DNS 记录可以是 A（主机）记录，也可以是 CNAME 记录。为帮助您排忧解难，我们将在下面指导您如何创建这些内部和外部 DNS 记录。如果需要进一步阅读有关移动用户的 DNS 要求的内容，您可以查看[Lync Server 2013 中的移动性技术要求](lync-server-2013-technical-requirements-for-mobility.md)。

## 创建内部 DNS CNAME 记录

1.  若要创建内部 DNS 记录，您需要使用属于 Domain Admins 组成员或 DnsAdmins 组成员的域帐户登录网络中的 DNS 服务器。

2.  打开 DNS 管理单元：依次单击“开始”、“管理工具”和“DNS”。

3.  在 DNS 服务器的控制台树中，展开已安装 Lync Server 2013控制器池和前端池的 Active Directory 域（例如 contoso.local）的“正向查找区域”。

4.  检查您的控制器池的内部 DNS 记录是否存在主机 A（对于 IPv6 为 AAAA）记录，您的控制器池（例如 lyncwebdir01.contoso.local）的内部 Web 服务完全限定的域名 (FQDN) 应存在主机 A 记录。如果不存在，则您不能使用控制器池，并且您需要使用前端池的 FQDN 甚至单个服务器 FQDN（如果您已设置）。

5.  请记住，检查您的前端池的内部 DNS 记录是否存在主机 A（对于 IPv6 为 AAAA）记录，您的前端池（例如 lyncwebpool01.contoso.local）的内部 Web 服务 FQDN 应存在主机 A（或 AAAA）记录。如果不存在，您需要记下前端服务器或 Standard Edition Server的 FQDN。

6.  在知道存在的具体主机 A（或 AAAA）记录后，请在 DNS 服务器的控制台树中，展开您的 SIP 域（例如 contoso.com）的“正向查找区域”。

7.  右键单击 SIP 域名，然后单击“新建别名 (CNAME)”。

8.  在“别名”中，键入 lyncdiscoverinternal 作为内部自动发现服务 URL 的主机名称。

9.  在“目标主机的完全合格的域名 (FQDN)”中，键入或浏览到控制器池（例如 lyncwebdir01.contoso.local）的内部 Web 服务 FQDN，然后单击“确定”。

10. 您必须在您的 Lync Server 2013 环境中支持的每个 SIP 域的正向查找区域中创建一条新的自动发现 CNAME 记录。

## 创建外部 DNS CNAME 记录

1.  要创建外部 DNS CNAME 记录，您需要连接到您的公共 DNS 提供商，然后按照我们的步骤执行操作。我们无法描述您在 DNS 提供商的环境中的确切位置，因为管理外部 DNS 的方式可能不同，然而我们希望这些步骤有所帮助。

2.  使用可在该环境中创建 DNS 记录的帐户登录到外部 DNS 提供商。

3.  您应该已为此环境创建了 SIP 域。请展开此 SIP 域的“正向查找区域”，否则请选中它，具体取决于所使用的外部 DNS 接口。

4.  您应该已经看到您的控制器池（如 lyncwebexdir01.contoso.com）的主机 A（对于 IPv6 为 AAAA）记录，因此请确认该记录存在。如果不存在，则您可能未使用控制器池。如果是这样或者您正在为单个服务器、前端服务器或 Standard Edition 服务器执行此操作，您需要使用前端池的 FQDN。

5.  您也需要确认您的前端池（如 lyncwebextpool01.contoso.com）的外部 Web 服务完全限定的域名 (FQDN) 或者单个服务器 FQDN（如果没有前端池）存在主机 A（对于 IPv6 为 AAAA）记录。如上一步骤所述，如果您没有控制器池，您在下面需要此内容。

6.  现在，针对外部 DNS 提供商采取合适的格式，选择用于创建**新别名 (CNAME)** 的选项（这可能是一个菜单选项或一个链接，具体取决于 DNS 提供商的格式）。

7.  应存在某种形式的与内部 DNS 相同的“别名”文本框，您应输入 lyncdiscover 作为外部自动发现服务 URL 的主机名。

8.  还应存在某种形式的“目标主机的完全合格的域名 (FQDN)”文本框，在这里，您将输入控制器池（例如 lyncwebexdir01.contoso.com）池的外部 Web 服务 FQDN，然后单击“确定”或者在外部 DNS 中执行某项操作以接受创建此条目。如上面的步骤 4 所述，如果您没有控制器池，您需要根据需要使用前端池 FQDN 或设置的单个服务器 FQDN。

9.  您需要在 Lync 2013 环境中支持的每个 SIP 域的正向查找区域中创建一条新的自动发现 CNAME 记录。

## 创建内部 DNS A 记录

1.  若要创建内部 DNS 记录，请使用属于 Domain Admins 组成员或 DnsAdmins 组成员的域帐户登录网络中的 DNS 服务器。

2.  打开 DNS 管理单元：依次单击“开始”、“管理工具”和“DNS”。

3.  对于内部 DNS 记录，在 DNS 服务器的控制台树中，展开已安装 Lync Server 2013控制器池和前端池的 Active Directory 域（例如 contoso.local）的“正向查找区域”。

4.  检查您的控制器池的内部 DNS 记录是否存在主机 A（对于 IPv6 为 AAAA）记录，您的控制器池（例如 lyncwebdir01.contoso.local）的内部 Web 服务完全限定的域名 (FQDN) 应存在主机 A 记录。如果不存在，则您不能使用控制器池，并且您需要使用前端池的 IP 地址甚至单个服务器 IP 地址（如果已设置）。

5.  请记住，检查您的前端池的内部 DNS 记录是否存在主机 A（对于 IPv6 为 AAAA）记录，您的前端池（例如 lyncwebpool01.contoso.local）的内部 Web 服务 FQDN 应存在主机 A（或 AAAA）记录。如果不存在，您需要记下前端服务器或 Standard Edition Server的 IP 地址。

6.  在知道存在的具体主机 A（或 AAAA）记录后，请在 DNS 服务器的控制台树中，展开您的 SIP 域（例如 contoso.com）的“正向查找区域”。

7.  右键单击 SIP 域名，然后单击“新建主机(A 或 AAAA)”。

8.  在“名称”中，键入 lyncdiscoverinternal 作为内部自动发现服务 URL 的主机名称。

9.  在“IP 地址”中，键入控制器的内部 Web 服务 IP 地址（或者，如果您使用的是负载平衡器，则键入控制器负载平衡器的虚拟 IP (VIP)）。如上面的步骤 4 所述，如果您未使用控制器，您可能需要输入前端服务器或 Standard Edition Server的 IP 地址，或者，如果您使用的是负载平衡器，则键入前端池负载平衡器的 VIP。

10. 单击“添加主机”，然后单击“确定”。

11. 要创建另一条 A 或 AAAA 记录，请重复步骤 8 至 10，请记住，您需要在 Lync Server 2013 环境中支持的每个 SIP 域的正向查找区域中创建一条新的自动发现 A 或 AAAA 记录。

12. 创建完 A 记录（对于 IPv6 为 AAAA）后，请单击“完成”。

## 创建外部 DNS A 记录

1.  要创建外部 DNS 记录，请连接到您的公共 DNS 提供商，然后按照我们的步骤执行操作。我们无法描述您在 DNS 提供商的环境中的确切位置，因为管理外部 DNS 的方式可能不同，然而我们希望这些步骤有所帮助。

2.  您需要作为可在该环境中创建 DNS 记录的帐户登录。

3.  对于外部 DNS 记录，请在 DNS 服务器的控制台树中，展开 SIP 域（例如，contoso.com）所对应的“正向查找区域”。对于外部 DNS 记录，请在 DNS 服务器的控制台树中，展开 SIP 域（例如，contoso.com）所对应的“正向查找区域”。

4.  您应该已经看到您的控制器池（如 lyncwebexdir01.contoso.com）的主机 A（对于 IPv6 为 AAAA）记录，因此请确认该记录存在以及具体的 IP 地址。如果不存在，则您可能未使用控制器池。如果是这样或者您正在为单个服务器、前端服务器或 Standard Edition 服务器执行此操作，您需要使用前端池的 IP 地址。请记住，您的服务器也可能位于负载平衡器后面或者正在使用反向代理。也请记下 IP 地址以用于下面的步骤。

5.  您也需要确认您的前端池（如 lyncwebextpool01.contoso.com）的外部 Web 服务完全限定的域名 (FQDN) 或者单个服务器安装（如果没有前端池）的 IP 地址存在主机 A（对于 IPv6 为 AAAA）记录。如上一步骤所述，如果您没有控制器池，您在下面需要此内容。

6.  现在，针对外部 DNS 提供商采取合适的格式，选择用于创建**新主机 A 或 AAAA** 的选项（这可能是一个菜单选项或一个链接，具体取决于 DNS 提供商的格式）。

7.  应有一个位置输入**名称**，请键入 lyncdiscover 作为外部自动发现服务 URL 的主机名。

8.  也应有一个“IP 地址”文本框，在这里，您将输入您的控制器池（例如 lyncwebexdir01.contoso.com）的 IP 或者可能是池的负载平衡器的 IP（或效果相同的反向代理 IP），然后单击“确定”或者在外部 DNS 中执行某项操作以接受创建此条目。如上面的步骤 4 所述，如果您没有控制器池，您需要根据需要使用前端池 IP 地址或设置的单个服务器 IP 地址。

9.  您需要在 Lync 2013 环境中支持的每个 SIP 域的正向查找区域中创建一条新的自动发现 A 或 AAAA 记录。

