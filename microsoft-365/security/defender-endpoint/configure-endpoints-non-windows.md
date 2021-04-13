---
title: 끝점용 Microsoft Defender 서비스에 비 Windows 장치 온보딩
description: 센서 데이터를 Microsoft Defender ATP 서비스로 보낼 수 있도록 비 Windows 장치를 구성합니다.
keywords: 비 Windows 장치, macos, linux, 장치 관리, Windows ATP 장치 구성, 끝점 장치에 대한 Microsoft Defender 구성
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 71f230f557792d75659dc4dbfc5911811514d5ea
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/13/2021
ms.locfileid: "51687880"
---
# <a name="onboard-non-windows-devices"></a><span data-ttu-id="c93f5-104">Windows가 아닌 장치 온보딩</span><span class="sxs-lookup"><span data-stu-id="c93f5-104">Onboard non-Windows devices</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="c93f5-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="c93f5-105">**Applies to:**</span></span>
- <span data-ttu-id="c93f5-106">[엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037) </span><span class="sxs-lookup"><span data-stu-id="c93f5-106">[Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)</span></span>
- [<span data-ttu-id="c93f5-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c93f5-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="c93f5-108">**플랫폼**</span><span class="sxs-lookup"><span data-stu-id="c93f5-108">**Platforms**</span></span>
- <span data-ttu-id="c93f5-109">macOS</span><span class="sxs-lookup"><span data-stu-id="c93f5-109">macOS</span></span>
- <span data-ttu-id="c93f5-110">Linux</span><span class="sxs-lookup"><span data-stu-id="c93f5-110">Linux</span></span>

><span data-ttu-id="c93f5-111">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="c93f5-111">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="c93f5-112">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="c93f5-112">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-nonwindows-abovefoldlink) 

<span data-ttu-id="c93f5-113">Endpoint용 Defender는 Windows가 아닌 플랫폼뿐만 아니라 Windows에 대한 중앙 집중식 보안 운영 환경을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c93f5-113">Defender for Endpoint provides a centralized security operations experience for Windows as well as non-Windows platforms.</span></span> <span data-ttu-id="c93f5-114">Microsoft Defender 보안 센터에서 지원되는 다양한 OS(운영 체제)에서 경고를 보고 조직의 네트워크를 보다 잘 보호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c93f5-114">You'll be able to see alerts from various supported operating systems (OS) in Microsoft Defender Security Center and better protect your organization's network.</span></span> 

