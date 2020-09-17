---
title: 데이터 개인 정보 규정의 영향을 받는 정보 제어
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 06/09/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- m365solution-infoprotection
ms.custom: ''
description: Microsoft 365 보존 레이블 및 정책을 사용 하 여 Microsoft 365 환경에서 개인 데이터를 관리 합니다.
ms.openlocfilehash: 766995b9c758d4ae8cbf7140fb259d208cfb7771
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/17/2020
ms.locfileid: "47949255"
---
# <a name="govern-information-subject-to-data-privacy-regulation"></a><span data-ttu-id="ad918-103">데이터 개인 정보 규정의 영향을 받는 정보 제어</span><span class="sxs-lookup"><span data-stu-id="ad918-103">Govern information subject to data privacy regulation</span></span>

<span data-ttu-id="ad918-104">정보 거 버 넌 스에서 일반 데이터 보호 규정 (GDPR), HIPAA-HITECH (미국 의료 보험 개인 정보 취급 방침), 캘리포니아 주 보호 Act (CCPA) 및 LGPD (브라질 Data Protection Act)와 관련 된 번호를 포함 하 여 데이터 개인 정보 규정 준수 요구 사항을 해결 하는 데 도움이 되도록 사용자 환경에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad918-104">Information governance controls can be employed in your environment to help address data privacy compliance needs, including a number that are specific to General Data Protection Regulation (GDPR), HIPAA-HITECH (the United States health care privacy act), California Consumer Protection Act (CCPA), and the Brazil Data Protection Act (LGPD).</span></span> 

<span data-ttu-id="ad918-105">이러한 컨트롤은 주로 다음 솔루션 영역에 속합니다.</span><span class="sxs-lookup"><span data-stu-id="ad918-105">These controls primarily fall into the following solution areas:</span></span>

- <span data-ttu-id="ad918-106">보존 정책</span><span class="sxs-lookup"><span data-stu-id="ad918-106">Retention policies</span></span>
- <span data-ttu-id="ad918-107">보존 레이블</span><span class="sxs-lookup"><span data-stu-id="ad918-107">Retention labels</span></span>
- <span data-ttu-id="ad918-108">레코드 관리</span><span class="sxs-lookup"><span data-stu-id="ad918-108">Records management</span></span>

## <a name="data-privacy-regulations-impacting-information-governance-controls"></a><span data-ttu-id="ad918-109">정보 거 버 넌 스 제어에 영향을 주는 데이터 개인 정보 규정</span><span class="sxs-lookup"><span data-stu-id="ad918-109">Data privacy regulations impacting information governance controls</span></span>

<span data-ttu-id="ad918-110">다음은 정보 거 버 넌 스 컨트롤과 관련이 있을 수 있는 데이터 개인 정보 규정의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="ad918-110">Here is a sample listing of data privacy regulations that may relate to information governance controls:</span></span>

- <span data-ttu-id="ad918-111">GDPR 문서 (13) (a)</span><span class="sxs-lookup"><span data-stu-id="ad918-111">GDPR Article (13)(2)(a)</span></span>
- <span data-ttu-id="ad918-112">GDPR 문서 (5) (1) (f)</span><span class="sxs-lookup"><span data-stu-id="ad918-112">GDPR Article (5)(1)(f)</span></span>
- <span data-ttu-id="ad918-113">HIPAA-HITECH (45 CFR 164.312 (2))</span><span class="sxs-lookup"><span data-stu-id="ad918-113">HIPAA-HITECH (45 CFR 164.312(c)(2))</span></span>
- <span data-ttu-id="ad918-114">HIPAA-HITECH (45 CFR 164.316 (b) (1) (i))</span><span class="sxs-lookup"><span data-stu-id="ad918-114">HIPAA-HITECH (45 CFR 164.316(b)(1)(i))</span></span>
- <span data-ttu-id="ad918-115">HIPAA-HITECH (45 CFR 164.316 (b) (1) (ii))</span><span class="sxs-lookup"><span data-stu-id="ad918-115">HIPAA-HITECH (45 CFR 164.316(b)(1)(ii))</span></span>
- <span data-ttu-id="ad918-116">LGPD 문서 46</span><span class="sxs-lookup"><span data-stu-id="ad918-116">LGPD Article 46</span></span>

