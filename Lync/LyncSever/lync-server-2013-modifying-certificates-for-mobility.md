---
title: Lync Server 2013：修改证书以实现移动功能
TOCTitle: 修改证书以实现移动功能
ms:assetid: 4e9107af-20f4-4c2a-8c98-ca35b39a4e2d
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Hh690015(v=OCS.15)
ms:contentKeyID: 49312811
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中修改证书以实现移动功能

 

_**上一次修改主题：** 2014-06-20_

要支持 Lync 环境和移动客户端之间的安全连接，您的控制器池、前端池和反向代理的安全套接字层 (SSL) 证书需要使用一些附加使用者可选名称 (SAN) 条目进行更新。如果需要查看有关移动性的证书要求的更多详细信息，请参阅[Lync Server 2013 中的移动性技术要求](lync-server-2013-technical-requirements-for-mobility.md)中的“证书要求”部分，但是基本上，您需要从证书颁发机构处获取包括附加 SAN 条目的新证书，然后使用本文的步骤添加这些证书。

当然，在开始之前最好先了解您的证书已有的使用者可选名称。如果不确定已配置的内容，则有多种方法可查明。可选择运行 **Get-CsCertificate** 和其他 PowerShell 命令来查看此信息（我们将在下面逐步介绍），默认情况下该数据将被截断，因此您可能不会看到需要的所有属性。为了更好地查看证书及其所有属性，您可以转到 Microsoft 管理控制台 (MMC) 并加载证书管理单元（我们也将在下面逐步介绍），或者您可以仅在 Lync Server 部署向导中查看。

如上所述，以下步骤将引导您使用 Lync Server 命令行管理程序 和 MMC 更新证书。如果对使用 Lync Server 部署向导中的证书向导代替此方法感兴趣，并且您已配置（可能没有）控制器或控制器池，则可以查看[在 Lync Server 2013 中为控制器配置证书](lync-server-2013-configure-certificates-for-the-director.md)。对于前端服务器或前端池，您需要查看[在 Lync Server 2013 中为服务器配置证书](lync-server-2013-configure-certificates-for-servers.md)。

最后请记住，您可能在 Lync Server 2013 环境中具有单个默认证书，也可能对于默认（Web 服务以外的所有内容）、WebServicesExternal 和 WebServicesInternal 具有单独的证书。无论您的配置如何，这些步骤都应可帮助您排忧解难。

## 使用 Lync Server 命令行管理程序更新具有新的使用者替代名称的证书

1.  您需要使用具有本地管理员权限的帐户登录 Lync Server 2013 服务器。此外，如果您在步骤 12 以及其他步骤中运行 PowerShell **Request-CsCertificate**，则帐户需要对指定的证书颁发机构 (CA) 具有权限。

2.  启动 Lync Server 命令行管理程序：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 命令行管理程序”。

3.  在可以分配更新的证书之前，您需要查明已为服务器分配了哪些证书并将这些证书用于哪些类型的使用情况。在命令行中键入：
    
        Get-CsCertificate

4.  查看上一步骤中的输出内容以了解是否为多种使用情况分配了一个证书，或是否为每种使用情况分配了不同的证书。查看 Use 参数以了解证书的用法。比较显示的证书的 Thumbprint 参数以了解同一个证书是否有多种用途。密切关注 Thumbprint 参数。

5.  更新证书。在命令行中键入：
    
        Set-CsCertificate -Type <type of certificate as displayed in the Use parameter> -Thumbprint <unique identifier>
    
    例如，如果 **Get-CsCertificate** cmdlet 显示了一个用于默认使用情况的证书、一个用于 WebServicesInternal 的证书和一个用于 WebServicesExternal 的证书，并且这些证书都具有相同的 Thumbprint 值，则应在命令行中键入：
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
    
    **重要说明：**
    
    如果为每种使用情况分配单独的证书（以便您在上面检查的 Thumbprint 值对于每个证书均不同），请**不要**对多种类型运行 **Set-CsCertificate** cmdlet，这一点很重要。在此情况下，请对每种使用情况单独运行 **Set-CsCertificate** cmdlet。例如：
    
        Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>

6.  若要查看证书，请单击“开始”，再单击“运行…”。键入 MMC 以打开 Microsoft 管理控制台。

