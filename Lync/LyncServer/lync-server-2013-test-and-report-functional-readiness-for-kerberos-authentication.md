---
title: Lync Server 2013：测试并报告 Kerberos 身份验证的功能准备工作
TOCTitle: 测试并报告 Kerberos 身份验证的功能准备工作
ms:assetid: d52c39e5-747d-4f29-88aa-30fd6f26b99c
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398925(v=OCS.15)
ms:contentKeyID: 49314369
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中测试并报告 Kerberos 身份验证的功能准备工作

 

_**上一次修改主题：** 2012-01-16_

要成功完成此过程，应以 RTCUniversalServerAdmins 组成员的身份登录。

可以使用 **Test-CsKerberosAccountAssignment**Windows PowerShell cmdlet 测试并报告 Kerberos 身份验证站点分配的运行就绪情况。此命令查询必需参数 Identity 中指定的站点。可选参数 Report 会导致该 cmdlet 将 HTML 报告写入运行该命令的计算机上的 C:\\Logs。可选参数 Verbose 会将活动信息显示在屏幕上。

## 测试并报告站点的 Kerberos 身份验证的运行就绪情况

1.  以 RTCUniversalServerAdmins 组成员的身份登录到运行 Lync Server 2013 的域中的计算机或登录到安装了管理工具的计算机。

2.  启动 Lync Server 命令行管理程序：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 命令行管理程序”。

3.  在命令行中运行以下命令：
    
        Test-CsKerberosAccountAssignment -Identity "site:SiteName" -Report "c:\logs\FileName.htm" -Verbose
    
    例如：
    
        Test-CsKerberosAccountAssignment -Identity "site:Redmond" -Report "c:\logs\KerberosReport.htm" -Verbose

