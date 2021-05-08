---
title: 새 디바이스 유효성 검사
description: 디바이스를 주문하기 전에 각 모델 중 하나를 얻은 후 테스트합니다.
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 772636fd72074c8fad30daa3eb25b785519e7772
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52246291"
---
# <a name="validate-new-devices"></a><span data-ttu-id="f1de0-103">새 디바이스 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="f1de0-103">Validate new devices</span></span>

<span data-ttu-id="f1de0-104">처음 Microsoft Managed Desktop 구독자이든, 장기 구독자이든, 처음으로 서비스에 등록하는 장치 모델의 예를 테스트하는 것이 가장 좋은 예입니다.</span><span class="sxs-lookup"><span data-stu-id="f1de0-104">Whether you're completely new to Microsoft Managed Desktop or a long-time subscriber, it's best to test an example of any device model you're enrolling in the service for the first time.</span></span> <span data-ttu-id="f1de0-105">새 디바이스를 주문하거나 기존 디바이스를 다시 사용(Shop Microsoft Managed Desktop 비즈니스 장치 사이트)에서 권장되는 장치를 Windows 10 Pro [마찬가지입니다.](https://www.microsoft.com/windowsforbusiness/view-all-devices)</span><span class="sxs-lookup"><span data-stu-id="f1de0-105">This is true whether you're ordering brand-new devices or reusing existing ones, including devices recommended for Microsoft Managed Desktop on the [Shop Windows 10 Pro business devices](https://www.microsoft.com/windowsforbusiness/view-all-devices) site.</span></span> <span data-ttu-id="f1de0-106">해당 사이트에서 필터로 필터링 영역의 기능을 확장한  다음  을 선택하여 서비스에 권장되는 장치를 **Microsoft Managed Desktop.**</span><span class="sxs-lookup"><span data-stu-id="f1de0-106">At that site, view the devices recommended for use with the service by expanding **Features** in the **Filter by** area, and then selecting **Microsoft Managed Desktop**.</span></span> <span data-ttu-id="f1de0-107">디바이스의 유효성을 검사하면 예상한 사용자 환경을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1de0-107">Validating devices ensures that they'll deliver the user experience you expect.</span></span>

## <a name="validate-devices"></a><span data-ttu-id="f1de0-108">디바이스 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="f1de0-108">Validate devices</span></span>

1. <span data-ttu-id="f1de0-109">다음 문서의 단계를 통해 새 모델의 예를 하나 이상 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="f1de0-109">Take one or more examples of new models through the steps in the following articles:</span></span>
    - [<span data-ttu-id="f1de0-110">Microsoft Managed Desktop 장치 설정</span><span class="sxs-lookup"><span data-stu-id="f1de0-110">Set up Microsoft Managed Desktop devices</span></span>](set-up-devices.md)
    - [<span data-ttu-id="f1de0-111">사용자 환경 현지화</span><span class="sxs-lookup"><span data-stu-id="f1de0-111">Localize the user experience</span></span>](localization.md)
    - [<span data-ttu-id="f1de0-112">Autopilot 및 등록 상태 페이지의 첫 실행 환경</span><span class="sxs-lookup"><span data-stu-id="f1de0-112">First-run experience with Autopilot and the Enrollment Status Page</span></span>](esp-first-run.md)
    - [<span data-ttu-id="f1de0-113">Windows 10 위치 서비스</span><span class="sxs-lookup"><span data-stu-id="f1de0-113">Windows 10 location service</span></span>](device-location.md)
    - [<span data-ttu-id="f1de0-114">앱 제어 시작하기</span><span class="sxs-lookup"><span data-stu-id="f1de0-114">Get started with app control</span></span>](get-started-app-control.md)
    - [<span data-ttu-id="f1de0-115">장치에 앱 배포</span><span class="sxs-lookup"><span data-stu-id="f1de0-115">Deploy apps to devices</span></span>](deploy-apps.md)
2. <span data-ttu-id="f1de0-116">오류, 오류 또는 프롬프트 없이 다음 환경이 작동 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1de0-116">Verify that the following experiences work without any failures, errors, or prompts:</span></span>
    - <span data-ttu-id="f1de0-117">네트워크에 가입하고 사용자가 로그인한 후 Autopilot 환경</span><span class="sxs-lookup"><span data-stu-id="f1de0-117">The Autopilot experience after joining the network and the user signs in</span></span>
    - <span data-ttu-id="f1de0-118">등록 상태 페이지를 사용하도록 설정한 경우 [작동합니다.](esp-first-run.md)</span><span class="sxs-lookup"><span data-stu-id="f1de0-118">If you've enabled the [Enrollment Status Page](esp-first-run.md), it works.</span></span>
    - <span data-ttu-id="f1de0-119">사용자가 응용 프로그램에 로그인할 Office 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1de0-119">User can sign into to Office applications</span></span>
    - <span data-ttu-id="f1de0-120">OneDrive, 문서 및 그림을 Windows 폴더 동기화</span><span class="sxs-lookup"><span data-stu-id="f1de0-120">OneDrive folders sync, including Windows Desktop, Documents, and Pictures</span></span>
    - <span data-ttu-id="f1de0-121">장치에서 업데이트, 정책 및 업무(LINE-OF-BUSINESS) 응용 프로그램을 수신합니다.</span><span class="sxs-lookup"><span data-stu-id="f1de0-121">Device receives updates, policies, and line-of-business applications</span></span>
3. <span data-ttu-id="f1de0-122">장치 인벤토리 보고서에서 [](../working-with-managed-desktop/device-inventory-report.md) 보고된 장치 및 하드웨어 요구 사항을 검토하여 예상과 일치하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="f1de0-122">Review the reported devices and hardware requirements in the [Device inventory report](../working-with-managed-desktop/device-inventory-report.md) to check that they match what you expect.</span></span>

<span data-ttu-id="f1de0-123">문제가 발생하는 경우 관리 [포털에서](../working-with-managed-desktop/admin-support.md) 지원을 요청할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1de0-123">If any problems occur, you can [request support](../working-with-managed-desktop/admin-support.md) in the Admin portal.</span></span>

<span data-ttu-id="f1de0-124">모든 것이 잘 진행되면 배포에 필요한 유효성이 검사된 나머지 장치를 주문할 준비가 된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f1de0-124">If everything goes well, you're ready to order the rest of the validated devices you need for your deployment.</span></span>