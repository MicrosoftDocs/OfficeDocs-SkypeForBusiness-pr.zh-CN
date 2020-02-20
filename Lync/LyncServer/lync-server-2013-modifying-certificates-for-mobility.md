---
title: Lync Server 2013：修改用于移动性的证书
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modifying certificates for mobility
ms:assetid: 4e9107af-20f4-4c2a-8c98-ca35b39a4e2d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690015(v=OCS.15)
ms:contentKeyID: 48184120
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 138e4c442f482550160b3a836a2d3258b5273853
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149391"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="modifying-certificates-for-mobility-in-lync-server-2013"></a>在 Lync Server 2013 中修改证书的移动性

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2014-06-20_

若要支持 Lync 环境与移动客户端之间的安全连接，必须使用其他一些使用者备用名称更新控制器池、前端池和反向代理的安全套接字层（SSL）证书（SAN）项。 如果您需要查看有关移动性的证书要求的更多详细信息，请参阅在[Lync Server 2013 中的移动技术要求](lync-server-2013-technical-requirements-for-mobility.md)中的证书要求部分，但基本上您需要从证书颁发机构获取新证书和包含的其他 SAN 条目，然后使用本文的步骤添加这些证书。

当然，在开始之前，通常最好知道证书已拥有的备选主题名称。 如果您不确定已配置的内容，可以通过多种方式来确定。[！注意] 此选项是运行**set-cscertificate**和其他 PowerShell 命令以查看此信息（我们将在下面进行介绍），默认情况下将截断数据，因此您可能无法看到所需的所有属性。 为了更好地了解证书及其所有属性，可以转到 Microsoft 管理控制台（MMC）并加载证书管理单元（我们还将在下面进行），也可以只签入 Lync Server 部署向导。

