---
title: 보고서 모니터링 및 보기-보안 센터
description: Microsoft 365 보안 센터가 보호 및 보안 상태의 요약 정보를 한눈에 제공 하는 방법에 대해 설명 합니다.
keywords: 보안, 맬웨어, Microsoft 365, M365, 보안 센터, 모니터, 보고서, 상태
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
search.appverid: met150
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: e434f6088fa1cd08e6b14e3808007e89f32b83a3
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/13/2020
ms.locfileid: "48431042"
---
# <a name="monitor-and-view-reports-in-the-microsoft-365-security-center"></a><span data-ttu-id="922b7-104">Microsoft 365 보안 센터에서 보고서 모니터링 및 보기</span><span class="sxs-lookup"><span data-stu-id="922b7-104">Monitor and view reports in the Microsoft 365 security center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="922b7-105">Microsoft 365 보안 센터에서는 Microsoft 365 환경 전체의 보호 및 보안 상태에 대 한 요약을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="922b7-105">The Microsoft 365 security center provides a summary of protection and security statuses across your Microsoft 365 environment.</span></span>

<span data-ttu-id="922b7-106">보안 센터에는 다양 한 영역을 다루는 카드 호스트를 포함 하는 **보고서** 섹션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="922b7-106">The security center includes a **Reports** section which features a host of cards covering a variety of areas.</span></span> <span data-ttu-id="922b7-107">보안 분석가와 관리자는 일상 작업의 일부로 카드를 추적할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="922b7-107">Security analysts and administrators can track the cards as part of their day-to-day operations.</span></span> <span data-ttu-id="922b7-108">드릴 다운 시 카드는 자세한 보고서와 경우에 따라 관리 옵션을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="922b7-108">On drill-down, cards provide detailed reports and, in some cases, management options.</span></span>

## <a name="customize-views"></a><span data-ttu-id="922b7-109">보기 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="922b7-109">Customize views</span></span>

<span data-ttu-id="922b7-110">기본적으로 카드는 다음 범주로 분류 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="922b7-110">By default, cards are grouped into these categories:</span></span>
  
* <span data-ttu-id="922b7-111">[Id](monitor-and-report-identities.md) -사용자 계정 및 자격 증명</span><span class="sxs-lookup"><span data-stu-id="922b7-111">[Identities](monitor-and-report-identities.md) - user accounts and credentials</span></span>
* <span data-ttu-id="922b7-112">[데이터](monitor-data.md) -전자 메일 및 문서 내용</span><span class="sxs-lookup"><span data-stu-id="922b7-112">[Data](monitor-data.md) - email and document contents</span></span>
* <span data-ttu-id="922b7-113">[장치](monitor-devices.md) -컴퓨터, 휴대폰 및 기타 장치</span><span class="sxs-lookup"><span data-stu-id="922b7-113">[Devices](monitor-devices.md) - computers, mobile phones, and other devices</span></span>
* <span data-ttu-id="922b7-114">[앱](monitor-apps.md) -프로그램 및 연결 된 온라인 서비스</span><span class="sxs-lookup"><span data-stu-id="922b7-114">[Apps](monitor-apps.md) - programs and attached online services</span></span>

<span data-ttu-id="922b7-115">그룹화 방법 **항목**으로 전환 하 여 카드를 다시 정렬 하 고 다음 항목으로 그룹화 합니다.</span><span class="sxs-lookup"><span data-stu-id="922b7-115">Switch to **Group by topic**, to rearrange the cards and group them into the following topics:</span></span>

* <span data-ttu-id="922b7-116">**위험** -계정 및 장치와 같이 위험에 노출 될 수 있는 엔터티를 강조 표시 하는 카드입니다.</span><span class="sxs-lookup"><span data-stu-id="922b7-116">**Risk** - cards that highlight entities, such as accounts and devices, that might be at risk.</span></span> <span data-ttu-id="922b7-117">이러한 카드는 새 위협 캠페인 및 권한이 부여 된 클라우드 앱과 같은 가능한 위험 출처를 강조 합니다.</span><span class="sxs-lookup"><span data-stu-id="922b7-117">These cards also highlight possible sources of risk, such as new threat campaigns and privileged cloud apps</span></span>  
* <span data-ttu-id="922b7-118">**검색 경향** -새로운 위협 감지, 예외 및 정책 위반을 강조 표시 하는 카드</span><span class="sxs-lookup"><span data-stu-id="922b7-118">**Detection trends** - cards that highlight new threat detections, anomalies, and policy violations</span></span>
* <span data-ttu-id="922b7-119">관리 서비스에 대 한 장치 온 보 딩 상태를 포함 하 여 보안 제어의 구성 및 배포를 다루는 **구성 및 상태** 카드</span><span class="sxs-lookup"><span data-stu-id="922b7-119">**Configuration and health** - cards that cover the configuration and deployment of security controls, including device onboarding states to management services</span></span>
* <span data-ttu-id="922b7-120">**기타** -기타 항목 아래에 분류 되지 않은 다른 모든 카드</span><span class="sxs-lookup"><span data-stu-id="922b7-120">**Other** - all other cards not categorized under other topics</span></span>
