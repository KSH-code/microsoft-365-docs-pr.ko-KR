---
title: Jamf Pro를 통해 macOS용 끝점용 Microsoft Defender 배포
description: Jamf Pro를 통해 macOS용 끝점용 Microsoft Defender 배포
keywords: microsoft, defender, atp, mac, 설치, 배포, 제거, intune, jamfpro, macos, 카탈로나, mojave, high sierra
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
ms.openlocfilehash: e49a56b138e792f06229345d19a5867c9f6438af
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2021
ms.locfileid: "51862262"
---
# <a name="deploying-microsoft-defender-for-endpoint-on-macos-with-jamf-pro"></a><span data-ttu-id="a323d-104">Jamf Pro를 통해 macOS에서 끝점용 Microsoft Defender 배포</span><span class="sxs-lookup"><span data-stu-id="a323d-104">Deploying Microsoft Defender for Endpoint on macOS with Jamf Pro</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="a323d-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="a323d-105">**Applies to:**</span></span>
- [<span data-ttu-id="a323d-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="a323d-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="a323d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a323d-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="a323d-108">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="a323d-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="a323d-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="a323d-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="a323d-110">Jamf Pro를 통해 macOS에서 끝점용 Microsoft Defender를 배포하는 방법을 학습합니다.</span><span class="sxs-lookup"><span data-stu-id="a323d-110">Learn how to deploy Microsoft Defender for Endpoint on macOS with Jamf Pro.</span></span>

> [!NOTE]
> <span data-ttu-id="a323d-111">MacOS 카탈로니아어(10.15.4) 이상 버전의 macOS를 사용하는 경우 macOS 카탈로니아 및 최신 [버전의 macOS에](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/mac-sysext-policies)대한 새 구성 프로필을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a323d-111">If you are using macOS Catalina (10.15.4) or newer versions of macOS, see [New configuration profiles for macOS Catalina and newer versions of macOS](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/mac-sysext-policies).</span></span>

<span data-ttu-id="a323d-112">이것은 여러 단계 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="a323d-112">This is a multi step process.</span></span> <span data-ttu-id="a323d-113">다음 단계를 모두 완료해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a323d-113">You'll need to complete all of the following steps:</span></span>

- [<span data-ttu-id="a323d-114">Jamf 포털에 로그인</span><span class="sxs-lookup"><span data-stu-id="a323d-114">Login to the Jamf Portal</span></span>](mac-install-jamfpro-login.md)
- [<span data-ttu-id="a323d-115">Jamf Pro에서 macOS 장치 그룹에서 끝점용 Microsoft Defender 설정</span><span class="sxs-lookup"><span data-stu-id="a323d-115">Setup the Microsoft Defender for Endpoint on macOS device groups in Jamf Pro</span></span>](mac-jamfpro-device-groups.md)
- [<span data-ttu-id="a323d-116">Jamf Pro에서 macOS에서 끝점용 Microsoft Defender 설정</span><span class="sxs-lookup"><span data-stu-id="a323d-116">Setup the Microsoft Defender for Endpoint on macOS policies in Jamf Pro</span></span>](mac-jamfpro-policies.md)
- [<span data-ttu-id="a323d-117">MacOS 장치에서 Endpoint용 Microsoft Defender를 Jamf Pro에 등록</span><span class="sxs-lookup"><span data-stu-id="a323d-117">Enroll the Microsoft Defender for Endpoint on macOS devices into Jamf Pro</span></span>](mac-jamfpro-enroll-devices.md)




