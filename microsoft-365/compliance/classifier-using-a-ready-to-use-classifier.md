---
title: 바로 사용 가능한 분류자 사용 (미리 보기)
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Microsoft 365에는 조직 전체에서 콘텐츠를 식별 하 고 레이블을 지정 하는 데 사용할 수 있는 기계 학습 분류자를 사용 하기 위한 다양 한 준비가 제공 됩니다. 이 항목에서는 이러한 분류자 사용을 위해 준비 된 사용을 준비 하는 방법을 설명 합니다.
ms.openlocfilehash: 6eaa3689dce1bfb37fdad6b1b22dcac3539bb31e
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/19/2019
ms.locfileid: "40807417"
---
# <a name="using-a-ready-to-use-classifier-preview"></a><span data-ttu-id="d525c-104">바로 사용 가능한 분류자 사용 (미리 보기)</span><span class="sxs-lookup"><span data-stu-id="d525c-104">Using a ready to use classifier (preview)</span></span>

<span data-ttu-id="d525c-105">Microsoft는 특정 콘텐츠 범주를 식별 하는 데 도움이 될 수 있는 매우 큰 예제 데이터 집합을 사용 하 여 여러 분류자를 교육 하 고 테스트 했습니다.</span><span class="sxs-lookup"><span data-stu-id="d525c-105">Microsoft has trained and tested a number of classifiers using very large sample data sets, which can help to identify certain categories of content.</span></span> <span data-ttu-id="d525c-106">[Trainable 분류자 (미리 보기) 시작을](classifier-getting-started-with.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d525c-106">See [Getting started with trainable classifiers (preview)](classifier-getting-started-with.md).</span></span> <span data-ttu-id="d525c-107">이러한 분류자는 `Ready to use` 기본적으로 그룹에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d525c-107">These classifiers show up in the `Ready to use` group by default.</span></span>

- <span data-ttu-id="d525c-108">**비속어**: profanities, slurs, taunts 및 가짜 식이 포함 된 텍스트 항목 (더 공격적인 용어와 의미가 동일한 식 임)을 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="d525c-108">**Offensive Language**: detects text items that contain profanities, slurs, taunts, and disguised expressions (which are expressions that have the same meaning as a more offensive term).</span></span>
- <span data-ttu-id="d525c-109">**다시 시작**: 지원자 개인, 교육, 전문가 자격, 작업 환경 및 기타 개인 식별 정보에 해당 하는 텍스트 계정인 항목을 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="d525c-109">**Resumes**: detects items that are textual accounts of an applicant's personal, educational, professional qualifications, work experience, and other personally identifying information.</span></span>
- <span data-ttu-id="d525c-110">**SourceCode**: 광범위 하 게 사용 되는 컴퓨터 프로그래밍 언어로 작성 된 지침 및 명령문 집합이 포함 되어 있는 항목을 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="d525c-110">**SourceCode**: detects items that contain a set of instructions and statements written in widely used computer programming languages.</span></span>
- <span data-ttu-id="d525c-111">**Harassment**: 레이스, ethnicity, religion, 국립 근원, 성별, 성적 방향, 연령, 장애 등의 특성을 기반으로 하 여 한 명 이상의 개인이 대상으로 하는 공격적인 언어 텍스트 항목의 특정 범주를 감지 합니다.</span><span class="sxs-lookup"><span data-stu-id="d525c-111">**Harassment**: detects a specific category of offensive language text items related to offensive conduct targeting one or multiple individuals based on the following traits: race, ethnicity, religion, national origin, gender, sexual orientation, age, disability.</span></span>
- <span data-ttu-id="d525c-112">**불경**: 대부분의 사용자를 embarrass 하는 식이 포함 된 공격적인 언어 텍스트 항목의 특정 범주를 감지 합니다.</span><span class="sxs-lookup"><span data-stu-id="d525c-112">**Profanity**: detects a specific category of offensive language text items that contain expressions that embarrass most people.</span></span>
- <span data-ttu-id="d525c-113">**위협**: 사용자 또는 속성에 대 한 폭력을 커밋하거나 물리적인 손상을 주거나 위협에 관련 된 비속어 텍스트 항목의 특정 범주를 감지 합니다.</span><span class="sxs-lookup"><span data-stu-id="d525c-113">**Threat**: detects a specific category of offensive language text items related to threats to commit violence or do physical harm or damage to a person or property,</span></span>

> [!NOTE]
> <span data-ttu-id="d525c-114">분류 및 레이블 지정 워크플로에 사용할 수 있는 분류자를 사용 하기 전에 분류 예측이 예상과 맞는지 확인 하기 위해 범주에 적합 한 조직의 콘텐츠 샘플에 대해 테스트 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d525c-114">Before using ready to use classifiers in your classification and labeling workflow, you should test it against a sample of your organization's content that you feel fits the category to verify that its classification predictions meet your expectations.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d525c-115">비속어, harassment, 비속어 및 threat 분류자는 검색 가능한 텍스트만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d525c-115">Please note that the offensive language, harassment, profanity, and threat classifiers only work with searchable text are not exhaustive or complete.</span></span> <span data-ttu-id="d525c-116">추가적으로, 언어 및 문화 표준이 지속적으로 변경 되 고 이러한 현실에 따라 Microsoft는 이러한 분류자를 업데이트할 수 있는 권리를 보유 합니다.</span><span class="sxs-lookup"><span data-stu-id="d525c-116">Further, language and cultural standards continually change, and in light of these realities, Microsoft reserves the right to update these classifiers in its discretion.</span></span> <span data-ttu-id="d525c-117">이 분류자는 사용 중인 공격적인 및 기타 언어를 모니터링 하는 데 도움이 될 수 있지만,이 분류자는 이러한 언어의 결과를 해결 하지 않으며, 조직의 사용자가 사용 하는 유일한 모니터링 또는 대응 수단을 제공 하기 위한 것이 아닙니다. 해당 언어</span><span class="sxs-lookup"><span data-stu-id="d525c-117">While the classifiers may assist your organization in monitoring offensive and other language used, the classifiers do not address consequences of such language and are not intended to provide your organization’s sole means of monitoring or responding to the use of such language.</span></span> <span data-ttu-id="d525c-118">Microsoft 또는 해당 자회사가 아닌 조직은 미리 훈련 된 분류자로 식별 되는 콘텐츠의 모니터링, 적용, 차단, 제거 및 보존과 관련 된 모든 결정을 계속 담당 합니다.</span><span class="sxs-lookup"><span data-stu-id="d525c-118">Your organization, and not Microsoft or its subsidiaries, remains responsible for all decisions related to monitoring, enforcement, blocking, removal and retention of any content identified by a pre-trained classifier.</span></span>

## <a name="how-to-prepare-for-and-use-a-ready-to-use-classifier"></a><span data-ttu-id="d525c-119">분류자 사용을 준비 하 고 사용 하는 방법</span><span class="sxs-lookup"><span data-stu-id="d525c-119">How to prepare for and use a ready to use classifier</span></span>

1. <span data-ttu-id="d525c-120">사용 가능한 분류자 (긍정 일치) 및 포함 하지 않을 항목 (음수 일치)이 테스트 대상 범주에 속하는 것으로 생각 하는 삭제 가능 테스트 콘텐츠를 수집 합니다.</span><span class="sxs-lookup"><span data-stu-id="d525c-120">Collect disposable test content items that you feel belong in the category of the ready to use classifier (positive matches) and ones that shouldn't be included (negative matches) in the category you're testing.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d525c-121">샘플 항목은 암호화 하지 않아야 하며 영어로 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d525c-121">The sample items must not be encrypted and they must be in English.</span></span>

2. <span data-ttu-id="d525c-122">전용 SharePoint Online 폴더를 만듭니다. 폴더를 검색 인덱스에 추가할 때까지 적어도 1 시간 이상 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="d525c-122">Create a dedicated SharePoint Online folder; wait at least an hour for the folder to be added to the search index.</span></span> <span data-ttu-id="d525c-123">폴더 URL을 기록해 둡니다.</span><span class="sxs-lookup"><span data-stu-id="d525c-123">Make note of the folder URL.</span></span>

3. <span data-ttu-id="d525c-124">준수 관리자 또는 보안 관리자 역할 액세스를 사용 하 여 microsoft 365 준수 센터에 로그인 하 고 **microsoft 365 준수 센터** 또는 **microsoft 365 보안 센터** > **레코드 관리 (미리 보기)** > **레이블 정책** 탭을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="d525c-124">Sign in to Microsoft 365 compliance center with compliance admin or security admin role access and open **Microsoft 365 compliance center** or **Microsoft 365 security center** > **Records management (preview)** > **Label policies** tab.</span></span>

4. <span data-ttu-id="d525c-125">을 `Auto-apply a label`선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d525c-125">Choose `Auto-apply a label`.</span></span>

5. <span data-ttu-id="d525c-126">을 `Choose a label to auto-apply`선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d525c-126">Choose `Choose a label to auto-apply`.</span></span>

6. <span data-ttu-id="d525c-127">이 `Create new labels` 테스트에만 사용할 레이블을 선택 하 고 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d525c-127">Choose `Create new labels` and create a label for use just with this test.</span></span> <span data-ttu-id="d525c-128">이렇게 하면 설정 해제로 유지 `Retention` 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d525c-128">When you do this, leave `Retention` set to off.</span></span> <span data-ttu-id="d525c-129">보존 또는 기타 작업을 설정 하지 않으려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="d525c-129">You don't want to turn on any retention or other actions.</span></span> <span data-ttu-id="d525c-130">이 경우에는 작업을 적용 하지 않고 보존 레이블을 단순히 텍스트 레이블로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d525c-130">In this case, you'll be using the retention label simply as a text label, without enforcing any actions.</span></span> <span data-ttu-id="d525c-131">예를 들어 작업 없이 "SourceCode 분류자 test" 라는 보존 레이블을 만든 다음 해당 보존 레이블을 조건으로 소스 코드 분류자가 있는 콘텐츠에 자동으로 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d525c-131">For example, you can create a retention label named "SourceCode classifier test" with no actions, and then auto-apply that retention label to content that has Source code classifier as a condition.</span></span> <span data-ttu-id="d525c-132">보존 레이블 만들기에 대 한 자세한 내용은 [Overview (보존 레이블](labels.md))를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="d525c-132">To learn more about creating retention labels, see [Overview of retention labels](labels.md).</span></span>
  
7. <span data-ttu-id="d525c-133">을 `Auto-apply a label` 선택 하 `Choose a label to auto-apply`고을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d525c-133">Choose `Auto-apply a label` and then `Choose a label to auto-apply`.</span></span> <span data-ttu-id="d525c-134">조건 기반 자동 적용 레이블을 사용 하는 방법에 대 한 자세한 내용은 [조건에 따라 보존 레이블 정책 자동 적용](labels.md#applying-a-retention-label-automatically-based-on-conditions)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="d525c-134">To learn more about using condition based auto-apply a label see, [auto-apply retention label policy based on a condition](labels.md#applying-a-retention-label-automatically-based-on-conditions).</span></span>

8. <span data-ttu-id="d525c-135">목록에서 테스트 레이블을 선택 하 고를 선택 `Next`합니다.</span><span class="sxs-lookup"><span data-stu-id="d525c-135">Choose your test label from the list and choose `Next`.</span></span>

9. <span data-ttu-id="d525c-136">을 `Apply label to content that matches a trainable classifier`선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d525c-136">Choose `Apply label to content that matches a trainable classifier`.</span></span>

![조건으로 분류자 선택](media/classifier-pre-trained-apply-label-match-trainable-classifier.png)<span data-ttu-id="d525c-138">.</span><span class="sxs-lookup"><span data-stu-id="d525c-138"></span></span>

10. <span data-ttu-id="d525c-139">이 경우 목록에서 분류자를 선택 합니다.`Source Code`</span><span class="sxs-lookup"><span data-stu-id="d525c-139">Choose your classifier from the list, in this case `Source Code`</span></span>

11. <span data-ttu-id="d525c-140">정책 이름 (예: "소스 코드에서 분류자 테스트를 사용할 준비가 되었습니다.")</span><span class="sxs-lookup"><span data-stu-id="d525c-140">Name the policy, for example "Source code ready to use classifier test".</span></span>

12. <span data-ttu-id="d525c-141">을 `Let me choose specific locations`선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d525c-141">Choose `Let me choose specific locations`.</span></span>

13. <span data-ttu-id="d525c-142">를 제외한 `SharePoint sites` 모든 위치를 해제 하 `Choose sites`고를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d525c-142">Turn off all locations except `SharePoint sites` and choose `Choose sites`.</span></span>

14. <span data-ttu-id="d525c-143">2 단계에 해당 하는 사이트의 URL을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="d525c-143">Enter the URL for the site from step 2.</span></span>

15. <span data-ttu-id="d525c-144">마법사를 완료 하 고`Auto-apply`</span><span class="sxs-lookup"><span data-stu-id="d525c-144">Finish the wizard and choose `Auto-apply`</span></span>

16. <span data-ttu-id="d525c-145">테스트 항목을 전용 SharePoint Online 폴더에 배치 합니다.</span><span class="sxs-lookup"><span data-stu-id="d525c-145">Place the test items into the dedicated SharePoint Online folder.</span></span>

17. <span data-ttu-id="d525c-146">레이블이 적용 되는 시간을 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d525c-146">Allow an hour for the label to be applied.</span></span>

18. <span data-ttu-id="d525c-147">레이블에 대 한 문서의 속성을 확인 하 여 해당 분류자가 필요한 대로 테스트 콘텐츠를 포함 하 고 제외 했는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d525c-147">Check the properties of the documents for the label to see if the classifier included and excluded the test content as you expected.</span></span>

19. <span data-ttu-id="d525c-148">레이블이 지정 된 항목을 검토 합니다.</span><span class="sxs-lookup"><span data-stu-id="d525c-148">Review the items that were labeled.</span></span>

20. <span data-ttu-id="d525c-149">테스트를 완료 한 경우 콘텐츠 및 레이블 정책을 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="d525c-149">Delete the content and the label policy if you're done with your testing.</span></span>

<span data-ttu-id="d525c-150">참고 항목:</span><span class="sxs-lookup"><span data-stu-id="d525c-150">See also:</span></span>

- [<span data-ttu-id="d525c-151">학습 가능한 분류자 시작 (미리 보기)</span><span class="sxs-lookup"><span data-stu-id="d525c-151">Getting started with trainable classifiers (preview)</span></span>](classifier-getting-started-with.md)
- [<span data-ttu-id="d525c-152">보존 레이블 개요</span><span class="sxs-lookup"><span data-stu-id="d525c-152">Overview of retention labels</span></span>](labels.md)
- [<span data-ttu-id="d525c-153">조건에 따라 보존 레이블 정책 자동 적용</span><span class="sxs-lookup"><span data-stu-id="d525c-153">Auto-apply retention label policy based on a condition</span></span>](labels.md#applying-a-retention-label-automatically-based-on-conditions)
