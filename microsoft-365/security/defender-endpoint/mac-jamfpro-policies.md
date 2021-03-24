---
title: Jamf Pro에서 macOS용 Microsoft Defender ATP 정책 설정
description: Jamf Pro에서 macOS용 Microsoft Defender ATP를 설정하는 방법을 배우기
keywords: 정책, Microsoft, defender, atp, mac, 설치, 배포, 제거, intune, jamfpro, macos, catalina, mojave, high sierra
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
ms.openlocfilehash: 1559d8dca6b6909f22473c5a8f4d25d4bac501d1
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51070292"
---
# <a name="set-up-the-microsoft-defender-for-endpoint-for-macos-policies-in-jamf-pro"></a><span data-ttu-id="caf50-104">Jamf Pro에서 macOS용 끝점용 Microsoft Defender 정책 설정</span><span class="sxs-lookup"><span data-stu-id="caf50-104">Set up the Microsoft Defender for Endpoint for macOS policies in Jamf Pro</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="caf50-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="caf50-105">**Applies to:**</span></span>

- [<span data-ttu-id="caf50-106">Mac용 끝점용 Defender</span><span class="sxs-lookup"><span data-stu-id="caf50-106">Defender for Endpoint for Mac</span></span>](microsoft-defender-endpoint-mac.md)

<span data-ttu-id="caf50-107">이 페이지에서는 Jamf Pro에서 macOS 정책을 설정하는 데 필요한 단계를 안내합니다.</span><span class="sxs-lookup"><span data-stu-id="caf50-107">This page will guide you through the steps you need to take to set up macOS policies in Jamf Pro.</span></span>

<span data-ttu-id="caf50-108">다음 단계를 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="caf50-108">You'll need to take the following steps:</span></span>

