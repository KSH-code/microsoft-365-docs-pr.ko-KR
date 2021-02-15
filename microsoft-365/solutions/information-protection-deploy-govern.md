---
title: 데이터 개인 정보 규정이 적용된 정보 관리
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
- m365solution-scenario
ms.custom: ''
description: Microsoft 365 보존 레이블 및 정책을 사용하여 Microsoft 365 환경에서 개인 데이터를 관리합니다.
ms.openlocfilehash: c2a933e556213ae4b78db9dc5f903885df969b27
ms.sourcegitcommit: 9841058fcc95f7c2fed6af92bc3c3686944829b6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/07/2020
ms.locfileid: "48377048"
---
# <a name="govern-information-subject-to-data-privacy-regulation"></a><span data-ttu-id="7141e-103">데이터 개인 정보 규정이 적용된 정보 관리</span><span class="sxs-lookup"><span data-stu-id="7141e-103">Govern information subject to data privacy regulation</span></span>

<span data-ttu-id="7141e-104">GDPR(일반 데이터 보호 규정), HIPAA-HITECH(미국 의료 개인 정보 보호법), 캘리포니아 소비자 보호법(CCPA) 및 브라질 데이터 보호법(LGPD)과 같은 데이터 개인 정보 보호 규정 준수 요구 사항을 해결하기 위해 사용자 환경에 정보 거버넌스 컨트롤을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7141e-104">Information governance controls can be employed in your environment to help address data privacy compliance needs, including a number that are specific to General Data Protection Regulation (GDPR), HIPAA-HITECH (the United States health care privacy act), California Consumer Protection Act (CCPA), and the Brazil Data Protection Act (LGPD).</span></span> 

<span data-ttu-id="7141e-105">이러한 컨트롤은 주로 다음 솔루션 영역에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="7141e-105">These controls primarily fall into the following solution areas:</span></span>

- <span data-ttu-id="7141e-106">보존 정책</span><span class="sxs-lookup"><span data-stu-id="7141e-106">Retention policies</span></span>
- <span data-ttu-id="7141e-107">보존 레이블</span><span class="sxs-lookup"><span data-stu-id="7141e-107">Retention labels</span></span>
- <span data-ttu-id="7141e-108">레코드 관리</span><span class="sxs-lookup"><span data-stu-id="7141e-108">Records management</span></span>

## <a name="data-privacy-regulations-impacting-information-governance-controls"></a><span data-ttu-id="7141e-109">정보 거버넌스 제어에 영향을 미치는 데이터 개인 정보 보호 규정</span><span class="sxs-lookup"><span data-stu-id="7141e-109">Data privacy regulations impacting information governance controls</span></span>

<span data-ttu-id="7141e-110">다음은 정보 거버넌스 제어와 관련이 있을 수 있는 데이터 개인 정보 규정의 샘플 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="7141e-110">Here is a sample listing of data privacy regulations that may relate to information governance controls:</span></span>

- <span data-ttu-id="7141e-111">GDPR 문서(13)(2)(a)</span><span class="sxs-lookup"><span data-stu-id="7141e-111">GDPR Article (13)(2)(a)</span></span>
- <span data-ttu-id="7141e-112">GDPR 문서(5)(1)(f)</span><span class="sxs-lookup"><span data-stu-id="7141e-112">GDPR Article (5)(1)(f)</span></span>
- <span data-ttu-id="7141e-113">HIPAA-HITECH(45 CFR 164.312(c)(2))</span><span class="sxs-lookup"><span data-stu-id="7141e-113">HIPAA-HITECH (45 CFR 164.312(c)(2))</span></span>
- <span data-ttu-id="7141e-114">HIPAA-HITECH (45 CFR 164.316(b)(1)(i))</span><span class="sxs-lookup"><span data-stu-id="7141e-114">HIPAA-HITECH (45 CFR 164.316(b)(1)(i))</span></span>
- <span data-ttu-id="7141e-115">HIPAA-HITECH(45 CFR 164.316(b)(1)(ii))</span><span class="sxs-lookup"><span data-stu-id="7141e-115">HIPAA-HITECH (45 CFR 164.316(b)(1)(ii))</span></span>
- <span data-ttu-id="7141e-116">LGPD 문서 46</span><span class="sxs-lookup"><span data-stu-id="7141e-116">LGPD Article 46</span></span>

<span data-ttu-id="7141e-117">이러한 규정에 대한 자세한 내용은 데이터 개인 정보 보호 위험 평가를 참조하고 [중요한 정보 문서를 식별합니다.](information-protection-deploy-assess.md)</span><span class="sxs-lookup"><span data-stu-id="7141e-117">For more information on these regulations, see the [assess data privacy risks and identify sensitive information article](information-protection-deploy-assess.md).</span></span>

<span data-ttu-id="7141e-118">정보 거버넌스에서 데이터 개인 정보 규정은 일반적으로 다음을 요구합니다.</span><span class="sxs-lookup"><span data-stu-id="7141e-118">For information governance, data privacy regulations typically call for the following:</span></span>

