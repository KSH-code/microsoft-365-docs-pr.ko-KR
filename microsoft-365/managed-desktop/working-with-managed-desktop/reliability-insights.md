---
title: 안정성 통찰력
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 설명서
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: f830e01d54aef9065727971533633f8e63bc1214
ms.sourcegitcommit: e292e9f0181d722a11398fbd012bb84589aef052
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/25/2019
ms.locfileid: "39257036"
---
# <a name="reliability-insights"></a><span data-ttu-id="9cc91-103">안정성 통찰력</span><span class="sxs-lookup"><span data-stu-id="9cc91-103">Reliability insights</span></span>

<span data-ttu-id="9cc91-104">이 보기는 관리 되는 장치에 대 한 상태 요약을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="9cc91-104">This view provides you with a health summary of your managed devices.</span></span> <span data-ttu-id="9cc91-105">안정성 데이터를 보려면 **안정성** 탭을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9cc91-105">To view reliability data, select the **Reliability** tab.</span></span>


![안정성 창](images/insights_reliability.png)

<span data-ttu-id="9cc91-107">**Devices에서의 안정성** 섹션에서는 "정상"으로 간주 되는 장치의 비율과 마지막으로 보고 된 오류 이후 관찰 된 평균 시간을 보고 하 여 지난 14 일 동안의 배포에 대 한 신속한 상태 요약을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="9cc91-107">The **Reliability across devices** section offers a quick health summary of your deployment over the last 14 days by reporting the percentage of devices considered to be “healthy” and the mean time observed since the last reported failure.</span></span> 

 
<span data-ttu-id="9cc91-108">오른쪽의 **안정성** 그래프에는 치명적인 오류가 발생 한 장치 수와 시간이 경과 함에 따라 관찰 된 중대 한 오류 총 수가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9cc91-108">The **Reliability over time** graph on the right reports the number of devices with critical errors and the total number of observed critical errors over time.</span></span>

<span data-ttu-id="9cc91-109">**주요 문제** 섹션에는 관리 되는 장치 중 5% 이상에 영향을 주는 특정 검색 된 문제에 대 한 세부 정보가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9cc91-109">The **Top issues** section details specific detected issues that affect at least 5% of your managed devices.</span></span> <span data-ttu-id="9cc91-110">보고 된 세부 정보는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9cc91-110">Reported details include:</span></span>

- <span data-ttu-id="9cc91-111">문제 유형</span><span class="sxs-lookup"><span data-stu-id="9cc91-111">The type of issue</span></span>
    - <span data-ttu-id="9cc91-112">앱 작동이 중지 되거나 예기치 않게 중지 되는 응용 프로그램 중단</span><span class="sxs-lookup"><span data-stu-id="9cc91-112">Application crashes, in which an app stops functioning or unexpectedly stops</span></span>
    - <span data-ttu-id="9cc91-113">응용 프로그램이 중단 되며, 응용 프로그램에서 입력에 대 한 응답을 중지 함</span><span class="sxs-lookup"><span data-stu-id="9cc91-113">Application hangs, where an application stops responding to input</span></span>
    - <span data-ttu-id="9cc91-114">치명적인 오류-Windows에 문제가 발생 하 여 복구할 수 없는 경우 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="9cc91-114">Critical errors, which occur when Windows has encountered an issue it can't recover from</span></span>
- <span data-ttu-id="9cc91-115">같은 문제로 인해 영향을 받는 장치 수입니다.</span><span class="sxs-lookup"><span data-stu-id="9cc91-115">The number of devices affected by the same issue</span></span>
- <span data-ttu-id="9cc91-116">해당 숫자가 나타내는 관리 되는 장치의 백분율</span><span class="sxs-lookup"><span data-stu-id="9cc91-116">The percentage of managed devices that number represents</span></span>
- <span data-ttu-id="9cc91-117">특정 문제의 총 발생 횟수입니다.</span><span class="sxs-lookup"><span data-stu-id="9cc91-117">The total count of occurences of the specific issue</span></span>
- <span data-ttu-id="9cc91-118">문제의 원인이 되는 것으로 표시 되는 소프트웨어 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="9cc91-118">The software component that appears to be the source of the problem</span></span>
- <span data-ttu-id="9cc91-119">Microsoft Managed Desktop 작업으로 인 한 현재 상태 조사 및 remediates 문제 해결</span><span class="sxs-lookup"><span data-stu-id="9cc91-119">The current status as Microsoft Managed Desktop Operations investigates and remediates the issue</span></span>

