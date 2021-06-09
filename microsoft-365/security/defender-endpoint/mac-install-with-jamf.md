---
title: Jamf 2013을 통해 macOS에서 끝점용 Microsoft Defender Pro
description: Jamf 2013을 통해 macOS에서 끝점용 Microsoft Defender Pro
keywords: microsoft, defender, Endpoint용 Microsoft Defender, mac, 설치, 배포, 제거, intune, jamfpro, macos, catalina, mojave, high sierra
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
ms.openlocfilehash: b41c5ec827e110e0101c50ce7babeb6442096edb
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842893"
---
# <a name="deploying-microsoft-defender-for-endpoint-on-macos-with-jamf-pro"></a><span data-ttu-id="0f9e8-104">Jamf 2013을 통해 macOS에서 끝점용 Microsoft Defender Pro</span><span class="sxs-lookup"><span data-stu-id="0f9e8-104">Deploying Microsoft Defender for Endpoint on macOS with Jamf Pro</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="0f9e8-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="0f9e8-105">**Applies to:**</span></span>
- [<span data-ttu-id="0f9e8-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="0f9e8-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="0f9e8-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0f9e8-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="0f9e8-108">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="0f9e8-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="0f9e8-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="0f9e8-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="0f9e8-110">Jamf 2013을 통해 macOS에서 끝점용 Microsoft Defender를 배포하는 Pro.</span><span class="sxs-lookup"><span data-stu-id="0f9e8-110">Learn how to deploy Microsoft Defender for Endpoint on macOS with Jamf Pro.</span></span>

> [!NOTE]
> <span data-ttu-id="0f9e8-111">MacOS 카탈로니아어(10.15.4) 이상 버전의 macOS를 사용하는 경우 macOS 카탈로니아 및 최신 [버전의 macOS에](/microsoft-365/security/defender-endpoint/mac-sysext-policies)대한 새 구성 프로필을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0f9e8-111">If you are using macOS Catalina (10.15.4) or newer versions of macOS, see [New configuration profiles for macOS Catalina and newer versions of macOS](/microsoft-365/security/defender-endpoint/mac-sysext-policies).</span></span>

<span data-ttu-id="0f9e8-112">이것은 여러 단계 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="0f9e8-112">This is a multi step process.</span></span> <span data-ttu-id="0f9e8-113">다음 단계를 모두 완료해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f9e8-113">You'll need to complete all of the following steps:</span></span>

- [<span data-ttu-id="0f9e8-114">Jamf 포털에 로그인</span><span class="sxs-lookup"><span data-stu-id="0f9e8-114">Login to the Jamf Portal</span></span>](mac-install-jamfpro-login.md)
- [<span data-ttu-id="0f9e8-115">Jamf 2013에서 macOS 장치 그룹에서 끝점용 Microsoft Defender Pro</span><span class="sxs-lookup"><span data-stu-id="0f9e8-115">Setup the Microsoft Defender for Endpoint on macOS device groups in Jamf Pro</span></span>](mac-jamfpro-device-groups.md)
- [<span data-ttu-id="0f9e8-116">Jamf 2013에서 macOS에서 끝점용 Microsoft Defender Pro</span><span class="sxs-lookup"><span data-stu-id="0f9e8-116">Setup the Microsoft Defender for Endpoint on macOS policies in Jamf Pro</span></span>](mac-jamfpro-policies.md)
- [<span data-ttu-id="0f9e8-117">MacOS 장치에서 Endpoint용 Microsoft Defender를 Jamf 2013에 Pro</span><span class="sxs-lookup"><span data-stu-id="0f9e8-117">Enroll the Microsoft Defender for Endpoint on macOS devices into Jamf Pro</span></span>](mac-jamfpro-enroll-devices.md)




