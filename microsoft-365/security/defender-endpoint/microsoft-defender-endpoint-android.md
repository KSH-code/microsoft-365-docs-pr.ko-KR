---
title: Microsoft Defender for Endpoint(Android용)
ms.reviewer: ''
description: Android에서 끝점용 Microsoft Defender를 설치하고 사용하는 방법을 설명
keywords: microsoft, defender, Endpoint용 Microsoft Defender, android, 설치, 배포, 제거, intune
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
ms.openlocfilehash: ceccd9e3c8a8137f672e7be519675034a84c7881
ms.sourcegitcommit: fa9efab24a84f71fec7d001f2ad8949125fa8eee
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/22/2021
ms.locfileid: "53055109"
---
# <a name="microsoft-defender-for-endpoint-on-android"></a><span data-ttu-id="6d682-104">Microsoft Defender for Endpoint(Android용)</span><span class="sxs-lookup"><span data-stu-id="6d682-104">Microsoft Defender for Endpoint on Android</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="6d682-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="6d682-105">**Applies to:**</span></span>
- [<span data-ttu-id="6d682-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="6d682-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="6d682-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6d682-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="6d682-108">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="6d682-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="6d682-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="6d682-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="6d682-110">이 항목에서는 Android에서 끝점용 Defender를 설치, 구성, 업데이트 및 사용하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6d682-110">This topic describes how to install, configure, update, and use Defender for Endpoint on Android.</span></span>

> [!CAUTION]
> <span data-ttu-id="6d682-111">Android에서 Endpoint용 Defender와 함께 다른 타사 끝점 보호 제품을 실행하면 성능 문제와 예측할 수 없는 시스템 오류가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d682-111">Running other third-party endpoint protection products alongside Defender for Endpoint on Android is likely to cause performance problems and unpredictable system errors.</span></span>


## <a name="how-to-install-microsoft-defender-for-endpoint-on-android"></a><span data-ttu-id="6d682-112">Android에 끝점용 Microsoft Defender를 설치하는 방법</span><span class="sxs-lookup"><span data-stu-id="6d682-112">How to install Microsoft Defender for Endpoint on Android</span></span>

### <a name="prerequisites"></a><span data-ttu-id="6d682-113">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="6d682-113">Prerequisites</span></span>

-   <span data-ttu-id="6d682-114">**최종 사용자의 경우**</span><span class="sxs-lookup"><span data-stu-id="6d682-114">**For end users**</span></span>

    -   <span data-ttu-id="6d682-115">앱의 최종 사용자에게 할당된 끝점용 Microsoft Defender 라이선스입니다.</span><span class="sxs-lookup"><span data-stu-id="6d682-115">Microsoft Defender for Endpoint license assigned to the end user(s) of the app.</span></span> <span data-ttu-id="6d682-116">끝점 라이선싱 요구 사항에 대한 [Microsoft Defender를 참조하세요.](/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements)</span><span class="sxs-lookup"><span data-stu-id="6d682-116">See [Microsoft Defender for Endpoint licensing requirements](/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements)</span></span>

    -   <span data-ttu-id="6d682-117">Intune 회사 포털 [앱은 Google Play에서](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) 다운로드할 수 있으며 Android 장치에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d682-117">Intune Company Portal app can be downloaded from [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) and is available on the Android device.</span></span>

        -   <span data-ttu-id="6d682-118">또한 Intune 장치 준수 [](/mem/intune/user-help/enroll-device-android-company-portal) 정책을 적용하기 위해 Intune 회사 포털 앱을 통해 장치를 등록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d682-118">Additionally, device(s) can be [enrolled](/mem/intune/user-help/enroll-device-android-company-portal) via the Intune Company Portal app to enforce Intune device compliance policies.</span></span> <span data-ttu-id="6d682-119">이렇게 하려면 최종 사용자에게 라이선스를 할당해야 Microsoft Intune 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d682-119">This requires the end user to be assigned a Microsoft Intune license.</span></span>

    -   <span data-ttu-id="6d682-120">라이선스를 할당하는 방법에 대한 자세한 내용은 사용자에게 라이선스 할당을 [참조하세요.](/azure/active-directory/users-groups-roles/licensing-groups-assign)</span><span class="sxs-lookup"><span data-stu-id="6d682-120">For more information on how to assign licenses, see [Assign licenses to users](/azure/active-directory/users-groups-roles/licensing-groups-assign).</span></span>
        

-   <span data-ttu-id="6d682-121">**관리자용**</span><span class="sxs-lookup"><span data-stu-id="6d682-121">**For Administrators**</span></span>

    -   <span data-ttu-id="6d682-122">사이트 포털에 Microsoft Defender 보안 센터 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="6d682-122">Access to the Microsoft Defender Security Center portal.</span></span>

        > [!NOTE]
        > <span data-ttu-id="6d682-123">Microsoft Intune Android에서 끝점용 Microsoft Defender를 배포하는 데 지원되는 유일한 MDM(모바일 장치 관리) 솔루션입니다.</span><span class="sxs-lookup"><span data-stu-id="6d682-123">Microsoft Intune is the only supported Mobile Device Management (MDM) solution for deploying Microsoft Defender for Endpoint on Android.</span></span> <span data-ttu-id="6d682-124">현재 등록된 장치만 Intune에서 Android 관련 장치 준수 정책에 끝점용 Defender를 적용하는 데 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d682-124">Currently only enrolled devices are supported for enforcing Defender for Endpoint on Android related device compliance policies in Intune.</span></span> 

    -   <span data-ttu-id="6d682-125">Microsoft Endpoint Manager [관리 센터에](https://go.microsoft.com/fwlink/?linkid=2109431)액세스하여 조직의 등록된 사용자 그룹에 앱을 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="6d682-125">Access [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), to deploy the app to enrolled user groups in your organization.</span></span>
        
### <a name="network-requirements"></a><span data-ttu-id="6d682-126">네트워크 요구 사항</span><span class="sxs-lookup"><span data-stu-id="6d682-126">Network Requirements</span></span>

- <span data-ttu-id="6d682-127">네트워크에 연결된 경우 Android의 끝점용 Microsoft Defender가 작동하려면 방화벽/프록시가 끝점 서비스 [URL용 Microsoft Defender에](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server)액세스할 수 있도록 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d682-127">For Microsoft Defender for Endpoint on Android to function when connected to a network the firewall/proxy will need to be configured to [enable access to Microsoft Defender for Endpoint service URLs](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server).</span></span>

### <a name="system-requirements"></a><span data-ttu-id="6d682-128">시스템 요구 사항</span><span class="sxs-lookup"><span data-stu-id="6d682-128">System Requirements</span></span>

-   <span data-ttu-id="6d682-129">Android 6.0 이상을 실행하는 휴대폰.</span><span class="sxs-lookup"><span data-stu-id="6d682-129">Mobile phones running Android 6.0 and above.</span></span> <span data-ttu-id="6d682-130">**Android를 실행하는 태블릿 및 기타 모바일 장치는 현재 지원되지 않습니다.**</span><span class="sxs-lookup"><span data-stu-id="6d682-130">**Tablets and other mobile devices running Android are not currently supported.**</span></span> 

-   <span data-ttu-id="6d682-131">Intune 회사 포털 [Google Play에서](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) 다운로드하여 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="6d682-131">Intune Company Portal app is downloaded from [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) and installed.</span></span> <span data-ttu-id="6d682-132">Intune 장치 준수 정책을 적용하려면 장치 등록이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="6d682-132">Device enrollment is required for Intune device compliance policies to be enforced.</span></span>

### <a name="installation-instructions"></a><span data-ttu-id="6d682-133">설치 지침</span><span class="sxs-lookup"><span data-stu-id="6d682-133">Installation instructions</span></span>

<span data-ttu-id="6d682-134">Android의 끝점용 Microsoft Defender는 레거시 장치 관리자 및 Android 및 Android 모드의 두 모드 모두에 Enterprise 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="6d682-134">Microsoft Defender for Endpoint on Android supports installation on both modes of enrolled devices - the legacy Device Administrator and Android Enterprise modes.</span></span>
<span data-ttu-id="6d682-135">**현재 회사 프로필이 있는 개인 소유 장치 및 회사 소유의 완전히 관리되는 사용자 장치 등록은 Android 2013에서 지원 Enterprise. 다른 Android Enterprise 모드에 대한 지원이 준비되면 발표됩니다.**</span><span class="sxs-lookup"><span data-stu-id="6d682-135">**Currently, Personally-owned devices with work profile and Corporate-owned fully managed user device enrollments are supported in Android Enterprise. Support for other Android Enterprise modes will be announced when ready.**</span></span>

<span data-ttu-id="6d682-136">Android에서 끝점용 Microsoft Defender를 배포하는 것은 MDM(Microsoft Intune)을 통해 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d682-136">Deployment of Microsoft Defender for Endpoint on Android is via Microsoft Intune (MDM).</span></span>
<span data-ttu-id="6d682-137">자세한 내용은 Deploy [Microsoft Defender for Endpoint on Android with Microsoft Intune.](android-intune.md)</span><span class="sxs-lookup"><span data-stu-id="6d682-137">For more information, see [Deploy Microsoft Defender for Endpoint on Android with Microsoft Intune](android-intune.md).</span></span>


> [!NOTE]
> <span data-ttu-id="6d682-138">**Android의 끝점용 Microsoft [Defender는 Google Play에서 지금 사용할 수](https://play.google.com/store/apps/details?id=com.microsoft.scmx) 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="6d682-138">**Microsoft Defender for Endpoint on Android is available on [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.scmx) now.**</span></span> <br> <span data-ttu-id="6d682-139">Intune에서 Google Play에 연결하여 디바이스 관리자 및 Android 관리 모드에 걸쳐 끝점용 Microsoft Defender 앱을 Enterprise 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d682-139">You can connect to Google Play from Intune to deploy Microsoft Defender for Endpoint app, across Device Administrator and Android Enterprise entrollment modes.</span></span> 

## <a name="how-to-configure-microsoft-defender-for-endpoint-on-android"></a><span data-ttu-id="6d682-140">Android에서 끝점용 Microsoft Defender를 구성하는 방법</span><span class="sxs-lookup"><span data-stu-id="6d682-140">How to Configure Microsoft Defender for Endpoint on Android</span></span>

<span data-ttu-id="6d682-141">Android 기능에서 끝점용 Microsoft Defender를 구성하는 방법에 대한 지침은 [Configure Microsoft Defender for Endpoint on Android features에서](android-configure.md)사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d682-141">Guidance on how to configure Microsoft Defender for Endpoint on Android features is available in [Configure Microsoft Defender for Endpoint on Android features](android-configure.md).</span></span>



## <a name="related-topics"></a><span data-ttu-id="6d682-142">관련 항목</span><span class="sxs-lookup"><span data-stu-id="6d682-142">Related topics</span></span>
- [<span data-ttu-id="6d682-143">Microsoft Intune으로 Microsoft Defender for Endpoint(Android용) 배포</span><span class="sxs-lookup"><span data-stu-id="6d682-143">Deploy Microsoft Defender for Endpoint on Android with Microsoft Intune</span></span>](android-intune.md)
- [<span data-ttu-id="6d682-144">Microsoft Defender for Endpoint(Android용) 기능 구성</span><span class="sxs-lookup"><span data-stu-id="6d682-144">Configure Microsoft Defender for Endpoint on Android features</span></span>](android-configure.md)