如前所述，以下步骤将指导您使用 Lync Server 命令行管理程序和 MMC 更新证书。 如果你想要改用 Lync Server 部署向导中的证书向导，则可以检查为控制器或控制器池[配置 Lync server 2013 中的 director 的证书](lync-server-2013-configure-certificates-for-the-director.md)（如果配置了一个）（你可能没有）。 对于前端服务器或前端池，您需要[在 Lync Server 2013 中查看 "配置服务器的证书](lync-server-2013-configure-certificates-for-servers.md)"。

要记住的最后一件事是，您可能在 Lync Server 2013 环境中有一个默认证书，或者，默认情况下（这是除 web 服务之外的所有内容）、WebServicesExternal 和 WebServicesInternal 的证书。 无论您是什么配置，这些步骤都应帮助您解决。

<div>

## <a name="to-update-certificates-with-new-subject-alternative-names-using-the-lync-server-management-shell"></a>使用 Lync Server 命令行管理程序将证书更新为新的使用者可选名称

1.  您需要使用具有本地管理员权限和权限的帐户登录到 Lync Server 2013 服务器。 此外，如果在步骤12和更高版本中运行 PowerShell**请求-set-cscertificate** ，则帐户需要具有指定的证书颁发机构（CA）的权限。

2.  启动 Lync Server 命令行管理程序：依次单击“开始”****、“所有程序”****、“Microsoft Lync Server 2013”**** 和“Lync Server 命令行管理程序”****。

3.  在分配更新的证书之前，需要找出已分配给服务器的证书以及使用的类型。 在命令行中键入：
    
        Get-CsCertificate

4.  查看上一步的输出，以查看是否已为多个使用分配了单个证书，或者是否为每个使用分配了不同的证书。 查看 Use 参数以了解如何使用证书。 比较显示的证书的 Thumbprint 参数以了解同一个证书是否有多种用途。 关注指纹参数。

5.  更新证书。 在命令行中键入：
    
        Set-CsCertificate -Type <type of certificate as displayed in the Use parameter> -Thumbprint <unique identifier>
    
    例如，如果**set-cscertificate** Cmdlet 显示使用 "默认" 的证书，另一个使用了 WebServicesInternal，另一个使用了 WebServicesExternal，而另一个使用的是相同的指纹值，则应在命令行中键入：
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
    
    **重要说明：**
    
    如果为每个使用分配了单独的证书（因此您在上面检查的指纹值与每个证书不同），请务必运行具有多种类型的**set-cscertificate** cmdlet，如上面的示例**中所示**。 在此情况下，请对每种使用情况单独运行 **Set-CsCertificate** cmdlet。 例如：
    
        Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>

6.  若要查看证书（或证书），请单击 "**开始**"，然后单击 "**运行 ...**"。 键入 MMC 以打开 Microsoft 管理控制台。

7.  从 MMC 菜单中，依次选择“文件”****、“添加/删除管理单元...”**** 和“证书”。 单击“添加”****。 出现提示时，请选择“计算机帐户”****，然后单击“下一步”****。

8.  如果这是证书所在的服务器，请选择 "**本地计算机**"。 如果证书位于另一台计算机上，则应选择**另一台计算机**，然后可以键入计算机的完全限定域名，或者单击 "**浏览** **" 以选择 "要选择的对象名称**"，然后键入计算机的名称。 单击“检查名称”****。 当计算机的名称解析时，它将带下划线。 单击“确定”****，然后单击“完成”****。 单击“确定”**** 以提交选项并关闭“添加或删除管理单元”**** 对话框。

9.  若要查看证书的属性，请展开“证书”****、“个人”****，然后选择“证书”****。选择要查看的证书，右键单击证书并选择“打开”****。

10. 在“证书”**** 视图中，选择“详细信息”****。从此处，您可通过选择“使用者”**** 来选择证书的使用者名称，这将显示分配的使用者名称和关联的属性。

11. 若要查看分配的使用者替代名称，请选择“使用者替代名称”****。 此处显示所有分配的主题备用名称。 此处找到的主题备用名称默认为 " **DNS 名称**" 类型。 您应看到下列成员（所有成员应是 DNS 主机中显示的完全限定域名）（A；如果是 IPv6，则为 AAAA）记录：
    
      - 此池的池名称，如果不是池，则为单个服务器名称
    
      - 证书将分配到的服务器名称
    
      - 简单 URL 记录，一般为 meet 和 dialin
    
      - Web 服务内部和 Web 服务外部名称（例如，webpool01.contoso.net、webpool01.contoso.com），这取决于在拓扑生成器和替代 Web 服务选择中所做的选择。
    
      - 如果已分配，则为 lyncdiscover.。\<sipdomain\>和 lyncdiscoverinternal.。\<sipdomain\>记录。
    
    最后一项是你最感兴趣的内容–如果有 lyncdiscover. 和 lyncdiscoverinternal. SAN 条目。
    
    如果您有多个要检查的证书，请重复这些步骤。 了解此信息后，您可关闭证书视图和 MMC。

12. 如果缺少自动发现服务使用者替代名称，并且要对 Default、WebServicesInternal 和 WebServiceExternal 类型使用单独的默认证书，请执行下列操作：
    
      - 在 Lync Server Management Shell 命令行提示符处，键入：
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        如果您有多个 SIP 域，则不能使用新的 AllSipDomain 参数。 相反，您需要使用 DomainName 参数。 使用 DomainName 参数时，您必须定义 lyncdiscoverinternal. 和 lyncdiscover. 记录的 FQDN。 例如：
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - 若要分配证书，请键入以下命令：
        
            Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        其中“Thumbprint”是新颁发的证书显示的指纹。

13. 对于在将单独的证书用于默认值、WebServicesInternal 和 WebServicesExternal 时缺少内部自动发现 SAN，请执行以下操作：
    
      - 在 Lync Server Management Shell 命令行提示符处，键入：
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
        
        如果您有多个 SIP 域，则不能使用新的 AllSipDomain 参数。 相反，您需要使用 DomainName 参数。 使用 DomainName 参数时，您必须对 SIP 域 FQDN 使用适当的前缀。 例如：
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - 对于缺少的外部自动发现服务使用者替代名称，请在命令行中键入：
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        如果您有多个 SIP 域，则不能使用新的 AllSipDomain 参数。 相反，您需要使用 DomainName 参数。 使用 DomainName 参数时，您必须对 SIP 域 FQDN 使用适当的前缀。 例如：
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -DomainName "Lyncdiscover.contoso.com, Lyncdiscover.contoso.net" -verbose
    
      - 若要分配单独的证书类型，请键入以下命令：
        
            Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        其中“Thumbprint”是新颁发的独立证书显示的指纹。
    
    <div>
    

    > [!NOTE]  
    > 应注意的是，仅当运行这些步骤的帐户具有适当权限的证书颁发机构的访问权限时，才应运行步骤12和13。 如果您无法使用获得这些权限的帐户登录，或者如果您使用的是证书的公用或远程证书颁发机构，则需要通过 Lync Server 部署向导请求它们，该向导的主要内容在<.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

