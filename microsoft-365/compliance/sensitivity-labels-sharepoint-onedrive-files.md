---
title: SharePoint 및 OneDrive에서 Office 파일에 대한 민감도 레이블 사용
ms.author: cabailey
author: cabailey
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 11/01/2019
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: 관리자는 SharePoint 및 OneDrive에서 Word, Excel 및 PowerPoint 파일에 대해 민감도 레이블 지원을 사용 하도록 설정할 수 있습니다.
ms.openlocfilehash: c62db0d77ed805c607e79bf25cb9816a554cb6d2
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/19/2019
ms.locfileid: "40802831"
---
# <a name="enable-sensitivity-labels-for-office-files-in-sharepoint-and-onedrive-public-preview"></a><span data-ttu-id="e509d-103">SharePoint 및 OneDrive에서 Office 파일에 대한 민감도 레이블 사용(공개 미리 보기)</span><span class="sxs-lookup"><span data-stu-id="e509d-103">Enable sensitivity labels for Office files in SharePoint and OneDrive (public preview)</span></span>

<span data-ttu-id="e509d-104">이전에는 SharePoint 및 OneDrive에 저장 된 Office 파일에 암호화를 포함 한 민감도 레이블을 적용 했을 때 서비스가 이러한 파일의 콘텐츠를 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e509d-104">Previously, when you applied sensitivity labels that included encryption to Office files stored in SharePoint and OneDrive, the service couldn't process the content of these files.</span></span> <span data-ttu-id="e509d-105">이러한 상황에서는 공동 작성, eDiscovery, 데이터 손실 방지, 검색, Delve 및 기타 공동 작업 기능이 작동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e509d-105">Coauthoring, eDiscovery, Data Loss Prevention, search, Delve, and other collaborative features didn't work under these circumstances.</span></span> <span data-ttu-id="e509d-106">이 미리 보기를 통해 다음 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e509d-106">This preview enables these features:</span></span>

- <span data-ttu-id="e509d-107">Sharepoint 및 OneDrive의 Word, Excel 및 PowerPoint 파일에 적용 되는 민감도 레이블을 인식할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e509d-107">SharePoint recognizes sensitivity labels applied to Word, Excel, and PowerPoint files in SharePoint and OneDrive.</span></span> <span data-ttu-id="e509d-108">또한 SharePoint에서는 각 레이블에 해당 하는 설정을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e509d-108">SharePoint also enforces the settings that correspond with each label.</span></span>

- <span data-ttu-id="e509d-109">SharePoint 또는 OneDrive에서 파일을 다운로드 하면 민감도 레이블이 파일과 함께 이동 하 고 설정이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e509d-109">When you download a file from SharePoint or OneDrive, the sensitivity label travels with the file and the settings remain enforced.</span></span>

