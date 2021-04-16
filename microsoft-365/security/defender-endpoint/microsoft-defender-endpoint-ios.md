---
title: Microsoft Defender for Endpoint(iOS용)
ms.reviewer: ''
description: iOS용 끝점용 Microsoft Defender를 설치하고 사용하는 방법을 설명
keywords: microsoft, defender, atp, ios, 개요, 설치, 배포, 제거, intune
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
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: a04d939d5c25341f07090ac896cfb80b43ab1a1c
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2021
ms.locfileid: "51861386"
---
# <a name="microsoft-defender-for-endpoint-on-ios"></a><span data-ttu-id="731a8-104">Microsoft Defender for Endpoint(iOS용)</span><span class="sxs-lookup"><span data-stu-id="731a8-104">Microsoft Defender for Endpoint on iOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="731a8-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="731a8-105">**Applies to:**</span></span>
- [<span data-ttu-id="731a8-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="731a8-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="731a8-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="731a8-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="731a8-108">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="731a8-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="731a8-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="731a8-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="731a8-110">**iOS의 끝점용 Microsoft Defender는** 웹 사이트, 전자 메일 및 앱의 피싱 및 안전하지 않은 네트워크 연결로부터 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="731a8-110">**Microsoft Defender for Endpoint on iOS** will offer protection against phishing and unsafe network connections from websites, emails, and apps.</span></span> <span data-ttu-id="731a8-111">모든 경고는 Microsoft Defender 보안 센터의 단일 창을 통해 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="731a8-111">All alerts will be available through a single pane of glass in the Microsoft Defender Security Center.</span></span> <span data-ttu-id="731a8-112">이 포털은 보안 팀에서 다른 플랫폼과 함께 iOS 장치에 대한 위협을 중앙 집중식으로 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="731a8-112">The portal gives security teams a centralized view of threats on iOS devices along with other platforms.</span></span>

> [!CAUTION]
> <span data-ttu-id="731a8-113">iOS에서 Endpoint용 Defender와 함께 다른 타사 끝점 보호 제품을 실행하면 성능 문제와 예측할 수 없는 시스템 오류가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="731a8-113">Running other third-party endpoint protection products alongside Defender for Endpoint on iOS is likely to cause performance problems and unpredictable system errors.</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="731a8-114">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="731a8-114">Pre-requisites</span></span>

<span data-ttu-id="731a8-115">**최종 사용자용**</span><span class="sxs-lookup"><span data-stu-id="731a8-115">**For End Users**</span></span>

- <span data-ttu-id="731a8-116">앱의 최종 사용자에게 할당된 끝점용 Microsoft Defender 라이선스입니다.</span><span class="sxs-lookup"><span data-stu-id="731a8-116">Microsoft Defender for Endpoint license assigned to the end user(s) of the app.</span></span> <span data-ttu-id="731a8-117">끝점 [라이선스 요구 사항에 대한 Microsoft Defender를 참조하세요.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements)</span><span class="sxs-lookup"><span data-stu-id="731a8-117">See [Microsoft Defender for Endpoint licensing requirements](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements).</span></span>

- <span data-ttu-id="731a8-118">Intune 장치 [](https://docs.microsoft.com/mem/intune/user-help/enroll-your-device-in-intune-ios) 준수 정책을 적용하기 위해 Intune 회사 포털 앱을 통해 장치가 등록됩니다.</span><span class="sxs-lookup"><span data-stu-id="731a8-118">Device(s) are [enrolled](https://docs.microsoft.com/mem/intune/user-help/enroll-your-device-in-intune-ios) via the Intune Company Portal app to enforce Intune device compliance policies.</span></span> <span data-ttu-id="731a8-119">이렇게 하려면 최종 사용자에게 Microsoft Intune 라이선스가 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="731a8-119">This requires the end user to be assigned a Microsoft Intune license.</span></span>
    - <span data-ttu-id="731a8-120">Intune 회사 포털 앱은 Apple 앱 스토어에서 [다운로드할 수 있습니다.](https://apps.apple.com/us/app/intune-company-portal/id719171358)</span><span class="sxs-lookup"><span data-stu-id="731a8-120">Intune Company Portal app can be downloaded from the [Apple App Store](https://apps.apple.com/us/app/intune-company-portal/id719171358).</span></span>
    - <span data-ttu-id="731a8-121">Apple은 사용자가 앱 스토어에서 다른 앱을 다운로드하도록 리디렉션을 허용하지 않습니다. 따라서 이 단계는 끝점용 Microsoft Defender 앱에 온보딩하기 전에 사용자가 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="731a8-121">Note that Apple does not allow redirecting users to download other apps from the app store and hence this step needs to be done by the user before onboarding to Microsoft Defender for Endpoint app.</span></span>

- <span data-ttu-id="731a8-122">라이선스를 할당하는 방법에 대한 자세한 내용은 사용자에게 라이선스 할당을 [참조하세요.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign)</span><span class="sxs-lookup"><span data-stu-id="731a8-122">For more information on how to assign licenses, see [Assign licenses to users](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign).</span></span>

<span data-ttu-id="731a8-123">**관리자용**</span><span class="sxs-lookup"><span data-stu-id="731a8-123">**For Administrators**</span></span>

- <span data-ttu-id="731a8-124">Microsoft Defender 보안 센터 포털에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="731a8-124">Access to the Microsoft Defender Security Center portal.</span></span>

    > [!NOTE]
    > <span data-ttu-id="731a8-125">Microsoft Intune은 iOS에서 끝점용 Microsoft Defender를 배포하는 데 지원되는 유일한 MDM(모바일 장치 관리) 솔루션입니다.</span><span class="sxs-lookup"><span data-stu-id="731a8-125">Microsoft Intune is the only supported Mobile Device Management (MDM) solution for deploying Microsoft Defender for Endpoint on iOS.</span></span> <span data-ttu-id="731a8-126">현재 등록된 장치만 Intune에서 iOS 관련 장치 준수 정책에 끝점용 Defender를 적용하는 데 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="731a8-126">Currently only enrolled devices are supported for enforcing Defender for Endpoint on iOS related device compliance policies in Intune.</span></span>

- <span data-ttu-id="731a8-127">Microsoft [Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431)관리 센터에 액세스하여 조직의 등록된 사용자 그룹에 앱을 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="731a8-127">Access to [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), to deploy the app to enrolled user groups in your organization.</span></span>

<span data-ttu-id="731a8-128">**시스템 요구 사항**</span><span class="sxs-lookup"><span data-stu-id="731a8-128">**System Requirements**</span></span>

- <span data-ttu-id="731a8-129">iOS 11.0 이상을 실행하는 iOS 장치.</span><span class="sxs-lookup"><span data-stu-id="731a8-129">iOS devices running iOS 11.0 and above.</span></span> <span data-ttu-id="731a8-130">iPad 장치는 버전 1.1.15010101 이상에서 공식적으로 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="731a8-130">iPad devices are officially supported from version 1.1.15010101 onward.</span></span>

- <span data-ttu-id="731a8-131">[장치가 Intune 회사 포털 앱에 등록됩니다.](https://apps.apple.com/us/app/intune-company-portal/id719171358)</span><span class="sxs-lookup"><span data-stu-id="731a8-131">Device is enrolled with the [Intune Company Portal app](https://apps.apple.com/us/app/intune-company-portal/id719171358).</span></span>

> [!NOTE]
> <span data-ttu-id="731a8-132">**iOS의 Microsoft Defender ATP(Microsoft Defender for Endpoint)는 [이제 Apple App Store에서 사용할 수 있습니다.](https://aka.ms/mdatpiosappstore)**</span><span class="sxs-lookup"><span data-stu-id="731a8-132">**Microsoft Defender ATP (Microsoft Defender for Endpoint) on iOS is now available on [Apple App Store](https://aka.ms/mdatpiosappstore).**</span></span>

## <a name="installation-instructions"></a><span data-ttu-id="731a8-133">설치 지침</span><span class="sxs-lookup"><span data-stu-id="731a8-133">Installation instructions</span></span>

<span data-ttu-id="731a8-134">iOS에서 끝점용 Microsoft Defender 배포는 Microsoft Intune(MDM)을 통해 배포할 수 있으며 감독되는 디바이스와 관리되지 않는 디바이스가 모두 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="731a8-134">Deployment of Microsoft Defender for Endpoint on iOS is via Microsoft Intune (MDM) and both supervised and unsupervised devices are supported.</span></span>
<span data-ttu-id="731a8-135">자세한 내용은 [iOS에서 끝점용 Microsoft Defender 배포를 참조하세요.](ios-install.md)</span><span class="sxs-lookup"><span data-stu-id="731a8-135">For more information, see [Deploy Microsoft Defender for Endpoint on iOS](ios-install.md).</span></span>

## <a name="resources"></a><span data-ttu-id="731a8-136">리소스</span><span class="sxs-lookup"><span data-stu-id="731a8-136">Resources</span></span>

- <span data-ttu-id="731a8-137">iOS 또는 블로그의 [끝점용 Microsoft Defender의 새로운](ios-whatsnew.md) 소식을 방문하여 예정된 릴리스에 대한 정보를 계속 [확인하세요.](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/iOS)</span><span class="sxs-lookup"><span data-stu-id="731a8-137">Stay informed about upcoming releases by visiting [What's new in Microsoft Defender for Endpoint on iOS](ios-whatsnew.md) or our [blog](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/iOS).</span></span>

- <span data-ttu-id="731a8-138">앱 내 피드백 시스템 또는 [SecOps](https://securitycenter.microsoft.com) 포털을 통해 피드백 제공</span><span class="sxs-lookup"><span data-stu-id="731a8-138">Provide feedback through in-app feedback system or through [SecOps portal](https://securitycenter.microsoft.com)</span></span>

## <a name="next-steps"></a><span data-ttu-id="731a8-139">다음 단계</span><span class="sxs-lookup"><span data-stu-id="731a8-139">Next steps</span></span>

- [<span data-ttu-id="731a8-140">iOS에서 끝점용 Microsoft Defender 배포</span><span class="sxs-lookup"><span data-stu-id="731a8-140">Deploy Microsoft Defender for Endpoint on iOS</span></span>](ios-install.md)
- [<span data-ttu-id="731a8-141">iOS 기능에 대한 끝점용 Microsoft Defender 구성</span><span class="sxs-lookup"><span data-stu-id="731a8-141">Configure Microsoft Defender for Endpoint on iOS features</span></span>](ios-configure-features.md)
