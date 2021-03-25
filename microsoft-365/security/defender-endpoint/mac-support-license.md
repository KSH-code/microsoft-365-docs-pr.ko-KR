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
ms.openlocfilehash: 44105ae8d1872c3ecefcf84a5e2efef122849b8c
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51074468"
---
# <a name="troubleshoot-license-issues-for-microsoft-defender-for-endpoint-for-mac"></a><span data-ttu-id="b586b-104">Mac용 끝점용 Microsoft Defender의 라이선스 문제 해결</span><span class="sxs-lookup"><span data-stu-id="b586b-104">Troubleshoot license issues for Microsoft Defender for Endpoint for Mac</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="b586b-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="b586b-105">**Applies to:**</span></span>

- [<span data-ttu-id="b586b-106">Mac용 끝점용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="b586b-106">Microsoft Defender for Endpoint for Mac</span></span>](microsoft-defender-endpoint-mac.md)
- [<span data-ttu-id="b586b-107">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="b586b-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="b586b-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b586b-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="b586b-109">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="b586b-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="b586b-110">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="b586b-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="b586b-111">[Mac용 끝점용 Microsoft Defender](microsoft-defender-endpoint-mac.md) 및 [](mac-install-manually.md) 수동 배포 테스트 또는 PoC(개념 증명)를 진행하는 동안 다음 오류가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b586b-111">While you are going through [Microsoft Defender for Endpoint for Mac](microsoft-defender-endpoint-mac.md) and [Manual deployment](mac-install-manually.md) testing or a Proof Of Concept (PoC), you might get the following error:</span></span>

![라이선스 오류 이미지](images/no-license-found.png)

<span data-ttu-id="b586b-113">**메시지:**</span><span class="sxs-lookup"><span data-stu-id="b586b-113">**Message:**</span></span> 

<span data-ttu-id="b586b-114">라이선스를 찾을 수 없음</span><span class="sxs-lookup"><span data-stu-id="b586b-114">No license found</span></span>

<span data-ttu-id="b586b-115">조직에 Microsoft 365 Enterprise 구독에 대한 라이선스가 없는 것 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b586b-115">Looks like your organization does not have a license for Microsoft 365 Enterprise subscription.</span></span>

<span data-ttu-id="b586b-116">관리자에게 문의하십시오.</span><span class="sxs-lookup"><span data-stu-id="b586b-116">Contact your administrator for help.</span></span>

<span data-ttu-id="b586b-117">**원인:**</span><span class="sxs-lookup"><span data-stu-id="b586b-117">**Cause:**</span></span> 

<span data-ttu-id="b586b-118">MacOS용 끝점용 Microsoft Defender 패키지("설치 패키지 다운로드")를 배포하거나 설치했지만 구성 스크립트("온보딩 패키지 다운로드")를 실행한 것일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b586b-118">You deployed and/or installed the Microsoft Defender for Endpoint for macOS package ("Download installation package") but you might have run the configuration script ("Download onboarding package").</span></span>

<span data-ttu-id="b586b-119">**해결 방법:**</span><span class="sxs-lookup"><span data-stu-id="b586b-119">**Solution:**</span></span>

<span data-ttu-id="b586b-120">클라이언트 구성에 MicrosoftDefenderATPOnboardingMacOs.py [지침에 따릅니다.](mac-install-manually.md#client-configuration)</span><span class="sxs-lookup"><span data-stu-id="b586b-120">Follow the MicrosoftDefenderATPOnboardingMacOs.py instructions documented here: [Client configuration](mac-install-manually.md#client-configuration)</span></span>

