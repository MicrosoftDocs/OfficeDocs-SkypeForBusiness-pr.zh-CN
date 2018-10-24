---
title: Lync Server 2013：运行域准备
TOCTitle: 运行域准备
ms:assetid: 95dab800-1f2c-4506-b36c-99986643b149
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398761(v=OCS.15)
ms:contentKeyID: 49313655
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 为 Lync Server 2013 运行域准备

 

_**上一次修改主题：** 2013-04-16_

您可以使用安装程序或 Lync Server 命令行管理程序 cmdlet 准备域。准备域的 cmdlet 为 **Enable-CsAdDomain**。

域准备是为 Lync Server 2013 准备 Active Directory 域服务 的最后一步。

## 使用安装程序来准备域

1.  以 Domain Admins 组成员的身份登录域中的任何服务器。

2.  从 Lync Server 2013 安装文件夹或媒体中，运行 Setup.exe 来启动 Lync Server 部署向导。

3.  单击“准备 Active Directory”，然后等待确定部署状态。

4.  在“步骤 5: 准备当前域”中，单击“运行”。

5.  在“准备域”页上，单击“下一步”。

6.  在“正在执行命令”页上，查找“任务状态: 已完成”，然后单击“查看日志”。

7.  在“操作”列下，展开“域准备”，在每项任务的结尾查找“\<成功\>”执行结果，以确认域准备成功完成，关闭日志，然后单击“完成”。

8.  等待 Active Directory 复制完成，或者强制向目录林根级域控制器的“Active Directory 站点和服务”管理单元中列出的所有域控制器进行复制。

## 使用 cmdlet 准备域

1.  以 Domain Admins 组成员的身份登录域中的任何服务器。

2.  安装 Lync Server 核心组件，如下所示：
    
    1.  从 Lync Server 2013 安装文件夹或媒体中，运行 Setup.exe 来启动 Lync Server 部署向导。
    
    2.  如果提示您安装 Microsoft Visual C++ 可再发行软件产品，单击“是”。
    
    3.  Lync Server 2013 的“安装”对话框将提示您选择安装 Lync Server 文件的位置。选择默认位置或“浏览”至要选择的位置，然后单击“安装”。
    
    4.  在“许可协议”页上，选中“我接受许可协议中的条款”，然后单击“确定”。此时安装程序将安装 Lync Server 2013 核心组件。

3.  启动 Lync Server 命令行管理程序：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 命令行管理程序”。

4.  运行：
    
        Enable-CsAdDomain [-Domain <DomainFQDN>] 
    
    例如：
    
        Enable-CsAdDomain -Domain domain1.contoso.net 
    
    如果不指定 Domain 参数，则默认为本地域。

5.  确认域准备是否已成功。运行：
    
        Get-CsAdDomain [-Domain <Domain FQDN>] [-DomainController <Domain controller FQDN>] [-GlobalCatalog <Global catalog server FQDN>] [-GlobalSettingsDomainController <Domain controller FQDN where global settings are stored>] 
    
    例如：
    
        Get-CsAdDomain -Domain domain1.contoso.net -GlobalSettingsDomainController dc01.domain1.contoso.com
    
    > [!NOTE]  
	> 参数 GlobalSettingsDomainController 用于指出存储全局设置的位置。如果设置存储在“系统”容器中（通常在全局设置尚未迁移到“配置”容器的升级部署中是这种情况），则定义 Active Directory 林的根中的某个域控制器。如果全局设置存储在“配置”容器中（通常在新部署或设置已迁移到“配置”容器的升级部署中是这种情况），则定义林中的任何域控制器。如果未指定此参数，则 cmdlet 会假定设置存储在“配置”容器中，并引用 AD DS 中的任何域控制器。
    
    
    如果不指定 **Domain** 参数，则默认为本地域。
    
    如果域准备已成功，cmdlet 将返回 **LC\_DOMAINSETTINGS\_STATE\_READY** 。

## 另请参阅

#### 任务

[使用 Cmdlet 为 Lync Server 2013 反向执行域准备](lync-server-2013-using-cmdlets-to-reverse-domain-preparation.md)  

#### 其他资源

[为 Lync Server 2013 准备域](lync-server-2013-preparing-domains.md)

