---
title: SharePoint 및 OneDrive에서 Office 파일에 대한 민감도 레이블 사용
f1.keywords:
- NOCSH
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
ms.openlocfilehash: 840087be38c6e50244437fea63de655d8cd9363e
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/21/2020
ms.locfileid: "42894304"
---
# <a name="enable-sensitivity-labels-for-office-files-in-sharepoint-and-onedrive-public-preview"></a><span data-ttu-id="a4044-103">SharePoint 및 OneDrive에서 Office 파일에 대한 민감도 레이블 사용(공개 미리 보기)</span><span class="sxs-lookup"><span data-stu-id="a4044-103">Enable sensitivity labels for Office files in SharePoint and OneDrive (public preview)</span></span>

<span data-ttu-id="a4044-104">이 미리 보기를 수행 하기 전에 SharePoint 및 OneDrive에 저장 된 Office 파일에 암호화를 포함 한 민감도 레이블을 적용할 때 서비스가 이러한 파일의 콘텐츠를 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a4044-104">Before this preview, when you applied sensitivity labels that included encryption to Office files stored in SharePoint and OneDrive, the service couldn't process the content of these files.</span></span> <span data-ttu-id="a4044-105">이러한 상황에서는 공동 작성, eDiscovery, 데이터 손실 방지, 검색, Delve 및 기타 공동 작업 기능이 작동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a4044-105">Coauthoring, eDiscovery, Data Loss Prevention, search, Delve, and other collaborative features didn't work under these circumstances.</span></span> <span data-ttu-id="a4044-106">이 미리 보기를 사용 하면 클라우드 기반 키를 사용 하 여 암호화를 포함 하는 우편물 종류 레이블이 적용 된 새 파일 및 변경 되는 이러한 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4044-106">This preview enables these features for new and changed files that have a sensitivity label applied that includes encryption with a cloud-based key:</span></span>

- <span data-ttu-id="a4044-107">Sharepoint 및 OneDrive에서 Word, Excel 및 PowerPoint 파일에 적용 되는 민감도 레이블 (sharepoint 및 비즈니스용 파일)은 sharepoint에 저장 되므로 파일 내용을 처리할 수 있도록 Azure Information Protection의 암호화가 제거 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4044-107">SharePoint recognizes sensitivity labels applied to Word, Excel, and PowerPoint files in SharePoint and OneDrive: While the file is stored in SharePoint, the encryption from Azure Information Protection is removed so that the file contents can be processed.</span></span> <span data-ttu-id="a4044-108">SharePoint에 저장 되어 있는 동안 문서를 보호 하는 방법에 대 한 자세한 내용은 [비즈니스용 OneDrive 및 SharePoint Online의 데이터 암호화](data-encryption-in-odb-and-spo.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a4044-108">For information about how documents are protected while they are stored in SharePoint, see [Data Encryption in OneDrive for Business and SharePoint Online](data-encryption-in-odb-and-spo.md).</span></span>

