---
title: SharePoint 및 OneDrive에서 Office 파일에 대한 민감도 레이블 사용
ms.author: cabailey
author: cabailey
manager: laurawi
audience: Admin
ms.topic: article
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: 관리자는 SharePoint 및 OneDrive에서 Word, Excel 및 PowerPoint 파일에 대해 민감도 레이블 지원을 사용 하도록 설정할 수 있습니다.
ms.openlocfilehash: fea28683136ae72603b3e7a6954d7d6ecf0ffbe4
ms.sourcegitcommit: 2eb4539291f5035b7bef746df89fbcc6faa17257
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/22/2020
ms.locfileid: "41263340"
---
# <a name="enable-sensitivity-labels-for-office-files-in-sharepoint-and-onedrive-public-preview"></a><span data-ttu-id="818bc-103">SharePoint 및 OneDrive에서 Office 파일에 대한 민감도 레이블 사용(공개 미리 보기)</span><span class="sxs-lookup"><span data-stu-id="818bc-103">Enable sensitivity labels for Office files in SharePoint and OneDrive (public preview)</span></span>

<span data-ttu-id="818bc-104">이 미리 보기를 수행 하기 전에 SharePoint 및 OneDrive에 저장 된 Office 파일에 암호화를 포함 한 민감도 레이블을 적용할 때 서비스가 이러한 파일의 콘텐츠를 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="818bc-104">Before this preview, when you applied sensitivity labels that included encryption to Office files stored in SharePoint and OneDrive, the service couldn't process the content of these files.</span></span> <span data-ttu-id="818bc-105">이러한 상황에서는 공동 작성, eDiscovery, 데이터 손실 방지, 검색, Delve 및 기타 공동 작업 기능이 작동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="818bc-105">Coauthoring, eDiscovery, Data Loss Prevention, search, Delve, and other collaborative features didn't work under these circumstances.</span></span> <span data-ttu-id="818bc-106">이 미리 보기에서는 클라우드 기반 키를 사용 하 여 암호화가 적용 된 경우 이러한 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="818bc-106">This preview enables these features when the encryption has been applied with a cloud-based key:</span></span>

- <span data-ttu-id="818bc-107">Sharepoint 및 OneDrive의 Word, Excel 및 PowerPoint 파일에 적용 되는 민감도 레이블을 인식할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="818bc-107">SharePoint recognizes sensitivity labels applied to Word, Excel, and PowerPoint files in SharePoint and OneDrive.</span></span> <span data-ttu-id="818bc-108">또한 SharePoint에서는 각 레이블에 해당 하는 설정을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="818bc-108">SharePoint also enforces the settings that correspond with each label.</span></span>

- <span data-ttu-id="818bc-109">SharePoint 또는 OneDrive에서 파일을 다운로드 하면 민감도 레이블이 파일과 함께 이동 하 고 설정이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="818bc-109">When you download a file from SharePoint or OneDrive, the sensitivity label travels with the file and the settings remain enforced.</span></span>