- <span data-ttu-id="7141e-119">Microsoft 365에 저장된 개인 데이터의 보존 및 삭제를 위한 기술 체계를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7141e-119">You should employ a technical scheme for retention and deletion for personal data stored in Microsoft 365.</span></span>
- <span data-ttu-id="7141e-120">개인 데이터를 저장하는 경우 데이터 저장 기간(현재 프런트 엔드 웹 시스템에서 표준 사례)을 주제에 알릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7141e-120">If you're going to store personal data, inform the subject of how long the data will be stored, which is a standard practice now on front-end web systems.</span></span>
- <span data-ttu-id="7141e-121">확인 가능한 방법을 사용하여 실수로 처리, 손실 또는 변경되지 않도록 개인 데이터를 보호해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7141e-121">Personal data should be protected against accidental processing, loss, or alteration using verifiable methods.</span></span>
- <span data-ttu-id="7141e-122">개인 데이터에 대해 실행되는 모든 작업은 문서화되고 해당 문서는 지정된 기간 동안 보존해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7141e-122">Any action executed against personal data should be documented and that documentation should be retained for a specified period.</span></span>

<span data-ttu-id="7141e-123">데이터 개인 정보 규정은 데이터 보존 및 삭제와 관련되어 매우 구체적인 것이 아니기 때문에 Microsoft 365 구독에 저장된 개인 정보에 대한 정보 거버넌스 지침을 규정할 수 있는 다른 요인을 고려해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7141e-123">Because the data privacy regulations are not very specific when it comes to data retention and deletion, other factors need to be taken into consideration that may dictate information governance guidelines for personal information stored in your Microsoft 365 subscription.</span></span> <span data-ttu-id="7141e-124">다음은 몇 가지 예입니다.</span><span class="sxs-lookup"><span data-stu-id="7141e-124">Here are a few examples:</span></span>

- <span data-ttu-id="7141e-125">5년 동안 비활성한 후 소비자 계정이 사용되지 않고, 해당 시점 이후에 계정 데이터를 삭제 또는 비유해야 하여 알림 및 기타 자동화와 관련된 데이터와 워크플로를 저장하는 시스템 간의 오케스트레이션이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="7141e-125">Aging out consumer accounts after 5 years of inactivity and requires deletion or anonymization of account data after that point, requiring orchestration between the system storing the data and workflows related to notifications and other automation.</span></span>
- <span data-ttu-id="7141e-126">GDPR과 관련된 정책 및 절차를 3년 동안 유지하도록 규칙을 구성하여 정책 및 절차에 대한 조직의 보존 일정에 부합합니다.</span><span class="sxs-lookup"><span data-stu-id="7141e-126">Configuring rules for keeping policies and procedures related to GDPR around for three years after they've been superseded, which aligns with the organization's retention schedule for policies and procedures.</span></span>
- <span data-ttu-id="7141e-127">지원 조직을 통해 소비자와 통신하기 위한 별도의 구독 유지 관리</span><span class="sxs-lookup"><span data-stu-id="7141e-127">Maintaining a separate subscription for communicating with consumers through its support organization.</span></span> <span data-ttu-id="7141e-128">모든 전자 메일 통신은 시스템의 개인 정보 부채 빌드를 줄이기 위해 2주 후에 보존 및 삭제되었습니다.</span><span class="sxs-lookup"><span data-stu-id="7141e-128">All email communications were retained and deleted after two weeks to reduce any privacy debt buildup in the system.</span></span>

<span data-ttu-id="7141e-129">답변할 주요 질문은 다음입니다.</span><span class="sxs-lookup"><span data-stu-id="7141e-129">A key question to answer is:</span></span> 

- <span data-ttu-id="7141e-130">개인 데이터를 포함하는 정보는 "계속 보관" 관행을 피하기 위해 유효한 비즈니스상의 이유로 유지해야 하는 기간은 얼마나 하나요?</span><span class="sxs-lookup"><span data-stu-id="7141e-130">How long does information containing personal data need to be kept around for valid business reasons to avoid "keep it forever" practices?</span></span> <span data-ttu-id="7141e-131">이는 비즈니스 연속성을 위한 보존 요구와 균형을 맞출 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7141e-131">This must be balanced with retention needs for business continuity.</span></span>

<span data-ttu-id="7141e-132">개인 정보를 보관하거나 삭제하는 법적 및 비즈니스 이유에 관계없이 Microsoft는 Microsoft 365에서 데이터 거버넌스 체계를 구현하는 다양한 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7141e-132">Regardless of the legal and business reasons for keeping personal information around or deleting it, Microsoft provides a number of capabilities to implement your data governance scheme in Microsoft 365.</span></span>

## <a name="managing-information-governance-in-microsoft-365"></a><span data-ttu-id="7141e-133">Microsoft 365에서 정보 거버넌스 관리</span><span class="sxs-lookup"><span data-stu-id="7141e-133">Managing information governance in Microsoft 365</span></span>

