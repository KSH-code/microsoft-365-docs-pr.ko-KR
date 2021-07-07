---
title: 메모리 회귀 분석
description: 메모리 회귀를 유추하는 방법
search.appverid: MET150
author: mansipatel-usl
ms.author: mapatel
manager: rshastri
audience: Software-Vendor
ms.topic: how-to
ms.date: 07/06/2021
ms.service: virtual-desktop
localization_priority: Normal
ms.collection: TestBase-M365
ms.custom: ''
ms.reviewer: mapatel
f1.keywords: NOCSH
ms.openlocfilehash: cd95c4e0eb04b05860ded256066913cf87d67e86
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/07/2021
ms.locfileid: "53323106"
---
# <a name="memory-regression-analysis"></a><span data-ttu-id="f7ba7-103">메모리 회귀 분석</span><span class="sxs-lookup"><span data-stu-id="f7ba7-103">Memory Regression Analysis</span></span>

<span data-ttu-id="f7ba7-104">Test Base를 사용하면 앱을 실행하는 테스트 VM에서 메모리 사용량이 크게 증가하는 것을 보다 명확하게 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7ba7-104">Test Base helps you more clearly notice significant memory usage increases in the test VMs running your apps.</span></span> <span data-ttu-id="f7ba7-105">메모리 사용량과 같은 성능 메트릭은 전반적인 응용 프로그램 상태의 표시일 수 있으며, 이 추가는 앱의 성능을 최적화하는 데 크게 도움이 될 것으로 기대합니다.</span><span class="sxs-lookup"><span data-stu-id="f7ba7-105">Performance metrics, such as memory usage, can be indicative of overall application health and we believe this addition will greatly help keep your apps performing optimally.</span></span>

<span data-ttu-id="f7ba7-106">자세한 내용을 확인하거나 이 비디오를 시청하면 최신 개선 사항을 빠르게 확인 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7ba7-106">Read on for more details or watch this video for a quick walk through of the latest improvements.</span></span> 

<span data-ttu-id="f7ba7-107">회귀 분석에 도움이 되는 M365의 능력에 대한 테스트 기준에 대한 자세한 내용은 프로세스 안정성에 기반한 회귀 결과를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f7ba7-107">For more information on Test Base for M365's ability to help with regression analysis, see Regression results based on process reliability.</span></span>

<span data-ttu-id="f7ba7-108"><b>메모리 회귀에 대해 자세히 살펴보기</b></span><span class="sxs-lookup"><span data-stu-id="f7ba7-108"><b>Looking closer at memory regressions</b></span></span>

<span data-ttu-id="f7ba7-109">M365용 테스트 기준 대시보드는 응용 프로그램에서 사전 릴리스된 새 Windows 업데이트에서 사용하는 메모리를 표시하고 마지막으로 릴리스된 Windows 업데이트에 사용된 메모리와 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="f7ba7-109">The Test Base for M365 dashboard shows the memory consumed by your application on a new pre-released Windows update and compares it with the memory used by the last released Windows update.</span></span> 

<span data-ttu-id="f7ba7-110">이번 달의 향상된 기능으로 이제는 즐겨찾는 프로세스에서 메모리 회귀 분석이 추천됩니다.</span><span class="sxs-lookup"><span data-stu-id="f7ba7-110">With this month’s enhancements, memory regression analysis is now featured in your favorited processes.</span></span> <span data-ttu-id="f7ba7-111">응용 프로그램은 여러 프로세스를 포함할 수 있으며 안정성 탭을 통해 즐겨찾기 프로세스를 수동으로 선택할 수 있습니다. 그런 다음 서비스는 이러한 즐겨찾기 프로세스에서 메모리 회귀를 식별하는 동시에 여러 Windows 업데이트 릴리스에서 테스트 실행을 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="f7ba7-111">Applications can contain multiple processes and you can manually select your favorite processes through the Reliability tab. Our service will then identify memory regressions in these favorited processes while comparing test runs across different Windows update releases.</span></span> <span data-ttu-id="f7ba7-112">회귀가 감지되면 회귀에 대한 세부 정보를 쉽게 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7ba7-112">If a regression is detected, details about the regression are easily available.</span></span>