<span data-ttu-id="ad918-117">이러한 규정에 대 한 자세한 내용은 [데이터 개인 정보 보호 위험 평가 및 중요 한 정보 식별 문서](information-protection-deploy-assess.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ad918-117">For more information on these regulations, see the [assess data privacy risks and identify sensitive information article](information-protection-deploy-assess.md).</span></span>

<span data-ttu-id="ad918-118">정보 관리를 위해 일반적으로 데이터 개인 정보 규정은 다음을 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad918-118">For information governance, data privacy regulations typically call for the following:</span></span>

- <span data-ttu-id="ad918-119">Microsoft 365에 저장 된 개인 데이터에 대 한 보존 및 삭제를 위한 기술 체계를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad918-119">You should employ a technical scheme for retention and deletion for personal data stored in Microsoft 365.</span></span>
- <span data-ttu-id="ad918-120">개인 데이터를 저장 하려는 경우에는 프런트 엔드 웹 시스템에서의 표준 관행 인 데이터가 저장 되는 기간을 알려 주어 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad918-120">If you're going to store personal data, inform the subject of how long the data will be stored, which is a standard practice now on front-end web systems.</span></span>
- <span data-ttu-id="ad918-121">개인 데이터는 안정형 메서드를 사용 하 여 실수로 처리, 손실 또는 변경 으로부터 보호 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad918-121">Personal data should be protected against accidental processing, loss, or alteration using verifiable methods.</span></span>
- <span data-ttu-id="ad918-122">개인 데이터에 대해 실행 되는 모든 작업을 문서화 하 고 지정 된 기간 동안 문서를 보존 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad918-122">Any action executed against personal data should be documented and that documentation should be retained for a specified period.</span></span>

<span data-ttu-id="ad918-123">데이터 개인 정보 규정은 데이터 보존 및 삭제와 관련 하 여 특정 하지 않으므로 Microsoft 365 구독에 저장 된 개인 정보에 대 한 정보 거 버 넌 스 지침을 지시할 수 있는 다른 요인을 고려해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad918-123">Because the data privacy regulations are not very specific when it comes to data retention and deletion, other factors need to be taken into consideration that may dictate information governance guidelines for personal information stored in your Microsoft 365 subscription.</span></span> <span data-ttu-id="ad918-124">몇 가지 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ad918-124">Here are a few examples:</span></span>

- <span data-ttu-id="ad918-125">5 년 동안 사용 하지 않으면 소비자 계정을 에이징 아웃 하 고, 해당 시점 이후 계정 데이터를 삭제 하거나 익명화 시스템 간에 오케스트레이션을 필요한 경우에는 알림 및 기타 자동화와 관련 된 데이터와 워크플로를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad918-125">Aging out consumer accounts after 5 years of inactivity and requires deletion or anonymization of account data after that point, requiring orchestration between the system storing the data and workflows related to notifications and other automation.</span></span>
- <span data-ttu-id="ad918-126">정책 및 절차에 대 한 조직의 보존 일정에 맞게 대체 된 3 년 동안 GDPR과 관련 된 정책 및 절차를 유지 하기 위한 규칙을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad918-126">Configuring rules for keeping policies and procedures related to GDPR around for three years after they've been superseded, which aligns with the organization's retention schedule for policies and procedures.</span></span>
- <span data-ttu-id="ad918-127">지원 조직을 통해 소비자와 통신 하기 위한 별도의 구독 유지 관리</span><span class="sxs-lookup"><span data-stu-id="ad918-127">Maintaining a separate subscription for communicating with consumers through its support organization.</span></span> <span data-ttu-id="ad918-128">모든 전자 메일 통신은 시스템의 개인 정보 부채 변환 하려면 buildup를 줄이기 위해 2 주 후에 유지 및 삭제 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ad918-128">All email communications were retained and deleted after two weeks to reduce any privacy debt buildup in the system.</span></span>

<span data-ttu-id="ad918-129">대답이 다음과 같은 주요 질문입니다.</span><span class="sxs-lookup"><span data-stu-id="ad918-129">A key question to answer is:</span></span> 

- <span data-ttu-id="ad918-130">개인 데이터를 포함 하는 정보를 보관 하는 데 걸리는 시간이 유효한 비즈니스 이유로 "영구적으로 유지" 되지 않도록 해야 하는 경우</span><span class="sxs-lookup"><span data-stu-id="ad918-130">How long does information containing personal data need to be kept around for valid business reasons to avoid "keep it forever" practices?</span></span> <span data-ttu-id="ad918-131">이는 비즈니스 연속성에 대 한 보존 요구와 균형을 유지 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad918-131">This must be balanced with retention needs for business continuity.</span></span>

<span data-ttu-id="ad918-132">Microsoft는 개인 정보를 유지 하거나 삭제 하는 법적 및 비즈니스 이유에 관계 없이 Microsoft 365에서 데이터 거 버 넌 스 체계를 구현 하기 위한 다양 한 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad918-132">Regardless of the legal and business reasons for keeping personal information around or deleting it, Microsoft provides a number of capabilities to implement your data governance scheme in Microsoft 365.</span></span>

## <a name="managing-information-governance-in-microsoft-365"></a><span data-ttu-id="ad918-133">Microsoft 365에서 정보 거 버 넌 스 관리</span><span class="sxs-lookup"><span data-stu-id="ad918-133">Managing information governance in Microsoft 365</span></span>

<span data-ttu-id="ad918-134">시작 하려면 Microsoft 365에서 [정보 거 버 넌 스](../compliance/manage-information-governance.md) 및 [데이터 보존, 삭제 및 소멸](https://docs.microsoft.com/office365/Enterprise/office-365-data-retention-deletion-and-destruction-overview)관리를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ad918-134">To begin, see [Manage information governance](../compliance/manage-information-governance.md) and [Data Retention, Deletion and Destruction in Microsoft 365](https://docs.microsoft.com/office365/Enterprise/office-365-data-retention-deletion-and-destruction-overview).</span></span>

### <a name="develop-data-retention-schedules-for-containers-email-and-content"></a><span data-ttu-id="ad918-135">컨테이너, 전자 메일 및 콘텐츠에 대 한 데이터 보존 일정 개발</span><span class="sxs-lookup"><span data-stu-id="ad918-135">Develop data retention schedules for containers, email, and content</span></span>

<span data-ttu-id="ad918-136">다음 사항에 유의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad918-136">Keep the following in mind:</span></span>

- <span data-ttu-id="ad918-137">정의 된 정보 유형에 대 한 데이터 보존 일정을 설정 하는 것은 보존 또는 삭제 체계를 구현 하기 위한 필수 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="ad918-137">Establishing a data retention schedule for defined information types should be considered a prerequisite to implementing any retention or deletion scheme.</span></span>

- <span data-ttu-id="ad918-138">대부분의 조직에서 중요 하 게 고려 하 고 해당 하는 대규모 레코드 보존 일정과 함께 이동 하는 정보 유형 수가 제공 되 면 데이터 보존 및 레코드 관리 전략을 구현 하려면 계획이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad918-138">Given the number of information types that most organizations consider important and the corresponding large records retention schedules that go along with them, implementing a data retention and records management strategy requires planning.</span></span> 

- <span data-ttu-id="ad918-139">이 유형의 효과적인 데이터 거 버 넌 스 전략을 설정 하는 것은 보다 높은 우선 순위 비즈니스 기능과 공식적인 관리를 요구 하는 정보 유형을 중점적으로 설명 하기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ad918-139">The key to establishing an effective data governance strategy of this type is to focus on the highest priority business functions and information types that require more formal management.</span></span> <span data-ttu-id="ad918-140">법적 계약, 금융 명세서 및 규정 준수 설명서를 예로 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad918-140">Examples are legal contracts, financial statements, and regulatory compliance documentation.</span></span> <span data-ttu-id="ad918-141">모든 단일 정보 유형에 별도의 보존 일정을 사용 하지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad918-141">Try to avoid having a separate retention schedule for every single information type.</span></span> <span data-ttu-id="ad918-142">일반 비즈니스 콘텐츠에 대 한 7 년간의 보존 일정을 사용 하는 등의 방법으로 일반 범주를 가능한 한 많이 활용 하십시오.</span><span class="sxs-lookup"><span data-stu-id="ad918-142">Try to utilize general categories as much as possible, for example, with retention schedules of 7 years for general business content.</span></span>

- <span data-ttu-id="ad918-143">환경의 개인 정보 유형을 더 잘 알고 있으면 이러한 유형의 콘텐츠에 대 한 보존 및 삭제 일정을 설정 하 고 정보 아키텍처를 조정 하 여 이러한 유형의 정보를 보다 쉽게 관리할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad918-143">Once the personal information types in your environment are better known, establish retention and deletion schedules for this type of content and adjust your information architecture to make governance of this sort of information easier.</span></span> <span data-ttu-id="ad918-144">예를 들어 개인 정보를 제어 된 액세스 권한이 있는 별도의 사이트, 라이브러리 또는 폴더에 격리 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad918-144">For example, isolate personal information in separate sites, libraries, or folders with controlled access.</span></span>

### <a name="retention-policies-and-retention-labels"></a><span data-ttu-id="ad918-145">보존 정책 및 보존 레이블</span><span class="sxs-lookup"><span data-stu-id="ad918-145">Retention policies and retention labels</span></span>

<span data-ttu-id="ad918-146">[보존 정책 및 보존 레이블을](../compliance/retention.md) 사용 하 여 개인 데이터가 포함 되거나 포함 될 것으로 예상 되는 Microsoft 365의 콘텐츠를 보존 하거나 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad918-146">Use [retention policies and retention labels](../compliance/retention.md) to retain or delete content in Microsoft 365 that contains or is expected to contain personal data.</span></span>

### <a name="records-management"></a><span data-ttu-id="ad918-147">레코드 관리</span><span class="sxs-lookup"><span data-stu-id="ad918-147">Records management</span></span>

<span data-ttu-id="ad918-148">Microsoft 365의 데이터에 대 한 [레코드 관리 솔루션](../compliance/records-management.md) 을 구현 하기 위해 콘텐츠 a 레코드를 선언 하는 보존 레이블을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad918-148">Use retention labels that declare content a record to implement a [records management solution](../compliance/records-management.md) for data in Microsoft 365.</span></span>

<span data-ttu-id="ad918-149">데이터 개인 정보 보호를 위해 법률 부서에서 수신 된 dsr (데이터 주체 요청)은 레코드로 선언 되며, 해당 활동 보존 사양을 준수 하기 위해 증거에 무기한으로 저장 하거나 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad918-149">For data privacy, data subject requests (DSRs) received by the legal department are declared a record and can be stored indefinitely or disposed of with proof, to adhere to regulatory activity retention specifications.</span></span>

