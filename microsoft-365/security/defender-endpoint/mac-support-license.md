---
title: Mac에서 끝점용 Microsoft Defender의 라이선스 문제 해결
description: Mac의 끝점용 Microsoft Defender에서 라이선스 문제를 해결합니다.
keywords: Microsoft, defender, Endpoint용 Microsoft Defender, mac, 성능
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 1f8428c2995eec2dece290049eda67a3683b4c1e
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52244983"
---
# <a name="troubleshoot-license-issues-for-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="92357-104">macOS에서 끝점용 Microsoft Defender의 라이선스 문제 해결</span><span class="sxs-lookup"><span data-stu-id="92357-104">Troubleshoot license issues for Microsoft Defender for Endpoint on macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="92357-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="92357-105">**Applies to:**</span></span>

- [<span data-ttu-id="92357-106">Microsoft Defender for Endpoint(macOS용)</span><span class="sxs-lookup"><span data-stu-id="92357-106">Microsoft Defender for Endpoint on macOS</span></span>](microsoft-defender-endpoint-mac.md)
- [<span data-ttu-id="92357-107">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="92357-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="92357-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="92357-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="92357-109">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="92357-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="92357-110">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="92357-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="92357-111">[macOS의 끝점용 Microsoft Defender](microsoft-defender-endpoint-mac.md) 및 [](mac-install-manually.md) 수동 배포 테스트 또는 PoC(개념 증명)를 진행하는 동안 다음 오류가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92357-111">While you are going through [Microsoft Defender for Endpoint on macOS](microsoft-defender-endpoint-mac.md) and [Manual deployment](mac-install-manually.md) testing or a Proof Of Concept (PoC), you might get the following error:</span></span>

![라이선스 오류 이미지](images/no-license-found.png)

<span data-ttu-id="92357-113&quot;>**메시지:**</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;92357-113&quot;>**Message:**</span></span> 

<span data-ttu-id=&quot;92357-114&quot;>라이선스를 찾을 수 없음</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;92357-114&quot;>No license found</span></span>

<span data-ttu-id=&quot;92357-115&quot;>조직에 구독에 대한 라이선스가 Microsoft 365 Enterprise 것 같아야 합니다.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;92357-115&quot;>Looks like your organization does not have a license for Microsoft 365 Enterprise subscription.</span></span>

<span data-ttu-id=&quot;92357-116&quot;>관리자에게 문의하십시오.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;92357-116&quot;>Contact your administrator for help.</span></span>

<span data-ttu-id=&quot;92357-117&quot;>**원인:**</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;92357-117&quot;>**Cause:**</span></span> 

<span data-ttu-id=&quot;92357-118&quot;>MacOS용 끝점용 Microsoft Defender 패키지(&quot;설치 패키지 다운로드")를 배포하거나 설치했으나 구성 스크립트("온보딩 패키지 다운로드")를 실행했거나 사용자에게 라이선스를 할당하지 않은 것일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92357-118">You deployed and/or installed the Microsoft Defender for Endpoint for macOS package ("Download installation package"), but you might have run the configuration script ("Download onboarding package"), or you have not assigned a license to the user.</span></span>

<span data-ttu-id="92357-119">**해결 방법:**</span><span class="sxs-lookup"><span data-stu-id="92357-119">**Solution:**</span></span>

<span data-ttu-id="92357-120">클라이언트 구성에 MicrosoftDefenderATPOnboardingMacOs.py [지침에 따릅니다.](mac-install-manually.md#client-configuration)</span><span class="sxs-lookup"><span data-stu-id="92357-120">Follow the MicrosoftDefenderATPOnboardingMacOs.py instructions documented here: [Client configuration](mac-install-manually.md#client-configuration)</span></span>
