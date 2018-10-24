---
title: Lync Server 2013：使用安全配置向导在 IIS 中关闭端口后重新激活服务器
TOCTitle: 使用安全配置向导在 IIS 中关闭端口后重新激活服务器
ms:assetid: cb8e17cf-f8c1-4099-b63b-c242d656c26a
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398851(v=OCS.15)
ms:contentKeyID: 49314256
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 使用安全配置向导在 IIS 中关闭端口后重新激活服务器

 

_**上一次修改主题：** 2012-10-01_

一些 Lync Server 2013 角色在 Internet Information Services (IIS) 端口 4443 上运行 Web 服务。运行 Lync Server 部署向导、Bootstrapper.exe 或使用 **Enable-CsComputer** cmdlet 创建防火墙中的例外并打开端口。如果随后运行 Windows Server 2008 R2 安全配置向导（或其他强化脚本），端口 4443 将被锁定，外部客户端将无法联系 Web 服务。要重新打开该端口，可以直接修改防火墙例外，也可以重新激活服务器。

## 通过使用部署向导重新激活服务器

1.  在 Lync Server 部署向导页上，单击“步骤 2: 安装或删除 Lync Server 组件”旁边的“运行”。

2.  在“设置 Lync Server 组件”页上，单击“下一步”。

3.  在“正在执行命令”页上，任务状态显示为已完成时，单击“完成”。
    
    > [!NOTE]  
	> 还可以使用 bootstrapper.exe 或 <strong>Enable-CsComputer</strong> 来重新激活服务器。
    

