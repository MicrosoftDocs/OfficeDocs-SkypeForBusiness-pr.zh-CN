---
title: 验证地址
TOCTitle: 验证地址
ms:assetid: aae557c9-e6f5-4d23-8af1-1d4cd7968c54
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg412808(v=OCS.15)
ms:contentKeyID: 49313890
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 验证地址

 

_**上一次修改主题：** 2012-09-17_

发布位置数据库前，必须根据您的 SIP 中继或公用电话交换网 (PSTN) E9-1-1 服务提供商维护的主街道地址指南 (MSAG) 验证新位置。

有关 SIP 中继E9-1-1 服务提供商的详细信息，请参阅[选择 Lync Server 2013 的 E9-1-1 服务提供商](lync-server-2013-choosing-an-e9-1-1-service-provider.md)。

有关验证地址的详细信息，请参阅 Lync Server 命令行管理程序文档中有关以下 cmdlet 的内容：

  - **Get-CsLisServiceProvider**

  - **Set-CsLisServiceProvider**

  - **Remove-CsLisServiceProvider**

  - **Get-CsLisCivicAddress**

  - **Test-CsLisCivicAddress**

## 验证位于位置数据库中的地址

1.  启动 Lync Server 命令行管理程序：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 命令行管理程序”。

2.  运行以下 cmdlet 配置紧急服务提供商连接。
    
        $pwd = Read-Host -AsSecureString <password>
        Set-CsLisServiceProvider -ServiceProviderName Provider1 -ValidationServiceUrl <URL provided by provider> -CertFileName <location of certificate provided by provider> -Password $pwd

3.  运行以下 cmdlet 验证位置数据库中的地址。
    
        Get-CsLisCivicAddress | Test-CsLisCivicAddress -UpdateValidationStatus
    
    还可以使用 **Test-CsLisCivicAddress** cmdlet 验证单个地址。