7.  从 MMC 菜单中，依次选择“文件”、“添加/删除管理单元...”和“证书”。单击“添加”。出现提示时，请选择“计算机帐户”，然后单击“下一步”。

8.  如果这是证书所在的服务器，请选择“本地计算机”。如果证书位于其他计算机上，则应选择“其他计算机”，然后您可以键入计算机的完全限定的域名或单击“输入要选择的对象名称”中的“浏览”，键入计算机的名称。单击“检查名称”。解析计算机的名称时，计算机名称将带下划线。单击“确定”，然后单击“完成”。单击“确定”以提交选项并关闭“添加或删除管理单元”对话框。

9.  若要查看证书的属性，请展开“证书”、“个人”，然后选择“证书”。选择要查看的证书，右键单击证书并选择“打开”。

10. 在“证书”视图中，选择“详细信息”。从此处，您可通过选择“使用者”来选择证书的使用者名称，这将显示分配的使用者名称和关联的属性。

11. 若要查看分配的使用者可选名称，请选择“使用者替代名称”。这里将显示分配的所有使用者可选名称。默认情况下，这里找到的使用者替代名称属于类型“DNS 名称”。您应看到下列成员（所有成员应是 DNS 主机中显示的完全限定的域名）（A；如果是 IPv6，则为 AAAA）记录：
    
      - 此池的池名称；如果它不是一个池，则为单台服务器名称
    
      - 证书将分配到的服务器名称
    
      - 简单 URL 记录，一般为 meet 和 dialin
    
      - Web 服务内部和 Web 服务外部名称（例如，webpool01.contoso.net、webpool01.contoso.com），这基于在 拓扑生成器和替代 Web 服务选择中做出的选择。
    
      - 如果已分配，则为 lyncdiscover.\<sipdomain\> 和 lyncdiscoverinternal.\<sipdomain\> 记录。
    
    最后一项是您最关注的内容 – 是否存在 lyncdiscover 和 lyncdiscoverinternal SAN 项。
    
    如果您有多个证书需要检查，请重复这些步骤。了解此信息后，您可关闭证书视图和 MMC。

12. 如果缺少自动发现服务使用者替代名称，并且要对 Default、WebServicesInternal 和 WebServiceExternal 类型使用单独的默认证书，请执行下列操作：
    
      - 在 Lync Server 命令行管理程序命令行提示符处，键入：
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        如果您有许多 SIP 域，则不能使用新的 AllSipDomain 参数，而必须使用 DomainName 参数。使用 DomainName 参数时，您必须为 lyncdiscoverinternal 和 lyncdiscover 记录定义 FQDN。例如：
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - 若要分配证书，请键入以下命令：
        
            Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        其中“Thumbprint”是新颁发的证书显示的指纹。

13. 对于对 Default、WebServicesInternal 和 WebServicesExternal 使用单独的证书时缺少内部自动发现 SAN 的情况，请执行下列操作：
    
      - 在 Lync Server 命令行管理程序命令行提示符处，键入：
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
        
        如果您有多个 SIP 域，则无法使用新的 AllSipDomain 参数。您需要改为使用 DomainName 参数。当您使用 DomainName 参数时，您必须对 SIP 域 FQDN 使用适当的前缀。例如：
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - 对于缺少的外部自动发现服务使用者替代名称，请在命令行中键入：
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        如果您有多个 SIP 域，则无法使用新的 AllSipDomain 参数。您需要改为使用 DomainName 参数。当您使用 DomainName 参数时，您必须对 SIP 域 FQDN 使用适当的前缀。例如：
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -DomainName "Lyncdiscover.contoso.com, Lyncdiscover.contoso.net" -verbose
    
      - 若要分配单独的证书类型，请键入以下命令：
        
            Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        其中“Thumbprint”是新颁发的独立证书显示的指纹。
    
    > [!NOTE]  
    > 请注意，只有当运行步骤 12 和 13 的帐户能够使用合适的权限访问证书颁发机构时，才应执行这两个步骤。如果您无法使用获得这些权限的帐户登录或者您正在为证书使用公共或远程证书颁发机构，则您需要通过 Lync Server 部署向导请求它们，文章顶部已进行了介绍。
    

