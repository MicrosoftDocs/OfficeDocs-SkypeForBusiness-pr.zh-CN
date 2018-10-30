---
title: 为自动发现配置证书
TOCTitle: 为自动发现配置证书
ms:assetid: 1842191d-df9a-41e0-9286-08c25f9b5dca
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ945617(v=OCS.15)
ms:contentKeyID: 52060969
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 为自动发现配置证书

 

_**上一次修改主题：** 2012-12-12_

您的控制器池、前端池和反向代理的证书需要其他使用者替代名称条目来支持与 Lync 客户端进行安全连接。

> [!NOTE]  
> 您可使用 <strong>Get-CsCertificate</strong> cmdlet 查看有关当前分配的证书的信息。但是，默认视图将截断证书的属性并且不会显示 SubjectAlternativeNames 属性中的所有值。您可使用 <strong>Get-CsCertificate</strong>、<strong>Request-</strong>CsCertificate 和 <strong>Set-CsCertificate</strong> cmdlet 查看部分信息以及请求和分配证书。但是，如果您不确定当前证书上使用者替代名称 (SAN) 的属性，则这不是最佳使用方法。若要查看证书和所有属性成员，则建议使用 <em>Microsoft 管理控制台 (MMC)</em> 中的证书管理单元或使用 Lync Server 部署向导。在 Lync Server 部署向导中，您可使用证书向导查看证书属性。下列过程中详细介绍了使用 Lync Server 命令行管理程序和 <em>Microsoft 管理控制台 (MMC)</em> 查看、请求和分配证书的过程。若要使用 Lync Server 部署向导，如果您已部署可选控制器或控制器池，请参阅此处的详细信息：<a href="lync-server-2013-configure-certificates-for-the-director.md">在 Lync Server 2013 中为控制器配置证书</a>。有关前端服务器或前端池，请参阅此处的详细信息：<a href="lync-server-2013-configure-certificates-for-servers.md">在 Lync Server 2013 中为服务器配置证书</a>。<br />
此过程中的初始步骤为准备步骤，以便为您确定当前证书扮演的角色。默认情况下，证书没有 lyncdiscover.&lt;sipdomain&gt; 或 lyncdiscoverinternal.&lt;内部域名&gt; 项，除非您之前安装了 Mobility Service 或提前准备了证书。此过程使用示例 SIP 域名“contoso.com”和示例内部域名“contoso.net”。<br />
Lync Server 2013 和 Lync Server 2010 的默认证书配置为对于 Default（对于 Web 服务之外的所有用途）、WebServicesExternal 和 WebServicesInternal 用途使用单个证书（名为“默认”）。可选配置是对每种用途使用单独的证书。可使用 Lync Server 命令行管理程序和 Windows PowerShell cmdlet 管理证书，也可以使用 Lync Server 部署向导中的证书向导进行管理。



## 使用 Lync Server 命令行管理程序更新具有新的使用者替代名称的证书

1.  使用具有本地管理员权限的帐户登录计算机。

2.  启动 Lync Server 命令行管理程序：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 命令行管理程序”。

3.  查明已为服务器分配哪些证书并将这些证书用于哪些类型的使用情况。您在下一个步骤中需要使用此信息来分配更新后的证书。在命令行中键入：
    
        Get-CsCertificate

4.  查看上一步骤中的输出内容以了解是否为多种使用情况分配了一个证书，或是否为每种使用情况分配了不同的证书。查看 Use 参数以了解证书的用法。比较显示的证书的 Thumbprint 参数以了解同一个证书是否有多种用途。

5.  更新证书。在命令行中键入：
    
        Set-CsCertificate -Type <type of certificate as displayed in the Use parameter> -Thumbprint <unique identifier>
    
    例如，如果 **Get-CsCertificate** cmdlet 显示了一个用于默认使用情况的证书、一个用于 WebServicesInternal 的证书和一个用于 WebServicesExternal 的证书，并且这些证书都具有相同的 Thumbprint 值，请在命令行中键入：
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
    
    **重要说明：**
    
    如果为每种使用情况分配一个单独的证书（每个证书的 Thumbprint 值不同），则请不要对多种类型运行 **Set-CsCertificate** cmdlet，这一点很重要。在此情况下，请对每种使用情况单独运行 **Set-CsCertificate** cmdlet。例如：
    
        Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>

