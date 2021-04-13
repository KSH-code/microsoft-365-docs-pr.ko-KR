---
title: Mac용 Microsoft Defender ATP의 라이선스 문제 해결
description: Mac용 Microsoft Defender ATP에서 라이선스 문제를 해결합니다.
keywords: microsoft, defender, atp, mac, 성능
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
ms.openlocfilehash: 69dd85394837bb7f37e7d277110c8a5dbf7b6506
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/13/2021
ms.locfileid: "51689116"
---
# <a name="troubleshoot-license-issues-for-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="2cb0c-104">macOS에서 끝점용 Microsoft Defender의 라이선스 문제 해결</span><span class="sxs-lookup"><span data-stu-id="2cb0c-104">Troubleshoot license issues for Microsoft Defender for Endpoint on macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="2cb0c-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="2cb0c-105">**Applies to:**</span></span>

- [<span data-ttu-id="2cb0c-106">MacOS의 끝점용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="2cb0c-106">Microsoft Defender for Endpoint on macOS</span></span>](microsoft-defender-endpoint-mac.md)
- <span data-ttu-id="2cb0c-107">[엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037) </span><span class="sxs-lookup"><span data-stu-id="2cb0c-107">[Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)</span></span>
- [<span data-ttu-id="2cb0c-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2cb0c-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="2cb0c-109">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="2cb0c-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="2cb0c-110">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="2cb0c-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="2cb0c-111">[macOS의 끝점용 Microsoft Defender](microsoft-defender-endpoint-mac.md) 및 [](mac-install-manually.md) 수동 배포 테스트 또는 PoC(개념 증명)를 진행하는 동안 다음 오류가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cb0c-111">While you are going through [Microsoft Defender for Endpoint on macOS](microsoft-defender-endpoint-mac.md) and [Manual deployment](mac-install-manually.md) testing or a Proof Of Concept (PoC), you might get the following error:</span></span>

![라이선스 오류 이미지](images/no-license-found.png)

<span data-ttu-id="2cb0c-113&quot;>**메시지:**</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;2cb0c-113&quot;>**Message:**</span></span> 

<span data-ttu-id=&quot;2cb0c-114&quot;>라이선스를 찾을 수 없음</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;2cb0c-114&quot;>No license found</span></span>

<span data-ttu-id=&quot;2cb0c-115&quot;>조직에 Microsoft 365 Enterprise 구독에 대한 라이선스가 없는 것 같아야 합니다.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;2cb0c-115&quot;>Looks like your organization does not have a license for Microsoft 365 Enterprise subscription.</span></span>

<span data-ttu-id=&quot;2cb0c-116&quot;>관리자에게 문의하십시오.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;2cb0c-116&quot;>Contact your administrator for help.</span></span>

<span data-ttu-id=&quot;2cb0c-117&quot;>**원인:**</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;2cb0c-117&quot;>**Cause:**</span></span> 

<span data-ttu-id=&quot;2cb0c-118&quot;>MacOS 패키지(&quot;설치 패키지 다운로드")에 끝점용 Microsoft Defender를 배포 및/또는 설치했지만 구성 스크립트("온보딩 패키지 다운로드")를 실행한 것일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cb0c-118">You deployed and/or installed the Microsoft Defender for Endpoint on macOS package ("Download installation package") but you might have run the configuration script ("Download onboarding package").</span></span>

<span data-ttu-id="2cb0c-119">**해결 방법:**</span><span class="sxs-lookup"><span data-stu-id="2cb0c-119">**Solution:**</span></span>

<span data-ttu-id="2cb0c-120">클라이언트 구성에 MicrosoftDefenderATPOnboardingMacOs.py [지침에 따릅니다.](mac-install-manually.md#client-configuration)</span><span class="sxs-lookup"><span data-stu-id="2cb0c-120">Follow the MicrosoftDefenderATPOnboardingMacOs.py instructions documented here: [Client configuration](mac-install-manually.md#client-configuration)</span></span>

