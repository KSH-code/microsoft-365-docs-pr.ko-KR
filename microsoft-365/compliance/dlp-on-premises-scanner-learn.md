---
title: Microsoft 365 데이터 손실 방지 온-프레미스 스캐너 알아보기(미리 보기)
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MET150
description: Microsoft 365 데이터 손실 방지 온-프레미스 스캐너는 파일 활동과 해당 파일에 대한 보호 작업 모니터링을 온-프레미스 파일 공유와 SharePoint 폴더 및 문서 라이브러리로 확대시킵니다. 파일은 AIP(정보 보호) 스캐너로 스캔되어 보호됩니다.
ms.openlocfilehash: f0a34a13630e42c5dd29734ad708b3c11bb1d587
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/30/2021
ms.locfileid: "52114166"
---
# <a name="learn-about-the-microsoft-365-data-loss-prevention-on-premises-scanner-preview"></a><span data-ttu-id="bfa41-104">Microsoft 365 데이터 손실 방지 온-프레미스 스캐너 알아보기(미리 보기)</span><span class="sxs-lookup"><span data-stu-id="bfa41-104">Learn about the Microsoft 365 data loss prevention on-premises scanner (preview)</span></span>

<span data-ttu-id="bfa41-105">Microsoft 데이터 손실 방지 온-프레미스 스캐너는 Microsoft 365 서비스에서 중요한 항목을 검색하고 보호하는 데 사용할 수 있는 Microsoft 365 데이터 손실 방지(DLP) 제품군의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="bfa41-105">Microsoft data loss prevention on-premises scanner is part of the Microsoft 365 data loss prevention (DLP) suite of features that you can use to discover and protect sensitive items across Microsoft 365 services.</span></span> <span data-ttu-id="bfa41-106">모든 Microsoft DLP 제공에 대한 자세한 내용은 [데이터 손실 방지에 대해 알아보기](dlp-learn-about-dlp.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bfa41-106">For more information about all of Microsoft’s DLP offerings, see [Learn about data loss prevention](dlp-learn-about-dlp.md).</span></span>

<span data-ttu-id="bfa41-107">**DLP 온-프레미스 스캐너** 는 유출됐을 경우 조직에 위험을 주거나 규정 준수 정책 위반의 위험을 초래하는 중요한 항목을 위해 파일 공유와 SharePoint 문서 라이브러리 및 폴더의 온-프레미스 미사용 데이터를 크롤링합니다.</span><span class="sxs-lookup"><span data-stu-id="bfa41-107">The **DLP on-premises scanner** crawls on-premises data-at-rest in file shares and SharePoint document libraries and folders for sensitive items that, if leaked, would pose a risk to your organization or pose a risk of compliance policy violation.</span></span> <span data-ttu-id="bfa41-108">이를 통해 중요한 항목이 올바르게 사용되고 보호받으며 위험을 초래하는 행동을 방지하는 데 필요한 가시성과 제어 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="bfa41-108">This gives you the visibility and control you need to ensure that sensitive items are used and protected properly, and to help prevent risky behavior that might compromise them.</span></span> <span data-ttu-id="bfa41-109">DLP 온-프레미스 스캐너는 [기본 제공](sensitive-information-type-entity-definitions.md) 또는 [사용자 지정 중요한 정보](create-a-custom-sensitive-information-type.md) 유형, [민감도 레이블](sensitivity-labels.md) 또는 파일 속성을 사용하여 중요한 정보를 감지합니다.</span><span class="sxs-lookup"><span data-stu-id="bfa41-109">The DLP on-premises scanner detects sensitive information by using [built-in](sensitive-information-type-entity-definitions.md) or [custom sensitive information](create-a-custom-sensitive-information-type.md) types, [sensitivity labels](sensitivity-labels.md) or file properties.</span></span> <span data-ttu-id="bfa41-110">사용자가 중요한 항목으로 수행하는 작업에 대한 정보는 [활동 탐색기](data-classification-activity-explorer.md)에서 확인할 수 있으며 해당 항목에 대한 보호 작업은 [DLP 정책](create-test-tune-dlp-policy.md)을 통해 적용시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfa41-110">The information about what users are doing with sensitive items is made visible in [activity explorer](data-classification-activity-explorer.md) and you can enforce protective actions on those items via [DLP policies](create-test-tune-dlp-policy.md).</span></span>

## <a name="the-dlp-on-premises-scanner-relies-on-azure-information-protection-scanner"></a><span data-ttu-id="bfa41-111">DLP 온-프레미스 스캐너는 Azure Information Protection(AIP) 스캐너를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="bfa41-111">The DLP on-premises scanner relies on Azure Information Protection scanner</span></span>

<span data-ttu-id="bfa41-112">DLP 온-프레미스 스캐너는 Azure Information Protection(AIP) 스캐너의 전체 구현을 사용하여 중요한 항목을 모니터링, 레이블 지정 및 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="bfa41-112">The DLP on-premises scanner relies on a full implementation of the Azure Information Protection (AIP) scanner to monitor, label and protect sensitive items.</span></span> <span data-ttu-id="bfa41-113">AIP 스캐너에 익숙하지 않은 경우 익숙해지도록 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="bfa41-113">If you aren't familiar with the AIP scanner, we strongly recommend familiarizing yourself with it.</span></span> <span data-ttu-id="bfa41-114">자세한 내용은 다음 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bfa41-114">See these articles:</span></span>

- [<span data-ttu-id="bfa41-115">Azure Information Protection이란?</span><span class="sxs-lookup"><span data-stu-id="bfa41-115">What is Azure Information Protection</span></span>](/azure/information-protection/what-is-information-protection)
- [<span data-ttu-id="bfa41-116">Azure Information Protection 통합 레이블 지정 스캐너란?</span><span class="sxs-lookup"><span data-stu-id="bfa41-116">What is the Azure Information Protection unified labeling scanner</span></span>](/azure/information-protection/deploy-aip-scanner)
- [<span data-ttu-id="bfa41-117">Azure Information Protection 통합 레이블 지정 스캐너 설치 및 배포를 위한 필수 사항</span><span class="sxs-lookup"><span data-stu-id="bfa41-117">Requirements for installing and deploying the Azure Information Protection unified labeling scanner</span></span>](/azure/information-protection/deploy-aip-scanner-prereqs)
- [<span data-ttu-id="bfa41-118">자습서: Azure Information Protection(AIP) 통합 라벨링 스캐너 설치</span><span class="sxs-lookup"><span data-stu-id="bfa41-118">Tutorial: Installing the Azure Information Protection (AIP) unified labeling scanner</span></span>](/azure/information-protection/tutorial-install-scanner)
- [<span data-ttu-id="bfa41-119">Azure Information Protection 통합 레이블 지정 스캐너 구성 및 설치</span><span class="sxs-lookup"><span data-stu-id="bfa41-119">Configuring and installing the Azure Information Protection unified labeling scanner</span></span>](/azure/information-protection/deploy-aip-scanner-configure-install)
- [<span data-ttu-id="bfa41-120">Azure Information Protection 통합 레이블 지정 클라이언트 - 버전 출시 기록 및 지원 정책</span><span class="sxs-lookup"><span data-stu-id="bfa41-120">Azure Information Protection unified labeling client - Version release history and support policy</span></span>](/azure/information-protection/rms-client/unifiedlabelingclient-version-release-history)

## <a name="dlp-on-premises-scanner-actions"></a><span data-ttu-id="bfa41-121">DLP 온-프레미스 스캐너 작업</span><span class="sxs-lookup"><span data-stu-id="bfa41-121">DLP on-premises scanner actions</span></span>

<span data-ttu-id="bfa41-122">DLP 온-프레미스 스캐너는 다음 네 가지 방법 중 하나를 통해 파일을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="bfa41-122">DLP on-premises scanner detects files by one of these four methods:</span></span>

- <span data-ttu-id="bfa41-123">중요한 정보 유형</span><span class="sxs-lookup"><span data-stu-id="bfa41-123">sensitive information types</span></span>
- <span data-ttu-id="bfa41-124">민감도 레이블</span><span class="sxs-lookup"><span data-stu-id="bfa41-124">sensitivity labels</span></span>
- <span data-ttu-id="bfa41-125">파일 확장명</span><span class="sxs-lookup"><span data-stu-id="bfa41-125">file extension</span></span>
- <span data-ttu-id="bfa41-126">Office 파일만 문서 속성 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="bfa41-126">custom document properties on Office files only</span></span> 

<span data-ttu-id="bfa41-127">검색된 파일이 유출되거나 규정 준수 정책 위반이 발생하여 위험에 처하면, DLP-프레미스 스캐너는 다음 네 가지 작업 중 하나를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfa41-127">When a detected file poses a potential risk if leaked or a compliance policy violation, the DLP on-premises scanner can take one of these four actions.</span></span>

|<span data-ttu-id="bfa41-128">작업</span><span class="sxs-lookup"><span data-stu-id="bfa41-128">Action</span></span> |<span data-ttu-id="bfa41-129">설명</span><span class="sxs-lookup"><span data-stu-id="bfa41-129">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="bfa41-130">**이러한 사용자들이 온-프레미스 스캐너에 저장된 파일에 액세스하지 못하도록 차단합니다 - 모든 사용자**</span><span class="sxs-lookup"><span data-stu-id="bfa41-130">**Block these people from accessing file stored in  on-premises scanner - Everyone**</span></span> | <span data-ttu-id="bfa41-131">이 작업을 적용하면 콘텐츠 소유자, 항목을 수정한 마지막 계정 및 관리자를 제외한 모든 계정의 액세스가 차단됩니다.</span><span class="sxs-lookup"><span data-stu-id="bfa41-131">When enforced, this action blocks access to all accounts except the content owner, the last account that modified the item and the administrator.</span></span> <span data-ttu-id="bfa41-132">이 작업은 파일 소유자, 리포지토리 소유자(콘텐츠 검색 작업 내 [리포지토리 소유자 설정](/azure/information-protection/deploy-aip-scanner-configure-install#use-a-data-loss-prevention-dlp-policy-public-preview)에서 설정됨), 마지막 수정자(SharePoint에서만 식별 가능) 및 관리자를 제외하고 파일 수준에서 NTFS/SharePoint 사용 권한으로부터 모든 계정을 제거합니다. 스캐너 계정에는 파일에 대한 FC 권한이 부여됩니다.</span><span class="sxs-lookup"><span data-stu-id="bfa41-132">It does this by removing all accounts from NTFS/SharePoint permissions at the file level except the file owner, repository owner (set in the [Set repository owner](/azure/information-protection/deploy-aip-scanner-configure-install#use-a-data-loss-prevention-dlp-policy-public-preview) setting in content scan job), last modifier (can be identified in SharePoint only) and admin. The scanner account is also granted FC rights on the file.</span></span>|
|<span data-ttu-id="bfa41-133">**이러한 사용자들이 온-프레미스 스캐너에 저장된 파일에 액세스하지 못하도록 차단합니다 - 조직 전체(공개) 액세스 차단**</span><span class="sxs-lookup"><span data-stu-id="bfa41-133">**Block these people from accessing file stored in  on-premises scanner - block org-wide (public) access**</span></span>    |<span data-ttu-id="bfa41-134">이 작업을 적용하면 **_Everyone_*_, _*_NT AUTHORITY\authenticated users_*_, and _*_Domain Users_** SID를 파일 액세스 제어 목록(ACL)에서 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="bfa41-134">When enforced, this action removes the **_Everyone_*_, _*_NT AUTHORITY\authenticated users_*_, and _*_Domain Users_** SIDs from the file access control list (ACL).</span></span> <span data-ttu-id="bfa41-135">파일 또는 상위 폴더에 명시적으로 권한을 부여받은 사용자 및 그룹만이 파일에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfa41-135">Only users and groups that have been explicitly granted rights to the file or parent folder will be able to access the file.</span></span>|
|<span data-ttu-id="bfa41-136">**파일 사용 권한 설정**</span><span class="sxs-lookup"><span data-stu-id="bfa41-136">**Set permissions on the file**</span></span>|<span data-ttu-id="bfa41-137">이 작업을 적용하면, 파일이 상위 폴더의 사용 권한을 상속하도록 강제 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="bfa41-137">When enforced, this action forces the file to inherit the permissions of its parent folder.</span></span> <span data-ttu-id="bfa41-138">기본적으로 이 작업은 파일에 이미 있는 사용 권한보다 상위 폴더에 대한 사용 권한이 더 제한적인 경우만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="bfa41-138">Be default, this action will only be enforced if the permissions on the parent folder are more restrictive than the permissions that are already on the file.</span></span> <span data-ttu-id="bfa41-139">예를 들어 파일의 ACL이 **_특정 사용자_*만_ 허용하도록 설정되어 있고 _\*_도메인 사용자_\*_ 그룹을 허용하도록 상위 폴더가 구성된 경우, 상위 폴더 사용 권한은 파일에 상속되지 않습니다. _\* 상위 사용 권한이 덜 제한적인 옵션인 경우에도 상속을 선택하여*\* 해당 동작을 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfa41-139">For example, if the ACL on the file is set to only allow **_specific users_*_ and the parent folder is configured to allow _*_Domain Users_*_ group, the parent folder permissions would not be inherited by the file. You can override this behavior by selecting the _\* Inherit even if parent permissions are less restrictive*\* option.</span></span>|
|<span data-ttu-id="bfa41-140">**부적절한 위치에서 파일 제거**</span><span class="sxs-lookup"><span data-stu-id="bfa41-140">**Remove the file from improper location**</span></span>|<span data-ttu-id="bfa41-141">이 작업을 적용하면 원본 파일을 .txt 확장명을 가지고 스텁 파일로 대체하고 원본 파일의 복사본을 격리 폴더에 배치합니다.</span><span class="sxs-lookup"><span data-stu-id="bfa41-141">When enforced, this action replaces the original file with a stub file with .txt extension and places a copy of the original file in a quarantine folder.</span></span> 

## <a name="whats-different-in-the-on-premises-scanner"></a><span data-ttu-id="bfa41-142">온-프레미스 스캐너의 특별한 점은?</span><span class="sxs-lookup"><span data-stu-id="bfa41-142">What's different in the on-premises scanner</span></span>

<span data-ttu-id="bfa41-143">온-프레미스 스캐너를 살펴보기 전에 알아야 할 몇 가지 추가 개념이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfa41-143">There are a few extra concepts that you need to be aware of before you dig into the on-premises scanner.</span></span>

### <a name="aip-repositories-and-content-scan-jobs"></a><span data-ttu-id="bfa41-144">AIP 리포지토리 및 콘텐츠 스캔 작업</span><span class="sxs-lookup"><span data-stu-id="bfa41-144">AIP repositories and content scan jobs</span></span>

<span data-ttu-id="bfa41-145">AIP 콘텐츠 스캔 작업을 만들고 DLP 엔진으로 평가받고 싶은 파일을 호스트하는 리포지토리를 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfa41-145">You must create an AIP content scan jobs and identify the repositories that host the files that you want to be evaluated by DLP engine.</span></span> <span data-ttu-id="bfa41-146">만든 AIP 콘텐츠 스캔 작업에서 DLP 규칙을 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfa41-146">Make sure you enable DLP rules in the created AIP content scan job.</span></span>

### <a name="policy-tips"></a><span data-ttu-id="bfa41-147">정책 팁</span><span class="sxs-lookup"><span data-stu-id="bfa41-147">Policy tips</span></span>

<span data-ttu-id="bfa41-148">온-프레미스 스캐너에서는 [정책 팁](use-notifications-and-policy-tips.md)을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bfa41-148">[Policy tips](use-notifications-and-policy-tips.md) are not available in on-premises scanner.</span></span>


### <a name="viewing-dlp-on-premises-scanner-events"></a><span data-ttu-id="bfa41-149">DLP 온-프레미스 스캐너 이벤트 보기</span><span class="sxs-lookup"><span data-stu-id="bfa41-149">Viewing DLP on-premises scanner events</span></span>

<span data-ttu-id="bfa41-150">M365 규정 준수 센터의 [활동 탐색기](data-classification-activity-explorer.md)에서 DLP 온-프레미스 스캐너 데이터를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfa41-150">You view DLP on-premises scanner data in the M365 Compliance Center [activity explorer](data-classification-activity-explorer.md).</span></span> 

## <a name="next-steps"></a><span data-ttu-id="bfa41-151">다음 단계</span><span class="sxs-lookup"><span data-stu-id="bfa41-151">Next steps</span></span>

<span data-ttu-id="bfa41-152">이제 DLP 온-프레미스 스캐너에 대해 살펴보았으므로 다음 단계로 넘어갑니다.</span><span class="sxs-lookup"><span data-stu-id="bfa41-152">Now that you've learned about DLP on-premises scanner, your next steps are:</span></span>

1. [<span data-ttu-id="bfa41-153">DLP 온-프레미스 스캐너 시작하기</span><span class="sxs-lookup"><span data-stu-id="bfa41-153">Get started with the DLP on-premises scanner</span></span>](dlp-on-premises-scanner-get-started.md)
2. [<span data-ttu-id="bfa41-154">DLP 온-프레미스 스캐너 사용하기</span><span class="sxs-lookup"><span data-stu-id="bfa41-154">Use the DLP on-premises scanner</span></span>](dlp-on-premises-scanner-use.md)

## <a name="see-also"></a><span data-ttu-id="bfa41-155">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bfa41-155">See also</span></span>

- [<span data-ttu-id="bfa41-156">Microsoft 데이터 손실 방지 온-프레미스 스캐너로 시작하기</span><span class="sxs-lookup"><span data-stu-id="bfa41-156">Getting started with the Microsoft data loss prevention on-premises scanner</span></span>](dlp-on-premises-scanner-get-started.md)
- [<span data-ttu-id="bfa41-157">Microsoft 데이터 손실 방지 온-프레미스 스캐너 사용하기</span><span class="sxs-lookup"><span data-stu-id="bfa41-157">Use the Microsoft data loss prevention on-premises scanner</span></span>](dlp-on-premises-scanner-use.md)
- [<span data-ttu-id="bfa41-158">데이터 손실 방지에 대해 알아보기</span><span class="sxs-lookup"><span data-stu-id="bfa41-158">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)
- [<span data-ttu-id="bfa41-159">DLP 정책 만들기, 테스트 및 조정</span><span class="sxs-lookup"><span data-stu-id="bfa41-159">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="bfa41-160">활동 탐색기 시작하기</span><span class="sxs-lookup"><span data-stu-id="bfa41-160">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)