6.  若要查看证书，请单击“开始”，再单击“运行…”。键入 MMC 以打开 Microsoft 管理控制台。

7.  从 MMC 菜单中，依次选择“文件”、“添加/删除管理单元...”和“证书”。单击“添加”。出现提示时，请选择“计算机帐户”，然后单击“下一步”。

8.  如果证书位于此计算机上，请选择“本地计算机”。如果证书位于其他计算机上，请选择“其他计算机”，键入计算机的完全限定域名或单击“输入要选择的对象名称”中的“浏览”，键入计算机的名称。单击“检查名称”。解析计算机的名称时，计算机名称将带下划线。单击“确定”，然后单击“完成”。单击“确定”以提交选项并关闭“添加或删除管理单元”对话框。
    
    > [!IMPORTANT]
    > 如果证书未显示在控制台中，则确保未选择“用户”或“服务”。必须选择“计算机”，否则将无法找到正确的证书。


9.  若要查看证书的属性，请展开“证书”、“个人”，然后选择“证书”。选择要查看的证书，右键单击证书并选择“打开”。

10. 在“证书”视图中，选择“详细信息”。从此处，您可通过选择“使用者”来选择证书的使用者名称，这将显示分配的使用者名称和关联的属性。

11. 若要查看分配的使用者替代名称，请选择“使用者替代名称”。这将显示分配的所有使用者替代名称。默认情况下，这将是在类型“DNS 名称”的属性中找到的使用者替代名称。您应看到下列成员（所有成员应是 DNS 主机中显示的完全限定域名）（A；如果是 IPv6，则为 AAAA）记录：
    
      - 此池的池名称；如果它不是一个池，则为单台服务器名称
    
      - 证书将分配到的服务器名称
    
      - 简单 URL 记录，一般为 meet 和 dialin
    
      - Web 服务内部和 Web 服务外部名称（例如，webpool01.contoso.net、webpool01.contoso.com），这基于在拓扑生成器和替代 Web 服务选择中做出的选择。
    
      - 如果已分配，则为 lyncdiscover.\<sipdomain\> 和 lyncdiscoverinternal.\<sipdomain\> 记录。
    
    最后一项是您最关注的内容 – 是否存在 lyncdiscover 和 lyncdiscoverinternal SAN 项。
    
    了解此信息后，您可关闭证书视图和 MMC。

12. 如果缺少含义为 lyncdiscover.\>域名\> 和 lyncdiscoverinternal.\<域名\>（基于这是外部证书还是内部证书）的自动发现服务的使用者替代名称，并且您要对 Default、WebServicesInternal 和 WebServiceExternal 类型使用单个默认证书，则执行下列操作：
    
      - 在 Lync Server 命令行管理程序命令行提示符处，键入：
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        如果您有许多 SIP 域，则不能使用新的 AllSipDomain 参数，而必须使用 DomainName 参数。使用 DomainName 参数时，您必须为 lyncdiscoverinternal 和 lyncdiscover 记录定义 FQDN。例如：
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - 若要分配证书，请键入以下命令：
        
            Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        其中“Thumbprint”是新颁发的证书显示的指纹。

13. 对于对 Default、WebServicesInternal 和 WebServicesExternal 使用单独的证书时缺少内部自动发现使用者替代名称的情况，请执行下列操作：
    
      - 在 Lync Server 命令行管理程序命令行提示符处，键入：
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
        
        如果您有多个 SIP 域，则无法使用新的 AllSipDomain 参数。相反，您必须使用 DomainName 参数。当您使用 DomainName 参数时，您必须对 SIP 域 FQDN 使用适当的前缀。例如：
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - 对于缺少的外部自动发现服务使用者替代名称，请在命令行中键入：
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        如果您有多个 SIP 域，则无法使用新的 AllSipDomain 参数。相反，您必须使用 DomainName 参数。当您使用 DomainName 参数时，您必须对 SIP 域 FQDN 使用适当的前缀。例如：
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -DomainName "Lyncdiscover.contoso.com, Lyncdiscover.contoso.net" -verbose
    
      - 若要分配单独的证书类型，请键入以下命令：
        
            Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        其中“Thumbprint”是新颁发的独立证书显示的指纹。

