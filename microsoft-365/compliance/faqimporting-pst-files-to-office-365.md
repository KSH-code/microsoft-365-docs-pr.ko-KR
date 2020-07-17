---
title: PST 파일 가져오기에 대한 FAQ
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 2fe71b05-f5a2-4182-ade7-4dc5cabdfd51
ms.custom: seo-marvel-apr2020
description: 이 문서에서는 Office 365 가져오기 서비스를 사용 하 여 PST 파일을 Microsoft 365로 가져오는 관리자를 위한 몇 가지 질문과 대답을 제공 합니다.
ms.openlocfilehash: 5ba6df2f2c6ed10edee22f58308a5e3ee5acd533
ms.sourcegitcommit: a4926e98b6594bbee68bfca90438c9c764499255
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/09/2020
ms.locfileid: "45091902"
---
# <a name="faq-about-importing-pst-files"></a><span data-ttu-id="d02e2-103">PST 파일 가져오기에 대한 FAQ</span><span class="sxs-lookup"><span data-stu-id="d02e2-103">FAQ about importing PST files</span></span>

<span data-ttu-id="d02e2-104">**이 문서는 관리자를 위한 것입니다. PST 파일을 자체 사서함으로 가져오시겠습니까? [Outlook .pst 파일에서 전자 메일, 연락처 및 일정 가져오기를](https://go.microsoft.com/fwlink/p/?LinkID=785075) 참조 하세요.**</span><span class="sxs-lookup"><span data-stu-id="d02e2-104">**This article is for administrators. Do you want to import PST files to your own mailbox? See [Import email, contacts, and calendar from an Outlook .pst file](https://go.microsoft.com/fwlink/p/?LinkID=785075)**</span></span>
   
<span data-ttu-id="d02e2-105">다음은 Office 365 가져오기 서비스를 사용 하 여 PST 파일을 Microsoft 365 사서함으로 대량으로 가져오는 방법에 대 한 몇 가지 질문과 대답입니다.</span><span class="sxs-lookup"><span data-stu-id="d02e2-105">Here are some frequently asked questions about using the Office 365 Import Service to bulk-import PST files to Microsoft 365 mailboxes.</span></span> <span data-ttu-id="d02e2-106">PST 파일을 가져오는 방법에 대 한 자세한 내용은 [pst 파일을 Office 365로 가져오기 개요](https://docs.microsoft.com/microsoft-365/compliance/importing-pst-files-to-office-365)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d02e2-106">For more information about how to import PST files, see [Overview of importing PST files to Office 365](https://docs.microsoft.com/microsoft-365/compliance/importing-pst-files-to-office-365).</span></span>
  
## <a name="using-network-upload-to-import-pst-files"></a><span data-ttu-id="d02e2-107">네트워크 업로드를 사용하여 PST 파일 가져오기</span><span class="sxs-lookup"><span data-stu-id="d02e2-107">Using network upload to import PST files</span></span>

<span data-ttu-id="d02e2-108">단계별 지침은 [네트워크 업로드를 사용 하 여 PST 파일을 Office 365에 가져오기](use-network-upload-to-import-pst-files.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d02e2-108">For step-by-step instructions, see [Use network upload to import PST files to Office 365](use-network-upload-to-import-pst-files.md).</span></span>
  
 <span data-ttu-id="d02e2-109">**Office 365 가져오기 서비스에서 가져오기 작업을 만드는 데 필요한 권한은 무엇입니까?**</span><span class="sxs-lookup"><span data-stu-id="d02e2-109">**What permissions are required to create import jobs in the Office 365 Import Service?**</span></span>
  
<span data-ttu-id="d02e2-110">PST 파일을 Microsoft 365 사서함으로 가져오려면 Exchange Online에서 사서함 가져오기/내보내기 역할을 할당받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d02e2-110">You have to be assigned the Mailbox Import Export role in Exchange Online to import PST files to Microsoft 365 mailboxes.</span></span> <span data-ttu-id="d02e2-111">기본적으로이 역할은 Exchange Online의 어떤 역할 그룹에도 할당되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d02e2-111">By default, this role isn't assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="d02e2-112">조직 관리 역할 그룹에 사서함 가져오기/내보내기 역할을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d02e2-112">You can add the Mailbox Import Export role to the Organization Management role group.</span></span> <span data-ttu-id="d02e2-113">또는 새 역할 그룹을 만들고, 사서함 가져오기 내보내기 역할을 할당한 다음 구성원으로 자신이나 다른 사용자를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d02e2-113">Or you can create a new role group, assign the Mailbox Import Export role, and then add yourself or other users as a member.</span></span> <span data-ttu-id="d02e2-114">자세한 내용은 [Exchange Online에서 역할 그룹 관리](https://go.microsoft.com/fwlink/p/?LinkId=730688)의 "역할 그룹에 역할 추가" 또는 "역할 그룹 만들기" 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d02e2-114">For more information, see the "Add a role to a role group" or the "Create a role group" sections in [Manage role groups in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=730688).</span></span>
  
<span data-ttu-id="d02e2-115">또한 보안 & 준수 센터에서 가져오기 작업을 만들려면 다음 중 하나가 충족되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d02e2-115">Additionally, to create import jobs in the Security & Compliance Center, one of the following must be true:</span></span>
  
- <span data-ttu-id="d02e2-116">Exchange Online에서 메일 받는 사람 역할을 할당받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d02e2-116">You have to be assigned the Mail Recipients role in Exchange Online.</span></span> <span data-ttu-id="d02e2-117">기본적으로 이 역할은 조직 관리 및 받는 사람 관리 역할 그룹에 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="d02e2-117">By default, this role is assigned to the Organization Management and Recipient Management roles groups.</span></span>
    
    <span data-ttu-id="d02e2-118">또는</span><span class="sxs-lookup"><span data-stu-id="d02e2-118">Or</span></span>
    
- <span data-ttu-id="d02e2-119">조직의 전역 관리자여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d02e2-119">You have to be a global administrator in your organization.</span></span>
    
> [!TIP]
> <span data-ttu-id="d02e2-120">Exchange Online에서 PST 파일을 Office 365로 가져오기 위한 새로운 역할 그룹을 만드는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d02e2-120">Consider creating a new role group in Exchange Online that's specifically intended for importing PST files to Office 365.</span></span> <span data-ttu-id="d02e2-121">PST 파일을 가져오는 데 필요한 최소 수준의 권한만 할당하려면 새 역할 그룹에 사서함 가져오기/내보내기 역할 및 메일 받는 사람 역할을 할당하고 구성원을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d02e2-121">For the minimum level of privileges required to import PST files, assign the Mailbox Import Export and Mail Recipients roles to the new role group, and then add members.</span></span> 
  
 <span data-ttu-id="d02e2-122">**네트워크 업로드는 어디에서 사용할 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="d02e2-122">**Where is network upload available?**</span></span>
  
<span data-ttu-id="d02e2-123">네트워크 업로드는 현재 지역에서 미국, 캐나다, 브라질, 영국, 프랑스, 독일, 유럽, 인도, 동부 아시아, 동남 아시아, 일본, 한국, 오스트레일리아 (아랍에미리트)입니다.</span><span class="sxs-lookup"><span data-stu-id="d02e2-123">Network upload is currently available in these regions: United States, Canada, Brazil, the United Kingdom, France, Germany, Europe, India, East Asia, Southeast Asia, Japan, Republic of Korea, Australia, and United Arab Emirates (UAE).</span></span> <span data-ttu-id="d02e2-124">Network upload will be available in more regions soon.</span><span class="sxs-lookup"><span data-stu-id="d02e2-124">Network upload will be available in more regions soon.</span></span>
  
 <span data-ttu-id="d02e2-125">**네트워크 업로드를 사용하여 PST 파일을 가져오는 경우 그 가격은 얼마인가요?**</span><span class="sxs-lookup"><span data-stu-id="d02e2-125">**What is the pricing for importing PST files by using network upload?**</span></span>
  
<span data-ttu-id="d02e2-126">Using network upload to import PST files is free.</span><span class="sxs-lookup"><span data-stu-id="d02e2-126">Using network upload to import PST files is free.</span></span>
  
<span data-ttu-id="d02e2-127">또한 Azure Storage 영역에서 PST 파일이 삭제된 후에는 Microsoft 365 관리 센터의 완료된 가져오기 작업 목록에 더 이상 해당 파일이 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d02e2-127">This also means that after PST files are deleted from the Azure Storage area, they're no longer displayed in the list of files for a completed import job in the Microsoft 365 admin center.</span></span> <span data-ttu-id="d02e2-128">가져오기 작업이 **Office 365로 데이터 가져오기** 페이지에 계속 표시되더라도, 이전 가져오기 작업의 세부 정보를 볼 때에는 PST 파일의 목록이 비어 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d02e2-128">Although an import job might still be listed on the **Import data to Office 365** page, the list of PST files might be empty when you view the details of older import jobs.</span></span> 
  
 <span data-ttu-id="d02e2-129">**Office 365로 가져올 수 있는 PST 파일 형식의 버전은 어떻게 되나요?**</span><span class="sxs-lookup"><span data-stu-id="d02e2-129">**What version of the PST file format is supported for importing to Office 365?**</span></span>
  
<span data-ttu-id="d02e2-130">PST 파일 형식의 버전은 두 가지로, ANSI와 유니코드입니다.</span><span class="sxs-lookup"><span data-stu-id="d02e2-130">There are two versions of the PST file format: ANSI and Unicode.</span></span> <span data-ttu-id="d02e2-131">유니코드 PST 파일 형식을 사용하는 파일을 가져오는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d02e2-131">We recommend importing files that use the Unicode PST file format.</span></span> <span data-ttu-id="d02e2-132">하지만 DBCS(더블바이트 문자 집합)를 사용하는 언어를 위한 파일 형식 등 ANSI PST를 사용하는 파일도 Office 365로 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d02e2-132">However, files that use the ANSI PST file format, such as those for languages that use a double-byte character set (DBCS), can also be imported to Office 365.</span></span> <span data-ttu-id="d02e2-133">ANSI PST 파일 가져오기에 대 한 자세한 내용은 네트워크 업로드 사용의 4 단계에서 [조직의 PST 파일을 Office 365로 가져오기](use-network-upload-to-import-pst-files.md#step-4-create-the-pst-import-mapping-file)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="d02e2-133">For more information about importing ANSI PST files, see Step 4 in [Use network upload to import your organization's PST files to Office 365](use-network-upload-to-import-pst-files.md#step-4-create-the-pst-import-mapping-file).</span></span>
  
<span data-ttu-id="d02e2-134">또한 Outlook 2007 이상 버전의 PST 파일도 Office 365로 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d02e2-134">Additionally, PST files from Outlook 2007 and later versions can be imported to Office 365.</span></span>
  
 <span data-ttu-id="d02e2-135">**Azure Storage 영역으로 내 PST 파일을 업로드한 후 삭제되기까지 Azure에서 얼마나 보관되나요?**</span><span class="sxs-lookup"><span data-stu-id="d02e2-135">**After I upload my PST files to the Azure Storage area, how long are they kept in Azure before they're deleted?**</span></span>
  
<span data-ttu-id="d02e2-136">네트워크 업로드 방법을 사용 하 여 PST 파일을 가져올 때는 라는 Azure blob 컨테이너에 업로드 `ingestiondata` 합니다.</span><span class="sxs-lookup"><span data-stu-id="d02e2-136">When you use the network upload method to import PST files, you upload them to an Azure blob container named `ingestiondata`.</span></span> <span data-ttu-id="d02e2-137">보안 & 준수 센터)의 **pst 파일 가져오기** 페이지에서 진행 중인 가져오기 작업이 없으면 Azure의 컨테이너에 있는 모든 PST 파일이 `ingestiondata` 보안 & 준수 센터에서 만들어진 후에 가장 최근 가져오기 작업이 30 일 후에 삭제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d02e2-137">If there are no import jobs in progress on the **Import PST files** page in the Security & Compliance Center), then all PST files in the `ingestiondata` container in Azure are deleted 30 days after the most recent import job was created in the Security & Compliance Center.</span></span> <span data-ttu-id="d02e2-138">즉, PST 파일을 Azure로 업로드한 후 30일 이내에 보안 & 준수 센터(네트워크 업로드 지침의 5단계에 설명됨)에 새 가져오기 작업을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d02e2-138">That also means you have to create a new import job in the Security & Compliance Center (described in Step 5 in the network upload instructions) within 30 days of uploading PST files to Azure.</span></span> 
  
<span data-ttu-id="d02e2-139">또한 Azure Storage 영역에서 PST 파일이 삭제된 후에는 보안 & 준수 센터의 완료된 가져오기 작업 목록에 더 이상 해당 파일이 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d02e2-139">This also means that after PST files are deleted from the Azure Storage area, they're no longer displayed in the list of files for a completed import job in the Security & Compliance Center.</span></span> <span data-ttu-id="d02e2-140">가져오기 작업이 보안 및 준수 센터에서 **PST 파일 가져오기** 페이지에 계속 표시되더라도, 이전 가져오기 작업의 세부 정보를 볼 때는 PST 파일의 목록이 비어 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d02e2-140">Although an import job might still be listed on the **Import PST files** page in the Security & Compliance Center, the list of PST files might be empty when you view the details of older import jobs.</span></span> 
  
 <span data-ttu-id="d02e2-141">**PST 파일을 사서함으로 가져오는 데 얼마나 걸리나요?**</span><span class="sxs-lookup"><span data-stu-id="d02e2-141">**How long does it take to import a PST file to a mailbox?**</span></span>
  
<span data-ttu-id="d02e2-142">트워크 용량에 따라 달라지지만 1TB(테라바이트)의 데이터를 조직의 Azure Storage 영역에 업로드하는 데 일반적으로 몇 시간이 걸립니다.</span><span class="sxs-lookup"><span data-stu-id="d02e2-142">It depends on the capacity of your network, but it typically takes several hours for each terabyte (TB) of data to be uploaded to the Azure Storage area for your organization.</span></span> <span data-ttu-id="d02e2-143">PST 파일을 Azure Storage 영역으로 복사한 후 하루당 24GB 이상의 속도로 PST 파일을 Microsoft 365 사서함으로 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d02e2-143">After the PST files are copied to the Azure Storage area, a PST file is imported to a Microsoft 365 mailbox at a rate of at least 24 GB per day.</span></span> <span data-ttu-id="d02e2-144">이 속도가 요구 사항을 충족하지 않는 경우 전자 메일 데이터를 Office 365로 마이그레이션하는 다른 방법을 고려할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d02e2-144">If this rate doesn't meet your needs, you might consider other methods for migrating email data to Office 365.</span></span> <span data-ttu-id="d02e2-145">자세한 내용은 [Office 365로 여러 전자 메일 계정을 마이그레이션하는 방법](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d02e2-145">For more information, see [Ways to migrate multiple email accounts to Office 365](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration).</span></span>
  
<span data-ttu-id="d02e2-146">다른 PST 파일을 다른 대상 사서함으로 가져오는 경우 가져오기 프로세스가 동시에 수행됩니다. 즉, 각 PST/사서함 쌍을 동시에 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d02e2-146">If different PST files are imported to different target mailboxes, the import process occurs in parallel; in other words, each PST/mailbox pair is imported simultaneously.</span></span> <span data-ttu-id="d02e2-147">마찬가지로, 여러 PST 파일을 같은 사서함으로 동시에 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d02e2-147">Likewise, if multiple PST files are imported to the same mailbox, they will be simultaneously imported.</span></span>
  
 <span data-ttu-id="d02e2-148">**PST 가져오기 프로세스는 중복 전자 메일 항목을 어떻게 처리합니까?**</span><span class="sxs-lookup"><span data-stu-id="d02e2-148">**How does the PST import process handle duplicate email items?**</span></span>

<span data-ttu-id="d02e2-149">PST 가져오기 프로세스는 중복 항목을 확인하고 대상 사서함 또는 대상 아카이브의 대상 폴더에 일치하는 항목이 있는 경우 PST 파일에서 사서함 또는 아카이브로 항목을 복사하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d02e2-149">The PST import process checks for duplicate items and doesn't copy the items from a PST file to the mailbox or archive if a matching item exists in the target folder in the target mailbox or target archive.</span></span> <span data-ttu-id="d02e2-150">이전 가져오기 작업에 지정한 것과 동일한 PST 파일을 다시 가져오고 PST 가져오기 매핑 파일의 TargetRootFolder 속성을 사용 하 여 다른 대상 폴더를 지정 하는 경우에는 PST 파일의 모든 항목이 reimported 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d02e2-150">If you reimport the same PST file and specify a different target folder (using the TargetRootFolder property in the PST import mapping file) than the one you specified in a previous import job, all items in the PST file will be reimported.</span></span>

 <span data-ttu-id="d02e2-151">**PST 파일을 가져올 때 메시지 크기가 제한되나요?**</span><span class="sxs-lookup"><span data-stu-id="d02e2-151">**Is there a message size limit when importing PST files?**</span></span>
  
<span data-ttu-id="d02e2-152">예.</span><span class="sxs-lookup"><span data-stu-id="d02e2-152">Yes.</span></span> <span data-ttu-id="d02e2-153">PST 파일이 150MB보다 큰 사서함을 포함한 경우 항목은 가져오기 프로세스 중에 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="d02e2-153">If a PST file contains a mailbox item that is larger than 150 MB, the item will be skipped during the import process.</span></span>
  
 <span data-ttu-id="d02e2-154">**PST 파일을 Microsoft 365 사서함으로 가져올 때 메시지를 보내거나 받은 시간, 받는 사람의 목록, 기타 속성 등 메시지 속성이 보존되나요?**</span><span class="sxs-lookup"><span data-stu-id="d02e2-154">**Are message properties, such as when the message was sent or received, the list of recipients and other properties, preserved when PST files are imported to a Microsoft 365 mailbox?**</span></span>
  
<span data-ttu-id="d02e2-155">예.</span><span class="sxs-lookup"><span data-stu-id="d02e2-155">Yes.</span></span> <span data-ttu-id="d02e2-156">가져오기 프로세스 중에는 원본 메시지 메타데이터가 변경되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d02e2-156">The original message metadata isn't changed during the import process.</span></span>
  
 <span data-ttu-id="d02e2-157">**사서함으로 가져오려는 PST 파일의 폴더 계층 구조에서 레벨 수에 제한이 있나요?**</span><span class="sxs-lookup"><span data-stu-id="d02e2-157">**Is there a limit to the number of levels in a folder hierarchy for a PST file that I want to import to a mailbox?**</span></span>
  
<span data-ttu-id="d02e2-p115">예. 300개 이상의 중첩 폴더 레벨이 있는 PST 파일을 가져올 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d02e2-p115">Yes. You can't import a PST file that has 300 or more levels of nested folders.</span></span>
  
 <span data-ttu-id="d02e2-160">**Office 365의 비활성 사서함에 PST 파일을 가져오기 위해 네트워크 업로드를 사용할 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="d02e2-160">**Can I use network upload to import PST files to an inactive mailbox in Office 365?**</span></span>
  
<span data-ttu-id="d02e2-161">예, 현재 이 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d02e2-161">Yes, this capability is now available.</span></span>
  
 <span data-ttu-id="d02e2-162">**Exchange 하이브리드 배포의 온라인 보관 사서함으로 PST 파일을 가져오기 위해 네트워크 업로드를 사용할 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="d02e2-162">**Can I use network upload to import PST files to an online archive mailbox in an Exchange hybrid deployment?**</span></span>
  
<span data-ttu-id="d02e2-163">예, 현재 이 기능을 사용할 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="d02e2-163">Yes, this capability is now available.</span></span>
  
 <span data-ttu-id="d02e2-164">**Exchange Online의 공용 폴더로 PST 파일 가져오는데 네트워크 업로드를 사용할 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="d02e2-164">**Can I use network upload to import PST files to public folders in Exchange Online?**</span></span>
  
<span data-ttu-id="d02e2-165">아니요, 공용 폴더에 PST 파일을 가져올 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d02e2-165">No, you can't import PST files to public folders.</span></span>
  
## <a name="using-drive-shipping-to-import-pst-files"></a><span data-ttu-id="d02e2-166">드라이브 배송을 사용하여 PST 파일 가져오기</span><span class="sxs-lookup"><span data-stu-id="d02e2-166">Using drive shipping to import PST files</span></span>

<span data-ttu-id="d02e2-167">단계별 지침은 [drive 발송을 사용 하 여 PST 파일을 Office 365에 가져오기](use-drive-shipping-to-import-pst-files-to-office-365.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d02e2-167">For step-by-step instructions, see [Use drive shipping to import PST files to Office 365](use-drive-shipping-to-import-pst-files-to-office-365.md).</span></span>
  
 <span data-ttu-id="d02e2-168">**Office 365 가져오기 서비스에서 가져오기 작업을 만드는 데 필요한 권한은 무엇입니까?**</span><span class="sxs-lookup"><span data-stu-id="d02e2-168">**What permissions are required to create import jobs in the Office 365 Import Service?**</span></span>
  
<span data-ttu-id="d02e2-169">PST 파일을 Microsoft 365 사서함으로 가져오려면 사서함 가져오기 내보내기 역할을 할당받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d02e2-169">You have to be assigned the Mailbox Import Export role to import PST files to Microsoft 365 mailboxes.</span></span> <span data-ttu-id="d02e2-170">기본적으로이 역할은 Exchange Online의 어떤 역할 그룹에도 할당되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d02e2-170">By default, this role isn't assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="d02e2-171">조직 관리 역할 그룹에 사서함 가져오기/내보내기 역할을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d02e2-171">You can add the Mailbox Import Export role to the Organization Management role group.</span></span> <span data-ttu-id="d02e2-172">또는 새 역할 그룹을 만들고, 사서함 가져오기 내보내기 역할을 할당한 다음 구성원으로 자신이나 다른 사용자를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d02e2-172">Or you can create a new role group, assign the Mailbox Import Export role, and then add yourself or other users as a member.</span></span> <span data-ttu-id="d02e2-173">자세한 내용은 [Exchange Online에서 역할 그룹 관리](https://go.microsoft.com/fwlink/p/?LinkId=730688)의 "역할 그룹에 역할 추가" 또는 "역할 그룹 만들기" 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d02e2-173">For more information, see the "Add a role to a role group" or the "Create a role group" sections in [Manage role groups in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=730688).</span></span>
  
<span data-ttu-id="d02e2-174">또한 보안 & 준수 센터에서 가져오기 작업을 만들려면 다음 중 하나가 충족되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d02e2-174">Additionally, to create import jobs in the Security & Compliance Center, one of the following must be true:</span></span>
  
- <span data-ttu-id="d02e2-175">Exchange Online에서 메일 받는 사람 역할을 할당받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d02e2-175">You have to be assigned the Mail Recipients role in Exchange Online.</span></span> <span data-ttu-id="d02e2-176">기본적으로 이 역할은 조직 관리 및 받는 사람 관리 역할 그룹에 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="d02e2-176">By default, this role is assigned to the Organization Management and Recipient Management roles groups.</span></span>
    
    <span data-ttu-id="d02e2-177">또는</span><span class="sxs-lookup"><span data-stu-id="d02e2-177">Or</span></span>
    
- <span data-ttu-id="d02e2-178">조직의 전역 관리자여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d02e2-178">You have to be a global administrator in your organization.</span></span>
    
> [!TIP]
> <span data-ttu-id="d02e2-179">Exchange Online에서 PST 파일을 Office 365로 가져오기 위한 새로운 역할 그룹을 만드는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d02e2-179">Consider creating a new role group in Exchange Online that's specifically intended for importing PST files to Office 365.</span></span> <span data-ttu-id="d02e2-180">PST 파일을 가져오는 데 필요한 최소 수준의 권한만 할당하려면 새 역할 그룹에 사서함 가져오기/내보내기 역할 및 메일 받는 사람 역할을 할당하고 구성원을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d02e2-180">For the minimum level of privileges required to import PST files, assign the Mailbox Import Export and Mail Recipients roles to the new role group, and then add members.</span></span> 
  
 <span data-ttu-id="d02e2-181">**드라이브 배송을 사용할 수 있는 지역은 어디인가요?**</span><span class="sxs-lookup"><span data-stu-id="d02e2-181">**Where is drive shipping available?**</span></span>
  
<span data-ttu-id="d02e2-182">현재 드라이브 배송은 미국, 캐나다, 브라질, 영국, 유럽, 인도, 동아시아, 동남 아시아, 일본, 대한민국 및 오스트레일리아에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d02e2-182">Drive shipping is currently available in the United States, Canada, Brazil, the United Kingdom, Europe, India, East Asia, Southeast Asia, Japan, Republic of Korea, and Australia.</span></span> <span data-ttu-id="d02e2-183">드라이브 배송을 사용할 수 있는 지역이 곧 더 많아질 예정입니다.</span><span class="sxs-lookup"><span data-stu-id="d02e2-183">Drive shipping will be available in more regions soon.</span></span>

> [!NOTE]
> <span data-ttu-id="d02e2-184">현재 독일 및 스위스에서는 PST 파일을 가져오기 위한 드라이브 배송을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d02e2-184">At this time, drive shipping to import PST files is not available in Germany and Switzerland.</span></span> <span data-ttu-id="d02e2-185">이러한 국가에서 드라이브 배송이 가능한 경우 이 FAQ가 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="d02e2-185">This FAQ will be updated when drive shipping is available in these countries.</span></span>
  
 <span data-ttu-id="d02e2-186">**어떤 상업용 사용권 계약을 통해 드라이브 배송을 사용할 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="d02e2-186">**What commercial licensing agreements support drive shipping?**</span></span>
  
<span data-ttu-id="d02e2-187">PST 파일을 Microsoft 365로 가져오기 위한 드라이브 배송은 Microsoft EA(Enterprise Agreement)를 통해 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="d02e2-187">Drive shipping to import PST files to Microsoft 365 is available through a Microsoft Enterprise Agreement (EA).</span></span> <span data-ttu-id="d02e2-188">MPSA(Microsoft 제품 및 서비스 계약)를 통해서는 드라이브 배송이 가능하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d02e2-188">Drive shipping isn't available through a Microsoft Products and Services Agreement (MPSA).</span></span>
  
 <span data-ttu-id="d02e2-189">**파일을 Microsoft 365로 가져오기 위해 드라이브 배송을 사용하는 경우 그 가격은 얼마인가요?**</span><span class="sxs-lookup"><span data-stu-id="d02e2-189">**What is the pricing for using drive shipping to import PST files to Microsoft 365?**</span></span>
  
<span data-ttu-id="d02e2-190">Microsoft 365 사서함으로 PST 파일을 가져오기 위해 드라이브 배송을 사용하는 비용은 1GB의 데이터당 2,000원입니다.</span><span class="sxs-lookup"><span data-stu-id="d02e2-190">The cost to use drive shipping to import PST files to Microsoft 365 mailboxes is $2 USD per GB of data.</span></span> <span data-ttu-id="d02e2-191">예를 들어 1,000GB(1TB)의 PST 파일이 포함된 하드 드라이브를 배송하는 경우 비용은 2,000,000원입니다.</span><span class="sxs-lookup"><span data-stu-id="d02e2-191">For example, if you ship a hard drive that contains 1,000 GB (1 TB) of PST files, the cost is $2,000 USD.</span></span> <span data-ttu-id="d02e2-192">파트너와 협의하여 가져오기 요금을 지불할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d02e2-192">You can work with a partner to pay the import fee.</span></span> <span data-ttu-id="d02e2-193">파트너를 찾는 방법에 대한 내용은 [Microsoft 파트너 또는 대리점 찾기](https://go.microsoft.com/fwlink/p/?LinkId=785197)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d02e2-193">For information about finding a partner, see [Find your Microsoft partner or reseller](https://go.microsoft.com/fwlink/p/?LinkId=785197).</span></span>
  
 <span data-ttu-id="d02e2-194">**드라이브 배송이 가능한 하드 드라이브는 어떤 종류인가요?**</span><span class="sxs-lookup"><span data-stu-id="d02e2-194">**What kind of hard drives are supported for drive shipping?**</span></span>
  
<span data-ttu-id="d02e2-195">Office 365 가져오기 서비스에는 2.5 인치, Ssd (반도체 드라이브) 또는 2.5 인치 또는 3.5 인치 SATA II/III 내부 하드 드라이브만 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d02e2-195">Only 2.5-inch solid-state drives (SSDs) or 2.5 inch or 3.5 inch SATA II/III internal hard drives are supported for use with the Office 365 Import service.</span></span> <span data-ttu-id="d02e2-196">최대 10TB의 하드 드라이브를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d02e2-196">You can use hard drives up to 10 TB.</span></span> <span data-ttu-id="d02e2-197">가져오기 작업의 경우에는 하드 드라이브의 첫 번째 데이터 볼륨만 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="d02e2-197">For import jobs, only the first data volume on the hard drive will be processed.</span></span> <span data-ttu-id="d02e2-198">데이터 볼륨은 NTFS 형식으로 포맷되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d02e2-198">The data volume must be formatted with NTFS.</span></span> <span data-ttu-id="d02e2-199">하드 드라이브에 데이터를 복사할 때는 2.5인치 SSD나 2.5인치 또는 3.5인치 SATA II/III 커넥터를 사용하여 직접 연결하거나 외장 2.5인치 SSD나 2.5인치 또는 3.5인치 SATA II/III USB 어댑터를 사용하여 외장으로 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d02e2-199">When copying data to a hard drive, you can attach it directly using a 2.5 inch SSD or 2.5 inch or 3.5 inch SATA II/III connector or you can attach it externally using an external 2.5 inch SSD or 2.5 inch or 3.5 inch SATA II/III USB adaptor.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="d02e2-200">USB 어댑터가 내장되어 함께 제공되는 외장 하드 드라이브는 Office 365 가져오기 서비스에서 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d02e2-200">External hard drives that come with an built-in USB adaptor aren't supported by the Office 365 Import service.</span></span> <span data-ttu-id="d02e2-201">또한 외장 하드 드라이브 케이스 내부의 디스크를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d02e2-201">Additionally, the disk inside the casing of an external hard drive can't be used.</span></span> <span data-ttu-id="d02e2-202">외장 하드 드라이브는 발송하지 마시기 바랍니다.</span><span class="sxs-lookup"><span data-stu-id="d02e2-202">Please don't ship external hard drives.</span></span> 
  
 <span data-ttu-id="d02e2-203">**단일 가져오기 작업을 위해 배송할 수 있는 하드 드라이브 수는 몇 개인가요?**</span><span class="sxs-lookup"><span data-stu-id="d02e2-203">**How many hard drives can I ship for a single import job?**</span></span>
  
<span data-ttu-id="d02e2-204">단일 가져오기 작업을 위해 최대 10개의 하드 드라이브를 배송할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d02e2-204">You can ship a maximum of 10 hard drives for a single import job.</span></span>
  
 <span data-ttu-id="d02e2-205">**하드 드라이브를 배송한 후 Microsoft 데이터 센터에 가져오는 데 얼마나 걸리나요?**</span><span class="sxs-lookup"><span data-stu-id="d02e2-205">**After I ship my hard drive, how long does it take to get to the Microsoft data center?**</span></span>
  
<span data-ttu-id="d02e2-p125">해당 기간은 Microsoft 데이터 센터에 대한 근접성, 하드 드라이브를 배송하는 데 사용한 배송 옵션 종류(예: 익일 배송, 2일 배송 또는 육로 배송) 등의 몇 가지 요인에 따라 다릅니다. 대부분의 운송업체에서, 추적 번호를 사용하여 배송 상태를 추적할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d02e2-p125">That depends on a few things, such as your proximity to the Microsoft data center and what kind of shipping option you used to ship your hard drive (such as, next-day delivery, two-day delivery, or ground-delivery). With most shippers, you can use the tracking number to track the status of your delivery.</span></span>
  
 <span data-ttu-id="d02e2-208">**하드 드라이브가 Microsoft 데이터 센터에 도착하면 내 PST 파일을 Azure에 업로드하는 데 얼마나 걸리나요?**</span><span class="sxs-lookup"><span data-stu-id="d02e2-208">**After my hard drive arrives at the Microsoft data center, how long does it take to upload my PST files to Azure?**</span></span>
  
<span data-ttu-id="d02e2-209">Microsoft 데이터 센터에서 하드 드라이브를 받은 후에는 해당 조직의 Azure Storage 영역에 PST 파일을 업로드 하기 위해 7 일에서 10 일까 지 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="d02e2-209">After your hard drive is received at the Microsoft data center, it will take between 7 to 10 business days to upload the PST files to the Azure Storage area for your organization.</span></span> <span data-ttu-id="d02e2-210">PST 파일은 `ingestiondata`라고 하는 Azure Blob 컨테이너에 업로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="d02e2-210">The PST files will be uploaded to an Azure blob container named `ingestiondata`.</span></span> 
  
 <span data-ttu-id="d02e2-211">**PST 파일을 사서함으로 가져오는 데 얼마나 걸리나요?**</span><span class="sxs-lookup"><span data-stu-id="d02e2-211">**How long does it take to import a PST file to a mailbox?**</span></span>
  
<span data-ttu-id="d02e2-212">PST 파일이 Azure Storage 영역에 업로드되면 Microsoft 365에서 PST 파일의 데이터를 안전한 방법으로 분석하여 항목 경과 시간과 PST 파일에 포함된 다양한 메시지 유형을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="d02e2-212">After the PST files are uploaded to the Azure Storage area, Microsoft 365 analyzes the data in the PST files (in a safe and secure manner) to identify the age of the items and the different message types included in the PST files.</span></span> <span data-ttu-id="d02e2-213">분석이 완료되면 PST 파일의 모든 데이터를 가져오거나 필터를 설정하여 가져온 데이터를 제어할 수 있는 옵션이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="d02e2-213">When this analysis is complete, you'll have the option to import all the data in the PST files or set filters to that control what data gets imported.</span></span> <span data-ttu-id="d02e2-214">가져오기 작업을 시작하면 하루당 최소 24GB의 속도로 PST 파일을 Microsoft 365 사서함으로 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d02e2-214">After you start the import job, a PST file is imported to a Microsoft 365 mailbox at a rate of at least 24 GB per day.</span></span> <span data-ttu-id="d02e2-215">이 속도가 요구 사항을 충족하지 않는 경우 전자 메일 데이터를 Office 365로 가져오는 다른 방법을 고려할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d02e2-215">If this rate doesn't meet your needs, you might consider other methods for importing email data to Office 365.</span></span> <span data-ttu-id="d02e2-216">자세한 내용은 [Office 365로 여러 전자 메일 계정을 마이그레이션하는 방법](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d02e2-216">For more information, see [Ways to migrate multiple email accounts to Office 365](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration).</span></span>
  
<span data-ttu-id="d02e2-217">다른 PST 파일을 다른 대상 사서함으로 가져오는 경우 가져오기 프로세스가 동시에 수행됩니다. 즉, 각 PST/사서함 쌍을 동시에 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d02e2-217">If different PST files are imported to different target mailboxes, the import process occurs in parallel; in other words, each PST/mailbox pair is imported simultaneously.</span></span> <span data-ttu-id="d02e2-218">마찬가지로, 여러 PST 파일을 같은 사서함으로 동시에 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d02e2-218">Likewise, if multiple PST files are imported to the same mailbox, they will be simultaneously imported.</span></span>
  
 <span data-ttu-id="d02e2-219">**Microsoft에서 Azure에 내 PST 파일을 업로드한 후 삭제되기까지 Azure에서 얼마나 보관되나요?**</span><span class="sxs-lookup"><span data-stu-id="d02e2-219">**After Microsoft uploads my PST files to Azure, how long are they kept in Azure before they're deleted?**</span></span>
  
<span data-ttu-id="d02e2-220">조직의 Azure Storage 위치(`ingestiondata`라고 하는 Blob 컨테이너)에 있는 모든 PST 파일은 보안 & 준수 센터에서 **PST 파일 가져오기** 페이지의 가장 최근 가져오기 작업이 만들어지고 30일 후에 삭제됩니다. </span><span class="sxs-lookup"><span data-stu-id="d02e2-220">All PST files in the Azure Storage location for your organization (in blob container named `ingestiondata`), are deleted 30 days after the most recent import job was created on the **Import PST files** page in the Security & Compliance Center.</span></span> 
  
<span data-ttu-id="d02e2-221">또한 Azure Storage 영역에서 PST 파일이 삭제된 후에는 보안 & 준수 센터의 완료된 가져오기 작업 목록에 더 이상 해당 파일이 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d02e2-221">This also means that after PST files are deleted from the Azure Storage area, they're no longer displayed in the list of files for a completed import job in the Security & Compliance Center.</span></span> <span data-ttu-id="d02e2-222">가져오기 작업이 보안 및 준수 센터에서 **PST 파일 가져오기** 페이지에 계속 표시되더라도, 이전 가져오기 작업의 세부 정보를 볼 때는 PST 파일의 목록이 비어 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d02e2-222">Although an import job might still be listed on the **Import PST files** page in the Security & Compliance Center, the list of PST files might be empty when you view the details of older import jobs.</span></span> 
  
 <span data-ttu-id="d02e2-223">**Microsoft 365로 가져올 수 있는 PST 파일 형식의 버전은 어떻게 되나요?**</span><span class="sxs-lookup"><span data-stu-id="d02e2-223">**What version of the PST file format is supported for importing to Microsoft 365?**</span></span>
  
<span data-ttu-id="d02e2-224">PST 파일 형식의 버전은 두 가지로, ANSI와 유니코드입니다.</span><span class="sxs-lookup"><span data-stu-id="d02e2-224">There are two versions of the PST file format: ANSI and Unicode.</span></span> <span data-ttu-id="d02e2-225">유니코드 PST 파일 형식을 사용하는 파일을 가져오는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d02e2-225">We recommend importing files that use the Unicode PST file format.</span></span> <span data-ttu-id="d02e2-226">하지만 DBCS(더블바이트 문자 집합)를 사용하는 언어를 위한 파일 형식 등 ANSI PST를 사용하는 파일도 Microsoft 365로 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d02e2-226">However, files that use the ANSI PST file format, such as those for languages that use a double-byte character set (DBCS), can also be imported to Microsoft 365.</span></span> <span data-ttu-id="d02e2-227">ANSI PST 파일을 가져오는 방법에 대 한 자세한 내용은 on [drive 발송을 사용 하 여 PST 파일을 Office 365로 가져오기](use-drive-shipping-to-import-pst-files-to-office-365.md#step-3-create-the-pst-import-mapping-file)의 3 단계를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d02e2-227">For more information about importing ANSI PST files, see Step 3 in [Use drive shipping to import PST files to Office 365](use-drive-shipping-to-import-pst-files-to-office-365.md#step-3-create-the-pst-import-mapping-file).</span></span>
  
<span data-ttu-id="d02e2-228">또한 Outlook 2007 이상 버전의 PST 파일도 Office 365로 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d02e2-228">Additionally, PST files from Outlook 2007 and later versions can be imported to Office 365.</span></span>
  
 <span data-ttu-id="d02e2-229">**PST 파일을 가져올 때 메시지 크기가 제한되나요?**</span><span class="sxs-lookup"><span data-stu-id="d02e2-229">**Is there a message size limit when importing PST files?**</span></span>
  
<span data-ttu-id="d02e2-230">예.</span><span class="sxs-lookup"><span data-stu-id="d02e2-230">Yes.</span></span> <span data-ttu-id="d02e2-231">PST 파일이 150MB보다 큰 사서함을 포함한 경우 항목은 가져오기 프로세스 중에 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="d02e2-231">If a PST file contains a mailbox item that is larger than 150 MB, the item will be skipped during the import process.</span></span>
  
  <span data-ttu-id="d02e2-232">**PST 가져오기 프로세스는 중복 전자 메일 항목을 어떻게 처리합니까?**</span><span class="sxs-lookup"><span data-stu-id="d02e2-232">**How does the PST import process handle duplicate email items?**</span></span>

<span data-ttu-id="d02e2-233">PST 가져오기 프로세스는 중복 항목을 확인하고 대상 사서함 또는 대상 아카이브의 대상 폴더에 일치하는 항목이 있는 경우 PST 파일에서 사서함 또는 아카이브로 항목을 복사하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d02e2-233">The PST import process checks for duplicate items and doesn't copy the items from a PST file to the mailbox or archive if a matching item exists in the target folder in the target mailbox or target archive.</span></span> <span data-ttu-id="d02e2-234">이전 가져오기 작업에 지정한 것과 동일한 PST 파일을 다시 가져오고 PST 가져오기 매핑 파일의 TargetRootFolder 속성을 사용 하 여 다른 대상 폴더를 지정 하는 경우에는 PST 파일의 모든 항목이 reimported 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d02e2-234">If you reimport the same PST file and specify a different target folder (using the TargetRootFolder property in the PST import mapping file) than the one you specified in a previous import job, all items in the PST file will be reimported.</span></span>
 
 <span data-ttu-id="d02e2-235">**PST 파일을 Microsoft 365 사서함으로 가져올 때 메시지를 보내거나 받은 시간, 받는 사람의 목록, 기타 속성 등 메시지 속성이 보존되나요?**</span><span class="sxs-lookup"><span data-stu-id="d02e2-235">**Are message properties, such as when the message was sent or received, the list of recipients and other properties, preserved when PST files are imported to a Microsoft 365 mailbox?**</span></span>
  
<span data-ttu-id="d02e2-236">예.</span><span class="sxs-lookup"><span data-stu-id="d02e2-236">Yes.</span></span> <span data-ttu-id="d02e2-237">가져오기 프로세스 중에는 원본 메시지 메타데이터가 변경되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d02e2-237">The original message metadata isn't changed during the import process</span></span>
  
 <span data-ttu-id="d02e2-238">**사서함으로 가져오려는 PST 파일의 폴더 계층 구조에서 레벨 수에 제한이 있나요?**</span><span class="sxs-lookup"><span data-stu-id="d02e2-238">**Is there a limit to the number of levels in a folder hierarchy for a PST file that I want to import to a mailbox?**</span></span>
  
<span data-ttu-id="d02e2-p134">예. 300개 이상의 중첩 폴더 레벨이 있는 PST 파일을 가져올 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d02e2-p134">Yes. You can't import a PST file that has 300 or more levels of nested folders.</span></span>
  
 <span data-ttu-id="d02e2-241">**Microsoft 365의 비활성 사서함으로 PST 파일을 가져오기 위해 드라이브 배송을 사용할 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="d02e2-241">**Can I use drive shipping to import PST files to an inactive mailbox in Microsoft 365?**</span></span>
  
<span data-ttu-id="d02e2-242">예, 현재 이 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d02e2-242">Yes, this capability is now available.</span></span>
  
 <span data-ttu-id="d02e2-243">**Exchange 하이브리드 배포의 온라인 보관 사서함으로 PST 파일을 가져오기 위해 드라이브 배송을 사용할 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="d02e2-243">**Can I use drive shipping to import PST files to an online archive mailbox in an Exchange hybrid deployment?**</span></span>
  
<span data-ttu-id="d02e2-244">예, 현재 이 기능을 사용할 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="d02e2-244">Yes, this capability is now available.</span></span>
  
 <span data-ttu-id="d02e2-245">**Exchange Online의 공용 폴더로 PST 파일을 가져오는데 드라이브 배송을 사용할 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="d02e2-245">**Can I use drive shipping to import PST files to public folders in Exchange Online?**</span></span>
  
<span data-ttu-id="d02e2-246">아니요, 공용 폴더에 PST 파일을 가져올 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d02e2-246">No, you can't import PST files to public folders.</span></span>
  
 <span data-ttu-id="d02e2-247">**Microsoft에서 나에게 다시 배송하기 전에 내 하드 드라이브를 초기화할 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="d02e2-247">**Can Microsoft wipe my hard drive before they ship it back to me?**</span></span>
  
<span data-ttu-id="d02e2-p135">아니요. Microsoft는 하드 드라이브를 고객에게 다시 보내기 전에 해당 드라이브를 지울 수 없습니다. 하드 드라이브는 Microsoft에서 받은 것과 동일한 상태로 고객에게 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="d02e2-p135">No, Microsoft can't wipe hard drives before shipping them back to customers. Hard drives are returned to you in the same state they were in when they were received by Microsoft.</span></span>
  
 <span data-ttu-id="d02e2-250">**Microsoft에서 내 하드 드라이브를 나에게 다시 배송하는 대신 폐기할 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="d02e2-250">**Can Microsoft shred my hard drive instead of shipping it back to me?**</span></span>
  
<span data-ttu-id="d02e2-p136">아니요, Microsoft에서는 고객의 하드 드라이브를 파괴할 수 없습니다. 하드 드라이브는 Microsoft에서 받을 때와 동일한 상태로 고객에게 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="d02e2-p136">No, Microsoft can't destroy your hard drive. Hard drives are returned to you in the same state they were in when they were received by Microsoft.</span></span>
  
 <span data-ttu-id="d02e2-253">**반환 배송에 어떤 택배 서비스를 사용할 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="d02e2-253">**What courier services are supported for return shipping?**</span></span>
  
<span data-ttu-id="d02e2-p137">미국 또는 유럽 고객인 경우 Microsoft에서는 FedEx를 통해 하드 드라이브를 반환합니다. 다른 모든 지역에서는 DHL을 이용합니다.</span><span class="sxs-lookup"><span data-stu-id="d02e2-p137">If you're a customer in the United States or Europe, Microsoft uses FedEx to return your hard drive. For all other regions, Microsoft uses DHL.</span></span>
  
 <span data-ttu-id="d02e2-256">**반환 배송 비용은 얼마인가요?**</span><span class="sxs-lookup"><span data-stu-id="d02e2-256">**What are the return shipping costs?**</span></span>
  
<span data-ttu-id="d02e2-p138">반환 배송 비용은 고객이 하드 드라이브를 배송한 Microsoft 데이터 센터와의 근접성에 따라 다릅니다. Microsoft는 FedEx 또는 DHL 계정으로 하드 드라이브 반환 비용을 청구합니다. 반환 배송의 비용은 고객이 부담해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d02e2-p138">Return shipping costs vary, depending on your proximity to the Microsoft data center that you shipped your hard drive to. Microsoft will bill your FedEx or DHL account to return your hard drive. The cost of return shipping is your responsibility.</span></span>
  
 <span data-ttu-id="d02e2-260">**Microsoft로 하드 드라이브를 배송하는 데 FedEx Custom Shipping과 같은 사용자 지정 택배 배송 서비스를 이용할 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="d02e2-260">**Can I use a custom courier shipping service, such as FedEx Custom Shipping, to ship my hard drive to Microsoft?**</span></span>
  
<span data-ttu-id="d02e2-261">예.</span><span class="sxs-lookup"><span data-stu-id="d02e2-261">Yes.</span></span>
  
 <span data-ttu-id="d02e2-262">**하드 드라이브를 다른 국가로 하드 드라이브를 배송해야 하는 경우 내가 해야 할 일이 있나요?**</span><span class="sxs-lookup"><span data-stu-id="d02e2-262">**If I have to ship my hard drive to another country, is there anything I need to do?**</span></span>
  
<span data-ttu-id="d02e2-p139">Microsoft에 배송하는 하드 드라이브가 국경을 통과해야 하는 경우도 있습니다. 이런 경우 하드 드라이브와 해당 하드 드라이브에 포함된 데이터를 해당 법규에 따라 가져오거나 내보내는 것은 고객의 책임입니다. 하드 드라이브를 배송하기 전에 드라이브 및 데이터를 지정된 Microsoft 데이터 센터로 합법적으로 배송할 수 있는지 고문 담당자와 확인하세요. 이렇게 하면 적시에 Microsoft로 도착할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d02e2-p139">The hard drive that you ship to Microsoft might have to cross international borders. If this is the case, you're responsible for ensuring that the hard drive and the data it contains are imported and/or exported in accordance with the applicable laws. Before shipping a hard drive, check with your advisors to verify that your drive and data can legally be shipped to the specified Microsoft data center. This will help to ensure that it reaches Microsoft in a timely manner.</span></span>