1. [<span data-ttu-id="caf50-109">끝점용 Microsoft Defender 온보딩 패키지 다운로드</span><span class="sxs-lookup"><span data-stu-id="caf50-109">Get the Microsoft Defender for Endpoint onboarding package</span></span>](#step-1-get-the-microsoft-defender-for-endpoint-onboarding-package)

2. [<span data-ttu-id="caf50-110">온보더링 패키지를 사용하여 Jamf Pro에서 구성 프로필 만들기</span><span class="sxs-lookup"><span data-stu-id="caf50-110">Create a configuration profile in Jamf Pro using the onboarding package</span></span>](#step-2-create-a-configuration-profile-in-jamf-pro-using-the-onboarding-package)

3. [<span data-ttu-id="caf50-111">끝점 설정에 맞게 Microsoft Defender 구성</span><span class="sxs-lookup"><span data-stu-id="caf50-111">Configure Microsoft Defender for Endpoint settings</span></span>](#step-3-configure-microsoft-defender-for-endpoint-settings)

4. [<span data-ttu-id="caf50-112">끝점 알림 설정에 맞게 Microsoft Defender 구성</span><span class="sxs-lookup"><span data-stu-id="caf50-112">Configure Microsoft Defender for Endpoint notification settings</span></span>](#step-4-configure-notifications-settings)

5. [<span data-ttu-id="caf50-113">MAU(Microsoft 자동 업데이트) 구성</span><span class="sxs-lookup"><span data-stu-id="caf50-113">Configure Microsoft AutoUpdate (MAU)</span></span>](#step-5-configure-microsoft-autoupdate-mau)

6. [<span data-ttu-id="caf50-114">끝점용 Microsoft Defender에 대한 전체 디스크 액세스 권한 부여</span><span class="sxs-lookup"><span data-stu-id="caf50-114">Grant full disk access to Microsoft Defender for Endpoint</span></span>](#step-6-grant-full-disk-access-to-microsoft-defender-for-endpoint)

7. [<span data-ttu-id="caf50-115">끝점용 Microsoft Defender에 대한 커널 확장 승인</span><span class="sxs-lookup"><span data-stu-id="caf50-115">Approve Kernel extension for Microsoft Defender for Endpoint</span></span>](#step-7-approve-kernel-extension-for-microsoft-defender-for-endpoint)

8. [<span data-ttu-id="caf50-116">끝점용 Microsoft Defender에 대한 시스템 확장 승인</span><span class="sxs-lookup"><span data-stu-id="caf50-116">Approve System extensions for Microsoft Defender for Endpoint</span></span>](#step-8-approve-system-extensions-for-microsoft-defender-for-endpoint)

9. [<span data-ttu-id="caf50-117">네트워크 확장 구성</span><span class="sxs-lookup"><span data-stu-id="caf50-117">Configure Network Extension</span></span>](#step-9-configure-network-extension)

10. [<span data-ttu-id="caf50-118">Mac용 끝점에 대한 Microsoft Defender 검사 예약</span><span class="sxs-lookup"><span data-stu-id="caf50-118">Schedule scans with Microsoft Defender for Endpoint for Mac</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/mac-schedule-scan-atp)

11. [<span data-ttu-id="caf50-119">MacOS용 끝점용 Microsoft Defender 배포</span><span class="sxs-lookup"><span data-stu-id="caf50-119">Deploy Microsoft Defender for Endpoint for macOS</span></span>](#step-11-deploy-microsoft-defender-for-endpoint-for-macos)


## <a name="step-1-get-the-microsoft-defender-for-endpoint-onboarding-package"></a><span data-ttu-id="caf50-120">1단계: 끝점용 Microsoft Defender 온보딩 패키지 다운로드</span><span class="sxs-lookup"><span data-stu-id="caf50-120">Step 1: Get the Microsoft Defender for Endpoint onboarding package</span></span>

1. <span data-ttu-id="caf50-121">[Microsoft Defender 보안 센터에서](https://securitycenter.microsoft.com )설정 > **온보딩으로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="caf50-121">In [Microsoft Defender Security Center](https://securitycenter.microsoft.com ), navigate to **Settings > Onboarding**.</span></span> 

2. <span data-ttu-id="caf50-122">운영 체제로 macOS를 선택하고 배포 방법으로 모바일 장치 관리/Microsoft Intune을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="caf50-122">Select macOS as the operating system and Mobile Device Management / Microsoft Intune as the deployment method.</span></span>

    ![Microsoft Defender 보안 센터의 이미지](images/onboarding-macos.png)

3. <span data-ttu-id="caf50-124">**온보더링 패키지 다운로드(WindowsDefenderATPOnboardingPackage.zip).**</span><span class="sxs-lookup"><span data-stu-id="caf50-124">Select **Download onboarding package** (WindowsDefenderATPOnboardingPackage.zip).</span></span>

4. <span data-ttu-id="caf50-125">추출 `WindowsDefenderATPOnboardingPackage.zip` .</span><span class="sxs-lookup"><span data-stu-id="caf50-125">Extract `WindowsDefenderATPOnboardingPackage.zip`.</span></span>

5. <span data-ttu-id="caf50-126">파일을 원하는 위치에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="caf50-126">Copy the file to your preferred location.</span></span> <span data-ttu-id="caf50-127">예:  `C:\Users\JaneDoe_or_JohnDoe.contoso\Downloads\WindowsDefenderATPOnboardingPackage_macOS_MDM_contoso\jamf\WindowsDefenderATPOnboarding.plist`.</span><span class="sxs-lookup"><span data-stu-id="caf50-127">For example,  `C:\Users\JaneDoe_or_JohnDoe.contoso\Downloads\WindowsDefenderATPOnboardingPackage_macOS_MDM_contoso\jamf\WindowsDefenderATPOnboarding.plist`.</span></span>


## <a name="step-2-create-a-configuration-profile-in-jamf-pro-using-the-onboarding-package"></a><span data-ttu-id="caf50-128">2단계: 온보더링 패키지를 사용하여 Jamf Pro에서 구성 프로필 만들기</span><span class="sxs-lookup"><span data-stu-id="caf50-128">Step 2: Create a configuration profile in Jamf Pro using the onboarding package</span></span>

1. <span data-ttu-id="caf50-129">이전 `WindowsDefenderATPOnboarding.plist` 섹션에서 파일을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="caf50-129">Locate the file `WindowsDefenderATPOnboarding.plist` from the previous section.</span></span>

   ![WindowsDefenderATPOnboarding 파일의 이미지](images/plist-onboarding-file.png)

 
2. <span data-ttu-id="caf50-131">Jamf Pro 대시보드에서 새로 만들 를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="caf50-131">In the Jamf Pro dashboard, select **New**.</span></span>

    ![새 Jamf Pro 대시보드를 만드는 이미지](images/jamf-pro-configure-profile.png)

3. <span data-ttu-id="caf50-133">다음 세부 정보를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="caf50-133">Enter the following details:</span></span>

   <span data-ttu-id="caf50-134">**일반**</span><span class="sxs-lookup"><span data-stu-id="caf50-134">**General**</span></span>
   - <span data-ttu-id="caf50-135">이름: macOS용 MDATP 온보드</span><span class="sxs-lookup"><span data-stu-id="caf50-135">Name: MDATP onboarding for macOS</span></span>
   - <span data-ttu-id="caf50-136">설명: macOS용 MDATP EDR 온보더링</span><span class="sxs-lookup"><span data-stu-id="caf50-136">Description: MDATP EDR onboarding for macOS</span></span>
   - <span data-ttu-id="caf50-137">범주: 없음</span><span class="sxs-lookup"><span data-stu-id="caf50-137">Category: None</span></span>
   - <span data-ttu-id="caf50-138">배포 방법: 자동으로 설치</span><span class="sxs-lookup"><span data-stu-id="caf50-138">Distribution Method: Install Automatically</span></span>
   - <span data-ttu-id="caf50-139">수준: 컴퓨터 수준</span><span class="sxs-lookup"><span data-stu-id="caf50-139">Level: Computer Level</span></span>

4. <span data-ttu-id="caf50-140">응용 **프로그램 & 사용자 지정 설정 구성을** **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="caf50-140">In **Application & Custom Settings** select **Configure**.</span></span>

    ![앱 및 사용자 지정 설정 구성 이미지](images/jamfpro-mac-profile.png)

5. <span data-ttu-id="caf50-142">파일 **업로드(PLIST 파일)를** 선택한 다음 **기본 설정 도메인에서 다음을** 입력합니다. `com.microsoft.wdav.atp` .</span><span class="sxs-lookup"><span data-stu-id="caf50-142">Select **Upload File (PLIST file)** then in **Preference Domain** enter: `com.microsoft.wdav.atp`.</span></span> 

    ![jamfpro plist 업로드 파일의 이미지](images/jamfpro-plist-upload.png)

    ![파일 업로드 속성 목록 파일의 이미지](images/jamfpro-plist-file.png)

7. <span data-ttu-id="caf50-145">열기 **를** 선택하고 온보더링 파일을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="caf50-145">Select **Open** and select the onboarding file.</span></span>

    ![온보더링 파일의 이미지](images/jamfpro-plist-file-onboard.png)

8. <span data-ttu-id="caf50-147">업로드를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="caf50-147">Select **Upload**.</span></span> 

    ![plist 파일 업로드 이미지](images/jamfpro-upload-plist.png)


9. <span data-ttu-id="caf50-149">범위 **탭을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="caf50-149">Select the **Scope** tab.</span></span>

    ![범위 탭의 이미지](images/jamfpro-scope-tab.png)

10. <span data-ttu-id="caf50-151">대상 컴퓨터를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="caf50-151">Select the target computers.</span></span>

    ![대상 컴퓨터의 이미지](images/jamfpro-target-computer.png)

    ![대상 이미지](images/jamfpro-targets.png) 

11. <span data-ttu-id="caf50-154">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="caf50-154">Select **Save**.</span></span>

    ![배포 대상 컴퓨터의 이미지](images/jamfpro-deployment-target.png)

    ![대상 컴퓨터의 이미지 선택](images/jamfpro-target-selected.png)

12. <span data-ttu-id="caf50-157">**완료** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="caf50-157">Select **Done**.</span></span>

    ![대상 그룹 컴퓨터의 이미지](images/jamfpro-target-group.png)

    ![구성 프로필 목록](images/jamfpro-configuration-policies.png)

## <a name="step-3-configure-microsoft-defender-for-endpoint-settings"></a><span data-ttu-id="caf50-160">3단계: 끝점 설정에 맞게 Microsoft Defender 구성</span><span class="sxs-lookup"><span data-stu-id="caf50-160">Step 3: Configure Microsoft Defender for Endpoint settings</span></span>

1.  <span data-ttu-id="caf50-161">끝점 구성 설정에 대해 다음 Microsoft Defender를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="caf50-161">Use the following Microsoft Defender for Endpoint configuration settings:</span></span>

    - <span data-ttu-id="caf50-162">enableRealTimeProtection</span><span class="sxs-lookup"><span data-stu-id="caf50-162">enableRealTimeProtection</span></span>
    - <span data-ttu-id="caf50-163">passiveMode</span><span class="sxs-lookup"><span data-stu-id="caf50-163">passiveMode</span></span>
    
    >[!NOTE]
    ><span data-ttu-id="caf50-164">macOS용 타사 AV를 실행하기 위해 계획하는 경우 기본적으로 켜져 있지 않습니다. 를 로 `true` 설정</span><span class="sxs-lookup"><span data-stu-id="caf50-164">Not turned on by default, if you are planning to run a third-party AV for macOS, set it to `true`.</span></span>

    - <span data-ttu-id="caf50-165">제외</span><span class="sxs-lookup"><span data-stu-id="caf50-165">exclusions</span></span>
    - <span data-ttu-id="caf50-166">excludedPath</span><span class="sxs-lookup"><span data-stu-id="caf50-166">excludedPath</span></span>
    - <span data-ttu-id="caf50-167">excludedFileExtension</span><span class="sxs-lookup"><span data-stu-id="caf50-167">excludedFileExtension</span></span>
    - <span data-ttu-id="caf50-168">excludedFileName</span><span class="sxs-lookup"><span data-stu-id="caf50-168">excludedFileName</span></span>
    - <span data-ttu-id="caf50-169">exclusionsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="caf50-169">exclusionsMergePolicy</span></span>
    - <span data-ttu-id="caf50-170">allowedThreats</span><span class="sxs-lookup"><span data-stu-id="caf50-170">allowedThreats</span></span>
    
    >[!NOTE]
    ><span data-ttu-id="caf50-171">EICAR이 샘플에 있습니다. 개념 증명을 진행하는 경우 EICAR을 테스트하는 경우 EICAR을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="caf50-171">EICAR is on the sample, if you are going through a proof-of-concept, remove it especially if you are testing EICAR.</span></span>
        
    - <span data-ttu-id="caf50-172">disallowedThreatActions</span><span class="sxs-lookup"><span data-stu-id="caf50-172">disallowedThreatActions</span></span>
    - <span data-ttu-id="caf50-173">potentially_unwanted_application</span><span class="sxs-lookup"><span data-stu-id="caf50-173">potentially_unwanted_application</span></span>
    - <span data-ttu-id="caf50-174">archive_bomb</span><span class="sxs-lookup"><span data-stu-id="caf50-174">archive_bomb</span></span>
    - <span data-ttu-id="caf50-175">cloudService</span><span class="sxs-lookup"><span data-stu-id="caf50-175">cloudService</span></span>
    - <span data-ttu-id="caf50-176">automaticSampleSubmission</span><span class="sxs-lookup"><span data-stu-id="caf50-176">automaticSampleSubmission</span></span>
    - <span data-ttu-id="caf50-177">tags</span><span class="sxs-lookup"><span data-stu-id="caf50-177">tags</span></span>
    - <span data-ttu-id="caf50-178">hideStatusMenuIcon</span><span class="sxs-lookup"><span data-stu-id="caf50-178">hideStatusMenuIcon</span></span>
    
     <span data-ttu-id="caf50-179">자세한 내용은 [Jamf 구성 프로필의 속성 목록을 참조하세요.](mac-preferences.md#property-list-for-jamf-configuration-profile)</span><span class="sxs-lookup"><span data-stu-id="caf50-179">For information, see [Property list for Jamf configuration profile](mac-preferences.md#property-list-for-jamf-configuration-profile).</span></span>

     ```XML
     <?xml version="1.0" encoding="UTF-8"?>
     <!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
     <plist version="1.0">
     <dict>
         <key>antivirusEngine</key>
         <dict>
             <key>enableRealTimeProtection</key>
             <true/>
             <key>passiveMode</key>
             <false/>
             <key>exclusions</key>
             <array>
                 <dict>
                     <key>$type</key>
                     <string>excludedPath</string>
                     <key>isDirectory</key>
                     <false/>
                     <key>path</key>
                     <string>/var/log/system.log</string>
                 </dict>
                 <dict>
                     <key>$type</key>
                     <string>excludedPath</string>
                     <key>isDirectory</key>
                     <true/>
                     <key>path</key>
                     <string>/home</string>
                 </dict>
                 <dict>
                     <key>$type</key>
                     <string>excludedFileExtension</string>
                     <key>extension</key>
                     <string>pdf</string>
                 </dict>
                 <dict>
                     <key>$type</key>
                     <string>excludedFileName</string>
                     <key>name</key>
                     <string>cat</string>
                 </dict>
             </array>
             <key>exclusionsMergePolicy</key>
             <string>merge</string>
             <key>allowedThreats</key>
             <array>
                 <string>EICAR-Test-File (not a virus)</string>
             </array>
             <key>disallowedThreatActions</key>
             <array>
                 <string>allow</string>
                 <string>restore</string>
             </array>
             <key>threatTypeSettings</key>
             <array>
                 <dict>
                     <key>key</key>
                     <string>potentially_unwanted_application</string>
                     <key>value</key>
                     <string>block</string>
                 </dict>
                 <dict>
                     <key>key</key>
                     <string>archive_bomb</string>
                     <key>value</key>
                     <string>audit</string>
                 </dict>
             </array>
             <key>threatTypeSettingsMergePolicy</key>
             <string>merge</string>
         </dict>
         <key>cloudService</key>
         <dict>
             <key>enabled</key>
             <true/>
             <key>diagnosticLevel</key>
             <string>optional</string>
             <key>automaticSampleSubmission</key>
             <true/>
         </dict>
         <key>edr</key>
         <dict>
             <key>tags</key>
             <array>
                 <dict>
                     <key>key</key>
                     <string>GROUP</string>
                     <key>value</key>
                     <string>ExampleTag</string>
                 </dict>
             </array>
         </dict>
         <key>userInterface</key>
         <dict>
             <key>hideStatusMenuIcon</key>
             <false/>
         </dict>
     </dict>
     </plist>
     ```

2. <span data-ttu-id="caf50-180">파일을 로 `MDATP_MDAV_configuration_settings.plist` 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="caf50-180">Save the file as `MDATP_MDAV_configuration_settings.plist`.</span></span>


3.  <span data-ttu-id="caf50-181">Jamf Pro 대시보드에서 일반 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="caf50-181">In the Jamf Pro dashboard, select **General**.</span></span>

    ![새 Jamf Pro 대시보드의 이미지](images/644e0f3af40c29e80ca1443535b2fe32.png)

4. <span data-ttu-id="caf50-183">다음 세부 정보를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="caf50-183">Enter the following details:</span></span>

    <span data-ttu-id="caf50-184">**일반**</span><span class="sxs-lookup"><span data-stu-id="caf50-184">**General**</span></span>
    
    - <span data-ttu-id="caf50-185">이름: MDATP MDAV 구성 설정</span><span class="sxs-lookup"><span data-stu-id="caf50-185">Name: MDATP MDAV configuration settings</span></span>
    - <span data-ttu-id="caf50-186">설명:\<blank\></span><span class="sxs-lookup"><span data-stu-id="caf50-186">Description:\<blank\></span></span>
    - <span data-ttu-id="caf50-187">범주: 없음(기본값)</span><span class="sxs-lookup"><span data-stu-id="caf50-187">Category: None (default)</span></span>
    - <span data-ttu-id="caf50-188">배포 방법: 자동으로 설치(기본값)</span><span class="sxs-lookup"><span data-stu-id="caf50-188">Distribution Method: Install Automatically(default)</span></span>
    - <span data-ttu-id="caf50-189">수준: 컴퓨터 수준(기본값)</span><span class="sxs-lookup"><span data-stu-id="caf50-189">Level: Computer Level(default)</span></span>

    ![MDATP MDAV 구성 설정의 이미지](images/3160906404bc5a2edf84d1d015894e3b.png)

5. <span data-ttu-id="caf50-191">응용 **프로그램 & 사용자 지정 설정 구성을** **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="caf50-191">In **Application & Custom Settings** select **Configure**.</span></span>

    ![앱 및 사용자 지정 설정의 이미지](images/e1cc1e48ec9d5d688087b4d771e668d2.png)

6. <span data-ttu-id="caf50-193">파일 **업로드(PLIST 파일)를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="caf50-193">Select **Upload File (PLIST file)**.</span></span>

    ![구성 설정 plist 파일의 이미지](images/6f85269276b2278eca4bce84f935f87b.png)

7. <span data-ttu-id="caf50-195">기본 **설정 도메인에서** `com.microsoft.wdav` 를 입력한 다음 **PLIST 파일 업로드를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="caf50-195">In **Preferences Domain**, enter `com.microsoft.wdav`, then select  **Upload PLIST File**.</span></span>

    ![구성 설정 기본 설정 도메인의 이미지](images/db15f147dd959e872a044184711d7d46.png)

8. <span data-ttu-id="caf50-197">파일 **선택 을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="caf50-197">Select **Choose File**.</span></span>

    ![구성 설정 파일 선택 이미지](images/526e978761fc571cca06907da7b01fd6.png)

9. <span data-ttu-id="caf50-199">**MDATP_MDAV_configuration_settings.plist를 선택한** 다음 **열기 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="caf50-199">Select the **MDATP_MDAV_configuration_settings.plist**, then select **Open**.</span></span>

    ![mdatpmdav 구성 설정의 이미지](images/98acea3750113b8dbab334296e833003.png)

10. <span data-ttu-id="caf50-201">업로드를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="caf50-201">Select **Upload**.</span></span>

    ![구성 설정 업로드 이미지](images/0adb21c13206861ba9b30a879ade93d3.png)

    ![구성 설정 업로드 이미지](images/f624de59b3cc86e3e2d32ae5de093e02.png)

    >[!NOTE]
    ><span data-ttu-id="caf50-204">Intune 파일을 업로드하는 경우 다음 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="caf50-204">If you happen to upload the Intune file, you'll get the following error:</span></span><br>
    ><span data-ttu-id="caf50-205">![구성 설정 intune 파일 업로드 이미지](images/8e69f867664668796a3b2904896f0436.png)</span><span class="sxs-lookup"><span data-stu-id="caf50-205">![Image of configuration settings intune file upload](images/8e69f867664668796a3b2904896f0436.png)</span></span>


11. <span data-ttu-id="caf50-206">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="caf50-206">Select **Save**.</span></span> 

    ![구성 설정 이미지 저장 이미지](images/1b6b5a4edcb42d97f1e70a6a0fa48e3a.png)

12. <span data-ttu-id="caf50-208">파일이 업로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="caf50-208">The file is uploaded.</span></span>

    ![구성 설정 파일 업로드 이미지](images/33e2b2a1611fdddf6b5b79e54496e3bb.png)

    ![업로드된 구성 설정 파일의 이미지](images/a422e57fe8d45689227e784443e51bd1.png)

13. <span data-ttu-id="caf50-211">범위 **탭을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="caf50-211">Select the **Scope** tab.</span></span>

    ![구성 설정 범위의 이미지](images/9fc17529e5577eefd773c658ec576a7d.png)

14. <span data-ttu-id="caf50-213">**Contoso의 컴퓨터 그룹을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="caf50-213">Select **Contoso's Machine Group**.</span></span> 

15. <span data-ttu-id="caf50-214">**추가를** 선택한 다음 **저장을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="caf50-214">Select **Add**, then select **Save**.</span></span>

    ![구성 설정 addsav의 이미지](images/cf30438b5512ac89af1d11cbf35219a6.png)

    ![구성 설정 저장 추가 이미지](images/6f093e42856753a3955cab7ee14f12d9.png)

16. <span data-ttu-id="caf50-217">**완료** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="caf50-217">Select **Done**.</span></span> <span data-ttu-id="caf50-218">새 구성 **프로필이 표시됩니다.**</span><span class="sxs-lookup"><span data-stu-id="caf50-218">You'll see the new **Configuration profile**.</span></span>

    ![구성 설정 구성 프로필 이미지 이미지](images/dd55405106da0dfc2f50f8d4525b01c8.png)


## <a name="step-4-configure-notifications-settings"></a><span data-ttu-id="caf50-220">4단계: 알림 설정 구성</span><span class="sxs-lookup"><span data-stu-id="caf50-220">Step 4: Configure notifications settings</span></span>

<span data-ttu-id="caf50-221">이러한 단계는 macOS 10.15(카탈로니아) 이상에서 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="caf50-221">These steps are applicable of macOS 10.15 (Catalina) or newer.</span></span>

1. <span data-ttu-id="caf50-222">`notif.mobileconfig` [GitHub 리포지토리에서 다운로드](https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/macos/mobileconfig/profiles/notif.mobileconfig)</span><span class="sxs-lookup"><span data-stu-id="caf50-222">Download `notif.mobileconfig` from [our GitHub repository](https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/macos/mobileconfig/profiles/notif.mobileconfig)</span></span>

2. <span data-ttu-id="caf50-223">으로 `MDATP_MDAV_notification_settings.plist` 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="caf50-223">Save it as `MDATP_MDAV_notification_settings.plist`.</span></span>

3. <span data-ttu-id="caf50-224">Jamf Pro 대시보드에서 일반 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="caf50-224">In the Jamf Pro dashboard, select **General**.</span></span> 
       
4. <span data-ttu-id="caf50-225">다음 세부 정보를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="caf50-225">Enter the following details:</span></span>

    <span data-ttu-id="caf50-226">**일반**</span><span class="sxs-lookup"><span data-stu-id="caf50-226">**General**</span></span> 
    
    - <span data-ttu-id="caf50-227">이름: MDATP MDAV 알림 설정</span><span class="sxs-lookup"><span data-stu-id="caf50-227">Name: MDATP MDAV Notification settings</span></span>
    - <span data-ttu-id="caf50-228">설명: macOS 10.15(카탈로니아) 이상</span><span class="sxs-lookup"><span data-stu-id="caf50-228">Description: macOS 10.15 (Catalina) or newer</span></span>
    - <span data-ttu-id="caf50-229">범주: 없음(기본값)</span><span class="sxs-lookup"><span data-stu-id="caf50-229">Category: None (default)</span></span>
    - <span data-ttu-id="caf50-230">배포 방법: 자동으로 설치(기본값)</span><span class="sxs-lookup"><span data-stu-id="caf50-230">Distribution Method: Install Automatically(default)</span></span>
    - <span data-ttu-id="caf50-231">수준: 컴퓨터 수준(기본값)</span><span class="sxs-lookup"><span data-stu-id="caf50-231">Level: Computer Level(default)</span></span>

    ![구성 설정의 이미지 mdatpmdav](images/c9820a5ff84aaf21635c04a23a97ca93.png)


5. <span data-ttu-id="caf50-233">파일 **업로드(PLIST 파일)를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="caf50-233">Select **Upload File (PLIST file)**.</span></span>

    ![구성 설정 업로드 plistfile의 이미지](images/7f9138053dbcbf928e5182ee7b295ebe.png)
 

6. <span data-ttu-id="caf50-235">Choose **File**  >  **MDATP_MDAV_Notification_Settings.plist 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="caf50-235">Select **Choose File** > **MDATP_MDAV_Notification_Settings.plist**.</span></span>


    ![구성 설정의 이미지 mdatpmdav notsettings](images/4bac6ce277aedfb4a674f2d9fcb2599a.png)


    ![구성 설정의 이미지 mdatpmdav notifsettings](images/20e33b98eb54447881dc6c89e58b890f.png)

7. <span data-ttu-id="caf50-238">업로드   >  **열기 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="caf50-238">Select **Open** > **Upload**.</span></span>

    ![구성 설정 upl img의 이미지](images/7697c33b9fd376ae5a8023d01f9d3857.png)


    ![구성 설정 업 이미지 이미지](images/2bda9244ec25d1526811da4ea91b1c86.png)

8. <span data-ttu-id="caf50-241">범위 **탭을** 선택한 다음 추가를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="caf50-241">Select the **Scope** tab, then select **Add**.</span></span>

    ![구성 설정 범위 추가 이미지](images/441aa2ecd36abadcdd8aed03556080b5.png)


9. <span data-ttu-id="caf50-243">**Contoso의 컴퓨터 그룹을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="caf50-243">Select **Contoso's Machine Group**.</span></span> 

10. <span data-ttu-id="caf50-244">**추가를** 선택한 다음 **저장을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="caf50-244">Select **Add**, then select **Save**.</span></span>
    
    ![구성 설정 contoso 컴퓨터 grp 저장 이미지](images/09a275e321268e5e3ac0c0865d3e2db5.png)

    
    ![구성 설정 추가 저장 이미지](images/4d2d1d4ee13d3f840f425924c3df0d51.png)

11. <span data-ttu-id="caf50-247">**완료** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="caf50-247">Select **Done**.</span></span> <span data-ttu-id="caf50-248">새 구성 **프로필이 표시됩니다.**</span><span class="sxs-lookup"><span data-stu-id="caf50-248">You'll see the new **Configuration profile**.</span></span>
    <span data-ttu-id="caf50-249">![구성 설정 완료 img의 이미지](images/633ad26b8bf24ec683c98b2feb884bdf.png)</span><span class="sxs-lookup"><span data-stu-id="caf50-249">![Image of configuration setting done img](images/633ad26b8bf24ec683c98b2feb884bdf.png)</span></span>

## <a name="step-5-configure-microsoft-autoupdate-mau"></a><span data-ttu-id="caf50-250">5단계: MAU(Microsoft 자동 업데이트) 구성</span><span class="sxs-lookup"><span data-stu-id="caf50-250">Step 5: Configure Microsoft AutoUpdate (MAU)</span></span>

1. <span data-ttu-id="caf50-251">끝점 구성 설정에 대해 다음 Microsoft Defender를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="caf50-251">Use the following Microsoft Defender for Endpoint configuration settings:</span></span>

      ```XML
   <?xml version="1.0" encoding="UTF-8"?>
   <!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
   <plist version="1.0">
   <dict>
    <key>ChannelName</key>
    <string>Current</string>
    <key>HowToCheck</key>
    <string>AutomaticDownload</string>
    <key>EnableCheckForUpdatesButton</key>
    <true/>
    <key>DisableInsiderCheckbox</key>
    <false/>
    <key>SendAllTelemetryEnabled</key>
    <true/>
   </dict>
   </plist>
   ```

2. <span data-ttu-id="caf50-252">으로 `MDATP_MDAV_MAU_settings.plist` 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="caf50-252">Save it as `MDATP_MDAV_MAU_settings.plist`.</span></span>

3. <span data-ttu-id="caf50-253">Jamf Pro 대시보드에서 일반 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="caf50-253">In the Jamf Pro dashboard, select **General**.</span></span> 

    ![구성 설정 일반 이미지 이미지](images/eaba2a23dd34f73bf59e826217ba6f15.png)

4. <span data-ttu-id="caf50-255">다음 세부 정보를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="caf50-255">Enter the following details:</span></span>

    <span data-ttu-id="caf50-256">**일반**</span><span class="sxs-lookup"><span data-stu-id="caf50-256">**General**</span></span> 
    
    - <span data-ttu-id="caf50-257">이름: MDATP MDAV MAU 설정</span><span class="sxs-lookup"><span data-stu-id="caf50-257">Name: MDATP MDAV MAU settings</span></span>
    - <span data-ttu-id="caf50-258">설명: MacOS용 MDATP에 대한 Microsoft 자동 업데이트 설정</span><span class="sxs-lookup"><span data-stu-id="caf50-258">Description: Microsoft AutoUpdate settings for MDATP for macOS</span></span>
    - <span data-ttu-id="caf50-259">범주: 없음(기본값)</span><span class="sxs-lookup"><span data-stu-id="caf50-259">Category: None (default)</span></span>
    - <span data-ttu-id="caf50-260">배포 방법: 자동으로 설치(기본값)</span><span class="sxs-lookup"><span data-stu-id="caf50-260">Distribution Method: Install Automatically(default)</span></span>
    - <span data-ttu-id="caf50-261">수준: 컴퓨터 수준(기본값)</span><span class="sxs-lookup"><span data-stu-id="caf50-261">Level: Computer Level(default)</span></span>

5. <span data-ttu-id="caf50-262">응용 **프로그램 & 사용자 지정 설정 구성을** **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="caf50-262">In **Application & Custom Settings** select **Configure**.</span></span>

    ![구성 설정 앱 및 사용자 지정 설정의 이미지](images/1f72e9c15eaafcabf1504397e99be311.png)

6. <span data-ttu-id="caf50-264">파일 **업로드(PLIST 파일)를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="caf50-264">Select **Upload File (PLIST file)**.</span></span>

    ![구성 설정 plist의 이미지](images/1213872db5833aa8be535da57653219f.png)  

7. <span data-ttu-id="caf50-266">기본 **설정 도메인에** 다음을 `com.microsoft.autoupdate2` 입력한 다음 **PLIST 파일 업로드를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="caf50-266">In **Preference Domain** enter: `com.microsoft.autoupdate2`, then select **Upload PLIST File**.</span></span>

    ![구성 설정 pref 도메인의 이미지](images/1213872db5833aa8be535da57653219f.png)

8. <span data-ttu-id="caf50-268">파일 **선택 을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="caf50-268">Select **Choose File**.</span></span>

    ![구성 설정의 이미지 choosefile](images/335aff58950ce62d1dabc289ecdce9ed.png)

9. <span data-ttu-id="caf50-270">**MDATP_MDAV_MAU_settings.plist 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="caf50-270">Select **MDATP_MDAV_MAU_settings.plist**.</span></span>

    ![구성 설정 mdatpmdavmau 설정의 이미지](images/a26bd4967cd54bb113a2c8d32894c3de.png)

10. <span data-ttu-id="caf50-272">업로드를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="caf50-272">Select **Upload**.</span></span>
    <span data-ttu-id="caf50-273">![구성 설정 uplimage 이미지](images/4239ca0528efb0734e4ca0b490bfb22d.png)</span><span class="sxs-lookup"><span data-stu-id="caf50-273">![Image of configuration setting uplimage](images/4239ca0528efb0734e4ca0b490bfb22d.png)</span></span>

    ![구성 설정 uplimg 이미지](images/4ec20e72c8aed9a4c16912e01692436a.png)

11. <span data-ttu-id="caf50-275">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="caf50-275">Select **Save**.</span></span>

    ![구성 설정 saveimg의 이미지](images/253274b33e74f3f5b8d475cf8692ce4e.png)

12. <span data-ttu-id="caf50-277">범위 **탭을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="caf50-277">Select the **Scope** tab.</span></span>
   
     ![구성 설정 범위 지정 이미지](images/10ab98358b2d602f3f67618735fa82fb.png)

13. <span data-ttu-id="caf50-279">**추가** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="caf50-279">Select **Add**.</span></span>
    
    ![구성 설정 addimg1의 이미지](images/56e6f6259b9ce3c1706ed8d666ae4947.png)

    ![구성 설정 addimg2의 이미지](images/38c67ee1905c4747c3b26c8eba57726b.png)

    ![구성 설정 addimg3의 이미지](images/321ba245f14743c1d5d51c15e99deecc.png)

14. <span data-ttu-id="caf50-283">**완료** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="caf50-283">Select **Done**.</span></span>
    
    ![구성 설정 완료 이미지](images/ba44cdb77e4781aa8b940fb83e3c21f7.png)

## <a name="step-6-grant-full-disk-access-to-microsoft-defender-for-endpoint"></a><span data-ttu-id="caf50-285">6단계: 끝점용 Microsoft Defender에 대한 전체 디스크 액세스 권한 부여</span><span class="sxs-lookup"><span data-stu-id="caf50-285">Step 6: Grant full disk access to Microsoft Defender for Endpoint</span></span>

1. <span data-ttu-id="caf50-286">Jamf Pro 대시보드에서 **구성 프로필 을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="caf50-286">In the Jamf Pro dashboard, select **Configuration Profiles**.</span></span>

    ![구성 설정 구성 프로필의 이미지](images/264493cd01e62c7085659d6fdc26dc91.png)

2. <span data-ttu-id="caf50-288">**+ 새로 고치기 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="caf50-288">Select **+ New**.</span></span> 

3. <span data-ttu-id="caf50-289">다음 세부 정보를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="caf50-289">Enter the following details:</span></span>

    <span data-ttu-id="caf50-290">**일반**</span><span class="sxs-lookup"><span data-stu-id="caf50-290">**General**</span></span> 
    - <span data-ttu-id="caf50-291">이름: MDATP MDAV - EDR 및 AV에 대한 전체 디스크 액세스 권한 부여</span><span class="sxs-lookup"><span data-stu-id="caf50-291">Name: MDATP MDAV - grant Full Disk Access to EDR and AV</span></span>
    - <span data-ttu-id="caf50-292">설명: macOS 카탈로니아 이상에서 새로운 개인 정보 기본 설정 정책 컨트롤</span><span class="sxs-lookup"><span data-stu-id="caf50-292">Description: On macOS Catalina or newer, the new Privacy Preferences Policy Control</span></span>
    - <span data-ttu-id="caf50-293">범주: 없음</span><span class="sxs-lookup"><span data-stu-id="caf50-293">Category: None</span></span>
    - <span data-ttu-id="caf50-294">배포 방법: 자동으로 설치</span><span class="sxs-lookup"><span data-stu-id="caf50-294">Distribution method: Install Automatically</span></span>
    - <span data-ttu-id="caf50-295">수준: 컴퓨터 수준</span><span class="sxs-lookup"><span data-stu-id="caf50-295">Level: Computer level</span></span>


    ![구성 설정 일반 이미지](images/ba3d40399e1a6d09214ecbb2b341923f.png)

4. <span data-ttu-id="caf50-297">개인 **정보 기본 설정 정책 제어 구성에서** **구성을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="caf50-297">In **Configure Privacy Preferences Policy Control** select **Configure**.</span></span>

    ![구성 개인 정보 취급 방침 제어 이미지](images/715ae7ec8d6a262c489f94d14e1e51bb.png)

5. <span data-ttu-id="caf50-299">개인 **정보 기본 설정 정책 제어에서** 다음 세부 정보를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="caf50-299">In **Privacy Preferences Policy Control**, enter the following details:</span></span>

    - <span data-ttu-id="caf50-300">식별자: `com.microsoft.wdav`</span><span class="sxs-lookup"><span data-stu-id="caf50-300">Identifier: `com.microsoft.wdav`</span></span>
    - <span data-ttu-id="caf50-301">식별자 유형: 번들 ID</span><span class="sxs-lookup"><span data-stu-id="caf50-301">Identifier Type: Bundle ID</span></span>
    - <span data-ttu-id="caf50-302">코드 요구 사항: `identifier "com.microsoft.wdav" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span><span class="sxs-lookup"><span data-stu-id="caf50-302">Code Requirement: `identifier "com.microsoft.wdav" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span></span>


    ![구성 설정 개인 정보 기본 설정 정책 컨트롤 세부 정보 이미지](images/22cb439de958101c0a12f3038f905b27.png)

6. <span data-ttu-id="caf50-304">**+ 추가** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="caf50-304">Select **+ Add**.</span></span>

    ![구성 설정의 이미지 시스템 정책 모든 파일 추가](images/bd93e78b74c2660a0541af4690dd9485.png)

    - <span data-ttu-id="caf50-306">앱 또는 서비스에서: **SystemPolicyAllFiles로 설정**</span><span class="sxs-lookup"><span data-stu-id="caf50-306">Under App or service: Set to **SystemPolicyAllFiles**</span></span>

    - <span data-ttu-id="caf50-307">"액세스"에서: 허용으로 **설정**</span><span class="sxs-lookup"><span data-stu-id="caf50-307">Under "access": Set to **Allow**</span></span>

7. <span data-ttu-id="caf50-308">저장을 **선택합니다(오른쪽** 아래에 있는 저장 안 ).</span><span class="sxs-lookup"><span data-stu-id="caf50-308">Select **Save** (not the one at the bottom right).</span></span>

    ![구성 설정 이미지 저장 이미지](images/6de50b4a897408ddc6ded56a09c09fe2.png)

8. <span data-ttu-id="caf50-310">앱 `+` 액세스 옆의 **기호를 클릭하여** 새 항목을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="caf50-310">Click the `+` sign next to **App Access** to add a new entry.</span></span>

    ![구성 설정 앱 액세스 이미지](images/tcc-add-entry.png)

9. <span data-ttu-id="caf50-312">다음 세부 정보를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="caf50-312">Enter the following details:</span></span>

    - <span data-ttu-id="caf50-313">식별자: `com.microsoft.wdav.epsext`</span><span class="sxs-lookup"><span data-stu-id="caf50-313">Identifier: `com.microsoft.wdav.epsext`</span></span>
    - <span data-ttu-id="caf50-314">식별자 유형: 번들 ID</span><span class="sxs-lookup"><span data-stu-id="caf50-314">Identifier Type: Bundle ID</span></span>
    - <span data-ttu-id="caf50-315">코드 요구 사항: `identifier "com.microsoft.wdav.epsext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span><span class="sxs-lookup"><span data-stu-id="caf50-315">Code Requirement: `identifier "com.microsoft.wdav.epsext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span></span>

10. <span data-ttu-id="caf50-316">**+ 추가** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="caf50-316">Select **+ Add**.</span></span>

    ![구성 설정 tcc epsext 항목의 이미지](images/tcc-epsext-entry.png)

    - <span data-ttu-id="caf50-318">앱 또는 서비스에서: **SystemPolicyAllFiles로 설정**</span><span class="sxs-lookup"><span data-stu-id="caf50-318">Under App or service: Set to **SystemPolicyAllFiles**</span></span>

    - <span data-ttu-id="caf50-319">"액세스"에서: 허용으로 **설정**</span><span class="sxs-lookup"><span data-stu-id="caf50-319">Under "access": Set to **Allow**</span></span>

11. <span data-ttu-id="caf50-320">저장을 **선택합니다(오른쪽** 아래에 있는 저장 안 ).</span><span class="sxs-lookup"><span data-stu-id="caf50-320">Select **Save** (not the one at the bottom right).</span></span>

    ![구성 설정 tcc epsext 이미지2의 이미지](images/tcc-epsext-entry2.png)

12. <span data-ttu-id="caf50-322">범위 **탭을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="caf50-322">Select the **Scope** tab.</span></span>

    ![구성 설정 범위의 이미지](images/2c49b16cd112729b3719724f581e6882.png)

13. <span data-ttu-id="caf50-324">**+ 추가** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="caf50-324">Select **+ Add**.</span></span>

    ![구성 설정 추가 이미지](images/57cef926d1b9260fb74a5f460cee887a.png)

14. <span data-ttu-id="caf50-326">그룹 **이름 >** 컴퓨터  그룹 > **Contoso의 MachineGroup을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="caf50-326">Select **Computer Groups** > under **Group Name** > select **Contoso's MachineGroup**.</span></span> 

    ![구성 설정 contoso machinegrp의 이미지](images/368d35b3d6179af92ffdbfd93b226b69.png)

15. <span data-ttu-id="caf50-328">**추가** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="caf50-328">Select **Add**.</span></span> 

16. <span data-ttu-id="caf50-329">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="caf50-329">Select **Save**.</span></span> 
    
17. <span data-ttu-id="caf50-330">**완료** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="caf50-330">Select **Done**.</span></span>
    
    ![구성 설정 donimg의 이미지](images/809cef630281b64b8f07f20913b0039b.png)
    
    ![구성 설정 donimg2의 이미지](images/6c8b406ee224335a8c65d06953dc756e.png)


## <a name="step-7-approve-kernel-extension-for-microsoft-defender-for-endpoint"></a><span data-ttu-id="caf50-333">7단계: 끝점용 Microsoft Defender에 대한 커널 확장 승인</span><span class="sxs-lookup"><span data-stu-id="caf50-333">Step 7: Approve Kernel extension for Microsoft Defender for Endpoint</span></span>

1. <span data-ttu-id="caf50-334">구성 **프로필에서**+ **새로 고치기 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="caf50-334">In the **Configuration Profiles**, select **+ New**.</span></span>

    ![소셜 미디어 게시물 설명이 자동으로 생성되는 스크린샷](images/6c8b406ee224335a8c65d06953dc756e.png)

2. <span data-ttu-id="caf50-336">다음 세부 정보를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="caf50-336">Enter the following details:</span></span>

    <span data-ttu-id="caf50-337">**일반**</span><span class="sxs-lookup"><span data-stu-id="caf50-337">**General**</span></span> 
    
    - <span data-ttu-id="caf50-338">이름: MDATP MDAV 커널 확장</span><span class="sxs-lookup"><span data-stu-id="caf50-338">Name: MDATP MDAV Kernel Extension</span></span>
    - <span data-ttu-id="caf50-339">설명: MDATP 커널 확장(kext)</span><span class="sxs-lookup"><span data-stu-id="caf50-339">Description: MDATP kernel extension (kext)</span></span>
    - <span data-ttu-id="caf50-340">범주: 없음</span><span class="sxs-lookup"><span data-stu-id="caf50-340">Category: None</span></span>
    - <span data-ttu-id="caf50-341">배포 방법: 자동으로 설치</span><span class="sxs-lookup"><span data-stu-id="caf50-341">Distribution Method: Install Automatically</span></span>
    - <span data-ttu-id="caf50-342">수준: 컴퓨터 수준</span><span class="sxs-lookup"><span data-stu-id="caf50-342">Level: Computer Level</span></span>

    ![구성 설정의 이미지 mdatpmdav 커널](images/24e290f5fc309932cf41f3a280d22c14.png)

3. <span data-ttu-id="caf50-344">승인된 커널 확장 **구성에서** 구성을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="caf50-344">In **Configure Approved Kernel Extensions** select **Configure**.</span></span>

    ![승인된 구성 설정 커널 ext 이미지](images/30be88b63abc5e8dde11b73f1b1ade6a.png)

   
4. <span data-ttu-id="caf50-346">승인된 **커널 확장에** 다음 세부 정보를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="caf50-346">In **Approved Kernel Extensions** Enter the following details:</span></span>

    - <span data-ttu-id="caf50-347">표시 이름: Microsoft Corp.</span><span class="sxs-lookup"><span data-stu-id="caf50-347">Display Name: Microsoft Corp.</span></span>
    - <span data-ttu-id="caf50-348">팀 ID: UBF8T346G9</span><span class="sxs-lookup"><span data-stu-id="caf50-348">Team ID: UBF8T346G9</span></span>

    ![구성 설정 앱 커널 확장의 이미지](images/39cf120d3ac3652292d8d1b6d057bd60.png)

5. <span data-ttu-id="caf50-350">범위 **탭을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="caf50-350">Select the **Scope** tab.</span></span>

    ![구성 설정 범위 탭 img의 이미지](images/0df36fc308ba569db204ee32db3fb40a.png)

6. <span data-ttu-id="caf50-352">**+ 추가** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="caf50-352">Select **+ Add**.</span></span>

7. <span data-ttu-id="caf50-353">컴퓨터 **그룹 >** 그룹  > **Contoso의 컴퓨터** 그룹을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="caf50-353">Select **Computer Groups** > under **Group Name** > select **Contoso's Machine Group**.</span></span>

8. <span data-ttu-id="caf50-354">**+ 추가** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="caf50-354">Select **+ Add**.</span></span>

    ![구성 설정 이미지 이미지 추가](images/0dde8a4c41110dbc398c485433a81359.png)

9. <span data-ttu-id="caf50-356">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="caf50-356">Select **Save**.</span></span>

    ![구성 설정 저장 이미지](images/0add8019b85a453b47fa5c402c72761b.png)

10. <span data-ttu-id="caf50-358">**완료** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="caf50-358">Select **Done**.</span></span>

    ![doneimag 구성 설정의 이미지](images/1c9bd3f68db20b80193dac18f33c22d0.png)


## <a name="step-8-approve-system-extensions-for-microsoft-defender-for-endpoint"></a><span data-ttu-id="caf50-360">8단계: 끝점용 Microsoft Defender의 시스템 확장 승인</span><span class="sxs-lookup"><span data-stu-id="caf50-360">Step 8: Approve System extensions for Microsoft Defender for Endpoint</span></span>

1. <span data-ttu-id="caf50-361">구성 **프로필에서**+ **새로 고치기 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="caf50-361">In the **Configuration Profiles**, select **+ New**.</span></span>

    ![소셜 미디어 게시물 설명이 자동으로 생성되는 스크린샷](images/6c8b406ee224335a8c65d06953dc756e.png)

2. <span data-ttu-id="caf50-363">다음 세부 정보를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="caf50-363">Enter the following details:</span></span>

    <span data-ttu-id="caf50-364">**일반**</span><span class="sxs-lookup"><span data-stu-id="caf50-364">**General**</span></span>
    
    - <span data-ttu-id="caf50-365">이름: MDATP MDAV 시스템 확장</span><span class="sxs-lookup"><span data-stu-id="caf50-365">Name: MDATP MDAV System Extensions</span></span>
    - <span data-ttu-id="caf50-366">설명: MDATP 시스템 확장</span><span class="sxs-lookup"><span data-stu-id="caf50-366">Description: MDATP system extensions</span></span>
    - <span data-ttu-id="caf50-367">범주: 없음</span><span class="sxs-lookup"><span data-stu-id="caf50-367">Category: None</span></span>
    - <span data-ttu-id="caf50-368">배포 방법: 자동으로 설치</span><span class="sxs-lookup"><span data-stu-id="caf50-368">Distribution Method: Install Automatically</span></span>
    - <span data-ttu-id="caf50-369">수준: 컴퓨터 수준</span><span class="sxs-lookup"><span data-stu-id="caf50-369">Level: Computer Level</span></span>

    ![구성 설정 sysext 새 prof의 이미지](images/sysext-new-profile.png)

3. <span data-ttu-id="caf50-371">시스템 **확장에서** **구성을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="caf50-371">In **System Extensions** select **Configure**.</span></span>

   ![구성 설정 sysext 구성의 이미지](images/sysext-configure.png)

4. <span data-ttu-id="caf50-373">시스템 **확장에** 다음 세부 정보를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="caf50-373">In **System Extensions** enter the following details:</span></span>

   - <span data-ttu-id="caf50-374">표시 이름: Microsoft Corp. 시스템 확장</span><span class="sxs-lookup"><span data-stu-id="caf50-374">Display Name: Microsoft Corp. System Extensions</span></span>
   - <span data-ttu-id="caf50-375">시스템 확장 유형: 허용되는 시스템 확장</span><span class="sxs-lookup"><span data-stu-id="caf50-375">System Extension Types: Allowed System Extensions</span></span>
   - <span data-ttu-id="caf50-376">팀 식별자: UBF8T346G9</span><span class="sxs-lookup"><span data-stu-id="caf50-376">Team Identifier: UBF8T346G9</span></span>
   - <span data-ttu-id="caf50-377">허용되는 시스템 확장:</span><span class="sxs-lookup"><span data-stu-id="caf50-377">Allowed System Extensions:</span></span>
     - <span data-ttu-id="caf50-378">**com.microsoft.wdav.epsext**</span><span class="sxs-lookup"><span data-stu-id="caf50-378">**com.microsoft.wdav.epsext**</span></span>
     - <span data-ttu-id="caf50-379">**com.microsoft.wdav.netext**</span><span class="sxs-lookup"><span data-stu-id="caf50-379">**com.microsoft.wdav.netext**</span></span>

    ![구성 설정 sysextconfig2의 이미지](images/sysext-configure2.png)

5. <span data-ttu-id="caf50-381">범위 **탭을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="caf50-381">Select the **Scope** tab.</span></span>

    ![구성 설정 범위이미지 이미지](images/0df36fc308ba569db204ee32db3fb40a.png)

6. <span data-ttu-id="caf50-383">**+ 추가** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="caf50-383">Select **+ Add**.</span></span>

7. <span data-ttu-id="caf50-384">컴퓨터 **그룹 >** 그룹  > **Contoso의 컴퓨터** 그룹을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="caf50-384">Select **Computer Groups** > under **Group Name** > select **Contoso's Machine Group**.</span></span>

8. <span data-ttu-id="caf50-385">**+ 추가** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="caf50-385">Select **+ Add**.</span></span>

   ![구성 설정 추가기 이미지](images/0dde8a4c41110dbc398c485433a81359.png)

9. <span data-ttu-id="caf50-387">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="caf50-387">Select **Save**.</span></span>

   ![구성 설정 sysext 범위의 이미지](images/sysext-scope.png)

10. <span data-ttu-id="caf50-389">**완료** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="caf50-389">Select **Done**.</span></span>

    ![구성 설정 sysext-final의 이미지](images/sysext-final.png)

## <a name="step-9-configure-network-extension"></a><span data-ttu-id="caf50-391">9단계: 네트워크 확장 구성</span><span class="sxs-lookup"><span data-stu-id="caf50-391">Step 9: Configure Network Extension</span></span>

<span data-ttu-id="caf50-392">끝점 검색 및 응답 기능의 일부로, Mac용 끝점용 Microsoft Defender는 소켓 트래픽을 검사하고 이 정보를 Microsoft Defender 보안 센터 포털에 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="caf50-392">As part of the Endpoint Detection and Response capabilities, Microsoft Defender for Endpoint for Mac inspects socket traffic and reports this information to the Microsoft Defender Security Center portal.</span></span> <span data-ttu-id="caf50-393">다음 정책은 네트워크 확장에서 이 기능을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="caf50-393">The following policy allows the network extension to perform this functionality.</span></span>

>[!NOTE]
><span data-ttu-id="caf50-394">JAMF에는 콘텐츠 필터링 정책에 대한 기본 제공 지원이 없습니다. 이는 Mac용 끝점용 Microsoft Defender가 장치에 설치하는 네트워크 확장을 사용하도록 설정하기 위한 전제입니다.</span><span class="sxs-lookup"><span data-stu-id="caf50-394">JAMF doesn’t have built-in support for content filtering policies, which are a pre-requisite for enabling the network extensions that Microsoft Defender for Endpoint for Mac installs on the device.</span></span> <span data-ttu-id="caf50-395">또한 JAMF는 배포되는 정책의 콘텐츠를 변경하는 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="caf50-395">Furthermore, JAMF sometimes changes the content of the policies being deployed.</span></span>
><span data-ttu-id="caf50-396">따라서 다음 단계에서는 구성 프로필에 서명하는 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="caf50-396">As such, the following steps provide a workaround that involve signing the configuration profile.</span></span>

1. <span data-ttu-id="caf50-397">`netfilter.mobileconfig` [GitHub 리포지토리에서](https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/macos/mobileconfig/profiles/netfilter.mobileconfig) 장치로 다운로드하여 다른 장치로 저장`com.microsoft.network-extension.mobileconfig`</span><span class="sxs-lookup"><span data-stu-id="caf50-397">Download `netfilter.mobileconfig` from [our GitHub repository](https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/macos/mobileconfig/profiles/netfilter.mobileconfig) to your device and save it as `com.microsoft.network-extension.mobileconfig`</span></span>

2. <span data-ttu-id="caf50-398">이 페이지의 지침에 [따라](https://www.jamf.com/jamf-nation/articles/649/creating-a-signing-certificate-using-jamf-pro-s-built-in-certificate-authority) JAMF의 기본 제공 인증 기관을 사용하여 서명 인증서 만들기</span><span class="sxs-lookup"><span data-stu-id="caf50-398">Follow the instructions on [this page](https://www.jamf.com/jamf-nation/articles/649/creating-a-signing-certificate-using-jamf-pro-s-built-in-certificate-authority) to create a signing certificate using JAMF’s built-in certificate authority</span></span>

3. <span data-ttu-id="caf50-399">인증서를 만들어 장치에 설치한 후 macOS 장치에서 터미널에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="caf50-399">After the certificate is created and installed to your device, run the following command from the Terminal from a macOS device:</span></span>

   ```bash
   $ security cms -S -N "<certificate name>" -i com.microsoft.network-extension.mobileconfig -o com.microsoft.network-extension.signed.mobileconfig
   ```

   ![서명된 구성 만들기 명령이 있는 터미널 창](images/netext-create-profile.png)

4. <span data-ttu-id="caf50-401">JAMF 포털에서 구성 프로필로 **이동하여** 업로드 **단추를** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="caf50-401">From the JAMF portal, navigate to **Configuration Profiles** and click the **Upload** button.</span></span> 

   ![업로드 창의 이미지](images/netext-upload-file.png)

5. <span data-ttu-id="caf50-403">파일 **선택을 선택하고** `microsoft.network-extension.signed.mobileconfig` 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="caf50-403">Select **Choose File** and select `microsoft.network-extension.signed.mobileconfig`.</span></span>

   ![업로드 창의 이미지 netext choose file](images/netext-choose-file.png)

6. <span data-ttu-id="caf50-405">업로드를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="caf50-405">Select **Upload**.</span></span>

   ![업로드 창 netext 업로드 파일의 이미지2](images/netext-upload-file2.png)

7. <span data-ttu-id="caf50-407">파일을 업로드한 후 이 프로필 만들기를 마무리하기 위해 새 페이지로 리디렉션됩니다.</span><span class="sxs-lookup"><span data-stu-id="caf50-407">After uploading the file, you are redirected to a new page to finalize the creation of this profile.</span></span>

   ![새 구성 프로필 netext 프로필 페이지의 이미지](images/netext-profile-page.png)

8. <span data-ttu-id="caf50-409">범위 **탭을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="caf50-409">Select the **Scope** tab.</span></span>

   ![구성 설정 sco 탭의 이미지](images/0df36fc308ba569db204ee32db3fb40a.png)

9. <span data-ttu-id="caf50-411">**+ 추가** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="caf50-411">Select **+ Add**.</span></span>

10. <span data-ttu-id="caf50-412">컴퓨터 **그룹 >** 그룹  > **Contoso의 컴퓨터** 그룹을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="caf50-412">Select **Computer Groups** > under **Group Name** > select **Contoso's Machine Group**.</span></span>

11. <span data-ttu-id="caf50-413">**+ 추가** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="caf50-413">Select **+ Add**.</span></span>

    ![구성 설정 adim 이미지](images/0dde8a4c41110dbc398c485433a81359.png)

12. <span data-ttu-id="caf50-415">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="caf50-415">Select **Save**.</span></span>

    ![구성 설정 savimg netextscop 이미지](images/netext-scope.png)

13. <span data-ttu-id="caf50-417">**완료** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="caf50-417">Select **Done**.</span></span>

    ![구성 설정 netextfinal의 이미지](images/netext-final.png)

## <a name="step-10-schedule-scans-with-microsoft-defender-for-endpoint-for-mac"></a><span data-ttu-id="caf50-419">10단계: Mac용 끝점에 대한 Microsoft Defender 검사 예약</span><span class="sxs-lookup"><span data-stu-id="caf50-419">Step 10: Schedule scans with Microsoft Defender for Endpoint for Mac</span></span>
<span data-ttu-id="caf50-420">[Mac용 끝점에 대한 Microsoft Defender 검사 예약에 대한 지침을 따릅니다.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/mac-schedule-scan-atp)</span><span class="sxs-lookup"><span data-stu-id="caf50-420">Follow the instructions on [Schedule scans with Microsoft Defender for Endpoint for Mac](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/mac-schedule-scan-atp).</span></span>

## <a name="step-11-deploy-microsoft-defender-for-endpoint-for-macos"></a><span data-ttu-id="caf50-421">11단계: macOS용 끝점용 Microsoft Defender 배포</span><span class="sxs-lookup"><span data-stu-id="caf50-421">Step 11: Deploy Microsoft Defender for Endpoint for macOS</span></span>

1. <span data-ttu-id="caf50-422">을 저장한 위치로 `wdav.pkg` 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="caf50-422">Navigate to where you saved `wdav.pkg`.</span></span>

    ![파일 탐색기 wdav pkg의 이미지](images/8dde76b5463047423f8637c86b05c29d.png)

2. <span data-ttu-id="caf50-424">이름을 로 다시 `wdav_MDM_Contoso_200329.pkg` 합니다.</span><span class="sxs-lookup"><span data-stu-id="caf50-424">Rename it to `wdav_MDM_Contoso_200329.pkg`.</span></span>

    ![파일 탐색기1 wdavmdmpkg의 이미지](images/fb2220fed3a530f4b3ef36f600da0c27.png)

3. <span data-ttu-id="caf50-426">Jamf Pro 대시보드를 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="caf50-426">Open the Jamf Pro dashboard.</span></span>

    ![구성 설정 jamfpro의 이미지](images/990742cd9a15ca9fdd37c9f695d1b9f4.png)

4. <span data-ttu-id="caf50-428">컴퓨터를 선택하고 맨 위에 있는 기어 아이콘을 클릭한 다음 컴퓨터 관리를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="caf50-428">Select your computer and click the gear icon at the top, then select **Computer Management**.</span></span>

    ![구성 설정 compmgmt의 이미지](images/b6d671b2f18b89d96c1c8e2ea1991242.png)

5. <span data-ttu-id="caf50-430">패키지에서 **+ 새로 고치기 를 선택합니다.** </span><span class="sxs-lookup"><span data-stu-id="caf50-430">In **Packages**, select **+ New**.</span></span> 
    <span data-ttu-id="caf50-431">![새가 포함된 그림 설명 자동으로 생성된 패키지 새로 추가](images/57aa4d21e2ccc65466bf284701d4e961.png)</span><span class="sxs-lookup"><span data-stu-id="caf50-431">![A picture containing bird Description automatically generated package new](images/57aa4d21e2ccc65466bf284701d4e961.png)</span></span>

6. <span data-ttu-id="caf50-432">새 **패키지에** 다음 세부 정보를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="caf50-432">In **New Package** Enter the following details:</span></span>

    <span data-ttu-id="caf50-433">**일반 탭**</span><span class="sxs-lookup"><span data-stu-id="caf50-433">**General tab**</span></span>
    - <span data-ttu-id="caf50-434">표시 이름: 지금은 비워 두십시오.</span><span class="sxs-lookup"><span data-stu-id="caf50-434">Display Name: Leave it blank for now.</span></span> <span data-ttu-id="caf50-435">pkg를 선택하면 초기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="caf50-435">Because it will be reset when you choose your pkg.</span></span>
    - <span data-ttu-id="caf50-436">범주: 없음(기본값)</span><span class="sxs-lookup"><span data-stu-id="caf50-436">Category: None (default)</span></span>
    - <span data-ttu-id="caf50-437">파일 이름: 파일 선택</span><span class="sxs-lookup"><span data-stu-id="caf50-437">Filename: Choose File</span></span>

    ![구성 설정 일반 탭의 이미지](images/21de3658bf58b1b767a17358a3f06341.png)

    <span data-ttu-id="caf50-439">파일을 열고 또는 을(를) `wdav.pkg` 지점으로 `wdav_MDM_Contoso_200329.pkg` 합니다.</span><span class="sxs-lookup"><span data-stu-id="caf50-439">Open the file and point it to `wdav.pkg` or `wdav_MDM_Contoso_200329.pkg`.</span></span>
    
    ![컴퓨터 화면의 스크린샷 자동으로 생성되는 설명](images/1aa5aaa0a387f4e16ce55b66facc77d1.png)

7. <span data-ttu-id="caf50-441">**열기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="caf50-441">Select **Open**.</span></span> <span data-ttu-id="caf50-442">표시 **이름을** Microsoft Defender Advanced Threat Protection 및 **Microsoft Defender 바이러스 백신으로 설정**</span><span class="sxs-lookup"><span data-stu-id="caf50-442">Set the **Display Name** to **Microsoft Defender Advanced Threat Protection and Microsoft Defender Antivirus**.</span></span>

    <span data-ttu-id="caf50-443">**매니페스트 파일은** 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="caf50-443">**Manifest File** is not required.</span></span> <span data-ttu-id="caf50-444">Microsoft Defender Advanced Threat Protection은 매니페스트 파일 없이 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="caf50-444">Microsoft Defender Advanced Threat Protection works without Manifest File.</span></span>
    
    <span data-ttu-id="caf50-445">**옵션 탭**</span><span class="sxs-lookup"><span data-stu-id="caf50-445">**Options tab**</span></span><br> <span data-ttu-id="caf50-446">기본값을 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="caf50-446">Keep default values.</span></span>

    <span data-ttu-id="caf50-447">**제한 사항 탭**</span><span class="sxs-lookup"><span data-stu-id="caf50-447">**Limitations tab**</span></span><br> <span data-ttu-id="caf50-448">기본값을 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="caf50-448">Keep default values.</span></span>
    
     ![구성 설정 제한 탭의 이미지](images/56dac54634d13b2d3948ab50e8d3ef21.png)
   
8. <span data-ttu-id="caf50-450">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="caf50-450">Select **Save**.</span></span> <span data-ttu-id="caf50-451">패키지가 Jamf Pro에 업로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="caf50-451">The package is uploaded to Jamf Pro.</span></span> 

   ![구성 설정 팩 upl jamf pro의 이미지](images/33f1ecdc7d4872555418bbc3efe4b7a3.png)

   <span data-ttu-id="caf50-453">패키지를 배포하는 데 몇 분 정도 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="caf50-453">It can take a few minutes for the package to be available for deployment.</span></span>
   
   ![구성 설정 팩 업L 이미지](images/1626d138e6309c6e87bfaab64f5ccf7b.png)

9. <span data-ttu-id="caf50-455">정책 **페이지로** 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="caf50-455">Navigate to the **Policies** page.</span></span>

    ![구성 설정 polocies의 이미지](images/f878f8efa5ebc92d069f4b8f79f62c7f.png)

10. <span data-ttu-id="caf50-457">**+ 새로 만들기를 선택하여** 새 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="caf50-457">Select **+ New** to create a new policy.</span></span>

    ![구성 설정 새 정책의 이미지](images/847b70e54ed04787e415f5180414b310.png)


11. <span data-ttu-id="caf50-459">**일반에서** 다음 세부 정보를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="caf50-459">In **General** Enter the following details:</span></span>

    - <span data-ttu-id="caf50-460">표시 이름: MDATP 온보드 Contoso 200329 v100.86.92 이상</span><span class="sxs-lookup"><span data-stu-id="caf50-460">Display name: MDATP Onboarding Contoso 200329 v100.86.92 or later</span></span>

    ![<span data-ttu-id="caf50-461">구성 설정mdatponboard의 이미지</span><span class="sxs-lookup"><span data-stu-id="caf50-461">Image of configuration settingsmdatponboard</span></span> ](images/625ba6d19e8597f05e4907298a454d28.png)

12. <span data-ttu-id="caf50-462">재발 **체크 인 을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="caf50-462">Select **Recurring Check-in**.</span></span> 
    
    ![구성 설정 재발 검사의 이미지](images/68bdbc5754dfc80aa1a024dde0fce7b0.png)

  
13. <span data-ttu-id="caf50-464">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="caf50-464">Select **Save**.</span></span> 
 
14. <span data-ttu-id="caf50-465">패키지를 **> 구성합니다.**</span><span class="sxs-lookup"><span data-stu-id="caf50-465">Select **Packages > Configure**.</span></span>
 
    ![구성 설정 팩 구성 이미지](images/8fb4cc03721e1efb4a15867d5241ebfb.png)

15. <span data-ttu-id="caf50-467">Microsoft  Defender Advanced Threat Protection 및 Microsoft Defender 바이러스 백신 옆에 있는 추가 **단추를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="caf50-467">Select the **Add** button next to **Microsoft Defender Advanced Threat Protection and Microsoft Defender Antivirus**.</span></span>

    ![구성 설정의 이미지 MDATP 및 MDA 추가](images/526b83fbdbb31265b3d0c1e5fbbdc33a.png)

16. <span data-ttu-id="caf50-469">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="caf50-469">Select **Save**.</span></span>

    ![구성 설정savimg의 이미지](images/9d6e5386e652e00715ff348af72671c6.png)

17. <span data-ttu-id="caf50-471">범위 **탭을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="caf50-471">Select the **Scope** tab.</span></span>  

    ![구성 설정 scptab의 이미지](images/8d80fe378a31143db9be0bacf7ddc5a3.png)

18. <span data-ttu-id="caf50-473">대상 컴퓨터를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="caf50-473">Select the target computers.</span></span>

    ![구성 설정 tgtcomp의 이미지](images/6eda18a64a660fa149575454e54e7156.png)

    <span data-ttu-id="caf50-475">**범위**</span><span class="sxs-lookup"><span data-stu-id="caf50-475">**Scope**</span></span>
    
    <span data-ttu-id="caf50-476">**추가** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="caf50-476">Select **Add**.</span></span>
    
    ![구성 설정 ad1img의 이미지](images/1c08d097829863778d562c10c5f92b67.png)

    ![구성 설정 ad2img의 이미지](images/216253cbfb6ae738b9f13496b9c799fd.png)

    <span data-ttu-id="caf50-479">**셀프 서비스**</span><span class="sxs-lookup"><span data-stu-id="caf50-479">**Self-Service**</span></span>
    
    ![구성 설정 셀프 서비스 이미지](images/c9f85bba3e96d627fe00fc5a8363b83a.png)

19. <span data-ttu-id="caf50-481">**완료** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="caf50-481">Select **Done**.</span></span> 

    ![구성 설정 do1img의 이미지](images/99679a7835b0d27d0a222bc3fdaf7f3b.png)

    ![구성 설정 do2img의 이미지](images/632aaab79ae18d0d2b8e0c16b6ba39e2.png)