- <span data-ttu-id="818bc-110">Word, Excel 및 PowerPoint의 웹 버전을 사용 하 여 Office 파일에 민감도 레이블을 적용 하 고 적용 된 우편물 종류를 포함 하는 파일을 열고 편집 합니다 (레이블의 사용 권한을 허용 하는 경우).</span><span class="sxs-lookup"><span data-stu-id="818bc-110">Apply sensitivity labels to Office files, and open and edit files that have sensitivity labels applied (if the label's permissions allow it) by using the web versions of Word, Excel, and PowerPoint.</span></span> <span data-ttu-id="818bc-111">웹에서 Word를 사용 하 여 문서를 편집할 때도 자동 레이블 지정을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="818bc-111">With Word on the web, you can also use auto labeling when you edit documents.</span></span>

- <span data-ttu-id="818bc-112">Office 365 eDiscovery는 민감도 레이블이 적용 된 파일에서 전체 텍스트 검색을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="818bc-112">Office 365 eDiscovery supports full-text search in files that have sensitivity labels applied.</span></span> <span data-ttu-id="818bc-113">DLP (데이터 손실 방지) 정책은 이러한 파일의 콘텐츠를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="818bc-113">Data Loss Prevention (DLP) policies cover content in these files.</span></span>

- <span data-ttu-id="818bc-114">세 개의 새로운 감사 이벤트를 모니터링 민감도 레이블로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="818bc-114">Three new audit events are available for monitoring sensitivity labels:</span></span>
  - <span data-ttu-id="818bc-115">FileSensitivityApplied 됨</span><span class="sxs-lookup"><span data-stu-id="818bc-115">FileSensitivityApplied</span></span>
  - <span data-ttu-id="818bc-116">FileSensitivityLabelChanged 됨</span><span class="sxs-lookup"><span data-stu-id="818bc-116">FileSensitivityLabelChanged</span></span>
  - <span data-ttu-id="818bc-117">FileSensitivityLabelRemoved 됨</span><span class="sxs-lookup"><span data-stu-id="818bc-117">FileSensitivityLabelRemoved</span></span>

> [!NOTE]
> <span data-ttu-id="818bc-118">암호화가 클라우드 기반 키와 함께 온-프레미스 키가 적용 되지 않은 경우 키 관리 토폴로지에서 흔히 "자체 키를 사용" (HYOK)으로 지칭 되는 경우에는이 미리 보기를 통해 SharePoint 동작이 변경 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="818bc-118">If encryption hasn't been applied with a cloud-based key but an on-premises key, a key management topology often referred to as "hold your own key" (HYOK), the SharePoint behavior doesn't change with this preview.</span></span> 

<span data-ttu-id="818bc-119">이제 Microsoft 팀, Office 365 그룹 및 SharePoint 사이트에 민감도 레이블을 적용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="818bc-119">You can also now apply sensitivity labels to Microsoft Teams, Office 365 groups, and SharePoint sites.</span></span> <span data-ttu-id="818bc-120">이 별도의 미리 보기에 대 한 자세한 내용은 [사용 민감도 레이블 (Microsoft 팀, Office 365 그룹 및 SharePoint 사이트 (공용 미리 보기))](sensitivity-labels-teams-groups-sites.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="818bc-120">For more information about this separate preview, see [Use sensitivity labels with Microsoft Teams, Office 365 groups, and SharePoint sites (public preview)](sensitivity-labels-teams-groups-sites.md).</span></span>

<span data-ttu-id="818bc-121">언제 든 지이 미리 보기를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="818bc-121">You always have the choice to opt out of this preview at any time.</span></span>

<span data-ttu-id="818bc-122">다음 비디오 (오디오 없음)를 시청 하 여 이러한 새로운 기능이 작동 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="818bc-122">Watch the following video (no audio) to see these new capabilities in action:</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed//RE4ornZ]

## <a name="requirements"></a><span data-ttu-id="818bc-123">요구 사항</span><span class="sxs-lookup"><span data-stu-id="818bc-123">Requirements</span></span>

<span data-ttu-id="818bc-124">이러한 기능은 [민감도 레이블](sensitivity-labels.md) 에서만 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="818bc-124">These features work with [sensitivity labels](sensitivity-labels.md) only.</span></span> <span data-ttu-id="818bc-125">현재 Azure Information Protection 레이블이 있는 경우에는 업로드 하는 새 파일에 대해 이러한 기능을 사용할 수 있도록 먼저 해당 레이블을 민감도 레이블로 마이그레이션하십시오.</span><span class="sxs-lookup"><span data-stu-id="818bc-125">If you currently have Azure Information Protection labels, first migrate them to sensitivity labels so that you can enable these features for new files that you upload.</span></span> <span data-ttu-id="818bc-126">자세한 내용은 [통합 민감도 레이블로 Azure Information Protection 레이블을 마이그레이션하는 방법](https://docs.microsoft.com/azure/information-protection/configure-policy-migrate-labels) 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="818bc-126">For instructions, see [How to migrate Azure Information Protection labels to unified sensitivity labels](https://docs.microsoft.com/azure/information-protection/configure-policy-migrate-labels)</span></span>

<span data-ttu-id="818bc-127">이 미리 보기의 경우 Windows 및 버전 19.002.0107.0008 이상에서 OneDrive 동기화 앱 버전 19.002.0121.0008 이상을 사용 하십시오.</span><span class="sxs-lookup"><span data-stu-id="818bc-127">For this preview, use the OneDrive sync app version 19.002.0121.0008 or later on Windows, and version 19.002.0107.0008 or later on Mac.</span></span> <span data-ttu-id="818bc-128">두 버전 모두 2019 년 1 월 28 일에 출시 되었으며 현재 모든 링으로 출시 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="818bc-128">Both these versions were released January 28, 2019, and are currently released to all rings.</span></span> <span data-ttu-id="818bc-129">자세한 내용은 [OneDrive 릴리스 노트](https://support.office.com/article/845dcf18-f921-435e-bf28-4e24b95e5fc0)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="818bc-129">For more information, see the [OneDrive release notes](https://support.office.com/article/845dcf18-f921-435e-bf28-4e24b95e5fc0).</span></span> <span data-ttu-id="818bc-130">이 미리 보기를 사용 하도록 설정한 후에는 이전 버전의 동기화 앱을 실행 하는 사용자에 게 업데이트 하 라는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="818bc-130">After you enable this preview, users who run an older version of the sync app are prompted to update it.</span></span>

## <a name="limitations"></a><span data-ttu-id="818bc-131">제한</span><span class="sxs-lookup"><span data-stu-id="818bc-131">Limitations</span></span>

- <span data-ttu-id="818bc-132">이 미리 보기를 사용 하도록 설정 하면 OneDrive 동기화 폴더의 파일에 대 한 레이블을 변경 하는 사용자가 파일에 변경한 다른 내용을 저장 하지 못할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="818bc-132">When you enable this preview, users who change a label to a file in a OneDrive Sync folder might be unable to save other changes they make to the file.</span></span>  <span data-ttu-id="818bc-133">사용자에 게 [흰색 횡단면 오류가 있는 빨간색 원이](https://support.office.com/article/what-do-the-onedrive-icons-mean-11143026-8000-44f8-aaa9-67c985aa49b3)표시 되 고 새 변경 내용을 별도의 복사본으로 저장할지 묻는 메시지가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="818bc-133">Users see a [red circle with a white cross icon error](https://support.office.com/article/what-do-the-onedrive-icons-mean-11143026-8000-44f8-aaa9-67c985aa49b3), and they are asked to save new changes as a separate copy.</span></span>  <span data-ttu-id="818bc-134">사용자가 시작한 레이블 변경 사항 외에도, 관리자가 사용자의 동기화 클라이언트에 다운로드 된 파일에 이미 적용 되어 있는 게시 한 레이블의 설정을 변경 하는 경우에도 같은 동작이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="818bc-134">In addition to label changes that are initiated by users, the same behavior can occur if an admin changes settings for a published label that's already applied to files downloaded to users' sync client.</span></span>
    
    <span data-ttu-id="818bc-135">이러한 시나리오에서 작업이 손실 되지 않도록 하려면 다음 작업 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="818bc-135">To avoid losing work for these scenarios, do one of these actions:</span></span>
    - <span data-ttu-id="818bc-136">레이블을 적용 하려면 Office 앱의 웹 버전을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="818bc-136">To apply labels, use the web versions of the Office apps.</span></span>
    - <span data-ttu-id="818bc-137">레이블을 적용 한 후 파일을 닫고 다른 내용을 변경 하기 위해 파일을 다시 엽니다.</span><span class="sxs-lookup"><span data-stu-id="818bc-137">Close a file after you apply a label, and then reopen the file to make other changes.</span></span>

- <span data-ttu-id="818bc-138">SharePoint에서는 Azure Information Protection 레이블을 사용 하 여 이미 암호화 한 기존 파일에 새 레이블을 자동으로 적용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="818bc-138">SharePoint doesn't automatically apply the new labels to existing files that you've already encrypted using Azure Information Protection labels.</span></span> <span data-ttu-id="818bc-139">대신이 미리 보기를 사용 하도록 설정한 후에 기능을 작동 시키려면 다음 작업을 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="818bc-139">Instead, to get the features to work after you enable this preview, complete these tasks:</span></span>
    
    1. <span data-ttu-id="818bc-140">Azure Information Protection 레이블을 민감도 레이블로 마이그레이션하고 Microsoft 365 준수 센터 또는 레이블 관리 센터에서 게시 했는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="818bc-140">Make sure you have migrated the Azure Information Protection labels to sensitivity labels and published them from the Microsoft 365 compliance center, or equivalent labeling admin center.</span></span>
    
    2. <span data-ttu-id="818bc-141">파일을 다운로드 하 여 SharePoint에 업로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="818bc-141">Download the files and upload them to SharePoint.</span></span>

- <span data-ttu-id="818bc-142">암호화를 적용 한 레이블에서 암호화에 대 한 다음 구성 중 하나를 수행 하면 SharePoint에서 암호화 된 파일을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="818bc-142">SharePoint can't process encrypted files when the label that applied the encryption has either of the following configurations for encryption:</span></span>
    - <span data-ttu-id="818bc-143">**사용자가 레이블을 적용할 때 사용 권한을 할당할 수 있도록** 하 고 **Word, PowerPoint 및 Excel에서 사용자에 게 사용 권한을 지정 하 라는 메시지를 표시** 합니다.</span><span class="sxs-lookup"><span data-stu-id="818bc-143">**Let users assign permissions when they apply the label** and **In Word, PowerPoint, and Excel, prompt users to specify permissions**</span></span>
    - <span data-ttu-id="818bc-144">**콘텐츠에 대 한 사용자 액세스 만료** 는 **Never**이외의 값으로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="818bc-144">**User access to content expires** is set to a value other than **Never**.</span></span>

- <span data-ttu-id="818bc-145">사용자에 게 편집 권한을 부여 하는 암호화 된 문서에서는 Office 앱의 웹 버전에서 복사를 차단할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="818bc-145">For an encrypted document that grants edit permissions to a user, copying can't be blocked in the web versions of the Office apps.</span></span>

- <span data-ttu-id="818bc-146">Azure Information Protection 문서 추적 사이트는 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="818bc-146">The Azure Information Protection document tracking site is not supported.</span></span>

- <span data-ttu-id="818bc-147">Office 데스크톱 앱 및 모바일 앱은 공동 작성을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="818bc-147">Office desktop apps and mobile apps don't support coauthoring.</span></span> <span data-ttu-id="818bc-148">대신 이러한 앱은 계속 해 서 단독 편집 모드로 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="818bc-148">Instead, these apps continue to open files in exclusive editing mode.</span></span>

- <span data-ttu-id="818bc-149">레이블에 암호화가 포함 되어 있으면 Microsoft Cloud App Security에서 SharePoint의 파일에 대 한 레이블 정보를 읽을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="818bc-149">If a label includes encryption, Microsoft Cloud App Security isn't able to read the label information for the files in SharePoint.</span></span>

## <a name="prepare-the-sharepoint-online-management-shell-for-the-preview"></a><span data-ttu-id="818bc-150">미리 보기에 대 한 SharePoint Online 관리 셸 준비</span><span class="sxs-lookup"><span data-stu-id="818bc-150">Prepare the SharePoint Online Management Shell for the preview</span></span>

<span data-ttu-id="818bc-151">미리 보기를 사용 하도록 설정 하기 전에 SharePoint Online 관리 셸 버전 16.0.19418.12000 이상이 실행 되 고 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="818bc-151">Before you enable the preview, ensure that you're running SharePoint Online Management Shell version 16.0.19418.12000 or above.</span></span> <span data-ttu-id="818bc-152">최신 버전을 이미 사용 하 고 있는 경우 미리 보기를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="818bc-152">If you already have the latest version, you can go ahead and enable the preview.</span></span>

1. <span data-ttu-id="818bc-153">PowerShell 갤러리에서 이전 버전의 SharePoint Online 관리 셸을 설치한 경우 다음 cmdlet을 실행 하 여 모듈을 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="818bc-153">If you have installed a previous version of the SharePoint Online Management Shell from PowerShell gallery, you can update the module by running the following cmdlet.</span></span>

    ```PowerShell
    Update-Module -Name Microsoft.Online.SharePoint.PowerShell
    ```

2. <span data-ttu-id="818bc-154">또는 Microsoft 다운로드 센터에서 이전 버전의 SharePoint Online 관리 셸을 설치한 경우 **프로그램 추가/제거** 로 이동 하 여 Sharepoint Online 관리 셸을 제거할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="818bc-154">Alternatively, if you have installed a previous version of the SharePoint Online Management Shell from the Microsoft Download Center, you can also go to **Add or remove programs** and uninstall the SharePoint Online Management Shell.</span></span>

3. <span data-ttu-id="818bc-155">웹 브라우저에서 다운로드 센터 페이지로 이동한 다음 [최신 SharePoint Online 관리 셸을 다운로드](https://go.microsoft.com/fwlink/p/?LinkId=255251)합니다.</span><span class="sxs-lookup"><span data-stu-id="818bc-155">In a web browser, go to the Download Center page and [Download the latest SharePoint Online Management Shell](https://go.microsoft.com/fwlink/p/?LinkId=255251).</span></span>

4. <span data-ttu-id="818bc-156">언어를 선택한 다음 **다운로드**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="818bc-156">Select your language and then click **Download**.</span></span>

5. <span data-ttu-id="818bc-157">X64 및 x86 .msi 파일 중에서 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="818bc-157">Choose between the x64 and x86 .msi file.</span></span> <span data-ttu-id="818bc-158">64 비트 버전의 Windows 또는 x86 파일 (32 비트 버전을 실행 하는 경우)을 실행 하는 경우 x64 파일을 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="818bc-158">Download the x64 file if you run the 64-bit version of Windows or the x86 file if you run the 32-bit version.</span></span> <span data-ttu-id="818bc-159">알 수 없는 경우 [실행 중인 Windows 운영 체제 버전](https://support.microsoft.com/help/13443/windows-which-operating-system) 을 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="818bc-159">If you don’t know, see [Which version of Windows operating system am I running?](https://support.microsoft.com/help/13443/windows-which-operating-system)</span></span>


6. <span data-ttu-id="818bc-160">파일을 다운로드 한 후에는 파일을 실행 하 고 설치 마법사의 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="818bc-160">After you have downloaded the file, run the file and follow the steps in the Setup Wizard.</span></span>

## <a name="enable-the-preview-by-using-microsoft-powershell-opt-in"></a><span data-ttu-id="818bc-161">Microsoft PowerShell을 사용 하 여 미리 보기 사용 (옵트인)</span><span class="sxs-lookup"><span data-stu-id="818bc-161">Enable the preview by using Microsoft PowerShell (opt-in)</span></span>

<span data-ttu-id="818bc-162">미리 보기를 사용 하도록 설정 하려면 Set-spotenant cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="818bc-162">To enable the preview, use the Set-SPOTenant cmdlet:</span></span>

1. <span data-ttu-id="818bc-163">Office 365에서 전역 관리자 또는 SharePoint 관리자 권한이 있는 회사 또는 학교 계정을 사용 하 여 SharePoint에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="818bc-163">Using a work or school account that has global administrator or SharePoint admin privileges in Office 365, connect to SharePoint.</span></span> <span data-ttu-id="818bc-164">자세한 방법은 [SharePoint Online 관리 셸 시작](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="818bc-164">To learn how, see [Getting started with SharePoint Online Management Shell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span></span>

2. <span data-ttu-id="818bc-165">다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="818bc-165">Run the following command:</span></span>

    ```PowerShell
    Set-SPOTenant -EnableAIPIntegration $true  
    ```

## <a name="schedule-roll-out-after-you-create-or-change-a-sensitivity-label"></a><span data-ttu-id="818bc-166">민감도 레이블을 만들거나 변경한 후 일정 롤업</span><span class="sxs-lookup"><span data-stu-id="818bc-166">Schedule roll-out after you create or change a sensitivity label</span></span>

<span data-ttu-id="818bc-167">Microsoft 365 준수 센터에서 민감도 레이블을 만들거나 변경한 후에는 스테이지에 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="818bc-167">After you create or change a sensitivity label in the Microsoft 365 compliance center, publish it in stages.</span></span> <span data-ttu-id="818bc-168">완전히 동기화 되지 않은 레이블을 게시 하면 사용자가 파일에 레이블을 적용 하 여 SharePoint에 업로드 하는 경우 Office 앱의 웹 버전에서는 파일을 열 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="818bc-168">If you publish labels that haven't fully synchronized, when users apply the labels to files and upload them to SharePoint, the files can’t be opened in the web versions of the Office apps.</span></span> <span data-ttu-id="818bc-169">검색 및 eDiscovery도 파일에 대해 작동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="818bc-169">Search and eDiscovery also don't work for the files.</span></span>

<span data-ttu-id="818bc-170">다음 단계를 따르는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="818bc-170">We recommend that you follow these steps:</span></span>

1. <span data-ttu-id="818bc-171">새 민감도 레이블을 한 명 또는 두 사람에 게 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="818bc-171">Publish the new or modified sensitivity label only to one or two people.</span></span>

2. <span data-ttu-id="818bc-172">초기 발행물 이후 24 시간 이상 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="818bc-172">Wait for at least 24 hours after initial publication.</span></span> <span data-ttu-id="818bc-173">레이블이 완전히 동기화 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="818bc-173">Verify that the label has fully synchronized.</span></span>

3. <span data-ttu-id="818bc-174">레이블을 보다 광범위 하 게 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="818bc-174">Publish the label more broadly.</span></span>

## <a name="disable-the-preview-by-using-microsoft-powershell-opt-out"></a><span data-ttu-id="818bc-175">Microsoft PowerShell을 사용 하 여 미리 보기 사용 안 함 (옵트아웃)</span><span class="sxs-lookup"><span data-stu-id="818bc-175">Disable the preview by using Microsoft PowerShell (opt-out)</span></span>

<span data-ttu-id="818bc-176">이 미리 보기를 사용 하지 않도록 설정 하는 경우 미리 보기 중에 업로드 한 파일은 계속 해 서 레이블로 보호 됩니다.</span><span class="sxs-lookup"><span data-stu-id="818bc-176">If you disable this preview, files that you uploaded during the preview continue to be protected by the label.</span></span> <span data-ttu-id="818bc-177">해당 설정이 계속 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="818bc-177">The corresponding settings continue to be enforced.</span></span> <span data-ttu-id="818bc-178">미리 보기를 사용 하지 않도록 설정한 후 새 파일에 레이블을 적용 하면 전체 텍스트 검색, eDiscovery 및 공동 작성이 더 이상 작동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="818bc-178">When you apply labels to new files after you disable the preview, full-text search, eDiscovery, and coauthoring will no longer work.</span></span>

<span data-ttu-id="818bc-179">미리 보기를 사용 하지 않도록 설정 하려면 Set-spotenant cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="818bc-179">To disable the preview, use the Set-SPOTenant cmdlet:</span></span>

1. <span data-ttu-id="818bc-180">Office 365에서 전역 관리자 또는 SharePoint 관리자 권한이 있는 회사 또는 학교 계정을 사용 하 여 SharePoint에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="818bc-180">Using a work or school account that has global administrator or SharePoint admin privileges in Office 365, connect to SharePoint.</span></span> <span data-ttu-id="818bc-181">자세한 방법은 [SharePoint Online 관리 셸 시작](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="818bc-181">To learn how, see [Getting started with SharePoint Online Management Shell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span></span>

2. <span data-ttu-id="818bc-182">다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="818bc-182">Run the following command:</span></span>

    ```PowerShell
    Set-SPOTenant -EnableAIPIntegration $false
    ```