<span data-ttu-id="7141e-134">시작은 Microsoft [](../compliance/manage-information-governance.md) [365에서](https://docs.microsoft.com/office365/Enterprise/office-365-data-retention-deletion-and-destruction-overview)정보 거버넌스 및 데이터 보존, 삭제 및 폐기 관리를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7141e-134">To begin, see [Manage information governance](../compliance/manage-information-governance.md) and [Data Retention, Deletion and Destruction in Microsoft 365](https://docs.microsoft.com/office365/Enterprise/office-365-data-retention-deletion-and-destruction-overview).</span></span>

### <a name="develop-data-retention-schedules-for-containers-email-and-content"></a><span data-ttu-id="7141e-135">컨테이너, 전자 메일 및 콘텐츠에 대한 데이터 보존 일정 개발</span><span class="sxs-lookup"><span data-stu-id="7141e-135">Develop data retention schedules for containers, email, and content</span></span>

<span data-ttu-id="7141e-136">다음 사항에 유의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7141e-136">Keep the following in mind:</span></span>

- <span data-ttu-id="7141e-137">정의된 정보 유형에 대한 데이터 보존 일정을 설정하는 것이 보존 또는 삭제 체계를 구현하기 위한 선행 요구 사항은 고려되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7141e-137">Establishing a data retention schedule for defined information types should be considered a prerequisite to implementing any retention or deletion scheme.</span></span>

- <span data-ttu-id="7141e-138">대부분의 조직에서 중요하게 고려하는 정보 유형과 그와 함께 수행되는 해당 큰 레코드 보존 일정의 수를 고려할 때 데이터 보존 및 레코드 관리 전략을 구현하려면 계획이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="7141e-138">Given the number of information types that most organizations consider important and the corresponding large records retention schedules that go along with them, implementing a data retention and records management strategy requires planning.</span></span> 

- <span data-ttu-id="7141e-139">이 유형의 효과적인 데이터 거버넌스 전략을 설정하는 핵심은 보다 공식적인 관리가 필요한 가장 우선 순위가 높은 비즈니스 기능 및 정보 유형에 중점을 두는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="7141e-139">The key to establishing an effective data governance strategy of this type is to focus on the highest priority business functions and information types that require more formal management.</span></span> <span data-ttu-id="7141e-140">법적 계약서, 재무 제표 및 규정 준수 설명서를 예로 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7141e-140">Examples are legal contracts, financial statements, and regulatory compliance documentation.</span></span> <span data-ttu-id="7141e-141">모든 단일 정보 유형에 대해 별도의 보존 일정을 설정하지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="7141e-141">Try to avoid having a separate retention schedule for every single information type.</span></span> <span data-ttu-id="7141e-142">예를 들어 일반 비즈니스 콘텐츠에 대한 보존 일정을 7년으로 설정하는 등 일반적인 범주를 최대한 활용해 보아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7141e-142">Try to utilize general categories as much as possible, for example, with retention schedules of 7 years for general business content.</span></span>

- <span data-ttu-id="7141e-143">사용자 환경의 개인 정보 유형을 더 잘 알 수 있는 경우 이러한 유형의 콘텐츠에 대한 보존 및 삭제 일정을 설정하고 정보 아키텍처를 조정하여 이러한 종류의 정보를 보다 쉽게 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="7141e-143">Once the personal information types in your environment are better known, establish retention and deletion schedules for this type of content and adjust your information architecture to make governance of this sort of information easier.</span></span> <span data-ttu-id="7141e-144">예를 들어 제어된 액세스로 개별 사이트, 라이브러리 또는 폴더에서 개인 정보를 격리합니다.</span><span class="sxs-lookup"><span data-stu-id="7141e-144">For example, isolate personal information in separate sites, libraries, or folders with controlled access.</span></span>

### <a name="retention-policies-and-retention-labels"></a><span data-ttu-id="7141e-145">보존 정책 및 보존 레이블</span><span class="sxs-lookup"><span data-stu-id="7141e-145">Retention policies and retention labels</span></span>

<span data-ttu-id="7141e-146">보존 [정책 및 보존](../compliance/retention.md) 레이블을 사용하여 개인 데이터를 포함하거나 포함할 것으로 예상되는 Microsoft 365의 콘텐츠를 보존하거나 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="7141e-146">Use [retention policies and retention labels](../compliance/retention.md) to retain or delete content in Microsoft 365 that contains or is expected to contain personal data.</span></span>

### <a name="records-management"></a><span data-ttu-id="7141e-147">레코드 관리</span><span class="sxs-lookup"><span data-stu-id="7141e-147">Records management</span></span>

<span data-ttu-id="7141e-148">Microsoft 365에서 데이터에 대한 레코드 [](../compliance/records-management.md) 관리 솔루션을 구현하기 위해 레코드를 선언하는 보존 레이블을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="7141e-148">Use retention labels that declare content a record to implement a [records management solution](../compliance/records-management.md) for data in Microsoft 365.</span></span>

<span data-ttu-id="7141e-149">데이터 개인 정보 보호를 위해 법률 부서에서 받은 DSRS(데이터 주체 요청)는 기록으로 선언되고 규정 활동 보존 사양을 준수하기 위해 무기한 또는 증명으로 삭제될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7141e-149">For data privacy, data subject requests (DSRs) received by the legal department are declared a record and can be stored indefinitely or disposed of with proof, to adhere to regulatory activity retention specifications.</span></span>

