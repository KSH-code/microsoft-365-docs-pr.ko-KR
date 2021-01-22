---
title: 데이터 모니터링 & 보고 - 보안 센터
description: Microsoft 365 보안 센터에서 무단 데이터 공개로 이어질 수 있는 사용자 활동을 추적하는 방법을 알아보습니다.
keywords: 보안, 맬웨어, Microsoft 365, M365, 보안 센터, 모니터링, 보고서, 데이터
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: a71f7a7284c2734c4cab2d4e9501a17f4e9ec6e7
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930441"
---
# <a name="data-monitoring-and-reporting-in-the-microsoft-365-security-center"></a><span data-ttu-id="91977-104">Microsoft 365 보안 센터의 데이터 모니터링 및 보고</span><span class="sxs-lookup"><span data-stu-id="91977-104">Data monitoring and reporting in the Microsoft 365 security center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="91977-105">**데이터** 범주를 통해서 승인받지 않은 데이터 노출이 발생할 가능성이 있는 사용자 활동을 추적할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91977-105">The **Data** category helps track user activity that could lead to unauthorized data disclosure.</span></span> <span data-ttu-id="91977-106">기존 DLP 정책 보고서와 타사 DLP 정책 일치 보고서의 재작업입니다.</span><span class="sxs-lookup"><span data-stu-id="91977-106">They are the rework of existing DLP policy reports plus a third-party DLP policy match report.</span></span>

<span data-ttu-id="91977-107">다음을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91977-107">You can see:</span></span>

- <span data-ttu-id="91977-108">클라우드 앱에서 파일을 가장 많이 공유한 사용자</span><span class="sxs-lookup"><span data-stu-id="91977-108">Users who share the most files from cloud apps</span></span>
- <span data-ttu-id="91977-109">발생한 DLP 정책의 수</span><span class="sxs-lookup"><span data-stu-id="91977-109">How many DLP policy matches occurred</span></span>
- <span data-ttu-id="91977-110">DLP 정책이 무시되거나 가양성이 보고된 건수</span><span class="sxs-lookup"><span data-stu-id="91977-110">How many DLP policies overrides or false positives are reported</span></span>
- <span data-ttu-id="91977-111">Microsoft Cloud App Security를 통해 타사 클라우드 서비스에서 DLP 정책 일치가 발생한 수</span><span class="sxs-lookup"><span data-stu-id="91977-111">How many DLP policy matches happened in third-party cloud services via Microsoft Cloud App Security</span></span>

![보고서 페이지의 데이터 범주](../../media/data.png)
