---
title: Microsoft 365 데이터 손실 방지 온-프레미스 스캐너 사용(미리 보기)
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
description: Microsoft 365 데이터 손실 방지 온-프레미스 스캐너 사용 방법을 배워서 미사용 데이터를 스캔하고 온-프레미스 파일 공유와 온-프레미스 SharePoint 폴더와 문서 라이브러리에 대한 보호 조치를 시행하세요.
ms.openlocfilehash: e81b48560a8011e955e6508daf27e96f9fdb70fa
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538090"
---
# <a name="use-the-microsoft-365-data-loss-prevention-on-premises-scanner-preview"></a><span data-ttu-id="a2927-103">Microsoft 365 데이터 손실 방지 온-프레미스 스캐너 사용(미리 보기)</span><span class="sxs-lookup"><span data-stu-id="a2927-103">Use the Microsoft 365 data loss prevention on-premises scanner (preview)</span></span>

<span data-ttu-id="a2927-104">DLP 온-프레미스 기능과 해당 기능이 DLP 정책에 나오는 방법에 대한 자세한 내용은 다음 몇 가지 시나리오를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a2927-104">To help familiarize you with DLP on-premises features and how they surface in DLP policies, we've put together some scenarios for you to follow.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a2927-105">이 DLP 온-프레미스 시나리오는 DLP 정책을 만들고 조정하는 공식 절차가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="a2927-105">These DLP on-premises scenarios are not the official procedures for creating and tuning DLP policies.</span></span> <span data-ttu-id="a2927-106">일반적으로 DLP 정책을 사용해야 하는 경우 다음 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a2927-106">Refer to the below topics when you need to work with DLP policies in general situations:</span></span>
>- [<span data-ttu-id="a2927-107">데이터 손실 방지에 대해 알아보기</span><span class="sxs-lookup"><span data-stu-id="a2927-107">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)
>- [<span data-ttu-id="a2927-108">기본 DLP 정책을 사용하여 시작</span><span class="sxs-lookup"><span data-stu-id="a2927-108">Get started with the default DLP policy</span></span>](get-started-with-the-default-dlp-policy.md)
>- [<span data-ttu-id="a2927-109">템플릿에서 DLP 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="a2927-109">Create a DLP policy from a template</span></span>](create-a-dlp-policy-from-a-template.md)
>- [<span data-ttu-id="a2927-110">DLP 정책 만들기, 테스트 및 조정</span><span class="sxs-lookup"><span data-stu-id="a2927-110">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)

### <a name="scenario-discover-files-matching-dlp-rules"></a><span data-ttu-id="a2927-111">시나리오: DLP 규칙에 일치하는 파일 발견</span><span class="sxs-lookup"><span data-stu-id="a2927-111">Scenario: Discover files matching DLP rules</span></span>

<span data-ttu-id="a2927-112">DLP 온-프레미스 스캐너의 데이터는 다양한 영역에서 나타납니다</span><span class="sxs-lookup"><span data-stu-id="a2927-112">Data from DLP on-premises scanner surfaces in several areas</span></span>

