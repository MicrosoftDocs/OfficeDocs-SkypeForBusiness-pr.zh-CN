---
title: 迁移通讯簿
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 一般情况下，您的拓扑的其余部分以及迁移通讯簿。 但是，您可能需要执行一些迁移后的步骤，如果旧环境中自定义以下：
ms.openlocfilehash: 081246acaaede37ab7f7f204a3f7204d9b25fbcc
ms.sourcegitcommit: 0458232441d3aed8dd578f41a13078aa379c9b00
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/10/2019
ms.locfileid: "27788992"
---
# <a name="migrate-address-book"></a><span data-ttu-id="d0ad7-104">迁移通讯簿</span><span class="sxs-lookup"><span data-stu-id="d0ad7-104">Migrate Address Book</span></span>

<span data-ttu-id="d0ad7-105">一般情况下，您的拓扑的其余部分以及迁移通讯簿。</span><span class="sxs-lookup"><span data-stu-id="d0ad7-105">In general, the Address Book is migrated along with the rest of your topology.</span></span> <span data-ttu-id="d0ad7-106">但是，您可能需要执行一些迁移后的步骤，如果旧环境中自定义以下：</span><span class="sxs-lookup"><span data-stu-id="d0ad7-106">However, you might need to perform some post-migration steps if you customized the following in your legacy environment:</span></span> 

- <span data-ttu-id="d0ad7-107">自定义通讯簿规范化规则。</span><span class="sxs-lookup"><span data-stu-id="d0ad7-107">Customized the Address Book normalization rules.</span></span>

- <span data-ttu-id="d0ad7-108">更改将**UseNormalizationRules**参数的默认值为 False。</span><span class="sxs-lookup"><span data-stu-id="d0ad7-108">Changed the default value for the **UseNormalizationRules** parameter to False.</span></span> 


 <span data-ttu-id="d0ad7-109">**通讯簿规范化规则**</span><span class="sxs-lookup"><span data-stu-id="d0ad7-109">**Address Book Normalization Rules**</span></span>

<span data-ttu-id="d0ad7-110">如果旧环境中自定义通讯簿规范化规则，您必须将自定义的规则迁移到试点池。</span><span class="sxs-lookup"><span data-stu-id="d0ad7-110">If you customized Address Book normalization rules in your legacy environment, you must migrate the customized rules to your pilot pool.</span></span> <span data-ttu-id="d0ad7-111">如果您未自定义通讯簿规范化规则，则必须 nothing 通讯簿服务的迁移。</span><span class="sxs-lookup"><span data-stu-id="d0ad7-111">If you did not customize Address Book normalization rules, you have nothing to migrate for Address Book service.</span></span> <span data-ttu-id="d0ad7-112">有关业务服务器 2019年的 Skype 的默认规范化规则是旧安装的默认规则相同。</span><span class="sxs-lookup"><span data-stu-id="d0ad7-112">The default normalization rules for Skype for Business Server 2019 are the same as the default rules for the legacy install.</span></span> <span data-ttu-id="d0ad7-113">按照本节迁移自定义的规范化规则后面的过程。</span><span class="sxs-lookup"><span data-stu-id="d0ad7-113">Follow the procedure later in this section to migrate customized normalization rules.</span></span>

> [!NOTE]
> <span data-ttu-id="d0ad7-114">如果您的组织使用远程呼叫控制并且您自定义通讯簿规范化规则，您必须在本主题中执行过程，然后才能使用远程呼叫控制。</span><span class="sxs-lookup"><span data-stu-id="d0ad7-114">If your organization uses remote call control and you customized Address Book normalization rules, you must perform the procedure in this topic before you can use remote call control.</span></span> <span data-ttu-id="d0ad7-115">过程要求中的 RTCUniversalServerAdmins 组或同等权限的成员身份。</span><span class="sxs-lookup"><span data-stu-id="d0ad7-115">The procedure requires membership in the RTCUniversalServerAdmins group or equivalent rights.</span></span> 

 <span data-ttu-id="d0ad7-116">**UseNormalizationRules 设置为 False**</span><span class="sxs-lookup"><span data-stu-id="d0ad7-116">**UseNormalizationRules Set to False**</span></span>