<span data-ttu-id="f7ba7-113">이제 이 기능을 자세히 살펴보고 성능 분석기를 사용하여 메모리 회귀 문제를 해결하는 Windows 살펴보아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7ba7-113">Now let's look at this feature in detail and discuss how you can troubleshoot memory regressions using Windows Performance Analyzer.</span></span>

<span data-ttu-id="f7ba7-114">메모리 회귀로 인한 오류 신호는 테스트 결과 페이지의 메모리 사용률 아래에 있는 M365용 테스트 기준 대시보드에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f7ba7-114">The failure signal caused by a memory regression is shown in the Test Base for M365 dashboard on the Test results page under Memory Utilization:</span></span>

![메모리 사용률 결과](Media/01_memory-utilization-results.png)


<span data-ttu-id="f7ba7-116">메모리 사용량이 높기 때문에 응용 프로그램에 대한 오류도 테스트 요약 페이지에 ```Fail``` 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f7ba7-116">Failure for the application due to higher memory consumption, will also be displayed as ```Fail``` on the Test Summary page:</span></span>

![요약 결과 테스트](Media/02_test-summary.png)

<span data-ttu-id="f7ba7-118">이러한 오류 신호를 선행에 제공하여 응용 프로그램의 최종 사용자 환경을 중단하고 영향을 줄 수 있는 잠재적인 문제에 명확하게 플래그를 지정하는 것이 목표입니다.</span><span class="sxs-lookup"><span data-stu-id="f7ba7-118">By providing these failure signals upfront, our goal is to clearly flag potential issues that can disrupt and impact the end user experience for your application.</span></span> 

<span data-ttu-id="f7ba7-119">그런 다음 로그 파일을 다운로드하고 추가 조사를 위해 Windows 성능 분석기 또는 기본 설정 도구 모음을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7ba7-119">You can then download the log files and use the Windows Performance Analyzer, or your preferred toolkit, to investigate further.</span></span> <span data-ttu-id="f7ba7-120">M365 테스트 기반 팀과 공동으로 문제를 해결하고 최종 사용자에게 영향을 미치는 문제를 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7ba7-120">You can also work jointly with the Test Base for M365 team on remediating the issue and help prevent issues impacting end users.</span></span>

<span data-ttu-id="f7ba7-121">모든 테스트 실행에 대한 M365용 테스트 기준 서비스의 메모리 사용률 탭에 메모리 신호가 캡처됩니다.</span><span class="sxs-lookup"><span data-stu-id="f7ba7-121">Memory signals are captured in the Memory Utilization tab in the Test Base for M365 service for all test runs.</span></span> <span data-ttu-id="f7ba7-122">아래 예제에서는 2020년 8월 시험판 보안 업데이트에 대해 온보드 응용 프로그램 "연기 테스트 메모리 스트레스"를 통해 최근 테스트 실행을 보여 주었다.</span><span class="sxs-lookup"><span data-stu-id="f7ba7-122">The example below shows a recent test run with the onboarded application “Smoke Test Memory Stress” against the pre-release August 2020 security update.</span></span> <span data-ttu-id="f7ba7-123">(이 응용 프로그램은 메모리 회귀를 설명하기 위해 팀에서 작성했습니다.)</span><span class="sxs-lookup"><span data-stu-id="f7ba7-123">(This application was written by our team to illustrate memory regressions.)</span></span>

![메모리 회귀 결과](Media/03_memory-regression%20comparison.png)

<span data-ttu-id="f7ba7-125">이 예에서 즐겨찾기 프로세스 "USLTestMemoryStress.exe" 프로세스는 릴리스된 7월 업데이트와 비교하여 시험판 8월 업데이트에서 평균 약 100MB를 소비하여 M365용 테스트 베이스에서 회귀를 확인했습니다.</span><span class="sxs-lookup"><span data-stu-id="f7ba7-125">In this example, the favorite process “USLTestMemoryStress.exe” process consumed an average of approximately 100 MB on the pre-release August update compared to the released July update, hence the Test Base for M365 identified a regression.</span></span> 