<span data-ttu-id="c93f5-115">통합을 위해 Endpoint용 Defender와 호환되는 정확한 Linux 배포판 및 macOS 버전을 알아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c93f5-115">You'll need to know the exact Linux distros and macOS versions that are compatible with Defender for Endpoint for the integration to work.</span></span> <span data-ttu-id="c93f5-116">자세한 내용은 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c93f5-116">For more information, see:</span></span>
- [<span data-ttu-id="c93f5-117">Linux 시스템 요구 사항의 끝점용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="c93f5-117">Microsoft Defender for Endpoint on Linux system requirements</span></span>](microsoft-defender-endpoint-linux.md#system-requirements)  
- <span data-ttu-id="c93f5-118">[MacOS 시스템 요구 사항의 끝점용 Microsoft Defender](microsoft-defender-endpoint-mac.md#system-requirements)</span><span class="sxs-lookup"><span data-stu-id="c93f5-118">[Microsoft Defender for Endpoint on macOS system requirements](microsoft-defender-endpoint-mac.md#system-requirements).</span></span>

## <a name="onboarding-non-windows-devices"></a><span data-ttu-id="c93f5-119">비 Windows 장치 온보드</span><span class="sxs-lookup"><span data-stu-id="c93f5-119">Onboarding non-Windows devices</span></span>
<span data-ttu-id="c93f5-120">비 Windows 장치를 온보드하려면 다음 단계를 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c93f5-120">You'll need to take the following steps to onboard non-Windows devices:</span></span>
1. <span data-ttu-id="c93f5-121">기본 온보더링 방법을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c93f5-121">Select your preferred method of onboarding:</span></span>

   - <span data-ttu-id="c93f5-122">macOS 장치의 경우 Microsoft Defender ATP 또는 타사 솔루션을 통해 온보딩할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c93f5-122">For macOS devices, you can choose to onboard through Microsoft Defender ATP or through a third-party solution.</span></span> <span data-ttu-id="c93f5-123">자세한 내용은 [Mac용 끝점용 Microsoft Defender를 참조하세요.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint-mac)</span><span class="sxs-lookup"><span data-stu-id="c93f5-123">For more information, see [Microsoft Defender for Endpoint for Mac](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint-mac).</span></span>

   - <span data-ttu-id="c93f5-124">다른 비 Windows 장치의 경우 타사 통합을 통해 비 Windows 장치 **온보드를 선택하십시오.**</span><span class="sxs-lookup"><span data-stu-id="c93f5-124">For other non-Windows devices choose **Onboard non-Windows devices through third-party integration**.</span></span>   
    1. <span data-ttu-id="c93f5-125">탐색 창에서 상호 교환 파트너 **를**  >  **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="c93f5-125">In the navigation pane, select **Interoperability** > **Partners**.</span></span> <span data-ttu-id="c93f5-126">타사 솔루션이 나열되어 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="c93f5-126">Make sure the third-party solution is listed.</span></span>
    2. <span data-ttu-id="c93f5-127">파트너 **응용 프로그램 탭에서** 비 Windows 장치를 지원하는 파트너를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c93f5-127">In the **Partner Applications** tab, select the partner that supports your non-Windows devices.</span></span>
    3. <span data-ttu-id="c93f5-128">파트너 **페이지 열기 를** 선택하여 파트너 페이지를 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c93f5-128">Select **Open partner page** to open the partner's page.</span></span> <span data-ttu-id="c93f5-129">페이지에 제공된 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="c93f5-129">Follow the instructions provided on the page.</span></span>
    4. <span data-ttu-id="c93f5-130">계정을 만들거나 파트너 솔루션을 신청한 후 조직의 테넌트 전역 관리자에게 파트너 응용 프로그램의 사용 권한 요청을 수락할지 묻는 단계가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c93f5-130">After creating an account or subscribing to the partner solution, you should get to a stage where a tenant Global Admin in your organization is asked to accept a permission request from the partner application.</span></span> <span data-ttu-id="c93f5-131">사용 권한 요청을 신중하게 읽어 필요한 서비스에 맞춰지십시오.</span><span class="sxs-lookup"><span data-stu-id="c93f5-131">Read the permission request carefully to make sure that it is aligned with the service that you require.</span></span> 

        
2. <span data-ttu-id="c93f5-132">타사 솔루션의 지침에 따라 검색 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c93f5-132">Run a detection test by following the instructions of the third-party solution.</span></span>

## <a name="offboard-non-windows-devices"></a><span data-ttu-id="c93f5-133">비 Windows 장치 온보드</span><span class="sxs-lookup"><span data-stu-id="c93f5-133">Offboard non-Windows devices</span></span>

1. <span data-ttu-id="c93f5-134">타사의 설명서에 따라 끝점용 Microsoft Defender에서 타사 솔루션 연결을 끊습니다.</span><span class="sxs-lookup"><span data-stu-id="c93f5-134">Follow the third-party's documentation to disconnect the third-party solution from Microsoft Defender for Endpoint.</span></span>

2. <span data-ttu-id="c93f5-135">Azure AD 테넌트에서 타사 솔루션에 대한 사용 권한을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="c93f5-135">Remove permissions for the third-party solution in your Azure AD tenant.</span></span>
   1. <span data-ttu-id="c93f5-136">[Azure 포털](https://portal.azure.com)에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="c93f5-136">Sign in to the [Azure portal](https://portal.azure.com).</span></span>
   2. <span data-ttu-id="c93f5-137">**Azure Active Directory > 엔터프라이즈 응용 프로그램을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="c93f5-137">Select **Azure Active Directory > Enterprise Applications**.</span></span>
   3. <span data-ttu-id="c93f5-138">오프보드할 응용 프로그램을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c93f5-138">Select the application you'd like to offboard.</span></span>
   4. <span data-ttu-id="c93f5-139">삭제 **단추를** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c93f5-139">Select the **Delete** button.</span></span>


## <a name="related-topics"></a><span data-ttu-id="c93f5-140">관련 항목</span><span class="sxs-lookup"><span data-stu-id="c93f5-140">Related topics</span></span>
- [<span data-ttu-id="c93f5-141">그룹 정책을 통한 Windows 10 장치 온보딩</span><span class="sxs-lookup"><span data-stu-id="c93f5-141">Onboard Windows 10 devices</span></span>](configure-endpoints.md)
- [<span data-ttu-id="c93f5-142">서버 온보드</span><span class="sxs-lookup"><span data-stu-id="c93f5-142">Onboard servers</span></span>](configure-server-endpoints.md)
- [<span data-ttu-id="c93f5-143">프록시 및 인터넷 연결 설정 구성</span><span class="sxs-lookup"><span data-stu-id="c93f5-143">Configure proxy and Internet connectivity settings</span></span>](configure-proxy-internet.md)
- [<span data-ttu-id="c93f5-144">끝점 온보딩 문제에 대한 Microsoft Defender 문제 해결</span><span class="sxs-lookup"><span data-stu-id="c93f5-144">Troubleshooting Microsoft Defender for Endpoint onboarding issues</span></span>](troubleshoot-onboarding.md)
