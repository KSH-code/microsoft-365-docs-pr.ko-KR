---
title: 안정성 인사이트
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 설명서
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 1f642d2790af5f4ec83dd1bbe57a9be249d095d1
ms.sourcegitcommit: b65c80051e53d9be223f4769f4d42a39f5a07735
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/10/2019
ms.locfileid: "39962335"
---
# <a name="reliability-insights"></a><span data-ttu-id="e04e7-103">안정성 인사이트</span><span class="sxs-lookup"><span data-stu-id="e04e7-103">Reliability insights</span></span>

<span data-ttu-id="e04e7-104">이 보기는 관리 되는 장치에 대 한 상태 요약을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e04e7-104">This view provides you with a health summary of your managed devices.</span></span> <span data-ttu-id="e04e7-105">안정성 데이터를 보려면 **안정성** 탭을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e04e7-105">To view reliability data, select the **Reliability** tab.</span></span>


![안정성 창: 왼쪽 위에 있는 장치 간의 안정성, 오른쪽 위의 안정성 그래프, 아래쪽에 있는 상위 문제 테이블](images/insights_reliability.png)

<span data-ttu-id="e04e7-108">**Devices에서의 안정성** 섹션에서는 "정상"으로 간주 되는 장치의 비율과 마지막으로 보고 된 오류 이후 관찰 된 평균 시간을 보고 하 여 지난 14 일 동안의 배포에 대 한 신속한 상태 요약을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e04e7-108">The **Reliability across devices** section offers a quick health summary of your deployment over the last 14 days by reporting the percentage of devices considered to be “healthy” and the mean time observed since the last reported failure.</span></span> 

 
<span data-ttu-id="e04e7-109">오른쪽의 **안정성** 그래프에는 치명적인 오류가 발생 한 장치 수와 시간이 경과 함에 따라 관찰 된 중대 한 오류 총 수가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e04e7-109">The **Reliability over time** graph on the right reports the number of devices with critical errors and the total number of observed critical errors over time.</span></span>

<span data-ttu-id="e04e7-110">**주요 문제** 섹션에는 관리 되는 장치 중 5% 이상에 영향을 주는 특정 검색 된 문제에 대 한 세부 정보가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e04e7-110">The **Top issues** section details specific detected issues that affect at least 5% of your managed devices.</span></span> <span data-ttu-id="e04e7-111">보고 된 세부 정보는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e04e7-111">Reported details include:</span></span>

- <span data-ttu-id="e04e7-112">문제 유형</span><span class="sxs-lookup"><span data-stu-id="e04e7-112">The type of issue</span></span>
    - <span data-ttu-id="e04e7-113">앱 작동이 중지 되거나 예기치 않게 중지 되는 응용 프로그램 중단</span><span class="sxs-lookup"><span data-stu-id="e04e7-113">Application crashes, in which an app stops functioning or unexpectedly stops</span></span>
    - <span data-ttu-id="e04e7-114">응용 프로그램이 중단 되며, 응용 프로그램에서 입력에 대 한 응답을 중지 함</span><span class="sxs-lookup"><span data-stu-id="e04e7-114">Application hangs, where an application stops responding to input</span></span>
    - <span data-ttu-id="e04e7-115">치명적인 오류-Windows에 문제가 발생 하 여 복구할 수 없는 경우 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="e04e7-115">Critical errors, which occur when Windows has encountered an issue it can't recover from</span></span>
- <span data-ttu-id="e04e7-116">같은 문제로 인해 영향을 받는 장치 수입니다.</span><span class="sxs-lookup"><span data-stu-id="e04e7-116">The number of devices affected by the same issue</span></span>
- <span data-ttu-id="e04e7-117">해당 숫자가 나타내는 관리 되는 장치의 백분율</span><span class="sxs-lookup"><span data-stu-id="e04e7-117">The percentage of managed devices that number represents</span></span>
- <span data-ttu-id="e04e7-118">특정 문제의 총 발생 횟수입니다.</span><span class="sxs-lookup"><span data-stu-id="e04e7-118">The total count of occurences of the specific issue</span></span>
- <span data-ttu-id="e04e7-119">문제의 원인이 되는 것으로 표시 되는 소프트웨어 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="e04e7-119">The software component that appears to be the source of the problem</span></span>
- <span data-ttu-id="e04e7-120">검색 된 문제의 범주:</span><span class="sxs-lookup"><span data-stu-id="e04e7-120">The category of the detected problem:</span></span>
    - <span data-ttu-id="e04e7-121">브라우저 (Edge, Chrome, IE)</span><span class="sxs-lookup"><span data-stu-id="e04e7-121">Browser (Edge, Chrome, IE)</span></span>
    - <span data-ttu-id="e04e7-122">알 수 없음 (Microsoft 구성 요소 아님)</span><span class="sxs-lookup"><span data-stu-id="e04e7-122">Unknown (Non-Microsoft components)</span></span>
    - <span data-ttu-id="e04e7-123">드라이버 (오디오, 그래픽 또는 기타 드라이버)</span><span class="sxs-lookup"><span data-stu-id="e04e7-123">Driver (audio, graphics, or other drivers)</span></span>
    - <span data-ttu-id="e04e7-124">생산성 (여유 시간, G-제품군, Microsoft Office 및 해당 추가 기능 또는 확장, 팀)</span><span class="sxs-lookup"><span data-stu-id="e04e7-124">Productivity (Slack, G-Suites, Microsoft Office and its add-ons or extensions, Teams)</span></span>
    - <span data-ttu-id="e04e7-125">미디어 (이미지, 음악 또는 비디오 앱)</span><span class="sxs-lookup"><span data-stu-id="e04e7-125">Media (image, music, or video apps</span></span>
    - <span data-ttu-id="e04e7-126">보안 (Windows 보안 구성 요소)</span><span class="sxs-lookup"><span data-stu-id="e04e7-126">Security (Windows security components)</span></span>
- <span data-ttu-id="e04e7-127">Microsoft Managed Desktop 작업으로 인 한 현재 상태 조사 및 remediates 문제 해결</span><span class="sxs-lookup"><span data-stu-id="e04e7-127">The current status as Microsoft Managed Desktop Operations investigates and remediates the issue</span></span>

