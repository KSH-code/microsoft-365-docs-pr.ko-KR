---
title: iOS의 끝점용 Microsoft Defender용 앱 기반 배포
ms.reviewer: ''
description: 앱을 사용하여 iOS에서 끝점용 Microsoft Defender를 배포하는 방법을 설명
keywords: microsoft, defender, Endpoint용 Microsoft Defender, ios, 앱, 설치, 배포, 제거, intune
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 371208433cbb0f65ab5a2808318c03dae6bb6d8b
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842310"
---
# <a name="deploy-microsoft-defender-for-endpoint-on-ios"></a><span data-ttu-id="b9270-104">iOS에서 끝점용 Microsoft Defender 배포</span><span class="sxs-lookup"><span data-stu-id="b9270-104">Deploy Microsoft Defender for Endpoint on iOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b9270-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="b9270-105">**Applies to:**</span></span>
- [<span data-ttu-id="b9270-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="b9270-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="b9270-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b9270-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="b9270-108">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="b9270-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="b9270-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="b9270-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="b9270-110">이 항목에서는 등록된 디바이스에서 iOS에 Endpoint용 Defender를 Intune 회사 포털 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b9270-110">This topic describes deploying Defender for Endpoint on iOS on Intune Company Portal enrolled devices.</span></span> <span data-ttu-id="b9270-111">Intune 장치 등록에 대한 자세한 내용은 [Intune에서 iOS/iPadOS 장치 등록을 참조하세요.](/mem/intune/enrollment/ios-enroll)</span><span class="sxs-lookup"><span data-stu-id="b9270-111">For more information about Intune device enrollment, see [Enroll iOS/iPadOS devices in Intune](/mem/intune/enrollment/ios-enroll).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="b9270-112">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="b9270-112">Before you begin</span></span>

- <span data-ttu-id="b9270-113">Microsoft Endpoint Manager 관리 센터에 액세스할 [수 있도록 합니다.](https://go.microsoft.com/fwlink/?linkid=2109431)</span><span class="sxs-lookup"><span data-stu-id="b9270-113">Ensure you have access to [Microsoft Endpoint manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431).</span></span>

- <span data-ttu-id="b9270-114">사용자에 대해 iOS 등록이 완료되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9270-114">Ensure iOS enrollment is done for your users.</span></span> <span data-ttu-id="b9270-115">iOS에서 끝점용 Defender를 사용하려면 사용자가 끝점용 Defender 라이선스를 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9270-115">Users need to have a Defender for Endpoint license assigned in order to use Defender for Endpoint on iOS.</span></span> <span data-ttu-id="b9270-116">라이선스를 [할당하는](/azure/active-directory/users-groups-roles/licensing-groups-assign) 방법에 대한 지침은 사용자에게 라이선스 할당을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b9270-116">Refer to [Assign licenses to users](/azure/active-directory/users-groups-roles/licensing-groups-assign) for instructions on how to assign licenses.</span></span>

> [!NOTE]
> <span data-ttu-id="b9270-117">iOS의 끝점용 Microsoft Defender는 [Apple App Store에서 사용할 수 있습니다.](https://aka.ms/mdatpiosappstore)</span><span class="sxs-lookup"><span data-stu-id="b9270-117">Microsoft Defender for Endpoint on iOS is available in the [Apple App Store](https://aka.ms/mdatpiosappstore).</span></span>

## <a name="deployment-steps"></a><span data-ttu-id="b9270-118">배포 단계</span><span class="sxs-lookup"><span data-stu-id="b9270-118">Deployment steps</span></span>

<span data-ttu-id="b9270-119">iOS에서 끝점용 Defender를 배포하는 Intune 회사 포털.</span><span class="sxs-lookup"><span data-stu-id="b9270-119">Deploy Defender for Endpoint on iOS via Intune Company Portal.</span></span>

### <a name="add-ios-store-app"></a><span data-ttu-id="b9270-120">iOS 스토어 앱 추가</span><span class="sxs-lookup"><span data-stu-id="b9270-120">Add iOS store app</span></span>

1. <span data-ttu-id="b9270-121">[Microsoft Endpoint Manager 관리 센터에서](https://go.microsoft.com/fwlink/?linkid=2109431)앱   ->  **iOS/iPadOS** iOS 스토어 앱  ->    ->  **추가로 이동하고** 선택을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="b9270-121">In [Microsoft Endpoint manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), go to **Apps** -> **iOS/iPadOS** -> **Add** -> **iOS store app** and click **Select**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="b9270-122">![Microsoft Endpoint Manager 관리 센터의 이미지1](images/ios-deploy-1.png)</span><span class="sxs-lookup"><span data-stu-id="b9270-122">![Image of Microsoft Endpoint Manager Admin Center1](images/ios-deploy-1.png)</span></span>

1. <span data-ttu-id="b9270-123">앱 추가 페이지에서 앱  스토어 검색을 클릭하고 검색 표시줄에 **Microsoft Defender 끝점을** 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="b9270-123">On the Add app page, click on **Search the App Store** and type **Microsoft Defender Endpoint** in the search bar.</span></span> <span data-ttu-id="b9270-124">검색 결과 섹션에서 *Microsoft Defender 끝점을 클릭하고* 선택을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="b9270-124">In the search results section, click on *Microsoft Defender Endpoint* and click **Select**.</span></span>

1. <span data-ttu-id="b9270-125">**최소 운영 체제로 iOS 11.0을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b9270-125">Select **iOS 11.0** as the Minimum operating system.</span></span> <span data-ttu-id="b9270-126">앱에 대한 나머지 정보를 검토하고 다음을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="b9270-126">Review the rest of information about the app and click **Next**.</span></span>

1. <span data-ttu-id="b9270-127">배정 *섹션에서* 필수 섹션으로 **이동하여** 그룹 **추가 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="b9270-127">In the *Assignments* section, go to the **Required** section and select **Add group**.</span></span> <span data-ttu-id="b9270-128">그런 다음 iOS 앱에서 끝점용 Defender를 대상으로 할 사용자 그룹을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9270-128">You can then choose the user group(s) that you would like to target Defender for Endpoint on iOS app.</span></span> <span data-ttu-id="b9270-129">선택을 **클릭한** 후 다음 을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="b9270-129">Click **Select** and then **Next**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b9270-130">선택한 사용자 그룹은 Intune에 등록된 사용자로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9270-130">The selected user group should consist of Intune enrolled users.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="b9270-131">![Microsoft Endpoint Manager 관리 센터의 이미지2](images/ios-deploy-2.png)</span><span class="sxs-lookup"><span data-stu-id="b9270-131">![Image of Microsoft Endpoint Manager Admin Center2](images/ios-deploy-2.png)</span></span>

1. <span data-ttu-id="b9270-132">검토 *+ 만들기 섹션에서* 입력한 모든 정보가 올바른지 확인하고 만들기를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="b9270-132">In the *Review + Create* section, verify that all the information entered is correct and then select **Create**.</span></span> <span data-ttu-id="b9270-133">잠시 후 Endpoint용 Defender 앱이 만들어지며 알림이 페이지의 오른쪽 위에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9270-133">In a few moments, the Defender for Endpoint app should be created successfully, and a notification should show up at the top-right corner of the page.</span></span>

1. <span data-ttu-id="b9270-134">표시되는 앱 정보 페이지의 모니터 섹션에서 장치  설치 상태를 선택하여 장치 설치가 성공적으로 완료되어 있는지 확인합니다. </span><span class="sxs-lookup"><span data-stu-id="b9270-134">In the app information page that is displayed, in the **Monitor** section, select **Device install status** to verify that the device installation has completed successfully.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="b9270-135">![관리 Microsoft Endpoint Manager 이미지3](images/ios-deploy-3.png)</span><span class="sxs-lookup"><span data-stu-id="b9270-135">![Image of Microsoft Endpoint Manager Admin Center3](images/ios-deploy-3.png)</span></span>

## <a name="auto-onboarding-of-vpn-profile-simplified-onboarding"></a><span data-ttu-id="b9270-136">VPN 프로필의 자동 온보더링(간소화된 온보더링)</span><span class="sxs-lookup"><span data-stu-id="b9270-136">Auto-Onboarding of VPN profile (Simplified Onboarding)</span></span>

<span data-ttu-id="b9270-137">관리자는 VPN 프로필의 자동 설정을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9270-137">Admins can configure auto-setup of VPN profile.</span></span> <span data-ttu-id="b9270-138">이렇게 하면 사용자가 온보딩하는 동안 이를 수행하지 않고도 Endpoint VPN용 Defender 프로필이 자동으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9270-138">This will automatically setup the Defender for Endpoint VPN profile without having the user to do so while onboarding.</span></span> <span data-ttu-id="b9270-139">VPN은 웹 보호 기능을 제공하기 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9270-139">Note that VPN is used in order to provide the Web Protection feature.</span></span> <span data-ttu-id="b9270-140">이는 일반 VPN이 아니며 장치 외부에서 트래픽을 취하지 않는 로컬/자체 루프 VPN입니다.</span><span class="sxs-lookup"><span data-stu-id="b9270-140">This is not a regular VPN and is a local/self-looping VPN that does not take traffic outside the device.</span></span>

1. <span data-ttu-id="b9270-141">[Microsoft 끝점 관리자 관리 센터에서](https://go.microsoft.com/fwlink/?linkid=2109431)장치 **구성** 프로필 프로필  ->    ->  **만들기로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="b9270-141">In [Microsoft Endpoint manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), go to **Devices** -> **Configuration Profiles** -> **Create Profile**.</span></span>
1. <span data-ttu-id="b9270-142">**플랫폼을 iOS/iPadOS로** 선택하고 **VPN으로 프로필 유형을** **선택하세요.** </span><span class="sxs-lookup"><span data-stu-id="b9270-142">Choose **Platform** as **iOS/iPadOS** and **Profile type** as **VPN**.</span></span> <span data-ttu-id="b9270-143">**만들기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b9270-143">Click **Create**.</span></span>
1. <span data-ttu-id="b9270-144">프로필 이름을 입력하고 다음 을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="b9270-144">Type a name for the profile and click **Next**.</span></span>
1. <span data-ttu-id="b9270-145">연결 **유형에** 대한 사용자 지정 **VPN을** 선택하고 기본 VPN 섹션에서 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="b9270-145">Select **Custom VPN** for Connection Type and in the **Base VPN** section, enter the following:</span></span>
    - <span data-ttu-id="b9270-146">연결 이름 = 끝점용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="b9270-146">Connection Name = Microsoft Defender for Endpoint</span></span>
    - <span data-ttu-id="b9270-147">VPN 서버 주소 = 127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="b9270-147">VPN server address = 127.0.0.1</span></span>
    - <span data-ttu-id="b9270-148">인증 방법 = "사용자 이름 및 암호"</span><span class="sxs-lookup"><span data-stu-id="b9270-148">Auth method = "Username and password"</span></span>
    - <span data-ttu-id="b9270-149">분할 터널링 = 사용 안 하게</span><span class="sxs-lookup"><span data-stu-id="b9270-149">Split Tunneling = Disable</span></span>
    - <span data-ttu-id="b9270-150">VPN 식별자 = com.microsoft.scmx</span><span class="sxs-lookup"><span data-stu-id="b9270-150">VPN identifier = com.microsoft.scmx</span></span>
    - <span data-ttu-id="b9270-151">키-값 쌍에서 **키 AutoOnboard를** 입력하고 값을 **True로 설정합니다.**</span><span class="sxs-lookup"><span data-stu-id="b9270-151">In the key-value pairs, enter the key **AutoOnboard** and set the value to **True**.</span></span>
    - <span data-ttu-id="b9270-152">자동 VPN 유형 = 수동 VPN</span><span class="sxs-lookup"><span data-stu-id="b9270-152">Type of Automatic VPN = On-demand VPN</span></span>
    - <span data-ttu-id="b9270-153">On  **Demand Rules에 대해** 추가를 클릭하고 다음을 하고 싶은 **경우를** 선택합니다. VPN 설정 , = 모든 도메인으로 **제한합니다.**</span><span class="sxs-lookup"><span data-stu-id="b9270-153">Click **Add** for **On Demand Rules** and select **I want to do the following = Establish VPN**, **I want to restrict to = All domains**.</span></span>

    ![VPN 프로필 구성 스크린샷](images/ios-deploy-8.png)

1. <span data-ttu-id="b9270-155">다음을 클릭하고 대상 사용자에게 프로필을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="b9270-155">Click Next and assign the profile to targeted users.</span></span>
1. <span data-ttu-id="b9270-156">검토 *+ 만들기 섹션에서* 입력한 모든 정보가 올바른지 확인하고 만들기를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="b9270-156">In the *Review + Create* section, verify that all the information entered is correct and then select **Create**.</span></span>

## <a name="complete-onboarding-and-check-status"></a><span data-ttu-id="b9270-157">온보더링 완료 및 상태 확인</span><span class="sxs-lookup"><span data-stu-id="b9270-157">Complete onboarding and check status</span></span>

1. <span data-ttu-id="b9270-158">iOS의 끝점용 Defender가 장치에 설치되면 앱 아이콘이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9270-158">Once Defender for Endpoint on iOS has been installed on the device, you  will see the app icon.</span></span>

    ![자동으로 생성된 스마트폰 설명의 스크린샷](images/41627a709700c324849bf7e13510c516.png)

2. <span data-ttu-id="b9270-160">끝점용 Defender 앱 아이콘(MSDefender)을 탭하고 화면의 지침에 따라 온보딩 단계를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="b9270-160">Tap the Defender for Endpoint app icon (MSDefender) and follow the on-screen instructions to complete the onboarding steps.</span></span> <span data-ttu-id="b9270-161">세부 정보에는 iOS의 끝점에 대한 Defender에서 요구하는 iOS 사용 권한의 최종 사용자 수락이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9270-161">The details include end-user acceptance of iOS permissions required by Defender for Endpoint on iOS.</span></span>

3. <span data-ttu-id="b9270-162">온보드에 성공하면 디바이스가 디바이스의 디바이스 목록에 Microsoft Defender 보안 센터.</span><span class="sxs-lookup"><span data-stu-id="b9270-162">Upon successful onboarding, the device will start showing up on the Devices list in Microsoft Defender Security Center.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="b9270-163">![휴대폰 설명이 자동으로 생성되는 스크린샷](images/e07f270419f7b1e5ee6744f8b38ddeaf.png)</span><span class="sxs-lookup"><span data-stu-id="b9270-163">![A screenshot of a cell phone Description automatically generated](images/e07f270419f7b1e5ee6744f8b38ddeaf.png)</span></span>

## <a name="configure-microsoft-defender-for-endpoint-for-supervised-mode"></a><span data-ttu-id="b9270-164">감독 모드에 대한 끝점에 대한 Microsoft Defender 구성</span><span class="sxs-lookup"><span data-stu-id="b9270-164">Configure Microsoft Defender for Endpoint for Supervised Mode</span></span>

<span data-ttu-id="b9270-165">iOS 앱의 끝점용 Microsoft Defender는 이러한 유형의 장치에서 플랫폼에서 제공하는 증가된 관리 기능을 감안할 때 감독되는 iOS/iPadOS 디바이스에서 특수한 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b9270-165">The Microsoft Defender for Endpoint on iOS app has specialized ability on supervised iOS/iPadOS devices, given the increased management capabilities provided by the platform on these types of devices.</span></span> <span data-ttu-id="b9270-166">이러한 기능을 활용하려면 끝점용 Defender 앱에서 장치가 감독 모드에 있는지 알아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9270-166">To take advantage of these capabilities, the Defender for Endpoint app needs to know if a device is in Supervised Mode.</span></span>

### <a name="configure-supervised-mode-via-intune"></a><span data-ttu-id="b9270-167">Intune을 통해 감독 모드 구성</span><span class="sxs-lookup"><span data-stu-id="b9270-167">Configure Supervised Mode via Intune</span></span>

<span data-ttu-id="b9270-168">Intune을 사용하면 앱 구성 정책을 통해 iOS용 Defender 앱을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9270-168">Intune allows you to configure the Defender for iOS app through an App Configuration policy.</span></span>

   > [!NOTE]
   > <span data-ttu-id="b9270-169">감독되는 장치에 대한 이 앱 구성 정책은 관리되는 장치에만 적용될 수 있으며 모범 사례로 관리되는 모든 iOS 장치를 대상으로 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9270-169">This app configuration policy for supervised devices is applicable only to managed devices and should be targeted for all managed iOS devices as a best practice.</span></span>

1. <span data-ttu-id="b9270-170">Microsoft Endpoint Manager 관리 센터에 [로그인하고](https://go.microsoft.com/fwlink/?linkid=2109431) 앱 앱 구성 정책 추가  >  **로**  >  **이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="b9270-170">Sign in to the [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431) and go to **Apps** > **App configuration policies** > **Add**.</span></span> <span data-ttu-id="b9270-171">관리되는 **장치를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="b9270-171">Click on **Managed devices**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="b9270-172">![Microsoft Endpoint Manager 관리 센터의 이미지](images/ios-deploy-4.png)</span><span class="sxs-lookup"><span data-stu-id="b9270-172">![Image of Microsoft Endpoint Manager Admin Center4](images/ios-deploy-4.png)</span></span>

1. <span data-ttu-id="b9270-173">앱 *구성 정책 만들기 페이지에서* 다음 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b9270-173">In the *Create app configuration policy* page, provide the following information:</span></span>
    - <span data-ttu-id="b9270-174">정책 이름</span><span class="sxs-lookup"><span data-stu-id="b9270-174">Policy Name</span></span>
    - <span data-ttu-id="b9270-175">플랫폼: iOS/iPadOS 선택</span><span class="sxs-lookup"><span data-stu-id="b9270-175">Platform: Select iOS/iPadOS</span></span>
    - <span data-ttu-id="b9270-176">대상 앱: 목록에서 **Microsoft Defender 끝점** 선택</span><span class="sxs-lookup"><span data-stu-id="b9270-176">Targeted app: Select **Microsoft Defender Endpoint** from the list</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="b9270-177">![Microsoft Endpoint Manager 관리 센터5의 이미지](images/ios-deploy-5.png)</span><span class="sxs-lookup"><span data-stu-id="b9270-177">![Image of Microsoft Endpoint Manager Admin Center5](images/ios-deploy-5.png)</span></span>

1. <span data-ttu-id="b9270-178">다음 화면에서 구성 **디자이너를** 형식으로 사용을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b9270-178">In the next screen, select **Use configuration designer** as the format.</span></span> <span data-ttu-id="b9270-179">다음 속성을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b9270-179">Specify the following property:</span></span>
    - <span data-ttu-id="b9270-180">구성 키: issupervised</span><span class="sxs-lookup"><span data-stu-id="b9270-180">Configuration Key: issupervised</span></span>
    - <span data-ttu-id="b9270-181">값 형식: String</span><span class="sxs-lookup"><span data-stu-id="b9270-181">Value type: String</span></span>
    - <span data-ttu-id="b9270-182">구성 값: {{issupervised}}</span><span class="sxs-lookup"><span data-stu-id="b9270-182">Configuration Value: {{issupervised}}</span></span>
    
    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="b9270-183">![관리 Microsoft Endpoint Manager 이미지6](images/ios-deploy-6.png)</span><span class="sxs-lookup"><span data-stu-id="b9270-183">![Image of Microsoft Endpoint Manager Admin Center6](images/ios-deploy-6.png)</span></span>

1. <span data-ttu-id="b9270-184">다음을 클릭하여 **범위** 태그 페이지를 열 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="b9270-184">Click **Next** to open the **Scope tags** page.</span></span> <span data-ttu-id="b9270-185">범위 태그는 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="b9270-185">Scope tags are optional.</span></span> <span data-ttu-id="b9270-186">**다음** 을 클릭하여 계속합니다.</span><span class="sxs-lookup"><span data-stu-id="b9270-186">Click **Next** to continue.</span></span>

1. <span data-ttu-id="b9270-187">과제 **페이지에서** 이 프로필을 받을 그룹을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b9270-187">On the **Assignments** page, select the groups that will receive this profile.</span></span> <span data-ttu-id="b9270-188">이 시나리오에서는 모든 장치를 대상으로 **지정하는 것이 가장 좋은 시나리오입니다.**</span><span class="sxs-lookup"><span data-stu-id="b9270-188">For this scenario, it is best practice to target **All Devices**.</span></span> <span data-ttu-id="b9270-189">프로필 할당에 대한 자세한 내용은 사용자 및 장치 프로필 [할당을 참조하세요.](/mem/intune/configuration/device-profile-assign)</span><span class="sxs-lookup"><span data-stu-id="b9270-189">For more information on assigning profiles, see [Assign user and device profiles](/mem/intune/configuration/device-profile-assign).</span></span>

   <span data-ttu-id="b9270-190">사용자 그룹에 배포할 때 정책이 적용되기 전에 사용자가 장치에 로그인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9270-190">When deploying to user groups, a user must sign in to a device before the policy applies.</span></span>

   <span data-ttu-id="b9270-191">**다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b9270-191">Click **Next**.</span></span>

1. <span data-ttu-id="b9270-192">검토 **+ 만들기 페이지에서** 완료되면 만들기 를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="b9270-192">On the **Review + create** page, when you're done, choose **Create**.</span></span> <span data-ttu-id="b9270-193">새 프로필이 구성 프로필 목록에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9270-193">The new profile is displayed in the list of configuration profiles.</span></span>

1. <span data-ttu-id="b9270-194">다음으로 향상된 피싱 방지 기능을 위해 감독되는 iOS 장치에 사용자 지정 프로필을 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9270-194">Next, for enhanced Anti-phishing capabilities, you can deploy a custom profile on the supervised iOS devices.</span></span> <span data-ttu-id="b9270-195">아래 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="b9270-195">Follow the steps below:</span></span>
    - <span data-ttu-id="b9270-196">에서 구성 프로필 다운로드 [https://aka.ms/mdatpiossupervisedprofile](https://aka.ms/mdatpiossupervisedprofile)</span><span class="sxs-lookup"><span data-stu-id="b9270-196">Download the config profile from [https://aka.ms/mdatpiossupervisedprofile](https://aka.ms/mdatpiossupervisedprofile)</span></span>
    - <span data-ttu-id="b9270-197">장치   ->  **iOS/iPadOS**  ->  **구성 프로필 프로필**  ->  **만들기로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="b9270-197">Navigate to **Devices** -> **iOS/iPadOS** -> **Configuration profiles** -> **Create Profile**</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="b9270-198">![Microsoft Endpoint Manager 관리 센터의 이미지7](images/ios-deploy-7.png)</span><span class="sxs-lookup"><span data-stu-id="b9270-198">![Image of Microsoft Endpoint Manager Admin Center7](images/ios-deploy-7.png)</span></span>

    - <span data-ttu-id="b9270-199">프로필 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="b9270-199">Provide a name of the profile.</span></span> <span data-ttu-id="b9270-200">구성 프로필 파일을 가져올지 묻는 메시지가 표시될 때 위에 다운로드한 프로필 파일을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b9270-200">When prompted to import a Configuration profile file, select the one downloaded above.</span></span>
    - <span data-ttu-id="b9270-201">할당 **섹션에서** 이 프로필을 적용할 장치 그룹을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b9270-201">In the **Assignment** section, select the device group to which you want to apply this profile.</span></span> <span data-ttu-id="b9270-202">이 방법은 모든 관리되는 iOS 장치에 적용하는 것이 가장 좋은 모범 사례입니다.</span><span class="sxs-lookup"><span data-stu-id="b9270-202">As a best practice, this should be applied to all managed iOS devices.</span></span> <span data-ttu-id="b9270-203">**다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b9270-203">Click **Next**.</span></span>
    - <span data-ttu-id="b9270-204">검토 **+ 만들기 페이지에서** 완료되면 만들기 를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="b9270-204">On the **Review + create** page, when you're done, choose **Create**.</span></span> <span data-ttu-id="b9270-205">새 프로필이 구성 프로필 목록에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9270-205">The new profile is displayed in the list of configuration profiles.</span></span>

## <a name="next-steps"></a><span data-ttu-id="b9270-206">다음 단계</span><span class="sxs-lookup"><span data-stu-id="b9270-206">Next Steps</span></span>

[<span data-ttu-id="b9270-207">iOS 기능에서 끝점에 대한 Defender 구성</span><span class="sxs-lookup"><span data-stu-id="b9270-207">Configure Defender for Endpoint on iOS features</span></span>](ios-configure-features.md)