#### <a name="activity-explorer"></a><span data-ttu-id="a2927-113">활동 탐색기</span><span class="sxs-lookup"><span data-stu-id="a2927-113">Activity explorer</span></span>

 <span data-ttu-id="a2927-114">온-프레미스용 Microsoft DLP는 DLP 규칙 일치 항목을 감지하고 이를 [활동 탐색기](https://compliance.microsoft.com/dataclassification?viewid=activitiesexplorer)에 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="a2927-114">Microsoft DLP for on-premises detects DLP rule matches and reports them to [Activity Explorer](https://compliance.microsoft.com/dataclassification?viewid=activitiesexplorer).</span></span> 
 
#### <a name="microsoft-365-audit-log"></a><span data-ttu-id="a2927-115">Microsoft 365 감사 로그</span><span class="sxs-lookup"><span data-stu-id="a2927-115">Microsoft 365 Audit log</span></span>

<span data-ttu-id="a2927-116">공개 미리 보기 동안 DLP 규칙 일치 항목은 감사 로그 UI에서 확인할 수 있으며, [규정 준수 센터에서 감사 로그 검색](search-the-audit-log-in-security-and-compliance.md)에서 보거나 [Search-UnifiedAuditLog](/powershell/module/exchange/search-unifiedauditlog?view=exchange-ps) PowerShell으로 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2927-116">During the public preview the DLP rule matches are available in Audit log UI, see [Search the audit log in the compliance center](search-the-audit-log-in-security-and-compliance.md)  or accessible by [Search-UnifiedAuditLog](/powershell/module/exchange/search-unifiedauditlog?view=exchange-ps) PowerShell.</span></span>

#### <a name="aip"></a><span data-ttu-id="a2927-117">AIP</span><span class="sxs-lookup"><span data-stu-id="a2927-117">AIP</span></span>

<span data-ttu-id="a2927-118">검색 데이터는 csv 형식의 로컬 보고서에서 확인할 수 있으며, 저장 위치는</span><span class="sxs-lookup"><span data-stu-id="a2927-118">Discovery data is available in a local report in csv format which is stored under:</span></span>

<span data-ttu-id="a2927-119">**%localappdata%\Microsoft\MSIP\Scanner\Reports\DetailedReport_%timestamp%.csv report** 입니다.</span><span class="sxs-lookup"><span data-stu-id="a2927-119">**%localappdata%\Microsoft\MSIP\Scanner\Reports\DetailedReport_%timestamp%.csv report**.</span></span>

 <span data-ttu-id="a2927-120">다음 열 레이블을 찾으세요.</span><span class="sxs-lookup"><span data-stu-id="a2927-120">Look for the following columns:</span></span>
- <span data-ttu-id="a2927-121">DLP 모드</span><span class="sxs-lookup"><span data-stu-id="a2927-121">DLP Mode</span></span>
- <span data-ttu-id="a2927-122">DLP 상태</span><span class="sxs-lookup"><span data-stu-id="a2927-122">DLP Status</span></span>
- <span data-ttu-id="a2927-123">DLP 메모</span><span class="sxs-lookup"><span data-stu-id="a2927-123">DLP Comment</span></span>
- <span data-ttu-id="a2927-124">DLP 규칙 이름 DLP 작업</span><span class="sxs-lookup"><span data-stu-id="a2927-124">DLP Rule Name DLP Actions</span></span>
- <span data-ttu-id="a2927-125">소유자</span><span class="sxs-lookup"><span data-stu-id="a2927-125">Owner</span></span>
- <span data-ttu-id="a2927-126">현재 NTFS 사용 권한(SDDL)</span><span class="sxs-lookup"><span data-stu-id="a2927-126">Current NTFS Permissions (SDDL)</span></span>
- <span data-ttu-id="a2927-127">적용된 NTFS 사용 권한(SDDL)</span><span class="sxs-lookup"><span data-stu-id="a2927-127">Applied NTFS Permissions (SDDL)</span></span>
- <span data-ttu-id="a2927-128">NTFS 사용 권한 유형</span><span class="sxs-lookup"><span data-stu-id="a2927-128">NTFS permissions type</span></span>
 
### <a name="scenario-enforce-dlp-rule"></a><span data-ttu-id="a2927-129">시나리오: DLP 규칙 적용</span><span class="sxs-lookup"><span data-stu-id="a2927-129">Scenario: Enforce DLP rule</span></span> 

<span data-ttu-id="a2927-130">DLP 규칙을 스캔된 파일에 적용하려면, 적용이 DLP의 AIP와 정책 수준에서의 콘텐츠 스캔 작업이 둘 다 활성화되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2927-130">If you want to enforce DLP rules on the scanned files, enforcement must be enabled on both the content scan job in AIP and at the policy level in DLP.</span></span>


#### <a name="configure-dlp-to-enforce-policy-actions"></a><span data-ttu-id="a2927-131">정책 작업을 적용하기 위한 DLP 구성</span><span class="sxs-lookup"><span data-stu-id="a2927-131">Configure DLP to enforce policy actions</span></span>

1. <span data-ttu-id="a2927-132">[데이터 손실 방지 페이지](https://compliance.microsoft.com/datalossprevention?viewid=policies)를 열고 AIP에서 사용자가 구성한 온-프레미스 위치 리포지토리를 대상으로 하는 DLP 정책을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a2927-132">Open the [Data loss prevention page](https://compliance.microsoft.com/datalossprevention?viewid=policies) and select the DLP policy that is targeted to the on-premises location repositories you have configured in AIP.</span></span> 
2. <span data-ttu-id="a2927-133">정책을 편집합니다.</span><span class="sxs-lookup"><span data-stu-id="a2927-133">Edit the policy.</span></span>
3. <span data-ttu-id="a2927-134">**정책 테스트 또는 켜기** 페이지에서 **지금 정책 켜기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a2927-134">On the **Test or turn on the policy** page, select **Yes, turn it on right away**.</span></span> 

## <a name="see-also"></a><span data-ttu-id="a2927-135">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a2927-135">See also</span></span>

- [<span data-ttu-id="a2927-136">DLP 온-프레미스 스캐너에 대한 자세한 정보(미리 보기)</span><span class="sxs-lookup"><span data-stu-id="a2927-136">Learn about DLP on-premises scanner (preview)</span></span>](dlp-on-premises-scanner-learn.md)
- [<span data-ttu-id="a2927-137">DLP 온-프레미스 스캐너 시작하기(미리 보기)</span><span class="sxs-lookup"><span data-stu-id="a2927-137">Get started with  DLP on-premises scanner (preview)</span></span>](dlp-on-premises-scanner-get-started.md)
- [<span data-ttu-id="a2927-138">데이터 손실 방지에 대해 알아보기</span><span class="sxs-lookup"><span data-stu-id="a2927-138">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)
- [<span data-ttu-id="a2927-139">DLP 정책 만들기, 테스트 및 조정</span><span class="sxs-lookup"><span data-stu-id="a2927-139">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="a2927-140">활동 탐색기 시작하기</span><span class="sxs-lookup"><span data-stu-id="a2927-140">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)