<span data-ttu-id="f7ba7-126">여기에 "USLTestMemoryStress_Aux1.exe" 및 "USLTestMemoryStress_Aux2.exe"로 표시된 다른 프로세스도 동일한 응용 프로그램에 속하지만 두 릴리스에서 거의 동일한 양의 메모리를 사용했기 때문에 "전달"하여 정상으로 간주되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f7ba7-126">The other processes—shown here as “USLTestMemoryStress_Aux1.exe” and “USLTestMemoryStress_Aux2.exe”—also belong to the same application, but consumed approximately the same amount of memory for the two releases so they "passed" and were considered healthy.</span></span>

<span data-ttu-id="f7ba7-127">주 프로세스의 회귀는 "통계적으로 유의"로 결정된 것이기 때문에 서비스가 이 차이점을 사용자에게 전달하고 강조 표시했습니다.</span><span class="sxs-lookup"><span data-stu-id="f7ba7-127">The regression on the main process was determined to be “statistically significant” so the service communicated and highlighted this difference to the user.</span></span> <span data-ttu-id="f7ba7-128">비교가 통계적으로 유의하지 않은 경우 강조 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f7ba7-128">If the comparison was not statistically significant, it would not be highlighted.</span></span> <span data-ttu-id="f7ba7-129">메모리 사용률이 시차가 있을 수 있으므로 통계 모델을 사용하여 빌드와 릴리스에서 의미 있는 차이와 불일치 차이점을 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="f7ba7-129">Memory utilization can be noisy, so we use statistical models to distinguish, across builds and releases, meaningful differences from inconsequential differences.</span></span> 

<span data-ttu-id="f7ba7-130">실제 차이점(가음성)이 없는 경우 비교 플래그가 지정되지 않을 수 있지만 회귀(또는 참 긍정)를 올바르게 식별할 가능성을 높이기 위해 이 장단점이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="f7ba7-130">A comparison may rarely be flagged when there is no true difference (a false positive), but this is a necessary tradeoff to improve the likelihood of correctly identifying regressions (or true positives.)</span></span>

<span data-ttu-id="f7ba7-131">다음 단계에서는 메모리 회귀의 원인을 파악합니다.</span><span class="sxs-lookup"><span data-stu-id="f7ba7-131">The next step is to understand what caused the memory regression.</span></span> <span data-ttu-id="f7ba7-132">아래와 같이 로그 파일 다운로드 옵션에서 두 실행 모두에 대한 zip 파일을 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7ba7-132">You can download the zip files for both executions from the Download log files option, as shown below.</span></span> 

<span data-ttu-id="f7ba7-133">이러한 zip 파일에는 스크립트 결과, 메모리 및 ETL 파일에 포함된 CPU 성능 데이터를 포함하여 테스트 실행 결과가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="f7ba7-133">These zip files contain the results of your test run, including script results and memory and CPU performance data which is included in the ETL file.</span></span>

![메모리 회귀 테스트 파일](Media/04_memory-regression-test-files.png)

<span data-ttu-id="f7ba7-135">두 테스트 실행에 대한 로그를 다운로드 및 제거한 다음 각 폴더 내에서 ETL 파일을 찾아 target.etl(시험판 업데이트에서 테스트 실행용) 및 baseline.etl(마지막 릴리스된 업데이트에서 테스트 실행용)으로 이름을 변경하여 탐색 및 탐색을 간소화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7ba7-135">You can download and unzip the logs for the two test runs, then locate the ETL file within each folder and rename them as target.etl (for the test run on the pre-release update) and baseline.etl (for the test run on last released update) to simplify exploration and navigation.</span></span>
 
## <a name="next-steps"></a><span data-ttu-id="f7ba7-136">다음 단계</span><span class="sxs-lookup"><span data-stu-id="f7ba7-136">Next steps</span></span>

<span data-ttu-id="f7ba7-137">다음 문서로 진행하여 지능형 CPU 회귀 분석 이해를 시작하세요.</span><span class="sxs-lookup"><span data-stu-id="f7ba7-137">Advance to the next article to get started with understanding intelligent CPU regression analysis.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="f7ba7-138">다음 단계</span><span class="sxs-lookup"><span data-stu-id="f7ba7-138">Next step</span></span>](cpu.md)

<!---
Add button for next page
-->