- <span data-ttu-id="a4044-109">SharePoint 또는 OneDrive에서이 파일을 다운로드 하거나 액세스할 때 레이블에 있는 민감도 레이블과 모든 암호화 설정이 파일에 다시 적용 되며, 이러한 설정은 파일을 저장할 때마다 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4044-109">When you download or access this file from SharePoint or OneDrive, the sensitivity label and any encryption settings from the label are reapplied with the file, and these settings remain enforced wherever the file is saved.</span></span> <span data-ttu-id="a4044-110">이 동작으로 인해 문서를 보호 하는 데 레이블만 사용 하는 사용자 지침이 제공 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4044-110">Because of this behavior, ensure you provide user guidance to use only labels to protect documents.</span></span> <span data-ttu-id="a4044-111">자세한 내용은 [IRM (정보 권한 관리) 옵션 및 민감도 레이블을](sensitivity-labels-office-apps.md#information-rights-management-irm-options-and-sensitivity-labels)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a4044-111">For more information, see [Information Rights Management (IRM) options and sensitivity labels](sensitivity-labels-office-apps.md#information-rights-management-irm-options-and-sensitivity-labels).</span></span>

- <span data-ttu-id="a4044-112">SharePoint에서 업로드 시 파일의 암호화를 제거 하려면 레이블이 지정 되 고 암호화 된 파일을 업로드 하는 사용자에 게 최소한 파일 보기에 대 한 사용 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4044-112">For SharePoint to remove the encryption from the file on upload, the user who uploads the labeled and encrypted file must have usage rights to at least view the file.</span></span> <span data-ttu-id="a4044-113">Sharepoint에서 사용자가 파일을 열 수 없는 경우 sharepoint에서 암호화를 제거 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a4044-113">SharePoint doesn't remove encryption from files if the user can't open them outside SharePoint.</span></span>

- <span data-ttu-id="a4044-114">웹에서 Office (Word, Excel, PowerPoint)를 사용 하 여 암호화를 적용 하는 레이블이 민감도 인 Office 파일을 열고 편집 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4044-114">Use Office on the web (Word, Excel, PowerPoint) to open and edit Office files that have sensitivity labels that apply encryption.</span></span> <span data-ttu-id="a4044-115">암호화를 통해 할당 된 사용 권한이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4044-115">The permissions that were assigned with the encryption are enforced.</span></span> <span data-ttu-id="a4044-116">웹에서 Word를 사용 하는 경우 이러한 문서를 편집 하는 경우에도 자동 레이블을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4044-116">With Word on the web, you can also use auto labeling when you edit these documents.</span></span>

- <span data-ttu-id="a4044-117">Office 365 eDiscovery는 이러한 파일에 대 한 전체 텍스트 검색을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4044-117">Office 365 eDiscovery supports full-text search for these files.</span></span> <span data-ttu-id="a4044-118">DLP (데이터 손실 방지) 정책은 이러한 파일의 콘텐츠를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4044-118">Data Loss Prevention (DLP) policies cover content in these files.</span></span>

- <span data-ttu-id="a4044-119">웹에서 Office를 사용 하 여 적용 되는 모니터링 민감도 레이블에 대해 세 가지 새로운 [감사 이벤트](search-the-audit-log-in-security-and-compliance.md#sensitivity-label-activities) 를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4044-119">Three new [audit events](search-the-audit-log-in-security-and-compliance.md#sensitivity-label-activities) are available for monitoring sensitivity labels that are applied using Office on the web:</span></span>
  - <span data-ttu-id="a4044-120">**파일에 적용된 민감도 레이블**</span><span class="sxs-lookup"><span data-stu-id="a4044-120">**Applied sensitivity label to file**</span></span>
  - <span data-ttu-id="a4044-121">**파일에 변경된 민감도 레이블을 적용**</span><span class="sxs-lookup"><span data-stu-id="a4044-121">**Changed sensitivity label applied to file**</span></span>
  - <span data-ttu-id="a4044-122">**파일에서 제거된 민감도 레이블**</span><span class="sxs-lookup"><span data-stu-id="a4044-122">**Removed sensitivity label from file**</span></span>

> [!NOTE]
> <span data-ttu-id="a4044-123">암호화가 클라우드 기반 키와 함께 온-프레미스 키가 적용 되지 않은 경우 키 관리 토폴로지에서 흔히 "자체 키를 사용" (HYOK)으로 지칭 되는 경우에는이 미리 보기를 통해 SharePoint 동작이 변경 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a4044-123">If encryption hasn't been applied with a cloud-based key but an on-premises key, a key management topology often referred to as "hold your own key" (HYOK), the SharePoint behavior doesn't change with this preview.</span></span>
>
> <span data-ttu-id="a4044-124">또한 SharePoint 동작은 미리 보기를 사용 하도록 설정 하기 전에 SharePoint에서 레이블이 지정 되 고 암호화 된 기존 파일에 대해서는 변경 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a4044-124">The SharePoint behavior also doesn't change for existing labeled and encrypted files in SharePoint before you enable the preview.</span></span> <span data-ttu-id="a4044-125">이러한 파일을 새 기능의 혜택을 얻으려면 미리 보기를 사용 하도록 설정한 후 다운로드 및 업로드 하거나 편집 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4044-125">For these files to benefit from the new capabilities, they must be either downloaded and uploaded, or edited after you enable the preview.</span></span> <span data-ttu-id="a4044-126">예를 들어 검색 및 eDiscovery 결과에서 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4044-126">For example, they will then be returned in search and eDiscovery results.</span></span>

<span data-ttu-id="a4044-127">이제 Microsoft 팀, Office 365 그룹 및 SharePoint 사이트에 민감도 레이블을 적용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4044-127">You can also now apply sensitivity labels to Microsoft Teams, Office 365 groups, and SharePoint sites.</span></span> <span data-ttu-id="a4044-128">이 별도의 미리 보기에 대 한 자세한 내용은 [사용 민감도 레이블 (Microsoft 팀, Office 365 그룹 및 SharePoint 사이트 (공용 미리 보기))](sensitivity-labels-teams-groups-sites.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="a4044-128">For more information about this separate preview, see [Use sensitivity labels with Microsoft Teams, Office 365 groups, and SharePoint sites (public preview)](sensitivity-labels-teams-groups-sites.md).</span></span>

<span data-ttu-id="a4044-129">언제 든 지이 미리 보기를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4044-129">You always have the choice to opt out of this preview at any time.</span></span>

<span data-ttu-id="a4044-130">다음 비디오 (오디오 없음)를 시청 하 여 이러한 새로운 기능이 작동 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4044-130">Watch the following video (no audio) to see these new capabilities in action:</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed//RE4ornZ]

## <a name="requirements"></a><span data-ttu-id="a4044-131">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a4044-131">Requirements</span></span>

<span data-ttu-id="a4044-132">이러한 기능은 [민감도 레이블](sensitivity-labels.md) 에서만 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4044-132">These features work with [sensitivity labels](sensitivity-labels.md) only.</span></span> <span data-ttu-id="a4044-133">현재 Azure Information Protection 레이블이 있는 경우에는 업로드 하는 새 파일에 대해 이러한 기능을 사용할 수 있도록 먼저 해당 레이블을 민감도 레이블로 마이그레이션하십시오.</span><span class="sxs-lookup"><span data-stu-id="a4044-133">If you currently have Azure Information Protection labels, first migrate them to sensitivity labels so that you can enable these features for new files that you upload.</span></span> <span data-ttu-id="a4044-134">자세한 내용은 [통합 민감도 레이블로 Azure Information Protection 레이블을 마이그레이션하는 방법](https://docs.microsoft.com/azure/information-protection/configure-policy-migrate-labels) 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="a4044-134">For instructions, see [How to migrate Azure Information Protection labels to unified sensitivity labels](https://docs.microsoft.com/azure/information-protection/configure-policy-migrate-labels)</span></span>

<span data-ttu-id="a4044-135">이 미리 보기의 경우 Windows 및 버전 19.002.0107.0008 이상에서 OneDrive 동기화 앱 버전 19.002.0121.0008 이상을 사용 하십시오.</span><span class="sxs-lookup"><span data-stu-id="a4044-135">For this preview, use the OneDrive sync app version 19.002.0121.0008 or later on Windows, and version 19.002.0107.0008 or later on Mac.</span></span> <span data-ttu-id="a4044-136">두 버전 모두 2019 년 1 월 28 일에 출시 되었으며 현재 모든 링으로 출시 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a4044-136">Both these versions were released January 28, 2019, and are currently released to all rings.</span></span> <span data-ttu-id="a4044-137">자세한 내용은 [OneDrive 릴리스 노트](https://support.office.com/article/845dcf18-f921-435e-bf28-4e24b95e5fc0)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a4044-137">For more information, see the [OneDrive release notes](https://support.office.com/article/845dcf18-f921-435e-bf28-4e24b95e5fc0).</span></span> <span data-ttu-id="a4044-138">이 미리 보기를 사용 하도록 설정한 후에는 이전 버전의 동기화 앱을 실행 하는 사용자에 게 업데이트 하 라는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4044-138">After you enable this preview, users who run an older version of the sync app are prompted to update it.</span></span>

## <a name="limitations"></a><span data-ttu-id="a4044-139">제한</span><span class="sxs-lookup"><span data-stu-id="a4044-139">Limitations</span></span>

- <span data-ttu-id="a4044-140">이 미리 보기를 사용 하도록 설정 하면 OneDrive 동기화 폴더에 있는 파일의 레이블을 변경 하는 사용자가 파일에 변경한 다른 내용을 저장 하지 못할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4044-140">When you enable this preview, users who change a label on a file in a OneDrive Sync folder might be unable to save other changes they make to the file.</span></span>  <span data-ttu-id="a4044-141">사용자에 게 [흰색 횡단면 오류가 있는 빨간색 원이](https://support.office.com/article/what-do-the-onedrive-icons-mean-11143026-8000-44f8-aaa9-67c985aa49b3)표시 되 고 새 변경 내용을 별도의 복사본으로 저장할지 묻는 메시지가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="a4044-141">Users see a [red circle with a white cross icon error](https://support.office.com/article/what-do-the-onedrive-icons-mean-11143026-8000-44f8-aaa9-67c985aa49b3), and they are asked to save new changes as a separate copy.</span></span>  <span data-ttu-id="a4044-142">사용자가 시작한 레이블 변경 사항 외에도, 관리자가 사용자의 동기화 클라이언트에 다운로드 된 파일에 이미 적용 되어 있는 게시 한 레이블의 설정을 변경 하는 경우에도 같은 동작이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4044-142">In addition to label changes that are initiated by users, the same behavior can occur if an admin changes settings for a published label that's already applied to files downloaded to users' sync client.</span></span>
    
    <span data-ttu-id="a4044-143">이러한 시나리오에서 작업이 손실 되지 않도록 하려면 다음 작업 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4044-143">To avoid losing work for these scenarios, do one of these actions:</span></span>
    - <span data-ttu-id="a4044-144">레이블을 적용 하려면 Office 앱의 웹 버전을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4044-144">To apply labels, use the web versions of the Office apps.</span></span>
    - <span data-ttu-id="a4044-145">레이블을 적용 한 후 파일을 닫고 다른 내용을 변경 하기 위해 파일을 다시 엽니다.</span><span class="sxs-lookup"><span data-stu-id="a4044-145">Close a file after you apply a label, and then reopen the file to make other changes.</span></span>

- <span data-ttu-id="a4044-146">SharePoint에서는 이미 Azure Information Protection 레이블을 사용 하 여 암호화 한 기존 파일에 민감도 레이블을 자동으로 적용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a4044-146">SharePoint doesn't automatically apply sensitivity labels to existing files that you've already encrypted using Azure Information Protection labels.</span></span> <span data-ttu-id="a4044-147">대신이 미리 보기를 사용 하도록 설정한 후에 기능을 작동 시키려면 다음 작업을 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4044-147">Instead, to get the features to work after you enable this preview, complete these tasks:</span></span>
    
    1. <span data-ttu-id="a4044-148">Azure Information Protection 레이블을 민감도 레이블로 마이그레이션하고 Microsoft 365 준수 센터 또는 레이블 관리 센터에서 게시 했는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4044-148">Make sure you have migrated the Azure Information Protection labels to sensitivity labels and published them from the Microsoft 365 compliance center, or equivalent labeling admin center.</span></span>
    
    2. <span data-ttu-id="a4044-149">파일을 다운로드 한 다음 SharePoint에 업로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4044-149">Download the files and then upload them to SharePoint.</span></span>

- <span data-ttu-id="a4044-150">암호화를 적용 한 레이블에서 암호화에 대 한 다음 구성 중 하나를 수행 하면 SharePoint에서 암호화 된 파일을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a4044-150">SharePoint can't process encrypted files when the label that applied the encryption has either of the following configurations for encryption:</span></span>
    - <span data-ttu-id="a4044-151">사용자가 **Word, PowerPoint 및 Excel에서 사용 권한을 지정할** **때 사용 권한을 할당할 수** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4044-151">**Let users assign permissions when they apply the label** and the checkbox for **In Word, PowerPoint, and Excel, prompt users to specify permissions** is selected.</span></span> <span data-ttu-id="a4044-152">이 설정을 "사용자 정의 권한"이 라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4044-152">This setting is sometimes referred to as "user-defined permissions".</span></span>
    - <span data-ttu-id="a4044-153">**콘텐츠에 대 한 사용자 액세스 만료** 는 **Never**이외의 값으로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4044-153">**User access to content expires** is set to a value other than **Never**.</span></span>
    
    <span data-ttu-id="a4044-154">이러한 암호화 구성 중 하나가 있는 레이블의 경우에는 웹에서 Office 사용자에 게 레이블이 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a4044-154">For labels with either of these encryption configurations, the labels aren't displayed to users in Office on the web.</span></span> <span data-ttu-id="a4044-155">또한이 미리 보기의 새로운 기능은 이미 이러한 암호화 설정이 적용 된 레이블이 지정 된 문서에는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a4044-155">Additionally, the new capabilities from this preview can't be used with labeled documents that already have these encryption settings.</span></span> <span data-ttu-id="a4044-156">예를 들어 이러한 문서는 업데이트 되더라도 검색 결과에 반환 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a4044-156">For example, these documents won't be returned in search results, even if they are updated.</span></span>

- <span data-ttu-id="a4044-157">사용자에 게 편집 권한을 부여 하는 암호화 된 문서에서는 Office 앱의 웹 버전에서 복사를 차단할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a4044-157">For an encrypted document that grants edit permissions to a user, copying can't be blocked in the web versions of the Office apps.</span></span>

- <span data-ttu-id="a4044-158">Azure Information Protection 문서 추적 사이트는 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a4044-158">The Azure Information Protection document tracking site is not supported.</span></span>

- <span data-ttu-id="a4044-159">Office 데스크톱 앱 및 모바일 앱은 공동 작성을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a4044-159">Office desktop apps and mobile apps don't support coauthoring.</span></span> <span data-ttu-id="a4044-160">대신 이러한 앱은 계속 해 서 단독 편집 모드로 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="a4044-160">Instead, these apps continue to open files in exclusive editing mode.</span></span>

- <span data-ttu-id="a4044-161">레이블이 지정 된 문서가 SharePoint에 업로드 되 고 레이블이 서비스 사용자 이름의 계정을 사용 하 여 암호화를 적용 한 경우에는 웹의 Office에서 해당 문서를 열 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a4044-161">If a labeled document is uploaded to SharePoint and the label applied encryption by using an account from a service principal name, the document can't be opened in Office on the web.</span></span> <span data-ttu-id="a4044-162">예제 시나리오에는 Microsoft Cloud App Security 및 팀별로 전자 메일로 전송 되는 파일이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4044-162">Example scenarios include Microsoft Cloud App Security and a file sent to Teams by email.</span></span>

- <span data-ttu-id="a4044-163">사용자는 오프 라인으로 전환 하거나 절전 모드로 전환한 후에 저장 문제를 경험 하거나, 웹에서 Office를 사용 하는 대신 Word, Excel 또는 PowerPoint 용 데스크톱 및 모바일 앱을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4044-163">Users can experience save problems after going offline or into a sleep mode when instead of using Office for the web, they use the desktop and mobile apps for Word, Excel, or PowerPoint.</span></span> <span data-ttu-id="a4044-164">이러한 사용자의 경우 Office 앱 세션을 다시 시작 하 고 변경 내용을 저장 하려고 하면 원본 파일을 저장 하는 대신 복사본을 저장 하는 옵션이 포함 된 업로드 실패 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4044-164">For these users, when they resume their Office app session and try to save changes, they see an upload failure message with an option to save a copy instead of saving the original file.</span></span> 

- <span data-ttu-id="a4044-165">다음과 같은 방법으로 암호화 된 문서는 웹에서 Office에서 열 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a4044-165">Documents that have been encrypted in the following ways can't be opened in Office on the web:</span></span>
    - <span data-ttu-id="a4044-166">온-프레미스 키를 사용 하는 암호화 ("자체 키를 포함" 또는 HYOK)</span><span class="sxs-lookup"><span data-stu-id="a4044-166">Encryption that uses an on-premises key ("hold your own key" or HYOK)</span></span>
    - <span data-ttu-id="a4044-167">예를 들어 권한 관리 보호 서식 파일을 직접 적용 하는 경우와 같이 레이블과 독립적으로 적용 되는 암호화</span><span class="sxs-lookup"><span data-stu-id="a4044-167">Encryption that was applied independently from a label, for example, by directly applying a Rights Management protection template.</span></span>

- <span data-ttu-id="a4044-168">해당 레이블 정책에서 레이블을 제거 하지 않고 SharePoint의 문서에 적용 된 레이블을 삭제 하는 경우에는 다운로드 시 문서를 레이블이 지정 되거나 암호화 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a4044-168">If you delete a label that's been applied to a document in SharePoint, rather than remove the label from the applicable label policy, the document when downloaded won't be labeled or encrypted.</span></span> <span data-ttu-id="a4044-169">비교에서 레이블이 지정 된 문서가 SharePoint 외부에 저장 된 경우 레이블이 삭제 되 면 문서는 암호화 된 상태로 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4044-169">In comparison, if the labeled document is stored outside SharePoint, the document remains encrypted if the label is deleted.</span></span> <span data-ttu-id="a4044-170">테스트 단계에서 레이블을 삭제할 수는 있지만 프로덕션 환경에서는 레이블을 삭제 하는 것이 거의 발생 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a4044-170">Note that although you might delete labels during a testing phase, it's very rare to delete a label in a production environment.</span></span>

## <a name="prepare-the-sharepoint-online-management-shell-for-the-preview"></a><span data-ttu-id="a4044-171">미리 보기에 대 한 SharePoint Online 관리 셸 준비</span><span class="sxs-lookup"><span data-stu-id="a4044-171">Prepare the SharePoint Online Management Shell for the preview</span></span>

<span data-ttu-id="a4044-172">미리 보기를 사용 하도록 설정 하기 전에 SharePoint Online 관리 셸 버전 16.0.19418.12000 이상이 실행 되 고 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4044-172">Before you enable the preview, ensure that you're running SharePoint Online Management Shell version 16.0.19418.12000 or above.</span></span> <span data-ttu-id="a4044-173">최신 버전을 이미 사용 하 고 있는 경우 미리 보기를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4044-173">If you already have the latest version, you can go ahead and enable the preview.</span></span>

1. <span data-ttu-id="a4044-174">PowerShell 갤러리에서 이전 버전의 SharePoint Online 관리 셸을 설치한 경우 다음 cmdlet을 실행하여 모듈을 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4044-174">If you have installed a previous version of the SharePoint Online Management Shell from PowerShell gallery, you can update the module by running the following cmdlet.</span></span>

    ```PowerShell
    Update-Module -Name Microsoft.Online.SharePoint.PowerShell
    ```

2. <span data-ttu-id="a4044-175">또는 Microsoft 다운로드 센터에서 이전 버전의 SharePoint Online 관리 셸을 설치한 경우 **프로그램 추가/제거** 로 이동 하 여 Sharepoint Online 관리 셸을 제거할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4044-175">Alternatively, if you have installed a previous version of the SharePoint Online Management Shell from the Microsoft Download Center, you can also go to **Add or remove programs** and uninstall the SharePoint Online Management Shell.</span></span>

3. <span data-ttu-id="a4044-176">웹 브라우저에서 다운로드 센터 페이지로 이동한 다음 [최신 SharePoint Online 관리 셸을 다운로드](https://go.microsoft.com/fwlink/p/?LinkId=255251)합니다.</span><span class="sxs-lookup"><span data-stu-id="a4044-176">In a web browser, go to the Download Center page and [Download the latest SharePoint Online Management Shell](https://go.microsoft.com/fwlink/p/?LinkId=255251).</span></span>

4. <span data-ttu-id="a4044-177">언어를 선택한 다음 **다운로드**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a4044-177">Select your language and then click **Download**.</span></span>

5. <span data-ttu-id="a4044-178">X64 및 x86 .msi 파일 중에서 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a4044-178">Choose between the x64 and x86 .msi file.</span></span> <span data-ttu-id="a4044-179">64 비트 버전의 Windows 또는 x86 파일 (32 비트 버전을 실행 하는 경우)을 실행 하는 경우 x64 파일을 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4044-179">Download the x64 file if you run the 64-bit version of Windows or the x86 file if you run the 32-bit version.</span></span> <span data-ttu-id="a4044-180">알 수 없는 경우 [실행 중인 Windows 운영 체제 버전](https://support.microsoft.com/help/13443/windows-which-operating-system) 을 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="a4044-180">If you don’t know, see [Which version of Windows operating system am I running?](https://support.microsoft.com/help/13443/windows-which-operating-system)</span></span>


6. <span data-ttu-id="a4044-181">파일을 다운로드 한 후에는 파일을 실행 하 고 설치 마법사의 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="a4044-181">After you have downloaded the file, run the file and follow the steps in the Setup Wizard.</span></span>

## <a name="enable-the-preview-by-using-microsoft-powershell-opt-in"></a><span data-ttu-id="a4044-182">Microsoft PowerShell을 사용 하 여 미리 보기 사용 (옵트인)</span><span class="sxs-lookup"><span data-stu-id="a4044-182">Enable the preview by using Microsoft PowerShell (opt-in)</span></span>

<span data-ttu-id="a4044-183">미리 보기를 사용 하도록 설정 하려면 Set-spotenant cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4044-183">To enable the preview, use the Set-SPOTenant cmdlet:</span></span>

1. <span data-ttu-id="a4044-184">Office 365에서 전역 관리자 또는 SharePoint 관리자 권한이 있는 회사 또는 학교 계정을 사용 하 여 SharePoint에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4044-184">Using a work or school account that has global administrator or SharePoint admin privileges in Office 365, connect to SharePoint.</span></span> <span data-ttu-id="a4044-185">자세한 방법은 [SharePoint Online 관리 셸 시작](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a4044-185">To learn how, see [Getting started with SharePoint Online Management Shell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span></span>
    
    <span data-ttu-id="a4044-186">참고: Office 365 다중 위치를 사용 하는 경우-Url 매개 변수를 [connect-sposervice와 연결](https://docs.microsoft.com/powershell/module/sharepoint-online/connect-sposervice?view=sharepoint-ps)하 고 지리적 위치 중 하나에 대 한 SharePoint Online 관리 센터 사이트 Url을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4044-186">Note: If you have Office 365 Multi-Geo, use the -Url parameter with [Connect-SPOService](https://docs.microsoft.com/powershell/module/sharepoint-online/connect-sposervice?view=sharepoint-ps), and specify the SharePoint Online Administration Center site URL for one of your geo-locations.</span></span>

2. <span data-ttu-id="a4044-187">다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="a4044-187">Run the following command:</span></span>

    ```PowerShell
    Set-SPOTenant -EnableAIPIntegration $true  
    ```
3. <span data-ttu-id="a4044-188">Office 365 다중 사용자의 경우 나머지 각 지리적 위치에 대해 1 ~ 2 단계를 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4044-188">For Office 365 Multi-Geo: Repeat steps 1 and 2 for each of your remaining geo-locations.</span></span>

## <a name="schedule-roll-out-after-you-create-or-change-a-sensitivity-label"></a><span data-ttu-id="a4044-189">민감도 레이블을 만들거나 변경한 후 일정 롤업</span><span class="sxs-lookup"><span data-stu-id="a4044-189">Schedule roll-out after you create or change a sensitivity label</span></span>

<span data-ttu-id="a4044-190">Microsoft 365 준수 센터에서 민감도 레이블을 만들거나 변경한 후에는 스테이지에 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4044-190">After you create or change a sensitivity label in the Microsoft 365 compliance center, publish it in stages.</span></span> <span data-ttu-id="a4044-191">완전히 동기화 되지 않은 레이블을 게시 하면 사용자가 파일에 레이블을 적용 하 여 SharePoint에 업로드 하는 경우 Office 앱의 웹 버전에서는 파일을 열 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a4044-191">If you publish labels that haven't fully synchronized, when users apply the labels to files and upload them to SharePoint, the files can’t be opened in the web versions of the Office apps.</span></span> <span data-ttu-id="a4044-192">검색 및 eDiscovery도 파일에 대해 작동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a4044-192">Search and eDiscovery also don't work for the files.</span></span>

<span data-ttu-id="a4044-193">다음 단계를 따르는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a4044-193">We recommend that you follow these steps:</span></span>

1. <span data-ttu-id="a4044-194">새 민감도 레이블을 한 명 또는 두 사람에 게 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4044-194">Publish the new or modified sensitivity label only to one or two people.</span></span>

2. <span data-ttu-id="a4044-195">초기 발행물 이후 24 시간 이상 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="a4044-195">Wait for at least 24 hours after initial publication.</span></span> <span data-ttu-id="a4044-196">레이블이 완전히 동기화 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4044-196">Verify that the label has fully synchronized.</span></span>

3. <span data-ttu-id="a4044-197">레이블을 보다 광범위 하 게 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4044-197">Publish the label more broadly.</span></span>

## <a name="disable-the-preview-by-using-microsoft-powershell-opt-out"></a><span data-ttu-id="a4044-198">Microsoft PowerShell을 사용 하 여 미리 보기 사용 안 함 (옵트아웃)</span><span class="sxs-lookup"><span data-stu-id="a4044-198">Disable the preview by using Microsoft PowerShell (opt-out)</span></span>

<span data-ttu-id="a4044-199">이 미리 보기를 사용 하지 않도록 설정 하는 경우 미리 보기 중에 업로드 한 파일은 계속 해 서 레이블로 보호 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4044-199">If you disable this preview, files that you uploaded during the preview continue to be protected by the label.</span></span> <span data-ttu-id="a4044-200">해당 설정이 계속 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4044-200">The corresponding settings continue to be enforced.</span></span> <span data-ttu-id="a4044-201">미리 보기를 사용 하지 않도록 설정한 후 새 파일에 레이블을 적용 하면 전체 텍스트 검색, eDiscovery 및 공동 작성이 더 이상 작동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a4044-201">When you apply labels to new files after you disable the preview, full-text search, eDiscovery, and coauthoring will no longer work.</span></span>

<span data-ttu-id="a4044-202">미리 보기를 사용 하지 않도록 설정 하려면 Set-spotenant cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4044-202">To disable the preview, use the Set-SPOTenant cmdlet:</span></span>

1. <span data-ttu-id="a4044-203">Office 365에서 전역 관리자 또는 SharePoint 관리자 권한이 있는 회사 또는 학교 계정을 사용 하 여 SharePoint에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4044-203">Using a work or school account that has global administrator or SharePoint admin privileges in Office 365, connect to SharePoint.</span></span> <span data-ttu-id="a4044-204">자세한 방법은 [SharePoint Online 관리 셸 시작](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a4044-204">To learn how, see [Getting started with SharePoint Online Management Shell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span></span>

2. <span data-ttu-id="a4044-205">다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="a4044-205">Run the following command:</span></span>

    ```PowerShell
    Set-SPOTenant -EnableAIPIntegration $false
    ```
