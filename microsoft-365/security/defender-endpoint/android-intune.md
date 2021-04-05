---
title: Microsoft Intune으로 엔드포인트용 Microsoft Defender(Android용) 배포
description: Microsoft Intune을 사용하여 Android용 끝점용 Microsoft Defender를 배포하는 방법에 대해 설명
keywords: microsoft, defender, atp, mde, android, 설치, 배포, 제거,
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: fdfc6e63945e15ce2d1f1a293c377f641eeb9bc4
ms.sourcegitcommit: 987f70e44e406ab6b1dd35f336a9d0c228032794
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2021
ms.locfileid: "51587698"
---
# <a name="deploy-microsoft-defender-for-endpoint-for-android-with-microsoft-intune"></a><span data-ttu-id="fe2a0-104">Microsoft Intune으로 엔드포인트용 Microsoft Defender(Android용) 배포</span><span class="sxs-lookup"><span data-stu-id="fe2a0-104">Deploy Microsoft Defender for Endpoint for Android with Microsoft Intune</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="fe2a0-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="fe2a0-105">**Applies to:**</span></span>
- <span data-ttu-id="fe2a0-106">[엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037) </span><span class="sxs-lookup"><span data-stu-id="fe2a0-106">[Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)</span></span>
- [<span data-ttu-id="fe2a0-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="fe2a0-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="fe2a0-108">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="fe2a0-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="fe2a0-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="fe2a0-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

<span data-ttu-id="fe2a0-110">Intune 회사 포털 등록 장치에서 Android용 끝점용 Defender를 배포하는 방법을 학습합니다.</span><span class="sxs-lookup"><span data-stu-id="fe2a0-110">Learn how to deploy Defender for Endpoint for Android on Intune Company Portal enrolled devices.</span></span> <span data-ttu-id="fe2a0-111">Intune 장치 등록에 대한 자세한 내용은 [장치 등록을 참조하세요.](https://docs.microsoft.com/mem/intune/user-help/enroll-device-android-company-portal)</span><span class="sxs-lookup"><span data-stu-id="fe2a0-111">For more information about Intune device enrollment, see  [Enroll your device](https://docs.microsoft.com/mem/intune/user-help/enroll-device-android-company-portal).</span></span>

> [!NOTE]
> <span data-ttu-id="fe2a0-112">**Android용 끝점용 Defender는 [이제 Google Play에서 사용할 수 있습니다.](https://play.google.com/store/apps/details?id=com.microsoft.scmx)**</span><span class="sxs-lookup"><span data-stu-id="fe2a0-112">**Defender for Endpoint for Android is now available on [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.scmx)**</span></span> <br>
> <span data-ttu-id="fe2a0-113">Intune에서 Google Play에 연결하여 장치 관리자 및 Android Enterprise 관리 모드로 끝점용 Defender 앱을 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe2a0-113">You can connect to Google Play from Intune to deploy Defender for Endpoint app across Device Administrator and Android Enterprise entrollment modes.</span></span>
<span data-ttu-id="fe2a0-114">앱 업데이트는 Google Play를 통해 자동으로 진행됩니다.</span><span class="sxs-lookup"><span data-stu-id="fe2a0-114">Updates to the app are automatic via Google Play.</span></span>

## <a name="deploy-on-device-administrator-enrolled-devices"></a><span data-ttu-id="fe2a0-115">장치 관리자 등록 장치에 배포</span><span class="sxs-lookup"><span data-stu-id="fe2a0-115">Deploy on Device Administrator enrolled devices</span></span>

<span data-ttu-id="fe2a0-116">**Intune 회사 포털에서 Android용 끝점용 Defender 배포 - 장치 관리자 등록 장치**</span><span class="sxs-lookup"><span data-stu-id="fe2a0-116">**Deploy Defender for Endpoint for Android on Intune Company Portal - Device Administrator enrolled devices**</span></span>

<span data-ttu-id="fe2a0-117">Intune 회사 포털 - 장치 관리자가 등록한 디바이스에서 Android용 끝점용 Defender를 배포하는 방법을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="fe2a0-117">Learn how to deploy Defender for Endpoint for Android on Intune Company Portal - Device Administrator enrolled devices.</span></span> 

### <a name="add-as-android-store-app"></a><span data-ttu-id="fe2a0-118">Android 스토어 앱으로 추가</span><span class="sxs-lookup"><span data-stu-id="fe2a0-118">Add as Android store app</span></span>

1. <span data-ttu-id="fe2a0-119">[Microsoft Endpoint Manager 관리 센터에서](https://go.microsoft.com/fwlink/?linkid=2109431) 앱 Android 앱 Android 스토어 앱  \>  \> **\> 추가로 이동하고** 선택을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="fe2a0-119">In [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431) , go to **Apps** \> **Android Apps** \> **Add \> Android store app** and choose **Select**.</span></span>

   ![Microsoft Endpoint Manager 관리 센터의 이미지 android 스토어 응용 프로그램 추가](images/mda-addandroidstoreapp.png)

2. <span data-ttu-id="fe2a0-121">앱 **추가 페이지에서** 앱 정보 *섹션에 다음을* 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="fe2a0-121">On the **Add app** page and in the *App Information* section enter:</span></span> 

   - <span data-ttu-id="fe2a0-122">**이름**</span><span class="sxs-lookup"><span data-stu-id="fe2a0-122">**Name**</span></span> 
   - <span data-ttu-id="fe2a0-123">**설명**</span><span class="sxs-lookup"><span data-stu-id="fe2a0-123">**Description**</span></span>
   - <span data-ttu-id="fe2a0-124">**Microsoft로 게시자.**</span><span class="sxs-lookup"><span data-stu-id="fe2a0-124">**Publisher** as Microsoft.</span></span>
   - <span data-ttu-id="fe2a0-125">**앱 스토어 URL** https://play.google.com/store/apps/details?id=com.microsoft.scmx as(Endpoint 앱용 Defender 앱 Google Play 스토어 URL)</span><span class="sxs-lookup"><span data-stu-id="fe2a0-125">**App store URL** as https://play.google.com/store/apps/details?id=com.microsoft.scmx (Defender for Endpoint app Google Play Store URL)</span></span> 

   <span data-ttu-id="fe2a0-126">다른 필드는 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="fe2a0-126">Other fields are optional.</span></span> <span data-ttu-id="fe2a0-127">**다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fe2a0-127">Select **Next**.</span></span>

   ![Microsoft Endpoint Manager 관리 센터의 이미지 앱 정보 추가](images/mda-addappinfo.png)

3. <span data-ttu-id="fe2a0-129">배정 *섹션에서* 필수 섹션으로 **이동하여** 그룹 **추가를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="fe2a0-129">In the *Assignments* section, go to the **Required** section and select **Add group.**</span></span> <span data-ttu-id="fe2a0-130">그런 다음 Android 앱용 끝점용 Defender를 대상으로 할 사용자 그룹을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe2a0-130">You can then choose the user group(s) that you would like to target Defender for Endpoint for Android app.</span></span> <span data-ttu-id="fe2a0-131">**Select(선택)를** 선택하고 **Next(다음)를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="fe2a0-131">Choose **Select** and then **Next**.</span></span>

    >[!NOTE]
    ><span data-ttu-id="fe2a0-132">선택한 사용자 그룹은 Intune에 등록된 사용자로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="fe2a0-132">The selected user group should consist of Intune enrolled users.</span></span>

    > [!div class="mx-imgBorder"]

    > ![선택한 사용자 그룹의 Microsoft Endpoint Manager 관리 센터 이미지](images/363bf30f7d69a94db578e8af0ddd044b.png)

4. <span data-ttu-id="fe2a0-134">**검토+만들기 섹션에서** 입력한 정보가 모두 올바른지 확인한 다음 만들기를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="fe2a0-134">In the **Review+Create** section, verify that all the information entered is correct and then select **Create**.</span></span>

    <span data-ttu-id="fe2a0-135">잠시 후 Endpoint용 Defender 앱이 성공적으로 만들어지며 알림이 페이지의 오른쪽 위 모서리에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="fe2a0-135">In a few moments, the Defender for Endpoint app would be created successfully, and a notification would show up at the top-right corner of the page.</span></span>

    ![Defender 끝점 앱의 Microsoft Endpoint Manager 관리 센터 알림 이미지](images/86cbe56f88bb6e93e9c63303397fc24f.png)

5. <span data-ttu-id="fe2a0-137">표시되는 앱 정보 페이지의 모니터 섹션에서 장치  설치 상태를 선택하여 장치 설치가 성공적으로 완료되어 있는지 확인합니다. </span><span class="sxs-lookup"><span data-stu-id="fe2a0-137">In the app information page that is displayed, in the **Monitor** section, select **Device install status** to verify that the device installation has completed successfully.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="fe2a0-138">![Microsoft Endpoint Manager 관리 센터 장치 설치 이미지](images/513cf5d59eaaef5d2b5bc122715b5844.png)</span><span class="sxs-lookup"><span data-stu-id="fe2a0-138">![Image of Microsoft Endpoint Manager Admin Center device install](images/513cf5d59eaaef5d2b5bc122715b5844.png)</span></span>

### <a name="complete-onboarding-and-check-status"></a><span data-ttu-id="fe2a0-139">온보더링 완료 및 상태 확인</span><span class="sxs-lookup"><span data-stu-id="fe2a0-139">Complete onboarding and check status</span></span>

1. <span data-ttu-id="fe2a0-140">Android용 끝점용 Defender가 장치에 설치되면 앱 아이콘이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="fe2a0-140">Once Defender for Endpoint for Android has been installed on the device, you'll see the app icon.</span></span>

    ![모바일 장치의 아이콘](images/7cf9311ad676ec5142002a4d0c2323ca.jpg)

2. <span data-ttu-id="fe2a0-142">Microsoft Defender ATP 앱 아이콘을 탭하고 화면 지침에 따라 앱 온보딩을 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="fe2a0-142">Tap the Microsoft Defender ATP app icon and follow the on-screen instructions to complete onboarding the app.</span></span> <span data-ttu-id="fe2a0-143">세부 정보에는 Android용 끝점용 Defender에 필요한 Android 사용 권한의 최종 사용자 수락이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="fe2a0-143">The details include end-user acceptance of Android permissions required by Defender for Endpoint for Android.</span></span>

3. <span data-ttu-id="fe2a0-144">온보딩에 성공하면 장치가 Microsoft Defender 보안 센터의 장치 목록에 표시될 것입니다.</span><span class="sxs-lookup"><span data-stu-id="fe2a0-144">Upon successful onboarding, the device will start showing up on the Devices list in Microsoft Defender Security Center.</span></span>

    ![Endpoint 포털용 Defender의 장치 이미지](images/9fe378a1dce0f143005c3aa53d8c4f51.png)

## <a name="deploy-on-android-enterprise-enrolled-devices"></a><span data-ttu-id="fe2a0-146">Android Enterprise 등록 장치에 배포</span><span class="sxs-lookup"><span data-stu-id="fe2a0-146">Deploy on Android Enterprise enrolled devices</span></span>

<span data-ttu-id="fe2a0-147">Android용 Endpoint용 Defender는 Android Enterprise 등록 장치를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="fe2a0-147">Defender for Endpoint for Android supports Android Enterprise enrolled devices.</span></span>

<span data-ttu-id="fe2a0-148">Intune에서 지원하는 등록 옵션에 대한 자세한 내용은 [등록 옵션 을 참조하세요.](https://docs.microsoft.com/mem/intune/enrollment/android-enroll)</span><span class="sxs-lookup"><span data-stu-id="fe2a0-148">For more information on the enrollment options supported by Intune, see [Enrollment Options](https://docs.microsoft.com/mem/intune/enrollment/android-enroll).</span></span>

<span data-ttu-id="fe2a0-149">**현재 회사 프로필이 있는 개인 소유 장치 및 회사 소유의 완전히 관리되는 사용자 장치 등록은 배포에 지원됩니다.**</span><span class="sxs-lookup"><span data-stu-id="fe2a0-149">**Currently, Personally owned devices with work profile and Corporate-owned fully managed user device enrollments are supported for deployment.**</span></span>

## <a name="add-microsoft-defender-for-endpoint-for-android-as-a-managed-google-play-app"></a><span data-ttu-id="fe2a0-150">Android용 끝점용 Microsoft Defender를 관리되는 Google Play 앱으로 추가</span><span class="sxs-lookup"><span data-stu-id="fe2a0-150">Add Microsoft Defender for Endpoint for Android as a Managed Google Play app</span></span>

<span data-ttu-id="fe2a0-151">아래 단계에 따라 관리되는 Google Play에 끝점용 Microsoft Defender 앱을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="fe2a0-151">Follow the steps below to add Microsoft Defender for Endpoint app into your managed Google Play.</span></span>

1. <span data-ttu-id="fe2a0-152">[Microsoft Endpoint Manager 관리 센터에서](https://go.microsoft.com/fwlink/?linkid=2109431) 앱 Android 앱 추가로  \>  \> **이동하여** **관리되는 Google Play 앱 을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="fe2a0-152">In [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431) , go to **Apps** \> **Android Apps** \> **Add** and select **Managed Google Play app**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="fe2a0-153">![Microsoft Endpoint Manager 관리 센터 관리 Google Play의 이미지](images/579ff59f31f599414cedf63051628b2e.png)</span><span class="sxs-lookup"><span data-stu-id="fe2a0-153">![Image of Microsoft Endpoint Manager admin center managed google play](images/579ff59f31f599414cedf63051628b2e.png)</span></span>

2. <span data-ttu-id="fe2a0-154">이후에 로드되는 관리되는 Google Play 페이지에서 검색 상자로 이동하여 **Microsoft Defender를 검색합니다.**</span><span class="sxs-lookup"><span data-stu-id="fe2a0-154">On your managed Google Play page that loads subsequently, go to the search box and lookup **Microsoft Defender.**</span></span> <span data-ttu-id="fe2a0-155">검색은 관리되는 Google Play에 끝점용 Microsoft Defender 앱을 표시해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe2a0-155">Your search should display the Microsoft Defender for Endpoint app in your Managed Google Play.</span></span> <span data-ttu-id="fe2a0-156">앱 검색 결과에서 끝점용 Microsoft Defender 앱을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="fe2a0-156">Click on the Microsoft Defender for Endpoint app from the Apps search result.</span></span>

    ![Microsoft Endpoint Manager 관리 센터 앱 검색의 이미지](images/0f79cb37900b57c3e2bb0effad1c19cb.png)

3. <span data-ttu-id="fe2a0-158">다음에 나오는 앱 설명 페이지에서 끝점용 Defender에서 앱 세부 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe2a0-158">In the App description page that comes up next, you should be able to see app details on Defender for Endpoint.</span></span> <span data-ttu-id="fe2a0-159">페이지에서 정보를 검토한 다음 승인 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="fe2a0-159">Review the information on the page and then select **Approve**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="fe2a0-160">![관리되는 Google Play의 스크린샷](images/07e6d4119f265037e3b80a20a73b856f.png)</span><span class="sxs-lookup"><span data-stu-id="fe2a0-160">![A screenshot of a Managed Google Play](images/07e6d4119f265037e3b80a20a73b856f.png)</span></span>

4. <span data-ttu-id="fe2a0-161">Endpoint용 Defender가 작동하기 위해 획득하는 사용 권한을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="fe2a0-161">You'll be presented with the permissions that Defender for Endpoint obtains for it to work.</span></span> <span data-ttu-id="fe2a0-162">검토한 다음 승인 **을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="fe2a0-162">Review them and then select **Approve**.</span></span>

    ![Endpoint 미리 보기 앱 승인을 위한 Defender 스크린샷](images/206b3d954f06cc58b3466fb7a0bd9f74.png)

5. <span data-ttu-id="fe2a0-164">승인 설정 페이지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="fe2a0-164">You'll be presented with the Approval settings page.</span></span> <span data-ttu-id="fe2a0-165">이 페이지에서는 Android용 Endpoint용 Defender가 요청하는 새 앱 권한을 처리하기 위한 기본 설정을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe2a0-165">The page confirms your preference to handle new app permissions that Defender for Endpoint for Android might ask.</span></span> <span data-ttu-id="fe2a0-166">선택을 검토하고 원하는 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fe2a0-166">Review the choices and select your preferred option.</span></span> <span data-ttu-id="fe2a0-167">**완료** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fe2a0-167">Select **Done**.</span></span>

    <span data-ttu-id="fe2a0-168">기본적으로 관리되는 Google Play는 앱이 새 권한을 요청할 때 *승인된 유지를 선택합니다.*</span><span class="sxs-lookup"><span data-stu-id="fe2a0-168">By default, managed Google Play selects *Keep approved when app requests new permissions*</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="fe2a0-169">![알림 탭의 이미지](images/ffecfdda1c4df14148f1526c22cc0236.png)</span><span class="sxs-lookup"><span data-stu-id="fe2a0-169">![Image of notifications tab](images/ffecfdda1c4df14148f1526c22cc0236.png)</span></span>

6. <span data-ttu-id="fe2a0-170">사용 권한 처리 선택이 끝나면 동기화를 선택하여 끝점용 Microsoft Defender를 앱 목록에 동기화합니다. </span><span class="sxs-lookup"><span data-stu-id="fe2a0-170">After the permissions handling selection is made, select **Sync** to sync Microsoft Defender for Endpoint to your apps list.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="fe2a0-171">![동기화 페이지의 이미지](images/34e6b9a0dae125d085c84593140180ed.png)</span><span class="sxs-lookup"><span data-stu-id="fe2a0-171">![Image of sync page](images/34e6b9a0dae125d085c84593140180ed.png)</span></span>

7. <span data-ttu-id="fe2a0-172">동기화는 몇 분 후에 완료됩니다.</span><span class="sxs-lookup"><span data-stu-id="fe2a0-172">The sync will complete in a few minutes.</span></span>

    ![Android 앱의 이미지](images/9fc07ffc150171f169dc6e57fe6f1c74.png)

8. <span data-ttu-id="fe2a0-174">Android 앱 **화면에서** 새로 고침 단추를 선택하면 Microsoft Defender ATP가 앱 목록에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="fe2a0-174">Select the **Refresh** button in the Android apps screen and Microsoft Defender ATP should be visible in the apps list.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="fe2a0-175">![Android 앱 목록의 이미지](images/fa4ac18a6333335db3775630b8e6b353.png)</span><span class="sxs-lookup"><span data-stu-id="fe2a0-175">![Image of list of Android apps](images/fa4ac18a6333335db3775630b8e6b353.png)</span></span>

9. <span data-ttu-id="fe2a0-176">Endpoint용 Defender는 Intune을 통해 관리되는 장치에 대한 앱 구성 정책을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="fe2a0-176">Defender for Endpoint supports App configuration policies for managed devices via Intune.</span></span> <span data-ttu-id="fe2a0-177">이 기능을 사용하여 적용 가능한 Android 사용 권한을 자동으로 그라데이터하여 최종 사용자가 이러한 사용 권한을 수락할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fe2a0-177">This capability can be leveraged to autogrant applicable Android permission(s), so the end user does not need to accept these permission(s).</span></span>

    1. <span data-ttu-id="fe2a0-178">앱 **페이지에서** 정책 > 앱 구성 정책 > 관리 > **이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="fe2a0-178">In the **Apps** page, go to **Policy > App configuration policies > Add > Managed devices**.</span></span>

       ![Microsoft Endpoint Manager 관리 센터 Android 관리 장치의 이미지](images/android-mem.png)

    1. <span data-ttu-id="fe2a0-180">앱 **구성 정책 만들기 페이지에서** 다음 세부 정보를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="fe2a0-180">In the **Create app configuration policy** page, enter the following details:</span></span>
    
        - <span data-ttu-id="fe2a0-181">이름: Microsoft Defender ATP.</span><span class="sxs-lookup"><span data-stu-id="fe2a0-181">Name: Microsoft Defender ATP.</span></span>
        - <span data-ttu-id="fe2a0-182">**플랫폼으로 Android Enterprise를** 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="fe2a0-182">Choose **Android Enterprise** as platform.</span></span>
        - <span data-ttu-id="fe2a0-183">프로필 **유형으로만 작업** 프로필을 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="fe2a0-183">Choose **Work Profile only** as Profile Type.</span></span>
        - <span data-ttu-id="fe2a0-184">앱 **선택을 클릭하고** **Microsoft Defender ATP를 선택하고** 확인을 선택한 후 다음을 **선택합니다.** </span><span class="sxs-lookup"><span data-stu-id="fe2a0-184">Click **Select App**, choose **Microsoft Defender ATP**, select **OK** and then **Next**.</span></span>
    
        > [!div class="mx-imgBorder"]
        > <span data-ttu-id="fe2a0-185">![앱 구성 정책 만들기 페이지 이미지](images/android-create-app.png)</span><span class="sxs-lookup"><span data-stu-id="fe2a0-185">![Image of create app configuration policy page](images/android-create-app.png)</span></span>

    1. <span data-ttu-id="fe2a0-186">설정 **페이지에서** 사용 권한 섹션으로 이동하여 추가를 클릭하여 지원되는 사용 권한 목록을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="fe2a0-186">In the **Settings** page, go to the Permissions section click on Add to view the list of supported permissions.</span></span> <span data-ttu-id="fe2a0-187">사용 권한 추가 섹션에서 다음 사용 권한을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fe2a0-187">In the Add Permissions section, select the following permissions:</span></span>

       - <span data-ttu-id="fe2a0-188">외부 저장소(읽기)</span><span class="sxs-lookup"><span data-stu-id="fe2a0-188">External storage (read)</span></span>
       - <span data-ttu-id="fe2a0-189">외부 저장소(쓰기)</span><span class="sxs-lookup"><span data-stu-id="fe2a0-189">External storage (write)</span></span>

       <span data-ttu-id="fe2a0-190">그런 다음 **확인** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fe2a0-190">Then select **OK**.</span></span>

       > [!div class="mx-imgBorder"]
      > <span data-ttu-id="fe2a0-191">![Android의 이미지 앱 구성 정책 만들기](images/android-create-app-config.png)</span><span class="sxs-lookup"><span data-stu-id="fe2a0-191">![Image of android create app configuration policy](images/android-create-app-config.png)</span></span>

    1. <span data-ttu-id="fe2a0-192">이제 두 사용 권한이 모두 나열되어 있으며 이제 사용 권한 상태 드롭다운에서 자동grant를 선택하고 다음 을 선택하여 둘 다 자동 그라데이트할 수 **있습니다.** </span><span class="sxs-lookup"><span data-stu-id="fe2a0-192">You should now see both the permissions listed and now you can autogrant both by choosing autogrant in the **Permission state** drop-down and then select **Next**.</span></span>

       > [!div class="mx-imgBorder"]
       > <span data-ttu-id="fe2a0-193">![Android 자동 부여 앱 구성 정책 만들기 이미지](images/android-auto-grant.png)</span><span class="sxs-lookup"><span data-stu-id="fe2a0-193">![Image of android auto grant create app configuration policy](images/android-auto-grant.png)</span></span>

    1. <span data-ttu-id="fe2a0-194">할당 **페이지에서** 이 앱 구성 정책을 할당할 사용자 그룹을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fe2a0-194">In the **Assignments** page, select the user group to which this app config policy would be assigned to.</span></span> <span data-ttu-id="fe2a0-195">그룹 **선택을 클릭하여** 해당 그룹을 포함하고 선택한 후 다음 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="fe2a0-195">Click **Select groups to include** and selecting the applicable group and then selecting **Next**.</span></span>  <span data-ttu-id="fe2a0-196">여기서 선택한 그룹은 일반적으로 Endpoint Android용 Microsoft Defender 앱을 할당할 그룹과 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="fe2a0-196">The group selected here is usually the same group to which you would assign Microsoft Defender for Endpoint Android app.</span></span> 

       > [!div class="mx-imgBorder"]
       > <span data-ttu-id="fe2a0-197">![앱 구성 정책 만들기 이미지](images/android-select-group.png)</span><span class="sxs-lookup"><span data-stu-id="fe2a0-197">![Image of the create app configuration policy](images/android-select-group.png)</span></span>
    

     1. <span data-ttu-id="fe2a0-198">다음에 **나오는 검토 + 만들기** 페이지에서 모든 정보를 검토하고 만들기를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="fe2a0-198">In the **Review + Create** page that comes up next, review all the information and then select **Create**.</span></span> <br>
    
        <span data-ttu-id="fe2a0-199">이제 저장소 권한을 자동으로 확장하기 위한 Defender에 대한 앱 구성 정책이 선택한 사용자 그룹에 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="fe2a0-199">The app configuration policy for Defender for Endpoint autogranting the storage permission is now assigned to the selected user group.</span></span>

        > [!div class="mx-imgBorder"]
        > <span data-ttu-id="fe2a0-200">![Android 리뷰 앱 구성 정책 만들기 이미지](images/android-review-create.png)</span><span class="sxs-lookup"><span data-stu-id="fe2a0-200">![Image of android review create app config policy](images/android-review-create.png)</span></span>


10. <span data-ttu-id="fe2a0-201">속성 할당 편집 목록에서 **Microsoft Defender ATP** \>  \> **앱을** \> **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="fe2a0-201">Select **Microsoft Defender ATP** app in the list \> **Properties** \> **Assignments** \> **Edit**.</span></span>

    ![앱 목록 이미지](images/mda-properties.png)


11. <span data-ttu-id="fe2a0-203">앱을 필수 *앱으로* 사용자 그룹에 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="fe2a0-203">Assign the app as a *Required* app to a user group.</span></span> <span data-ttu-id="fe2a0-204">회사 포털 앱을  통해 다음에 디바이스를 동기화하는 동안 회사 프로필에 자동으로 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="fe2a0-204">It is automatically installed in the *work profile* during the next sync of the device via Company Portal app.</span></span> <span data-ttu-id="fe2a0-205">이 할당은 필수 섹션 그룹 추가로 가고  사용자 그룹을 선택하고 선택을 클릭하여 \>  완료할 **수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="fe2a0-205">This assignment can be done by navigating to the *Required* section \> **Add group,** selecting the user group and click **Select**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="fe2a0-206">![응용 프로그램 페이지 편집 이미지](images/ea06643280075f16265a596fb9a96042.png)</span><span class="sxs-lookup"><span data-stu-id="fe2a0-206">![Image of edit application page](images/ea06643280075f16265a596fb9a96042.png)</span></span>


12. <span data-ttu-id="fe2a0-207">응용 **프로그램 편집 페이지에서** 위에 입력한 모든 정보를 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="fe2a0-207">In the **Edit Application** page, review all the information that was entered above.</span></span> <span data-ttu-id="fe2a0-208">그런 다음 **검토 + 저장을 선택한** 다음 다시 **저장을** 선택하여 배정을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="fe2a0-208">Then select **Review + Save** and then **Save** again to commence assignment.</span></span>

### <a name="auto-setup-of-always-on-vpn"></a><span data-ttu-id="fe2a0-209">Always-on VPN의 자동 설정</span><span class="sxs-lookup"><span data-stu-id="fe2a0-209">Auto Setup of Always-on VPN</span></span> 
<span data-ttu-id="fe2a0-210">Endpoint용 Defender는 Intune을 통해 관리되는 장치에 대한 장치 구성 정책을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="fe2a0-210">Defender for Endpoint supports Device configuration policies for managed devices via Intune.</span></span> <span data-ttu-id="fe2a0-211">이 기능을 활용하여 Android Enterprise 등록 장치에서 **Always-on VPN의** 자동 설정에 활용할 수 있으므로 최종 사용자는 온보드하는 동안 VPN 서비스를 설정할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fe2a0-211">This capability can be leveraged to **Auto setup of Always-on VPN** on Android Enterprise enrolled devices, so the end user does not need to set up VPN service while onboarding.</span></span>
1.  <span data-ttu-id="fe2a0-212">장치에서 **구성** 프로필 만들기 프로필 플랫폼 Android 엔터프라이즈 장치 등록 유형에 따라 다음 중 하나에서 장치 제한  >    >    >   선택을 선택합니다. </span><span class="sxs-lookup"><span data-stu-id="fe2a0-212">On **Devices**, select **Configuration Profiles** > **Create Profile** > **Platform** > **Android Enterprise** Select **Device restrictions** under one of the following, based on your device enrollment type</span></span> 
- <span data-ttu-id="fe2a0-213">**완전히 관리, 전용 및 Corporate-Owned 프로필**</span><span class="sxs-lookup"><span data-stu-id="fe2a0-213">**Fully Managed, Dedicated, and Corporate-Owned Work Profile**</span></span>
- <span data-ttu-id="fe2a0-214">**개인 소유의 작업 프로필**</span><span class="sxs-lookup"><span data-stu-id="fe2a0-214">**Personally owned Work Profile**</span></span>

<span data-ttu-id="fe2a0-215">**만들기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fe2a0-215">Select **Create**.</span></span>
 
   > ![장치 구성 프로필 만들기의 이미지](images/1autosetupofvpn.png)
    
2. <span data-ttu-id="fe2a0-217">**구성 설정** 구성 **프로필을** 고유하게 식별하는 **이름** 및 설명을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="fe2a0-217">**Configuration Settings** Provide a **Name** and a **Description** to uniquely identify the configuration profile.</span></span> 

   > ![장치 구성 프로필 이름 및 설명 이미지](images/2autosetupofvpn.png)
   
 3. <span data-ttu-id="fe2a0-219">연결을 **선택하고** VPN을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="fe2a0-219">Select **Connectivity** and configure VPN:</span></span>
- <span data-ttu-id="fe2a0-220">항상 **VPN 설정** 작업 프로필에서 VPN 클라이언트를 설정하여 가능하면 VPN에 자동으로 연결하고 다시 연결하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe2a0-220">Enable **Always-on VPN** Setup a VPN client in the work profile to automatically connect and reconnect to the VPN whenever possible.</span></span> <span data-ttu-id="fe2a0-221">특정 디바이스에서 항상 사용되는 VPN에 대해 VPN 클라이언트를 하나만 구성할 수 있으므로 단일 디바이스에 항상 실행형 VPN 정책이 두 개 이상 배포되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fe2a0-221">Only one VPN client can be configured for always-on VPN on a given device, so be sure to have no more than one always-on VPN policy deployed to a single device.</span></span> 
- <span data-ttu-id="fe2a0-222">VPN **클라이언트** 드롭다운 목록에서 사용자 지정을 선택합니다. 이 경우 웹 보호 기능을 제공하는 데 사용되는 끝점 VPN용 Defender VPN입니다.</span><span class="sxs-lookup"><span data-stu-id="fe2a0-222">Select **Custom** in VPN client dropdown list Custom VPN in this case is Defender for Endpoint VPN which is used to provide the Web Protection feature.</span></span> 
    > [!NOTE]
    > <span data-ttu-id="fe2a0-223">이 VPN의 자동 설치를 작동하려면 Microsoft Defender ATP 앱을 사용자 장치에 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe2a0-223">Microsoft Defender ATP app must be installed on user’s device, in order to functioning of auto setup of this VPN.</span></span>

- <span data-ttu-id="fe2a0-224">Google  Play 스토어에서 Microsoft Defender ATP 앱의 패키지 ID를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="fe2a0-224">Enter **Package ID** of the Microsoft Defender ATP app in Google Play store.</span></span> <span data-ttu-id="fe2a0-225">Defender 앱 URL의 https://play.google.com/store/apps/details?id=com.microsoft.scmx 경우 패키지 ID는 **com.microsoft.scmx입니다.**</span><span class="sxs-lookup"><span data-stu-id="fe2a0-225">For the Defender app URL https://play.google.com/store/apps/details?id=com.microsoft.scmx, Package ID is **com.microsoft.scmx**</span></span>  
- <span data-ttu-id="fe2a0-226">**잠금 모드** 구성되지 않습니다(기본값)</span><span class="sxs-lookup"><span data-stu-id="fe2a0-226">**Lockdown mode** Not configured (Default)</span></span> 

     ![장치 구성 프로필의 이미지로 Always-On VPN을 사용하도록 설정](images/3autosetupofvpn.png)
   
4. <span data-ttu-id="fe2a0-228">**배정** 할당  **페이지에서** 이 앱 구성 정책을 할당할 사용자 그룹을   선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fe2a0-228">**Assignment** In the **Assignments** page, select the user group to which this app config policy would be assigned to.</span></span> <span data-ttu-id="fe2a0-229">그룹 **선택을** 클릭하여 해당 그룹을 포함 및 선택하고 다음을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="fe2a0-229">Click **Select groups** to include and selecting the applicable group and then click **Next**.</span></span> <span data-ttu-id="fe2a0-230">여기서 선택한 그룹은 일반적으로 Endpoint Android용 Microsoft Defender 앱을 할당할 그룹과 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="fe2a0-230">The group selected here is usually the same group to which you would assign Microsoft Defender for Endpoint Android app.</span></span> 

     ![장치 구성 프로필의 이미지 할당](images/4autosetupofvpn.png)

5. <span data-ttu-id="fe2a0-232">다음에 **나오는 검토 + 만들기** 페이지에서 모든 정보를 검토하고 만들기를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="fe2a0-232">In the **Review + Create** page that comes up next, review all the information and then select **Create**.</span></span> <span data-ttu-id="fe2a0-233">이제 장치 구성 프로필이 선택한 사용자 그룹에 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="fe2a0-233">The device configuration profile is now assigned to the selected user group.</span></span>    

    ![장치 구성 프로필의 이미지 검토 및 만들기](images/5autosetupofvpn.png)

## <a name="complete-onboarding-and-check-status"></a><span data-ttu-id="fe2a0-235">온보더링 완료 및 상태 확인</span><span class="sxs-lookup"><span data-stu-id="fe2a0-235">Complete onboarding and check status</span></span>

1. <span data-ttu-id="fe2a0-236">장치 설치 상태를 클릭하여 Android용 끝점용 Microsoft Defender의 설치 **상태를 확인합니다.**</span><span class="sxs-lookup"><span data-stu-id="fe2a0-236">Confirm the installation status of Microsoft Defender for Endpoint for Android by clicking on the **Device Install Status**.</span></span> <span data-ttu-id="fe2a0-237">디바이스가 여기에 표시되는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="fe2a0-237">Verify that the device is displayed here.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="fe2a0-238">![장치 설치 상태의 이미지](images/900c0197aa59f9b7abd762ab2b32e80c.png)</span><span class="sxs-lookup"><span data-stu-id="fe2a0-238">![Image of device installation status](images/900c0197aa59f9b7abd762ab2b32e80c.png)</span></span>


2. <span data-ttu-id="fe2a0-239">장치에서 작업 프로필로 가면 온보더링 상태의 유효성을 **검사할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="fe2a0-239">On the device, you can validate the onboarding status by going to the **work profile**.</span></span> <span data-ttu-id="fe2a0-240">끝점용 Defender를 사용할 수 있으며, 작업 프로필을 사용하여 개인 소유 장치에 **등록하는지 확인**</span><span class="sxs-lookup"><span data-stu-id="fe2a0-240">Confirm that Defender for Endpoint is available and that you are enrolled to the **Personally owned devices with work profile**.</span></span>  <span data-ttu-id="fe2a0-241">회사 소유의 완전히 관리되는 사용자 장치에 등록한 경우 디바이스에 단일 프로필이 있습니다. 여기서 끝점용 Defender를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe2a0-241">If you are enrolled to a **Corporate-owned, fully managed user device**, you will have a single profile on the device where you can confirm that Defender for Endpoint is available.</span></span>

    ![모바일 장치의 앱 이미지](images/c2e647fc8fa31c4f2349c76f2497bc0e.png)

3. <span data-ttu-id="fe2a0-243">앱이 설치되면 앱을 열고 사용 권한을 수락한 다음 온보더링이 성공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe2a0-243">When the app is installed, open the app and accept the permissions and then your onboarding should be successful.</span></span>

    ![Microsoft Defender for Endpoint 앱을 사용하여 모바일 장치의 이미지](images/mda-devicesafe.png)

4. <span data-ttu-id="fe2a0-245">이 단계에서 장치는 Android용 끝점용 Defender에 성공적으로 온보딩됩니다.</span><span class="sxs-lookup"><span data-stu-id="fe2a0-245">At this stage the device is successfully onboarded onto Defender for Endpoint for Android.</span></span> <span data-ttu-id="fe2a0-246">장치 페이지로 이동하여 [Microsoft Defender 보안](https://securitycenter.microsoft.com) 센터에서 이를 확인할 **수** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe2a0-246">You can verify this on the [Microsoft Defender Security Center](https://securitycenter.microsoft.com) by navigating to the **Devices** page.</span></span>

    ![Endpoint 포털용 Microsoft Defender 이미지](images/9fe378a1dce0f143005c3aa53d8c4f51.png)


## <a name="related-topics"></a><span data-ttu-id="fe2a0-248">관련 항목</span><span class="sxs-lookup"><span data-stu-id="fe2a0-248">Related topics</span></span>
- [<span data-ttu-id="fe2a0-249">엔드포인트용 Microsoft Defender(Android용) 개요</span><span class="sxs-lookup"><span data-stu-id="fe2a0-249">Overview of Microsoft Defender for Endpoint for Android</span></span>](microsoft-defender-endpoint-android.md)
- [<span data-ttu-id="fe2a0-250">엔드포인트용 Microsoft Defender(Android용) 기능 구성</span><span class="sxs-lookup"><span data-stu-id="fe2a0-250">Configure Microsoft Defender for Endpoint for Android features</span></span>](android-configure.md)