- <span data-ttu-id="e509d-110">Word, Excel 및 PowerPoint의 웹 버전을 사용 하 여 Office 파일에 민감도 레이블을 적용 하 고 적용 된 우편물 종류를 포함 하는 파일을 열고 편집 합니다 (레이블의 사용 권한을 허용 하는 경우).</span><span class="sxs-lookup"><span data-stu-id="e509d-110">Apply sensitivity labels to Office files, and open and edit files that have sensitivity labels applied (if the label's permissions allow it) by using the web versions of Word, Excel, and PowerPoint.</span></span> <span data-ttu-id="e509d-111">웹에서 Word를 사용 하 여 문서를 편집할 때도 자동 레이블 지정을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e509d-111">With Word on the web, you can also use Auto labeling when you edit documents.</span></span>

- <span data-ttu-id="e509d-112">Office 365 eDiscovery는 민감도 레이블이 적용 된 파일에서 전체 텍스트 검색을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="e509d-112">Office 365 eDiscovery supports full-text search in files that have sensitivity labels applied.</span></span> <span data-ttu-id="e509d-113">DLP (데이터 손실 방지) 정책은 이러한 파일의 콘텐츠를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="e509d-113">Data Loss Prevention (DLP) policies cover content in these files.</span></span>

- <span data-ttu-id="e509d-114">세 개의 새로운 감사 이벤트를 모니터링 민감도 레이블로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e509d-114">Three new audit events are available for monitoring sensitivity labels:</span></span>
  - <span data-ttu-id="e509d-115">FileSensitivityApplied 됨</span><span class="sxs-lookup"><span data-stu-id="e509d-115">FileSensitivityApplied</span></span>
  - <span data-ttu-id="e509d-116">FileSensitivityLabelChanged 됨</span><span class="sxs-lookup"><span data-stu-id="e509d-116">FileSensitivityLabelChanged</span></span>
  - <span data-ttu-id="e509d-117">FileSensitivityLabelRemoved 됨</span><span class="sxs-lookup"><span data-stu-id="e509d-117">FileSensitivityLabelRemoved</span></span>

<span data-ttu-id="e509d-118">이제 Microsoft 팀, Office 365 그룹 및 SharePoint 사이트에 민감도 레이블을 적용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e509d-118">You can also now apply sensitivity labels to Microsoft Teams, Office 365 groups, and SharePoint sites.</span></span> <span data-ttu-id="e509d-119">[자세히 알아보기](sensitivity-labels-teams-groups-sites.md).</span><span class="sxs-lookup"><span data-stu-id="e509d-119">[Learn more](sensitivity-labels-teams-groups-sites.md).</span></span>

<span data-ttu-id="e509d-120">필요한 경우 언제 든 지 미리 보기를 거부할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e509d-120">If necessary, you can opt out of the preview at any time.</span></span>

## <a name="requirements"></a><span data-ttu-id="e509d-121">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e509d-121">Requirements</span></span>

<span data-ttu-id="e509d-122">이러한 기능은 [민감도 레이블과](sensitivity-labels.md)함께 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="e509d-122">These features work only with [sensitivity labels](sensitivity-labels.md).</span></span> <span data-ttu-id="e509d-123">Azure Information Protection 레이블을 사용 하는 경우 업로드 하는 새 파일에 대해 이러한 기능을 사용 하도록 설정 하 여 민감도 레이블로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e509d-123">If you used Azure Information Protection labels, you can convert them to sensitivity labels to enable these features for new files that you upload.</span></span> [<span data-ttu-id="e509d-124">방법 알아보기</span><span class="sxs-lookup"><span data-stu-id="e509d-124">Learn how</span></span>](https://docs.microsoft.com/azure/information-protection/configure-policy-migrate-labels)

<span data-ttu-id="e509d-125">이 미리 보기의 경우 Windows 및 버전 19.002.0107.0008 이상에서 OneDrive 동기화 앱 버전 19.002.0121.0008 이상을 사용 하십시오 (Mac에 해당).</span><span class="sxs-lookup"><span data-stu-id="e509d-125">For this preview, use the OneDrive sync app version 19.002.0121.0008 or later on Windows and version 19.002.0107.0008 or later on Mac.</span></span> <span data-ttu-id="e509d-126">이러한 두 버전은 모두 2019 년 1 월 28 일에 출시 되었으며 현재 모든 링으로 출시 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e509d-126">Both of these versions were released on January 28, 2019, and are currently released to all rings.</span></span> <span data-ttu-id="e509d-127">[OneDrive 릴리스 정보를 참조](https://support.office.com/article/845dcf18-f921-435e-bf28-4e24b95e5fc0)하세요.</span><span class="sxs-lookup"><span data-stu-id="e509d-127">[See the OneDrive release notes](https://support.office.com/article/845dcf18-f921-435e-bf28-4e24b95e5fc0).</span></span> <span data-ttu-id="e509d-128">이 미리 보기를 사용 하도록 설정한 후에는 이전 버전의 동기화 앱을 실행 하는 사용자에 게 업데이트 하 라는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e509d-128">After you enable this preview, users who run an older version of the sync app will be prompted to update it.</span></span>

## <a name="limitations"></a><span data-ttu-id="e509d-129">제한</span><span class="sxs-lookup"><span data-stu-id="e509d-129">Limitations</span></span>

- <span data-ttu-id="e509d-130">이 미리 보기를 사용 하도록 설정 하면 Office 데스크톱 또는 모바일 앱을 사용 하 여 파일에 레이블을 적용 하는 사용자가 파일에 대해 변경한 다른 내용을 저장 하지 못할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e509d-130">When you enable this preview, users who apply a label to a file by using the Office desktop or mobile apps might be unable to save other changes they make to the file.</span></span> <span data-ttu-id="e509d-131">대신, 앱이 사용자에 게 로컬 변경 사항을 저장 하거나 삭제 하 라는 메시지를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="e509d-131">Instead, the app prompts users to Save As or Discard local changes.</span></span> <span data-ttu-id="e509d-132">작업이 손실 되지 않도록 하려면 다음 작업 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e509d-132">To avoid losing work, do one of these actions:</span></span>

  - <span data-ttu-id="e509d-133">레이블을 적용 하려면 Office 앱의 웹 버전을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e509d-133">To apply labels, use the web versions of the Office apps.</span></span>

  - <span data-ttu-id="e509d-134">레이블을 적용 한 후 파일을 닫고 다른 내용을 변경 하기 위해 파일을 다시 엽니다.</span><span class="sxs-lookup"><span data-stu-id="e509d-134">Close a file after you apply a label and then reopen the file to make other changes.</span></span>

- <span data-ttu-id="e509d-135">SharePoint에서는 Azure Information Protection 레이블을 사용 하 여 이미 암호화 한 기존 파일에 새 레이블을 자동으로 적용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e509d-135">SharePoint doesn't automatically apply the new labels to existing files that you've already encrypted using Azure Information Protection labels.</span></span> <span data-ttu-id="e509d-136">대신이 미리 보기를 사용 하도록 설정한 후에 기능을 작동 시키려면 다음 작업을 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="e509d-136">Instead, to get the features to work after you enable this preview, complete these tasks:</span></span>

  - <span data-ttu-id="e509d-137">Azure Information Protection 레이블을 민감도 레이블로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="e509d-137">Convert the Azure Information Protection labels to sensitivity labels.</span></span>

  - <span data-ttu-id="e509d-138">파일을 다운로드 하 여 SharePoint에 업로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="e509d-138">Download the files and upload them to SharePoint.</span></span>

- <span data-ttu-id="e509d-139">SharePoint에서는 사용자 지정 권한 및 레이블로 만료 날짜가 포함 된 레이블을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e509d-139">SharePoint can't process labels with custom permissions and labels with expiration dates.</span></span>

- <span data-ttu-id="e509d-140">사용자에 게 편집 권한이 있는 경우 Office 앱의 웹 버전에서는 레이블의 복사 정책 설정에 관계 없이 복사를 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e509d-140">When users have edit permissions, the web versions of the Office apps allow copying regardless of the copy policy setting in the label.</span></span>

- <span data-ttu-id="e509d-141">RMS 해지, 추적 및 보고 기능은 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e509d-141">RMS revocation, tracking, and reporting are unsupported.</span></span>

- <span data-ttu-id="e509d-142">Office 데스크톱 앱 및 모바일 앱은 공동 작성을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e509d-142">Office desktop apps and mobile apps don't support coauthoring.</span></span> <span data-ttu-id="e509d-143">대신 이러한 앱은 계속 해 서 단독 편집 모드로 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="e509d-143">Instead, these apps continue to open files in exclusive editing mode.</span></span>

- <span data-ttu-id="e509d-144">레이블에 암호화가 포함 되어 있으면 Microsoft Cloud App Security에서 SharePoint의 파일에 대 한 레이블 정보를 읽을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e509d-144">If a label includes encryption, Microsoft Cloud App Security isn't able to read the label information for the files in SharePoint.</span></span>

## <a name="prepare-the-sharepoint-online-management-shell-for-the-preview"></a><span data-ttu-id="e509d-145">미리 보기에 대 한 SharePoint Online 관리 셸 준비</span><span class="sxs-lookup"><span data-stu-id="e509d-145">Prepare the SharePoint Online Management Shell for the preview</span></span>

<span data-ttu-id="e509d-146">미리 보기를 사용 하도록 설정 하기 전에 SharePoint Online 관리 셸 버전 16.0.19418.12000 이상이 실행 되 고 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e509d-146">Before you enable the preview, ensure that you're running SharePoint Online Management Shell version 16.0.19418.12000 or above.</span></span> <span data-ttu-id="e509d-147">최신 버전을 이미 사용 하 고 있는 경우 미리 보기를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e509d-147">If you already have the latest version, you can go ahead and enable the preview.</span></span>

1. <span data-ttu-id="e509d-148">PowerShell 갤러리에서 이전 버전의 SharePoint Online 관리 셸을 설치한 경우 다음 cmdlet을 실행 하 여 모듈을 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e509d-148">If you have installed a previous version of the SharePoint Online Management Shell from PowerShell gallery, you can update the module by running the following cmdlet.</span></span>

    ```PowerShell
    Update-Module -Name Microsoft.Online.SharePoint.PowerShell
    ```

2. <span data-ttu-id="e509d-149">또는 Microsoft 다운로드 센터에서 이전 버전의 SharePoint Online 관리 셸을 설치한 경우 **프로그램 추가/제거** 로 이동 하 여 Sharepoint Online 관리 셸을 제거할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e509d-149">Alternatively, if you have installed a previous version of the SharePoint Online Management Shell from the Microsoft Download Center, you can also go to **Add or remove programs** and uninstall the SharePoint Online Management Shell.</span></span>

3. <span data-ttu-id="e509d-150">웹 브라우저에서 다운로드 센터 페이지로 이동 하 [여 최신 SharePoint Online 관리 셸을 다운로드](https://go.microsoft.com/fwlink/p/?LinkId=255251)합니다.</span><span class="sxs-lookup"><span data-stu-id="e509d-150">In a web browser, go to the Download Center page and [Download the latest SharePoint Online Management Shell](https://go.microsoft.com/fwlink/p/?LinkId=255251).</span></span>

4. <span data-ttu-id="e509d-151">언어를 선택 하 고 **다운로드**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e509d-151">Select your language and then click **Download**.</span></span>

5. <span data-ttu-id="e509d-152">X64 파일과 x86 .msi 파일 중에서 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e509d-152">Choose between the x64 and x86 .msi file.</span></span> <span data-ttu-id="e509d-153">64 비트 버전의 Windows 또는 x86 파일 (32 비트 버전을 실행 하는 경우)을 실행 하는 경우 x64 파일을 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="e509d-153">Download the x64 file if you run the 64-bit version of Windows or the x86 file if you run the 32-bit version.</span></span> <span data-ttu-id="e509d-154">알 수 없는 경우 [실행 중인 Windows 운영 체제 버전](https://support.microsoft.com/help/13443/windows-which-operating-system) 을 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="e509d-154">If you don’t know, see [Which version of Windows operating system am I running?](https://support.microsoft.com/help/13443/windows-which-operating-system)</span></span>


6. <span data-ttu-id="e509d-155">파일을 다운로드 한 후에는 파일을 실행 하 고 설치 마법사의 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="e509d-155">After you have downloaded the file, run the file and follow the steps in the Setup Wizard.</span></span>

## <a name="enable-the-preview-by-using-microsoft-powershell-opt-in"></a><span data-ttu-id="e509d-156">Microsoft PowerShell을 사용 하 여 미리 보기 사용 (옵트인)</span><span class="sxs-lookup"><span data-stu-id="e509d-156">Enable the preview by using Microsoft PowerShell (opt-in)</span></span>

<span data-ttu-id="e509d-157">미리 보기를 사용 하도록 설정 하려면 Set-spotenant cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e509d-157">To enable the preview, use the Set-SPOTenant cmdlet:</span></span>

1. <span data-ttu-id="e509d-158">Office 365에서 전역 관리자 또는 SharePoint 관리자 권한이 있는 회사 또는 학교 계정을 사용 하 여 SharePoint에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="e509d-158">Using a work or school account that has global administrator or SharePoint admin privileges in Office 365, connect to SharePoint.</span></span> <span data-ttu-id="e509d-159">자세한 방법은 [SharePoint Online 관리 셸 시작](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e509d-159">To learn how, see [Getting started with SharePoint Online Management Shell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span></span>

2. <span data-ttu-id="e509d-160">다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="e509d-160">Run the following command:</span></span>

    ```PowerShell
    Set-SPOTenant -EnableAIPIntegration $true  
    ```

## <a name="schedule-roll-out-after-you-create-or-change-a-sensitivity-label"></a><span data-ttu-id="e509d-161">민감도 레이블을 만들거나 변경한 후 일정 롤업</span><span class="sxs-lookup"><span data-stu-id="e509d-161">Schedule roll-out after you create or change a sensitivity label</span></span>

<span data-ttu-id="e509d-162">Microsoft 365 준수 센터에서 민감도 레이블을 만들거나 변경한 후에는 스테이지에 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="e509d-162">After you create or change a sensitivity label in the Microsoft 365 compliance center, publish it in stages.</span></span> <span data-ttu-id="e509d-163">완전히 동기화 되지 않은 레이블을 게시 하면 사용자가 파일에 레이블을 적용 하 여 SharePoint에 업로드 하는 경우 Office 앱의 웹 버전에서는 파일을 열 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e509d-163">If you publish labels that haven't fully synchronized, when users apply the labels to files and upload them to SharePoint, the files can’t be opened in the web versions of the Office apps.</span></span> <span data-ttu-id="e509d-164">검색 및 eDiscovery도 파일에 대해 작동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e509d-164">Search and eDiscovery also don't work for the files.</span></span>

<span data-ttu-id="e509d-165">다음 단계를 따르는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="e509d-165">We recommend that you follow these steps:</span></span>

1. <span data-ttu-id="e509d-166">새 민감도 레이블을 한 명 또는 두 사람에 게 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="e509d-166">Publish the new or modified sensitivity label only to one or two people.</span></span>

2. <span data-ttu-id="e509d-167">초기 발행물 이후 24 시간 이상 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="e509d-167">Wait for at least 24 hours after initial publication.</span></span> <span data-ttu-id="e509d-168">레이블이 완전히 동기화 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e509d-168">Verify that the label has fully synchronized.</span></span>

3. <span data-ttu-id="e509d-169">레이블을 보다 광범위 하 게 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="e509d-169">Publish the label more broadly.</span></span>

## <a name="disable-the-preview-by-using-microsoft-powershell-opt-out"></a><span data-ttu-id="e509d-170">Microsoft PowerShell을 사용 하 여 미리 보기 사용 안 함 (옵트아웃)</span><span class="sxs-lookup"><span data-stu-id="e509d-170">Disable the preview by using Microsoft PowerShell (opt-out)</span></span>

<span data-ttu-id="e509d-171">이 미리 보기를 사용 하지 않도록 설정 하는 경우 미리 보기 중에 업로드 한 파일은 계속 해 서 레이블로 보호 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e509d-171">If you disable this preview, files that you uploaded during the preview continue to be protected by the label.</span></span> <span data-ttu-id="e509d-172">해당 설정이 계속 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e509d-172">The corresponding settings continue to be enforced.</span></span> <span data-ttu-id="e509d-173">미리 보기를 사용 하지 않도록 설정한 후 새 파일에 레이블을 적용 하면 전체 텍스트 검색, eDiscovery 및 공동 작성이 더 이상 작동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e509d-173">When you apply labels to new files after you disable the preview, full-text search, eDiscovery, and coauthoring will no longer work.</span></span>

<span data-ttu-id="e509d-174">미리 보기를 사용 하지 않도록 설정 하려면 Set-spotenant cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e509d-174">To disable the preview, use the Set-SPOTenant cmdlet:</span></span>

1. <span data-ttu-id="e509d-175">Office 365에서 전역 관리자 또는 SharePoint 관리자 권한이 있는 회사 또는 학교 계정을 사용 하 여 SharePoint에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="e509d-175">Using a work or school account that has global administrator or SharePoint admin privileges in Office 365, connect to SharePoint.</span></span> <span data-ttu-id="e509d-176">자세한 방법은 [SharePoint Online 관리 셸 시작](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e509d-176">To learn how, see [Getting started with SharePoint Online Management Shell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span></span>

2. <span data-ttu-id="e509d-177">다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="e509d-177">Run the following command:</span></span>

    ```PowerShell
    Set-SPOTenant -EnableAIPIntegration $false
    ```
