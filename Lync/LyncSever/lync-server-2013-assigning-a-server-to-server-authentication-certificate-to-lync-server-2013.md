---
title: 将服务器到服务器身份验证证书分配到 Microsoft Lync Server 2013
TOCTitle: 将服务器到服务器身份验证证书分配到 Microsoft Lync Server 2013
ms:assetid: c7413954-2504-47f4-a073-44548aff1c0c
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205253(v=OCS.15)
ms:contentKeyID: 49314199
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 将服务器到服务器身份验证证书分配到 Microsoft Lync Server 2013

 

_**上一次修改主题：** 2013-10-24_

要确定是否已经为 Microsoft Lync Server 2013 分配服务器到服务器身份验证证书，请从 Lync Server 2013 命令行管理程序运行以下命令：

    Get-CsCertificate -Type OAuthTokenIssuer

如果没有返回任何证书信息，则必须在分配令牌颁发者证书后才能使用服务器到服务器身份验证。一般而言，任何 Lync Server 2013 证书均可用作 OAuthTokenIssuer 证书；例如，Lync Server 2013 默认证书也可以用作 OAuthTokenIssuer 证书。（OAUthTokenIssuer 证书也可以是任何在“使用者”字段中包含 SIP 域名的 Web 服务器证书。）用于服务器到服务器身份验证的证书有两个主要要求：1) 必须在所有前端服务器上配置与 OAuthTokenIssuer 证书相同的证书；2) 证书必须至少为 2048 位。

如果没有可用于服务器到服务器身份验证的证书，则可以获取新证书，导入新证书，然后将该证书用于服务器到服务器身份验证。在请求并获取新证书后，可以登录到任一前端服务器并使用类似如下的 Windows PowerShell 命令导入和分配该证书：

    Import-CsCertificate -Identity global -Type OAuthTokenIssuer -Path C:\Certificates\ServerToServerAuth.pfx  -Password "P@ssw0rd"

在上述命令中，Path 参数表示证书文件的完整路径，Password 参数表示分配给该证书的密码。此过程只应运行一次：Lync Server 的复制服务随后将自动创建一组计划任务，这些任务会将证书解密并部署到所有前端服务器。

您也可以使用现有证书作为服务器到服务器身份验证证书。（如前所述，默认证书可用作服务器到服务器身份验证证书。）以下 Windows PowerShell 命令对可检索默认证书的 Thumbprint 属性的值，然后使用该值使默认证书成为服务器到服务器身份验证证书：

    $x = (Get-CsCertificate -Type Default).Thumbprint
    Set-CsCertificate -Identity global -Type OAuthTokenIssuer -Thumbprint $x

在上述命令中，所检索的证书配置为用作全局服务器到服务器身份验证证书；这意味着该证书将被复制到所有前端服务器并被这些服务器使用。再强调一次，此命令只应在其中一台前端服务器上运行一次。尽管所有前端服务器都必须使用相同证书，但您不应在每台前端服务器上都配置 OAuthTokenIssuer 证书。相反，只需配置该证书一次，然后让 Lync Server 的复制服务器负责将该证书复制到每台服务器。

Set-CsCertificate cmdlet 可获得相关证书并立即将该证书配置为用作当前的 OAuthTokenIssuer 证书。（Lync Server 2013 会保存一种证书类型的两个副本：当前证书和上一个证书。）如果需要新证书立即开始用作 OAuthTokenIssuer 证书，则应使用 Set-CsCertificate cmdlet。

您还可以使用 Set-CsCertificate cmdlet“滚动”新证书。“滚动”证书仅意味着在指定时间点将新证书配置为成为当前 OAuthTokenIssuer 证书。例如，以下命令将检索默认证书，然后将该证书配置为从 2012 年 7 月 1 日起成为当前 OAuthTokenIssuer 证书：

    $x = (Get-CsCertificate -Type Default).Thumbprint
    Set-CsCertificate -Identity global -Type OAuthTokenIssuer -Thumbprint $x -EffectiveDate "7/1/2012" -Roll

在 2012 年 7 月 1 日，新证书将配置为当前 OAuthTokenIssuer 证书，“旧”OAuthTokenIssuer 证书将配置为上一个证书。

如果不想使用 Windows PowerShell，还可以使用证书 MMC 控制台从一台前端服务器中导出证书，然后在所有其他前端服务器上导入相同证书。如果执行此操作，请确保将私钥连同证书本身一起导出。

> [!CAUTION]
> 在这种情况下，必须在每台前端服务器上执行该过程。以这种方式导出和导入证书时，Lync Server 2013 不会将该证书复制到每台前端服务器。


将证书导入到所有前端服务器后，可使用 Lync Server 部署向导而不是 Windows PowerShell 来分配该证书。要使用部署向导分配证书，请在安装了部署向导的计算机上完成以下步骤：

1.  依次单击“开始”、“所有程序”、“Microsoft Lync Server 2013”和“Lync Server 部署向导”。

2.  在部署向导中，单击“安装或更新 Lync Server 系统”。

3.  在 Microsoft Lync Server 2013 页面上，单击标题“步骤 3：请求、安装或分配证书”下的“运行”按钮。（注意：如果已在此计算机上安装证书，则“运行”按钮的标签将为“再次运行”。）

4.  在证书向导中，选择 OAuthTokenIssuer 证书，然后单击“分配”。

5.  在证书分配向导的“证书分配”页上，单击“下一步”。

6.  在“证书存储”页上，选择要用于服务器到服务器身份验证的证书，然后单击“下一步”。

7.  在“证书分配摘要”页上，单击“下一步”。

8.  在“正在执行命令”页上，单击“完成”。

9.  关闭证书向导和部署向导。

