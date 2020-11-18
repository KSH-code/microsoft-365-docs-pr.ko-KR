---
title: 파일럿 Microsoft 365 Defender 프로젝트 결과 요약
description: 성과 기록표를 완성 하 고, 보고서의 결과를 분석 하 고, 앞으로 이동 하는 방법을 결정 하 여 파일럿 Microsoft 365 Defender 프로젝트를 마무리 합니다.
keywords: Microsoft Threat protection 파일럿, Microsoft threat Protection 프로젝트를 파일럿으로 실행 한 후에 수행할 작업, 프로덕션에서 Microsoft 위협 보호를 평가한 후 수행 해야 하는 작업, Microsoft Threat Protection 파일럿에서 배포로 전환, 사이버 보안, 고급 영구 위협, 엔터프라이즈 보안, 장치, 장치, id, 사용자, 데이터, 응용 프로그램, 인시던트, 자동화 된 조사, 개선, 고급 구하기
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dolmont
author: DulceMontemayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-pilotmtpproject
ms.topic: conceptual
ms.openlocfilehash: 3fe5bfdec566b0988d9f565595624fc8dd597788
ms.sourcegitcommit: ce46d1bd67091d4ed0e2b776dfed55e2d88cdbf4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/18/2020
ms.locfileid: "49130946"
---
# <a name="closing-and-summarizing-your-microsoft-365-defender-pilot"></a><span data-ttu-id="73faa-104">Microsoft 365 Defender 파일럿 마감 및 요약</span><span class="sxs-lookup"><span data-stu-id="73faa-104">Closing and summarizing your Microsoft 365 Defender pilot</span></span>  

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="73faa-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="73faa-105">**Applies to:**</span></span>
- <span data-ttu-id="73faa-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="73faa-106">Microsoft 365 Defender</span></span>



|<span data-ttu-id="73faa-107">[![계획](../../media/phase-diagrams/1-planning.png)](mtp-pilot-plan.md)</span><span class="sxs-lookup"><span data-stu-id="73faa-107">[![Planning](../../media/phase-diagrams/1-planning.png)](mtp-pilot-plan.md)</span></span><br/>[<span data-ttu-id="73faa-108">계획</span><span class="sxs-lookup"><span data-stu-id="73faa-108">Planning</span></span>](mtp-pilot-plan.md) |<span data-ttu-id="73faa-109">[![준비](../../media/phase-diagrams/2-prepare.png)](prepare-mtpeval.md)</span><span class="sxs-lookup"><span data-stu-id="73faa-109">[![Prepare](../../media/phase-diagrams/2-prepare.png)](prepare-mtpeval.md)</span></span><br/>[<span data-ttu-id="73faa-110">미리</span><span class="sxs-lookup"><span data-stu-id="73faa-110">Preparation</span></span>](prepare-mtpeval.md) | <span data-ttu-id="73faa-111">[![공격 시뮬레이션](../../media/phase-diagrams/3-simluate.png)](mtp-pilot-simulate.md)</span><span class="sxs-lookup"><span data-stu-id="73faa-111">[![Simulate attack](../../media/phase-diagrams/3-simluate.png)](mtp-pilot-simulate.md)</span></span><br/>[<span data-ttu-id="73faa-112">공격 시뮬레이션</span><span class="sxs-lookup"><span data-stu-id="73faa-112">Simulate attack</span></span>](mtp-pilot-simulate.md) | ![닫기 및 요약](../../media/phase-diagrams/4-summary.png)<br/><span data-ttu-id="73faa-114">닫기 및 요약</span><span class="sxs-lookup"><span data-stu-id="73faa-114">Close and summarize</span></span>|
|--|--|--|--|
|| | |<span data-ttu-id="73faa-115">*사용자가 여기 있어!*</span><span class="sxs-lookup"><span data-stu-id="73faa-115">*You are here!*</span></span>|


<span data-ttu-id="73faa-116">현재 종료 및 요약 단계가 진행 되 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73faa-116">You're currently in the closing and summarizing phase.</span></span>