<span data-ttu-id="d0ad7-117">如果您将值设置为**UseNormalizationRules**为 False，以便用户可以使用电话号码，如中定义无业务服务器 2019 Skype 的 Active Directory 域服务应用规范化规则，您需要设置**UseNormalizationRules**和**IgnoreGenericRules**参数为 True。</span><span class="sxs-lookup"><span data-stu-id="d0ad7-117">If you set the value for **UseNormalizationRules** to False so that users can use phone numbers as they are defined in Active Directory Domain Services without having Skype for Business Server 2019 apply normalization rules, you need to set the **UseNormalizationRules** and **IgnoreGenericRules** parameters to True.</span></span> <span data-ttu-id="d0ad7-118">按照此部分将这些参数设置为 True 中稍后介绍的过程。</span><span class="sxs-lookup"><span data-stu-id="d0ad7-118">Follow the procedure later in this section to set these parameters to True.</span></span> 

## <a name="to-migrate-address-book-customized-normalization-rules"></a><span data-ttu-id="d0ad7-119">迁移通讯簿自定义规范化规则</span><span class="sxs-lookup"><span data-stu-id="d0ad7-119">To migrate Address Book customized normalization rules</span></span>

1. <span data-ttu-id="d0ad7-120">通讯簿共享文件夹的根目录中查找 Company_Phone_Number_Normalization_Rules.txt 文件，并将其复制到您的业务服务器 2019年试点池的 Skype 中的通讯簿共享文件夹的根目录。</span><span class="sxs-lookup"><span data-stu-id="d0ad7-120">Find the Company_Phone_Number_Normalization_Rules.txt file in the root of the Address Book shared folder, and copy it to the root of the Address Book shared folder in your Skype for Business Server 2019 pilot pool.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d0ad7-121">已在 ABS Web 组件文件目录中安装通讯簿规范化规则示例。</span><span class="sxs-lookup"><span data-stu-id="d0ad7-121">The sample Address Book normalization rules have been installed in your ABS Web component file directory.</span></span> <span data-ttu-id="d0ad7-122">路径为 **$installedDriveLetter: \Program Files\Microsoft Business Server 2019\Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules.txt 的 Skype**。</span><span class="sxs-lookup"><span data-stu-id="d0ad7-122">The path is **$installedDriveLetter:\Program Files\Microsoft Skype for Business Server 2019\Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules.txt**.</span></span> <span data-ttu-id="d0ad7-123">可复制此文件，并将其重命名为**Company_Phone_Number_Normalization_Rules.txt**为通讯簿共享的文件夹的根目录。</span><span class="sxs-lookup"><span data-stu-id="d0ad7-123">This file can be copied and renamed as **Company_Phone_Number_Normalization_Rules.txt** to the address book shared folder's root directory.</span></span> <span data-ttu-id="d0ad7-124">例如，通讯簿中 **$serverX**共享，则路径将会类似于： \*\* \\$serverX \SkypeForBusiness-FileShare\2-WebServices-1\ABFiles\*\*。</span><span class="sxs-lookup"><span data-stu-id="d0ad7-124">For example, the address book shared in **$serverX**, the path will be similar to: **\\$serverX \SkypeForBusiness-FileShare\2-WebServices-1\ABFiles**.</span></span> 

2. <span data-ttu-id="d0ad7-125">使用文本编辑器，如记事本中，打开 Company_Phone_Number_Normalization_Rules.txt 文件。</span><span class="sxs-lookup"><span data-stu-id="d0ad7-125">Use a text editor, such as Notepad, to open the Company_Phone_Number_Normalization_Rules.txt file.</span></span>

3. <span data-ttu-id="d0ad7-126">某些类型的项将无法正常工作 Skype 中的业务服务器 2019年。</span><span class="sxs-lookup"><span data-stu-id="d0ad7-126">Certain types of entries will not work correctly in Skype for Business Server 2019.</span></span> <span data-ttu-id="d0ad7-127">在此步骤中所述的条目的类型的文件中查找、 根据需要，对其进行编辑和保存对试点池中通讯簿共享文件夹的更改。</span><span class="sxs-lookup"><span data-stu-id="d0ad7-127">Look through the file for the types of entries described in this step, edit them as necessary, and save the changes to the Address Book shared folder in your pilot pool.</span></span>

    <span data-ttu-id="d0ad7-128">包含需要的空格或标点符号原因规范化规则失败，因为这些字符去除超出输入到的规范化规则的字符串的字符串。</span><span class="sxs-lookup"><span data-stu-id="d0ad7-128">Strings that include required whitespace or punctuation cause normalization rules to fail because these characters are stripped out of the string that is input to the normalization rules.</span></span> <span data-ttu-id="d0ad7-129">如果必须包含必需的空格或标点的字符串，您需要修改字符串。</span><span class="sxs-lookup"><span data-stu-id="d0ad7-129">If you have strings that include required whitespace or punctuation, you need to modify the strings.</span></span> <span data-ttu-id="d0ad7-130">例如，以下字符串会导致规范化规则失败：</span><span class="sxs-lookup"><span data-stu-id="d0ad7-130">For example, the following string would cause the normalization rule to fail:</span></span>

   ```
   \s*\(\s*\d\d\d\s*\)\s*\-\s*\d\d\d\s*\-\s*\d\d\d\d
   ```

    <span data-ttu-id="d0ad7-131">以下字符串不会导致规范化规则失败：</span><span class="sxs-lookup"><span data-stu-id="d0ad7-131">The following string would not cause the normalization rule to fail:</span></span>

   ```
   \s*\(?\s*\d\d\d\s*\)?\s*\-?\s*\d\d\d\s*\-?\s*\d\d\d\d
   ```

