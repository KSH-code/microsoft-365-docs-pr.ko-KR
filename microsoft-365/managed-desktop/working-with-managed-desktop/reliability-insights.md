---
title: 안정성 인사이트
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 문서
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 06e1446ca290439c9e6689f4461c825438cf6aaf
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950345"
---
# <a name="reliability-insights"></a><span data-ttu-id="055f2-103">안정성 인사이트</span><span class="sxs-lookup"><span data-stu-id="055f2-103">Reliability insights</span></span>

<span data-ttu-id="055f2-104">이 보기는 관리되는 장치에 대한 상태 요약을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="055f2-104">This view provides you with a health summary of your managed devices.</span></span> <span data-ttu-id="055f2-105">안정성 데이터를 보기 위해 안정성 **탭을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="055f2-105">To view reliability data, select the **Reliability** tab.</span></span>


![안정성 창: 왼쪽 위에 있는 디바이스의 안정성, 오른쪽 위에 있는 시간의 안정성 그래프, 맨 아래 문제 표](../../media/insights_reliability.png)

<span data-ttu-id="055f2-108">장치  간 안정성 섹션에서는 "정상"으로 간주되는 장치의 백분율과 마지막으로 보고된 오류 이후 관찰된 평균 시간을 보고하여 지난 14일 동안의 배포에 대한 빠른 상태 요약을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="055f2-108">The **Reliability across devices** section offers a quick health summary of your deployment over the last 14 days by reporting the percentage of devices considered to be “healthy” and the mean time observed since the last reported failure.</span></span> 

 
<span data-ttu-id="055f2-109">오른쪽의 **시간의** 안정성 그래프에서는 중요한 오류가 있는 장치 수와 관찰된 총 중요 오류 수를 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="055f2-109">The **Reliability over time** graph on the right reports the number of devices with critical errors and the total number of observed critical errors over time.</span></span>

<span data-ttu-id="055f2-110">상위 **문제점 섹션에서는** 관리되는 장치의 5% 이상에 영향을 주는 검색된 특정 문제에 대해 자세히 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="055f2-110">The **Top issues** section details specific detected issues that affect at least 5% of your managed devices.</span></span> <span data-ttu-id="055f2-111">보고된 세부 정보는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="055f2-111">Reported details include:</span></span>

- <span data-ttu-id="055f2-112">문제 유형</span><span class="sxs-lookup"><span data-stu-id="055f2-112">The type of issue</span></span>
    - <span data-ttu-id="055f2-113">응용 프로그램 작동이 중지되거나 예기치 않게 중지되는 응용 프로그램 크래시</span><span class="sxs-lookup"><span data-stu-id="055f2-113">Application crashes, in which an app stops functioning or unexpectedly stops</span></span>
    - <span data-ttu-id="055f2-114">응용 프로그램이 입력에 응답하지 못하게 하는 응용 프로그램 중단</span><span class="sxs-lookup"><span data-stu-id="055f2-114">Application hangs, where an application stops responding to input</span></span>
    - <span data-ttu-id="055f2-115">Windows에서 복구할 수 없는 문제가 발생할 때 발생하는 중요한 오류</span><span class="sxs-lookup"><span data-stu-id="055f2-115">Critical errors, which occur when Windows has encountered an issue it can't recover from</span></span>
- <span data-ttu-id="055f2-116">동일한 문제의 영향을 받는 장치 수</span><span class="sxs-lookup"><span data-stu-id="055f2-116">The number of devices affected by the same issue</span></span>
- <span data-ttu-id="055f2-117">숫자가 나타내는 관리되는 장치의 백분율</span><span class="sxs-lookup"><span data-stu-id="055f2-117">The percentage of managed devices that number represents</span></span>
- <span data-ttu-id="055f2-118">특정 문제의 총 발생 횟수</span><span class="sxs-lookup"><span data-stu-id="055f2-118">The total count of occurrences of the specific issue</span></span>
- <span data-ttu-id="055f2-119">문제의 원인으로 나타나는 소프트웨어 구성 요소</span><span class="sxs-lookup"><span data-stu-id="055f2-119">The software component that appears to be the source of the problem</span></span>
- <span data-ttu-id="055f2-120">검색된 문제의 범주:</span><span class="sxs-lookup"><span data-stu-id="055f2-120">The category of the detected problem:</span></span>
    - <span data-ttu-id="055f2-121">브라우저(Edge, Chrome, IE)</span><span class="sxs-lookup"><span data-stu-id="055f2-121">Browser (Edge, Chrome, IE)</span></span>
    - <span data-ttu-id="055f2-122">알 수 없음(Microsoft가 아닌 구성 요소)</span><span class="sxs-lookup"><span data-stu-id="055f2-122">Unknown (Non-Microsoft components)</span></span>
    - <span data-ttu-id="055f2-123">드라이버(오디오, 그래픽 또는 기타 드라이버)</span><span class="sxs-lookup"><span data-stu-id="055f2-123">Driver (audio, graphics, or other drivers)</span></span>
    - <span data-ttu-id="055f2-124">생산성(Slack, G-Suites, Microsoft Office 및 추가 기능 또는 확장, Teams)</span><span class="sxs-lookup"><span data-stu-id="055f2-124">Productivity (Slack, G-Suites, Microsoft Office and its add-ons or extensions, Teams)</span></span>
    - <span data-ttu-id="055f2-125">미디어(이미지, 음악 또는 비디오 앱)</span><span class="sxs-lookup"><span data-stu-id="055f2-125">Media (image, music, or video apps</span></span>
    - <span data-ttu-id="055f2-126">보안(Windows 보안 구성 요소)</span><span class="sxs-lookup"><span data-stu-id="055f2-126">Security (Windows security components)</span></span>
- <span data-ttu-id="055f2-127">Microsoft Managed Desktop Operations에서 문제를 조사하고 수정하는 현재 상태</span><span class="sxs-lookup"><span data-stu-id="055f2-127">The current status as Microsoft Managed Desktop Operations investigates and remediates the issue</span></span>