<span data-ttu-id="73faa-117">이제 도메인 컨트롤러에서 코드를 원격으로 실행 한 고급 메모리 전용 공격 시뮬레이션이 실행 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="73faa-117">You’ve just ran an advanced memory-only attack simulation that executed code remotely on a domain controller.</span></span> <span data-ttu-id="73faa-118">Microsoft Defender for Identity for stealthy 악성 활동에 대 한 Id를 검색 하 고 경고를 만들기 위한 microsoft defender를 살펴보았습니다.</span><span class="sxs-lookup"><span data-stu-id="73faa-118">You’ve seen how Microsoft Defender for Endpoint and Microsoft Defender for Identity detect and create alerts on stealthy malicious activity.</span></span> <span data-ttu-id="73faa-119">또한 다른 상황 정보를 Microsoft 365 보안 센터 포털의 단일 인시던트에 함께 사용 하 여 다양 한 원본의 알림이 제공 되는 방식에 대해 살펴보았습니다.</span><span class="sxs-lookup"><span data-stu-id="73faa-119">You’ve also seen how alerts from different sources are delivered along with other contextual information into a single incident in the Microsoft 365 Security Center portal.</span></span> <span data-ttu-id="73faa-120">이러한 통합이 발생 하면 SOC 분석가가 필요한 작업을 조사 하 고 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73faa-120">Experiencing such integration enables SOC analysts to investigate and take necessary action.</span></span> <span data-ttu-id="73faa-121">또한 사용자가 첨부 파일을 열거나 저장 한 후 해당 쿼리를 기반으로 검색을 만든 인바운드 전자 메일을 식별 하는 고급 구하기 쿼리를 만들었습니다.</span><span class="sxs-lookup"><span data-stu-id="73faa-121">You’ve also created an advanced hunting query that will identify inbound emails where the user opened or saved the attachment and created detection based on that query.</span></span>

<span data-ttu-id="73faa-122">모든 테스트가 완료 된 후 프로세스의 끝에 도달 했습니다.</span><span class="sxs-lookup"><span data-stu-id="73faa-122">You’ve reached the end of the process after all tests have concluded.</span></span>

<span data-ttu-id="73faa-123">최종 출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="73faa-123">The final output should be:</span></span>

- <span data-ttu-id="73faa-124">완성 된 성과 기록표</span><span class="sxs-lookup"><span data-stu-id="73faa-124">A completed scorecard</span></span>
- <span data-ttu-id="73faa-125">파일럿의 결과에 대 한 자세한 보고서</span><span class="sxs-lookup"><span data-stu-id="73faa-125">A detailed report of the findings of the pilot</span></span>
- <span data-ttu-id="73faa-126">앞으로 이동 하는 방법을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="73faa-126">A decision on how to move forward</span></span>

<span data-ttu-id="73faa-127">최종 결과의 보고서를 내부 이해 관계자 ( [준비](https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval) 단계에서 확인) 및 Microsoft 연락처에 게 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="73faa-127">Present the reports from your final output to internal stakeholders (which you’ve identified during the [preparation](https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval) phase) and Microsoft contacts.</span></span> <span data-ttu-id="73faa-128">이러한 노력을 통해 제품 및 문서를 개선 하는 데 모든 의견을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73faa-128">Such an effort ensures that any feedback can be used to improve products and documentation.</span></span>

<span data-ttu-id="73faa-129">이 시뮬레이션을 사용할 예정 이었습니다.</span><span class="sxs-lookup"><span data-stu-id="73faa-129">We hope you enjoyed this simulation.</span></span> <span data-ttu-id="73faa-130">통합 보안 솔루션을 최대한 활용 하기 위해 조직의 대규모 확장에 대해 배운 내용을 구현 하기 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="73faa-130">Start implementing what you've learned on a larger scale in your organization to get the most out of the integrated security solution.</span></span>

## <a name="next-step"></a><span data-ttu-id="73faa-131">다음 단계</span><span class="sxs-lookup"><span data-stu-id="73faa-131">Next step</span></span>
<span data-ttu-id="73faa-132">다음 대화형 가이드를 통해 Microsoft 365 Defender 핵심 요소로에 대해 자세히 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="73faa-132">Learn more about the Microsoft 365 Defender pillars through the following interactive guides:</span></span>
- [<span data-ttu-id="73faa-133">Microsoft Defender for Office 365를 사용 하 여 조직 보호</span><span class="sxs-lookup"><span data-stu-id="73faa-133">Safeguard your organization with Microsoft Defender for Office 365</span></span>](https://aka.ms/O365ATP-Interactive-Guide)
- [<span data-ttu-id="73faa-134">Microsoft Defender for Identity를 사용하여 의심스러운 활동과 잠재적인 공격을 감지</span><span class="sxs-lookup"><span data-stu-id="73faa-134">Detect suspicious activities and potential attacks with Microsoft Defender for Identity</span></span>](https://aka.ms/AATP-Interactive-Guide)
- [<span data-ttu-id="73faa-135">Microsoft Cloud App Security를 사용 하 여 위협 검색 및 알림 관리</span><span class="sxs-lookup"><span data-stu-id="73faa-135">Detect threats and manage alerts with Microsoft Cloud App Security</span></span>](https://aka.ms/DetectThreatsAndAlertsMCAS-InteractiveGuide)
- [<span data-ttu-id="73faa-136">끝점에 대 한 Microsoft Defender를 사용 하 여 위협 조사 및 수정</span><span class="sxs-lookup"><span data-stu-id="73faa-136">Investigate and remediate threats with Microsoft Defender for Endpoint</span></span>](https://aka.ms/MDATP-IR-Interactive-Guide)
