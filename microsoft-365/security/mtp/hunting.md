---
title: Microsoft 365의 기타 위협 요소 구하기
description: Microsoft 365 보안 센터의 위협 검색 기능을 사용 하 여 위반 및 기타 위협 요소를 사전에 찾기
keywords: 보안, 맬웨어, Microsoft 365, M365, 보안 센터, 헌트, 사냥, Microsoft Defender ATP, Office 365 ATP, Azure ATP, 고급 구하기
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
ms.author: lomayor
author: lomayor
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
search.appverid: met150
ms.openlocfilehash: 795a7d88c2b6021a5bdd665b3787644b50fb346a
ms.sourcegitcommit: 0c9c28a87201c7470716216d99175356fb3d1a47
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/09/2019
ms.locfileid: "39909431"
---
# <a name="hunt-for-threats-in-microsoft-365"></a><span data-ttu-id="72e4b-104">Microsoft 365의 위협에 대 한 사냥</span><span class="sxs-lookup"><span data-stu-id="72e4b-104">Hunt for threats in Microsoft 365</span></span>

<span data-ttu-id="72e4b-105">Microsoft 365 보안 센터의 위협 검색 기능을 사용 하 여 조직의 전자 메일 및 데이터, 장치 및 id에 영향을 주는 위협을 사전에 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72e4b-105">With threat hunting capabilities in the Microsoft 365 security center, you can proactively find threats in your organization affecting email and data, devices, and identities.</span></span> <span data-ttu-id="72e4b-106">**구하기** 화면에서 다양 한 솔루션에서 제공 하는 위협 요소 도구에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72e4b-106">From the **Hunting** screen, you can access threat hunting tools made available by various solutions:</span></span>
- <span data-ttu-id="72e4b-107">Office 365 ATP- [전자 메일 및 데이터에 대 한 위협을 사냥 합니다](../office-365-security/office-365-atp.md) .</span><span class="sxs-lookup"><span data-stu-id="72e4b-107">Office 365 ATP — [hunt for threats to email and data](../office-365-security/office-365-atp.md)</span></span>
- <span data-ttu-id="72e4b-108">Microsoft Defender ATP- [장치에 대 한 위협 구하기](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting)</span><span class="sxs-lookup"><span data-stu-id="72e4b-108">Microsoft Defender ATP — [hunt for threats to devices](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting)</span></span>
- <span data-ttu-id="72e4b-109">Azure ATP- [id에 대 한 위협을 사냥 합니다](https://docs.microsoft.com/azure-advanced-threat-protection/investigate-a-user) .</span><span class="sxs-lookup"><span data-stu-id="72e4b-109">Azure ATP — [hunt for threats to identities](https://docs.microsoft.com/azure-advanced-threat-protection/investigate-a-user)</span></span>

![사냥 페이지](../images/hunt.png)


## <a name="hunt-with-microsoft-threat-protection"></a><span data-ttu-id="72e4b-111">Microsoft Threat Protection을 사용한 헌트</span><span class="sxs-lookup"><span data-stu-id="72e4b-111">Hunt with Microsoft Threat Protection</span></span>

<span data-ttu-id="72e4b-112">Microsoft [Threat Protection을 설정](mtp-enable.md) 하 여 microsoft 365 보안 센터에서 고급 구하기 쿼리 인터페이스를 직접 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="72e4b-112">[Turn on Microsoft Threat Protection](mtp-enable.md) to get the advanced hunting query interface directly in the Microsoft 365 security center.</span></span> <span data-ttu-id="72e4b-113">[고급](advanced-hunting-overview.md)검색을 사용 하 여 MICROSOFT Defender atp에서 데이터를 확인 하 고, 등록 장치의 데이터를 포함 하 고, OFFICE 365 ATP를 통해 전자 메일에서 데이터를 제공 하는 단일 쿼리를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72e4b-113">With [advanced hunting](advanced-hunting-overview.md), you can create single queries that look into data from both Microsoft Defender ATP, covering data from onboarded devices, and Office 365 ATP, providing data from emails.</span></span>

## <a name="related-topics"></a><span data-ttu-id="72e4b-114">관련 항목</span><span class="sxs-lookup"><span data-stu-id="72e4b-114">Related topics</span></span>
- [<span data-ttu-id="72e4b-115">고급 구하기 개요</span><span class="sxs-lookup"><span data-stu-id="72e4b-115">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="72e4b-116">Microsoft 위협 보호 개요</span><span class="sxs-lookup"><span data-stu-id="72e4b-116">Microsoft Threat Protection overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="72e4b-117">Microsoft Threat Protection 설정</span><span class="sxs-lookup"><span data-stu-id="72e4b-117">Turn on Microsoft Threat Protection</span></span>](mtp-enable.md)