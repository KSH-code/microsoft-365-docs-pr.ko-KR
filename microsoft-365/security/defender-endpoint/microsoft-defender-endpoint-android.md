---
title: Android용 Microsoft Defender ATP
ms.reviewer: ''
description: Android용 Microsoft Defender ATP를 설치하고 사용하는 방법을 설명
keywords: microsoft, defender, atp, android, 설치, 배포, 제거, intune
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
ms.openlocfilehash: 6518b86861fd5d03533bb787d4ee005d7ace1a0c
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51076868"
---
# <a name="microsoft-defender-for-endpoint-for-android"></a><span data-ttu-id="e2073-104">Android용 끝점용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="e2073-104">Microsoft Defender for Endpoint for Android</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="e2073-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="e2073-105">**Applies to:**</span></span>
- [<span data-ttu-id="e2073-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="e2073-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="e2073-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e2073-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="e2073-108">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="e2073-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="e2073-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="e2073-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="e2073-110">이 항목에서는 Android용 끝점용 Defender를 설치, 구성, 업데이트 및 사용하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e2073-110">This topic describes how to install, configure, update, and use Defender for Endpoint for Android.</span></span>

> [!CAUTION]
> <span data-ttu-id="e2073-111">Android용 Endpoint용 Defender와 함께 다른 타사 끝점 보호 제품을 실행하면 성능 문제와 예측할 수 없는 시스템 오류가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2073-111">Running other third-party endpoint protection products alongside Defender for Endpoint for Android is likely to cause performance problems and unpredictable system errors.</span></span>


## <a name="how-to-install-microsoft-defender-for-endpoint-for-android"></a><span data-ttu-id="e2073-112">Android용 끝점용 Microsoft Defender를 설치하는 방법</span><span class="sxs-lookup"><span data-stu-id="e2073-112">How to install Microsoft Defender for Endpoint for Android</span></span>

### <a name="prerequisites"></a><span data-ttu-id="e2073-113">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="e2073-113">Prerequisites</span></span>

-   <span data-ttu-id="e2073-114">**최종 사용자의 경우**</span><span class="sxs-lookup"><span data-stu-id="e2073-114">**For end users**</span></span>

    -   <span data-ttu-id="e2073-115">앱의 최종 사용자에게 할당된 끝점용 Microsoft Defender 라이선스입니다.</span><span class="sxs-lookup"><span data-stu-id="e2073-115">Microsoft Defender for Endpoint license assigned to the end user(s) of the app.</span></span> <span data-ttu-id="e2073-116">끝점 라이선싱 요구 사항에 대한 [Microsoft Defender를 참조하세요.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements)</span><span class="sxs-lookup"><span data-stu-id="e2073-116">See [Microsoft Defender for Endpoint licensing requirements](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements)</span></span>

    -   <span data-ttu-id="e2073-117">Intune 회사 포털 앱은 [Google Play에서](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) 다운로드할 수 있으며 Android 장치에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2073-117">Intune Company Portal app can be downloaded from [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) and is available on the Android device.</span></span>

        -   <span data-ttu-id="e2073-118">또한 Intune 회사 포털 [](https://docs.microsoft.com/mem/intune/user-help/enroll-device-android-company-portal) 앱을 통해 디바이스를 등록하여 Intune 장치 준수 정책을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2073-118">Additionally, device(s) can be [enrolled](https://docs.microsoft.com/mem/intune/user-help/enroll-device-android-company-portal) via the Intune Company Portal app to enforce Intune device compliance policies.</span></span> <span data-ttu-id="e2073-119">이렇게 하려면 최종 사용자에게 Microsoft Intune 라이선스가 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="e2073-119">This requires the end user to be assigned a Microsoft Intune license.</span></span>

    -   <span data-ttu-id="e2073-120">라이선스를 할당하는 방법에 대한 자세한 내용은 사용자에게 라이선스 할당을 [참조하세요.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign)</span><span class="sxs-lookup"><span data-stu-id="e2073-120">For more information on how to assign licenses, see [Assign licenses to users](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign).</span></span>
        

-   <span data-ttu-id="e2073-121">**관리자용**</span><span class="sxs-lookup"><span data-stu-id="e2073-121">**For Administrators**</span></span>

    -   <span data-ttu-id="e2073-122">Microsoft Defender 보안 센터 포털에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="e2073-122">Access to the Microsoft Defender Security Center portal.</span></span>

        > [!NOTE]
        > <span data-ttu-id="e2073-123">Microsoft Intune은 Android용 끝점용 Microsoft Defender를 배포하는 데 지원되는 유일한 MDM(모바일 장치 관리) 솔루션입니다.</span><span class="sxs-lookup"><span data-stu-id="e2073-123">Microsoft Intune is the only supported Mobile Device Management (MDM) solution for deploying Microsoft Defender for Endpoint for Android.</span></span> <span data-ttu-id="e2073-124">현재 등록된 장치만 Intune에서 Android용 끝점용 Defender 관련 장치 준수 정책을 적용하는 데 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="e2073-124">Currently only enrolled devices are supported for enforcing Defender for Endpoint for Android related device compliance policies in Intune.</span></span> 

    -   <span data-ttu-id="e2073-125">[Microsoft Endpoint Manager 관리 센터 에](https://go.microsoft.com/fwlink/?linkid=2109431)액세스하여 조직의 등록된 사용자 그룹에 앱을 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="e2073-125">Access [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), to deploy the app to enrolled user groups in your organization.</span></span>

### <a name="system-requirements"></a><span data-ttu-id="e2073-126">시스템 요구 사항</span><span class="sxs-lookup"><span data-stu-id="e2073-126">System Requirements</span></span>

-   <span data-ttu-id="e2073-127">Android 6.0 이상을 실행하는 Android 장치.</span><span class="sxs-lookup"><span data-stu-id="e2073-127">Android devices running Android 6.0 and above.</span></span>
-   <span data-ttu-id="e2073-128">Intune 회사 포털 앱은 [Google Play에서](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) 다운로드하여 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="e2073-128">Intune Company Portal app is downloaded from [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) and installed.</span></span> <span data-ttu-id="e2073-129">Intune 장치 준수 정책을 적용하려면 장치 등록이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="e2073-129">Device enrollment is required for Intune device compliance policies to be enforced.</span></span>

### <a name="installation-instructions"></a><span data-ttu-id="e2073-130">설치 지침</span><span class="sxs-lookup"><span data-stu-id="e2073-130">Installation instructions</span></span>

<span data-ttu-id="e2073-131">Android용 끝점용 Microsoft Defender는 레거시 장치 관리자 및 Android 엔터프라이즈 모드인 등록된 디바이스의 두 모드 모두에서 설치를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="e2073-131">Microsoft Defender for Endpoint for Android supports installation on both modes of enrolled devices - the legacy Device Administrator and Android Enterprise modes.</span></span>
<span data-ttu-id="e2073-132">**현재 회사 프로필 및 회사 소유의 완전히 관리되는 사용자 장치 열이 있는 개인 소유 디바이스는 Android Enterprise에서 지원됩니다. 다른 Android 엔터프라이즈 모드에 대한 지원이 준비되면 발표됩니다.**</span><span class="sxs-lookup"><span data-stu-id="e2073-132">**Currently, Personally-owned devices with work profile and Corporate-owned fully managed user device enrolments are supported in Android Enterprise. Support for other Android Enterprise modes will be announced when ready.**</span></span>

<span data-ttu-id="e2073-133">Android용 끝점용 Microsoft Defender 배포는 MDM(Microsoft Intune)을 통해 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2073-133">Deployment of Microsoft Defender for Endpoint for Android is via Microsoft Intune (MDM).</span></span>
<span data-ttu-id="e2073-134">자세한 내용은 [Microsoft Intune을 통해 Android용 끝점용 Microsoft Defender 배포를 참조하세요.](android-intune.md)</span><span class="sxs-lookup"><span data-stu-id="e2073-134">For more information, see [Deploy Microsoft Defender for Endpoint for Android with Microsoft Intune](android-intune.md).</span></span>


> [!NOTE]
> <span data-ttu-id="e2073-135">**Android용 끝점용 Microsoft [Defender는 Google Play에서 지금 사용할 수](https://play.google.com/store/apps/details?id=com.microsoft.scmx) 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="e2073-135">**Microsoft Defender for Endpoint for Android is available on [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.scmx) now.**</span></span> <br> <span data-ttu-id="e2073-136">Intune에서 Google Play에 연결하여 장치 관리자 및 Android Enterprise 관리 모드로 끝점용 Microsoft Defender 앱을 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2073-136">You can connect to Google Play from Intune to deploy Microsoft Defender for Endpoint app, across Device Administrator and Android Enterprise entrollment modes.</span></span> 

## <a name="how-to-configure-microsoft-defender-for-endpoint-for-android"></a><span data-ttu-id="e2073-137">Android용 끝점에 대해 Microsoft Defender를 구성하는 방법</span><span class="sxs-lookup"><span data-stu-id="e2073-137">How to Configure Microsoft Defender for Endpoint for Android</span></span>

<span data-ttu-id="e2073-138">Android용 끝점용 Microsoft Defender 기능을 구성하는 방법에 대한 지침은 [Configure Microsoft Defender for Endpoint for Android features 에서 사용할 수 있습니다.](android-configure.md)</span><span class="sxs-lookup"><span data-stu-id="e2073-138">Guidance on how to configure Microsoft Defender for Endpoint for Android features is available in [Configure Microsoft Defender for Endpoint for Android features](android-configure.md).</span></span>



## <a name="related-topics"></a><span data-ttu-id="e2073-139">관련 항목</span><span class="sxs-lookup"><span data-stu-id="e2073-139">Related topics</span></span>
- [<span data-ttu-id="e2073-140">Microsoft Intune을 사용할 수 있는 끝점용 Microsoft Defender 배포</span><span class="sxs-lookup"><span data-stu-id="e2073-140">Deploy Microsoft Defender for Endpoint for with Microsoft Intune</span></span>](android-intune.md)
- [<span data-ttu-id="e2073-141">Android용 끝점 기능에 대한 Microsoft Defender 구성</span><span class="sxs-lookup"><span data-stu-id="e2073-141">Configure Microsoft Defender for Endpoint for Android features</span></span>](android-configure.md)

