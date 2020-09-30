---
title: 파일럿 Microsoft Threat Protection 프로젝트 결과 요약
description: 성과 기록표를 완성 하 고, 보고서의 결과를 분석 하 고, 앞으로 이동 하는 방법을 결정 하 여 파일럿 Microsoft 위협 보호 프로젝트를 마무리 합니다.
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
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.openlocfilehash: dbd20263fce059bc57b6a19b58f15e3f5223b4e7
ms.sourcegitcommit: 61ef32f802a1fb6d1e3a3aa005764ead32a7951e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/30/2020
ms.locfileid: "48318209"
---
# <a name="closing-and-summarizing-your-microsoft-threat-protection-pilot"></a><span data-ttu-id="bf6d3-104">Microsoft Threat Protection 파일럿 테스트 종료 및 요약</span><span class="sxs-lookup"><span data-stu-id="bf6d3-104">Closing and summarizing your Microsoft Threat Protection pilot</span></span>  

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="bf6d3-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="bf6d3-105">**Applies to:**</span></span>
- <span data-ttu-id="bf6d3-106">Microsoft 위협 방지</span><span class="sxs-lookup"><span data-stu-id="bf6d3-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="bf6d3-107">지금까지 도메인 컨트롤러에서 코드를 원격으로 실행 한 고급 메모리 전용 공격을 시뮬레이션 했습니다.</span><span class="sxs-lookup"><span data-stu-id="bf6d3-107">You’ve just simulated an advanced memory-only attack that executed code remotely on a domain controller.</span></span> <span data-ttu-id="bf6d3-108">Microsoft Defender ATP 및 Azure ATP에서 stealthy 악성 활동을 감지 하 고 경고 하는 방법을 살펴보았습니다.</span><span class="sxs-lookup"><span data-stu-id="bf6d3-108">You’ve seen how Microsoft Defender ATP and Azure ATP detects and alerts on stealthy malicious activity.</span></span> <span data-ttu-id="bf6d3-109">또한 다양 한 원본의 알림을 Microsoft 365 보안 센터 포털의 단일 인시던트에 함께 제공 하 여 SOC 분석가가 필요한 작업을 조사 하 고 취할 수 있는 방법을 살펴보았습니다.</span><span class="sxs-lookup"><span data-stu-id="bf6d3-109">You’ve also seen how alerts from different sources are delivered along with other contextual information into a single incident in the Microsoft 365 Security Center portal, enabling SOC analysts to investigate and take necessary action.</span></span> <span data-ttu-id="bf6d3-110">또한 사용자가 첨부 파일을 열거나 저장 한 후 해당 쿼리를 기반으로 검색을 만든 인바운드 전자 메일을 식별 하는 고급 구하기 쿼리를 만들었습니다.</span><span class="sxs-lookup"><span data-stu-id="bf6d3-110">You’ve also created an advanced hunting query that will identify inbound emails where the user opened or saved the attachment and created detection based on that query.</span></span>

<span data-ttu-id="bf6d3-111">모든 테스트가 완료 된 후 프로세스의 끝에 도달 했습니다.</span><span class="sxs-lookup"><span data-stu-id="bf6d3-111">You’ve reached the end of the process after all tests have concluded.</span></span>

<span data-ttu-id="bf6d3-112">최종 출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="bf6d3-112">The final output should be:</span></span>

- <span data-ttu-id="bf6d3-113">완성 된 성과 기록표</span><span class="sxs-lookup"><span data-stu-id="bf6d3-113">A completed scorecard</span></span>
- <span data-ttu-id="bf6d3-114">파일럿의 결과에 대 한 자세한 보고서</span><span class="sxs-lookup"><span data-stu-id="bf6d3-114">A detailed report of the findings of the pilot</span></span>
- <span data-ttu-id="bf6d3-115">앞으로 이동 하는 방법을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf6d3-115">A decision on how to move forward</span></span>

<span data-ttu-id="bf6d3-116">이 정보는 내부 이해 관계자 ( [준비](https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval) 단계에서 확인) 및 Microsoft 연락처에 모두 표시 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf6d3-116">This information should be presented to both internal stakeholders (which you’ve identified during the [preparation](https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval) phase) and Microsoft contacts.</span></span> <span data-ttu-id="bf6d3-117">이렇게 하면 모든 피드백을 사용 하 여 제품 및 문서를 개선할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf6d3-117">This ensures that any feedback can be used to improve products and documentation.</span></span>

<span data-ttu-id="bf6d3-118">이 시뮬레이션이 제공 되었으며 배운 것을 구현 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="bf6d3-118">We hope you enjoyed this simulation and are encouraged to start implementing what you've learned.</span></span>

## <a name="next-step"></a><span data-ttu-id="bf6d3-119">다음 단계</span><span class="sxs-lookup"><span data-stu-id="bf6d3-119">Next step</span></span>

****

<span data-ttu-id="bf6d3-120">[Microsoft 365 솔루션 및 아키텍처 센터](https://docs.microsoft.com/microsoft-365/solutions/solution-architecture-center) 에서 살펴보고 조직에 적합 한 솔루션 및 아키텍처를 디자인 하는 방법을 이해 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf6d3-120">Browse through the [Microsoft 365 solution and architecture center](https://docs.microsoft.com/microsoft-365/solutions/solution-architecture-center) to Understand how to design the solution and architecture that is right for your organization.</span></span>