## <a name="to-set-usenormalizationrules-and-ignoregenericrules-to-true"></a><span data-ttu-id="d0ad7-132">若要将 UseNormalizationRules 和 IgnoreGenericRules 设置为 true</span><span class="sxs-lookup"><span data-stu-id="d0ad7-132">To set UseNormalizationRules and IgnoreGenericRules to true</span></span>

1. <span data-ttu-id="d0ad7-133">为业务 Server 命令行管理程序启动 Skype： 单击**开始**，单击**所有程序**，都单击**Microsoft Skype 的业务服务器 2019年**，，然后都单击**Skype 的业务 Server Management Shell**。</span><span class="sxs-lookup"><span data-stu-id="d0ad7-133">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="d0ad7-134">请执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="d0ad7-134">Do one of the following:</span></span>

   - <span data-ttu-id="d0ad7-135">如果您的部署包括仅 Skype 的业务服务器 2019，在要以**将 UseNormalizationRules**和**IgnoreGenericRules**的值更改为 True 的全局级别运行以下 cmdlet:</span><span class="sxs-lookup"><span data-stu-id="d0ad7-135">If your deployment includes only Skype for Business Server 2019, run the following cmdlet at the global level to change the values for **UseNormalizationRules** and **IgnoreGenericRules** to True:</span></span> 

   ```
   Set-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
   ```

   - <span data-ttu-id="d0ad7-136">如果您的部署包括业务服务器 2019年和旧安装 Skype 的组合，运行以下 cmdlet 并将其分配给每个 Skype 业务服务器 2019年池拓扑中：</span><span class="sxs-lookup"><span data-stu-id="d0ad7-136">If your deployment includes a combination of Skype for Business Server 2019 and a legacy install, run the following cmdlet and assign it to each Skype for Business Server 2019 pool in the topology:</span></span>

   ```
   New-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
   ```

3. <span data-ttu-id="d0ad7-137">等待在所有池上发生中央管理存储复制。</span><span class="sxs-lookup"><span data-stu-id="d0ad7-137">Wait for Central Management store replication to occur on all pools.</span></span>

4. <span data-ttu-id="d0ad7-138">修改电话规范化规则文件，若要清除的内容部署"Company_Phone_Number_Normalization_Rules.txt"。</span><span class="sxs-lookup"><span data-stu-id="d0ad7-138">Modify the phone normalization rules file, "Company_Phone_Number_Normalization_Rules.txt", for your deployment to clear the content.</span></span> <span data-ttu-id="d0ad7-139">文件是在每个 Skype 业务服务器 2019年池的文件共享上。</span><span class="sxs-lookup"><span data-stu-id="d0ad7-139">The file is on the file share of each Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="d0ad7-140">如果文件不存在，然后创建一个名为"Company_Phone_Number_Normalization_Rules.txt"的空文件。</span><span class="sxs-lookup"><span data-stu-id="d0ad7-140">If the file is not present, then create an empty file named "Company_Phone_Number_Normalization_Rules.txt".</span></span>

5. <span data-ttu-id="d0ad7-141">等待几分钟，以便所有前端池读取新文件。</span><span class="sxs-lookup"><span data-stu-id="d0ad7-141">Wait several minutes for all Front End pools to read the new files.</span></span>

6. <span data-ttu-id="d0ad7-142">在部署中的业务服务器 2019年池的每个 Skype 上运行以下 cmdlet:</span><span class="sxs-lookup"><span data-stu-id="d0ad7-142">Run the following cmdlet on each Skype for Business Server 2019 pool in your deployment:</span></span>

   ```
   Update-CsAddressBook
   ```


