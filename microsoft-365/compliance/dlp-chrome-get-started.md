---
title: Microsoft 규정 준수 확장 시작(미리 보기)
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MET150
description: Microsoft 규정 준수 확장을 준비하고 배포합니다.
ms.openlocfilehash: 6ae44a86d415161cd3d7adf40671f02d93fb83c6
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/30/2021
ms.locfileid: "52113866"
---
# <a name="get-started-with-microsoft-compliance-extension-preview"></a><span data-ttu-id="35262-103">Microsoft 규정 준수 확장 시작(미리 보기)</span><span class="sxs-lookup"><span data-stu-id="35262-103">Get started with Microsoft Compliance Extension (preview)</span></span>

<span data-ttu-id="35262-104">이 절차를 사용하여 Microsoft 규정 준수 확장을 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="35262-104">Use these procedures to roll out the Microsoft Compliance Extension.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="35262-105">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="35262-105">Before you begin</span></span>

<span data-ttu-id="35262-106">Microsoft 규정 준수 확장을 사용하려면 장치가 엔드포인트 DLP에 온보드되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="35262-106">To use Microsoft Compliance Extension, the device must be onboarded into endpoint DLP.</span></span> <span data-ttu-id="35262-107">DLP 또는 엔드포인트 DLP를 처음 사용하는 경우 이 문서를 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="35262-107">Review these articles if you are new to DLP or endpoint DLP</span></span>

- [<span data-ttu-id="35262-108">Microsoft 규정 준수 확장에 대해 알아보기</span><span class="sxs-lookup"><span data-stu-id="35262-108">Learn about Microsoft Compliance Extension</span></span>](dlp-chrome-learn-about.md)
- [<span data-ttu-id="35262-109">데이터 손실 방지에 대해 알아보기</span><span class="sxs-lookup"><span data-stu-id="35262-109">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)
- [<span data-ttu-id="35262-110">DLP 정책 생성, 테스트 및 조정</span><span class="sxs-lookup"><span data-stu-id="35262-110">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="35262-111">서식 파일에서 DLP 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="35262-111">Create a DLP policy from a template</span></span>](create-a-dlp-policy-from-a-template.md)
- [<span data-ttu-id="35262-112">끝점 데이터 손실 방지에 대한 자세한 정보</span><span class="sxs-lookup"><span data-stu-id="35262-112">Learn about endpoint data loss prevention</span></span>](endpoint-dlp-learn-about.md)
- [<span data-ttu-id="35262-113">끝점 데이터 손실 방지 시작</span><span class="sxs-lookup"><span data-stu-id="35262-113">Get started with Endpoint data loss prevention</span></span>](endpoint-dlp-getting-started.md)
- [<span data-ttu-id="35262-114">Windows 10 장치용 온보딩 도구 및 방법</span><span class="sxs-lookup"><span data-stu-id="35262-114">Onboarding tools and methods for Windows 10 devices</span></span>](dlp-configure-endpoints.md)
- [<span data-ttu-id="35262-115">끝점 DLP에 대한 장치 프록시 및 인터넷 연결 설정 구성하기</span><span class="sxs-lookup"><span data-stu-id="35262-115">Configure device proxy and internet connection settings for Endpoint DLP</span></span>](endpoint-dlp-configure-proxy.md)
- [<span data-ttu-id="35262-116">엔드포인트 데이터 손실 방지 사용</span><span class="sxs-lookup"><span data-stu-id="35262-116">Using Endpoint data loss prevention</span></span>](endpoint-dlp-using.md)

### <a name="skusubscriptions-licensing"></a><span data-ttu-id="35262-117">SKU/구독 라이선싱</span><span class="sxs-lookup"><span data-stu-id="35262-117">SKU/subscriptions licensing</span></span>

<span data-ttu-id="35262-118">시작하기 전에 [Microsoft 365 구독](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)과 추가 기능을 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="35262-118">Before you get started, you should confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) and any add-ons.</span></span> <span data-ttu-id="35262-119">Endpoint DLP 기능에 액세스하고 사용하려면 다음 구독 또는 추가 기능 중 하나가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="35262-119">To access and use Endpoint DLP functionality, you must have one of these subscriptions or add-ons.</span></span>

- <span data-ttu-id="35262-120">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="35262-120">Microsoft 365 E5</span></span>
- <span data-ttu-id="35262-121">Microsoft 365 A5(EDU)</span><span class="sxs-lookup"><span data-stu-id="35262-121">Microsoft 365 A5 (EDU)</span></span>
- <span data-ttu-id="35262-122">Microsoft 365 E5 compliance</span><span class="sxs-lookup"><span data-stu-id="35262-122">Microsoft 365 E5 compliance</span></span>
- <span data-ttu-id="35262-123">Microsoft 365 A5 compliance</span><span class="sxs-lookup"><span data-stu-id="35262-123">Microsoft 365 A5 compliance</span></span>
- <span data-ttu-id="35262-124">Microsoft 365 E5 Information Protection 및 거버넌스</span><span class="sxs-lookup"><span data-stu-id="35262-124">Microsoft 365 E5 information protection and governance</span></span>
- <span data-ttu-id="35262-125">Microsoft 365 A5 Information Protection 및 거버넌스</span><span class="sxs-lookup"><span data-stu-id="35262-125">Microsoft 365 A5 information protection and governance</span></span>

<span data-ttu-id="35262-126">자세한 라이선싱에 대한 지침은 [보안 및 준수에 대한 Microsoft 365 라이선스 지침](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="35262-126">For detailed licensing guidance, see [Microsoft 365 licensing guidance for security & compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection).</span></span>

- <span data-ttu-id="35262-127">조직에는 엔드포인트 DLP에 대한 라이선스가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="35262-127">Your org must be licensed for Endpoint DLP</span></span>
- <span data-ttu-id="35262-128">장치에서 Windows 10 x64 빌드 1809 이상을 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="35262-128">Your devices must be running Windows 10 x64 build 1809 or later.</span></span>
- <span data-ttu-id="35262-129">장치에는 Antimalware Client 버전이 4.18.2101.9 이상이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="35262-129">The device must have Antimalware Client Version is 4.18.2101.9 or later.</span></span> <span data-ttu-id="35262-130">**Windows 보안** 앱을 열고, **설정** 아이콘을 선택한 다음 **정보** 를 선택하여 현재 버전을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="35262-130">Check your current version by opening **Windows Security** app, select the **Settings** icon, and then select **About**.</span></span>


### <a name="permissions"></a><span data-ttu-id="35262-131">사용 권한</span><span class="sxs-lookup"><span data-stu-id="35262-131">Permissions</span></span>

<span data-ttu-id="35262-132">엔드포인트 DLP의 데이터는 [활동 탐색기](data-classification-activity-explorer.md)에서 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35262-132">Data from Endpoint DLP can be viewed in [Activity explorer](data-classification-activity-explorer.md).</span></span> <span data-ttu-id="35262-133">활동 탐색기에 대한 사용 권한을 부여하는 7개의 역할이 있습니다. 데이터에 액세스하는 데 사용하는 계정은 해당 역할 중 하나의 구성원이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="35262-133">There are seven roles that grant permission to activity explorer, the account you use for accessing the data must be a member of any one of them.</span></span>

- <span data-ttu-id="35262-134">전역 관리자</span><span class="sxs-lookup"><span data-stu-id="35262-134">Global admin</span></span>
- <span data-ttu-id="35262-135">준수 관리자</span><span class="sxs-lookup"><span data-stu-id="35262-135">Compliance admin</span></span>
- <span data-ttu-id="35262-136">보안 관리자</span><span class="sxs-lookup"><span data-stu-id="35262-136">Security admin</span></span>
- <span data-ttu-id="35262-137">준수 데이터 관리자</span><span class="sxs-lookup"><span data-stu-id="35262-137">Compliance data admin</span></span>
- <span data-ttu-id="35262-138">전역 읽기 권한자</span><span class="sxs-lookup"><span data-stu-id="35262-138">Global reader</span></span>
- <span data-ttu-id="35262-139">보안 읽기 권한자</span><span class="sxs-lookup"><span data-stu-id="35262-139">Security reader</span></span>
- <span data-ttu-id="35262-140">보고서 읽기 권한자</span><span class="sxs-lookup"><span data-stu-id="35262-140">Reports reader</span></span>

### <a name="overall-installation-workflow"></a><span data-ttu-id="35262-141">전체 설치 워크플로</span><span class="sxs-lookup"><span data-stu-id="35262-141">Overall installation workflow</span></span>

<span data-ttu-id="35262-p105">Microsoft 규정 준수 확장 배포는 다단계 프로세스입니다. 한 번에 한 컴퓨터에 설치하거나 조직 전체의 배포를 위해 Microsoft Endpoint Manager 또는 그룹 정책을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35262-p105">Deploying Microsoft Compliance Extension is a multi-phase process. You can choose to install on one machine at a time, or use Microsoft Endpoint Manager or Group Policy for organization-wide deployments.</span></span>

1. <span data-ttu-id="35262-144">[장치 준비](#prepare-your-devices)</span><span class="sxs-lookup"><span data-stu-id="35262-144">[Prepare your devices](#prepare-your-devices).</span></span>
2. [<span data-ttu-id="35262-145">기본 설정 단일 컴퓨터 셀프호스트</span><span class="sxs-lookup"><span data-stu-id="35262-145">Basic Setup Single Machine Selfhost</span></span>](#basic-setup-single-machine-selfhost)
3. [<span data-ttu-id="35262-146">Microsoft Endpoint Manager를 사용하여 배포</span><span class="sxs-lookup"><span data-stu-id="35262-146">Deploy using Microsoft Endpoint Manager</span></span>](#deploy-using-microsoft-endpoint-manager)
4. [<span data-ttu-id="35262-147">그룹 정책을 사용하여 배포</span><span class="sxs-lookup"><span data-stu-id="35262-147">Deploy using Group Policy</span></span>](#deploy-using-group-policy)
5. [<span data-ttu-id="35262-148">확장 테스트</span><span class="sxs-lookup"><span data-stu-id="35262-148">Test the Extension</span></span>](#test-the-extension)
6. [<span data-ttu-id="35262-149">경고 관리 대시보드를 사용하여 Chrome DLP 경고 보기</span><span class="sxs-lookup"><span data-stu-id="35262-149">Use the Alerts Management Dashboard to viewing Chrome DLP alerts</span></span>](#use-the-alerts-management-dashboard-to-viewing-chrome-dlp-alerts)
7. [<span data-ttu-id="35262-150">활동 탐색기에서 Chrome DLP 데이터 보기</span><span class="sxs-lookup"><span data-stu-id="35262-150">Viewing Chrome DLP data in activity explorer</span></span>](#viewing-chrome-dlp-data-in-activity-explorer) 

### <a name="prepare-infrastructure"></a><span data-ttu-id="35262-151">인프라 준비</span><span class="sxs-lookup"><span data-stu-id="35262-151">Prepare infrastructure</span></span>

<span data-ttu-id="35262-152">모니터링되는 모든 Windows 10 장치에 Microsoft 규정 준수 확장을 배포하는 경우, 허용되지 않는 앱 및 허용되지 않는 브라우저 목록에서 Google Chrome을 제거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="35262-152">If you are rolling out the Microsoft Compliance Extension to all your monitored Windows 10 devices, you should remove Google Chrome from the unallowed app and unallowed browser lists.</span></span> <span data-ttu-id="35262-153">자세한 내용은 [허용되지 않는 브라우저](endpoint-dlp-using.md#unallowed-browsers)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="35262-153">For more information, see [Unallowed browsers](endpoint-dlp-using.md#unallowed-browsers).</span></span> <span data-ttu-id="35262-154">일부 장치에만 배포하는 경우, 허용되지 않은 브라우저 또는 허용되지 않는 앱 목록에 Chrome을 남겨둘 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35262-154">If you are only rolling it out to a few devices, you can leave Chrome on the unallowed browser or unallowed app lists.</span></span> <span data-ttu-id="35262-155">Microsoft 규정 준수 확장은 앱이 설치된 컴퓨터의 두 목록 모두의 제한을 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="35262-155">The Microsoft Compliance Extension will bypass the restrictions of both lists for those computers where it is installed.</span></span>  

### <a name="prepare-your-devices"></a><span data-ttu-id="35262-156">장치 준비</span><span class="sxs-lookup"><span data-stu-id="35262-156">Prepare your devices</span></span>

1. <span data-ttu-id="35262-157">다음 항목의 절차를 사용하여 장치를 온보드합니다.</span><span class="sxs-lookup"><span data-stu-id="35262-157">Use the procedures in these topics to onboard your devices:</span></span>
    1. [<span data-ttu-id="35262-158">끝점 데이터 손실 방지 시작</span><span class="sxs-lookup"><span data-stu-id="35262-158">Get started with Endpoint data loss prevention</span></span>](endpoint-dlp-getting-started.md)
    1. [<span data-ttu-id="35262-159">Windows 10 장치용 온보딩 도구 및 방법</span><span class="sxs-lookup"><span data-stu-id="35262-159">Onboarding tools and methods for Windows 10 devices</span></span>](dlp-configure-endpoints.md)
    1. [<span data-ttu-id="35262-160">끝점 DLP에 대한 장치 프록시 및 인터넷 연결 설정 구성하기</span><span class="sxs-lookup"><span data-stu-id="35262-160">Configure device proxy and internet connection settings for Endpoint DLP</span></span>](endpoint-dlp-configure-proxy.md)

### <a name="basic-setup-single-machine-selfhost"></a><span data-ttu-id="35262-161">기본 설정 단일 컴퓨터 셀프호스트</span><span class="sxs-lookup"><span data-stu-id="35262-161">Basic Setup Single Machine Selfhost</span></span>

<span data-ttu-id="35262-162">이 방법을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="35262-162">This is the recommended method.</span></span> 

1. <span data-ttu-id="35262-163">Microsoft 규정 준수 확장을 설치하려는 Windows 10 컴퓨터에 로그인하고 이 PowerShell 스크립트를 관리자로 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="35262-163">Sign in to the Windows 10 computer on which you want to install the Microsoft Compliance Extension on, and run this PowerShell script as an administrator.</span></span> 

   ```powershell
   Get-Item -path "HKLM:\SOFTWARE\Microsoft\Windows Defender\Miscellaneous Configuration" | New-ItemProperty -Name DlpDisableBrowserCache -Value 0 -Force
   ``` 

2.  <span data-ttu-id="35262-164">[Microsoft 규정 준수 확장 - Chrome Web Store(google.com)](https://chrome.google.com/webstore/detail/microsoft-compliance-exte/echcggldkblhodogklpincgchnpgcdco)으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="35262-164">Navigate to [Microsoft Compliance Extension - Chrome Web Store (google.com)](https://chrome.google.com/webstore/detail/microsoft-compliance-exte/echcggldkblhodogklpincgchnpgcdco).</span></span>

3.  <span data-ttu-id="35262-165">Chrome Web Store 페이지의 지침을 사용하여 확장을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="35262-165">Install the extension using the instructions on the Chrome Web Store page.</span></span>

### <a name="deploy-using-microsoft-endpoint-manager"></a><span data-ttu-id="35262-166">Microsoft Endpoint Manager를 사용하여 배포</span><span class="sxs-lookup"><span data-stu-id="35262-166">Deploy using Microsoft Endpoint Manager</span></span>

<span data-ttu-id="35262-167">조직 전체 배포에 이 설정 방법을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="35262-167">Use this setup method for organization-wide deployments.</span></span>


##### <a name="enabling-required-registry-key-via-microsoft-endpoint-manager"></a><span data-ttu-id="35262-168">Microsoft Endpoint Manager를 통해 필수 레지스트리 키 사용</span><span class="sxs-lookup"><span data-stu-id="35262-168">Enabling Required Registry Key via Microsoft Endpoint Manager</span></span>

1.  <span data-ttu-id="35262-169">다음 내용으로 PowerShell 스크립트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="35262-169">Create a PowerShell script with the following contents:</span></span>

    ```powershell
    Get-Item -path "HKLM:\SOFTWARE\Microsoft\Windows Defender\Miscellaneous Configuration" | New-ItemProperty -Name DlpDisableBrowserCache -Value 0 -Force
    ```

2.  <span data-ttu-id="35262-170">[Microsoft Endpoint Manager 관리 센터](https://endpoint.microsoft.com)에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="35262-170">Sign in to the [Microsoft Endpoint Manager Admin Center](https://endpoint.microsoft.com).</span></span>

3.  <span data-ttu-id="35262-171">**장치** > **스크립트** 로 이동한 다음 **추가** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="35262-171">Navigate to **Devices** > **Scripts** and select **Add**.</span></span>

4.  <span data-ttu-id="35262-172">메시지가 표시되면 만든 스크립트의 위치로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="35262-172">Browse to the location of the script created when prompted.</span></span>

5.  <span data-ttu-id="35262-173">다음 설정을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="35262-173">Select the following settings:</span></span>
    1. <span data-ttu-id="35262-174">로그인된 자격 증명을 사용하여 이 스크립트를 실행: 예</span><span class="sxs-lookup"><span data-stu-id="35262-174">Run this script using the logged-on credentials: YES</span></span>
    1. <span data-ttu-id="35262-175">스크립트 서명 검사 강제: 아니요</span><span class="sxs-lookup"><span data-stu-id="35262-175">Enforce script signature check: NO</span></span>
    1. <span data-ttu-id="35262-176">64비트 PowerShell 호스트에서 스크립트 실행: 예</span><span class="sxs-lookup"><span data-stu-id="35262-176">Run script in 64-bit PowerShell Host: YES</span></span>

6.  <span data-ttu-id="35262-177">적절한 장치 그룹을 선택하고 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="35262-177">Select the proper device groups and apply the policy.</span></span>

#### <a name="microsoft-endpoint-manager-force-install-steps"></a><span data-ttu-id="35262-178">Microsoft Endpoint Manager 강제 설치 단계</span><span class="sxs-lookup"><span data-stu-id="35262-178">Microsoft Endpoint Manager Force Install Steps</span></span>

<span data-ttu-id="35262-179">강제 설치된 확장 목록에 Microsoft 규정 준수 확장을 추가하기 전에 Chrome ADMX를 입수하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="35262-179">Before adding the Microsoft Compliance Extension to the list of force-installed extensions, it is important to ingest the Chrome ADMX.</span></span> <span data-ttu-id="35262-180">Microsoft Endpoint Manager의 이 프로세스에 대한 단계는 Google: [Microsoft Intune으로 Chrome 브라우저 관리 - Google Chrome Enterprise 도움말](https://support.google.com/chrome/a/answer/9102677?hl=en#zippy=%2Cstep-ingest-the-chrome-admx-file-into-intune)에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35262-180">Steps for this process in Microsoft Endpoint Manager are documented by Google: [Manage Chrome Browser with Microsoft Intune - Google Chrome Enterprise Help](https://support.google.com/chrome/a/answer/9102677?hl=en#zippy=%2Cstep-ingest-the-chrome-admx-file-into-intune).</span></span>

 <span data-ttu-id="35262-181">ADMX를 입수한 후 아래 단계를 따라 이 확장에 대한 구성 프로필을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35262-181">After ingesting the ADMX, the steps below can be followed to create a configuration profile for this extension.</span></span>

1.  <span data-ttu-id="35262-182">Microsoft Endpoint Manager 관리 센터(https://endpoint.microsoft.com))에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="35262-182">Sign in to the Microsoft Endpoint Manager Admin Center (https://endpoint.microsoft.com).</span></span>

2.  <span data-ttu-id="35262-183">구성 프로필로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="35262-183">Navigate to Configuration Profiles.</span></span>

3.  <span data-ttu-id="35262-184">**프로필 만들기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="35262-184">Select **Create Profile**.</span></span>

4.  <span data-ttu-id="35262-185">**Windows 10** 을 플랫폼으로 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="35262-185">Select **Windows 10** as the platform.</span></span>

5.  <span data-ttu-id="35262-186">**사용자 지정** 을 사용자 유형으로 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="35262-186">Select **Custom** as profile type.</span></span>

6.  <span data-ttu-id="35262-187">**설정** 탭을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="35262-187">Select the **Settings** tab.</span></span>

7.  <span data-ttu-id="35262-188">**추가** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="35262-188">Select **Add**.</span></span>

8.  <span data-ttu-id="35262-189">다음 정책 정보를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="35262-189">Enter the following policy information.</span></span>
    
    <span data-ttu-id="35262-190">OMA-URI: `./Device/Vendor/MSFT/Policy/Config/Chrome~Policy~googlechrome~Extensions/ExtensionInstallForcelist`</span><span class="sxs-lookup"><span data-stu-id="35262-190">OMA-URI: `./Device/Vendor/MSFT/Policy/Config/Chrome~Policy~googlechrome~Extensions/ExtensionInstallForcelist`</span></span><br/>
    <span data-ttu-id="35262-191">데이터 형식: `String`</span><span class="sxs-lookup"><span data-stu-id="35262-191">Data type: `String`</span></span><br/>
    <span data-ttu-id="35262-192">값: `<enabled/><data id="ExtensionInstallForcelistDesc" value="1&#xF000; echcggldkblhodogklpincgchnpgcdco;https://clients2.google.com/service/update2/crx"/>`</span><span class="sxs-lookup"><span data-stu-id="35262-192">Value: `<enabled/><data id="ExtensionInstallForcelistDesc" value="1&#xF000; echcggldkblhodogklpincgchnpgcdco;https://clients2.google.com/service/update2/crx"/>`</span></span>

9.  <span data-ttu-id="35262-193">만들기를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="35262-193">Click create.</span></span>

### <a name="deploy-using-group-policy"></a><span data-ttu-id="35262-194">그룹 정책을 사용하여 배포</span><span class="sxs-lookup"><span data-stu-id="35262-194">Deploy using Group Policy</span></span>

<span data-ttu-id="35262-195">Microsoft Endpoint Manager를 사용하지 않으려면 그룹 정책을 사용하여 조직 전체에 Microsoft 규정 준수 확장을 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35262-195">If you don't want to use Microsoft Endpoint Manager, you can use group policies to deploy the Microsoft Compliance Extension across your organization</span></span>

1. <span data-ttu-id="35262-196">장치는 그룹 정책을 통해 관리할 수 있어야 하며 모든 Chrome ADMX를 그룹 정책 중앙 저장소로 가져와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="35262-196">Your devices must be manageable via Group Policy, and you need to import all Chrome ADMXs into the Group Policy Central Store.</span></span> <span data-ttu-id="35262-197">자세한 내용은 [Windows의 그룹 정책 관리 서식 파일에 대한 중앙 저장소를 만들고 관리하는 방법](https://docs.microsoft.com/troubleshoot/windows-client/group-policy/create-and-manage-central-store)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="35262-197">For more information, see [How to create and manage the Central Store for Group Policy Administrative Templates in Windows](https://docs.microsoft.com/troubleshoot/windows-client/group-policy/create-and-manage-central-store).</span></span>

2.  <span data-ttu-id="35262-198">다음 PowerShell 명령을 사용하여 PowerShell 스크립트를 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="35262-198">Create a PowerShell script using this PowerShell command:</span></span>

    ```powershell
    Get-Item -path "HKLM:\SOFTWARE\Microsoft\Windows Defender\Miscellaneous Configuration" | New-ItemProperty -Name DlpDisableBrowserCache -Value 0 -Force
    ```

3.  <span data-ttu-id="35262-199">**그룹 정책 관리 콘솔** 을 열고 OU(조직 구성 단위)로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="35262-199">Open the **Group Policy Management Console** and navigate to your organizational unit (OU).</span></span>

4.  <span data-ttu-id="35262-200">마우스 오른쪽 단추를 클릭하고 **이 도메인에 GPO를 만들고 여기에 연결** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="35262-200">Right-click and select **Create a GPO in this domain and Link it here**.</span></span> <span data-ttu-id="35262-201">메시지가 표시되면 이 GPO(그룹 정책 개체)에 설명 이름을 지정하고 만들기를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="35262-201">When prompted, assign a descriptive name to this group policy object (GPO) and finish creating it.</span></span>

5.  <span data-ttu-id="35262-202">GPO를 마우스 오른쪽 단추로 클릭하고 **편집** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="35262-202">Right-click the GPO and select **Edit**.</span></span>

6.  <span data-ttu-id="35262-203">**컴퓨터 구성** > **기본 설정** > **제어판 설정** > **예약된 작업** 으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="35262-203">Go to **Computer Configuration** > **Preferences** > **Control Panel Settings** > **Scheduled Tasks**.</span></span>

7.  <span data-ttu-id="35262-204">마우스 오른쪽 단추를 클릭하고 **새로 만들기** > **즉시 작업(최소 Windows 7)** 을 선택하고 새 즉시 작업을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="35262-204">Create a new immediate task by selecting right-clicking and selecting **New** > **Immediate Task (At least Windows 7)**.</span></span>

8.  <span data-ttu-id="35262-205">작업에 이름 및 설명을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="35262-205">Give the task a name & description.</span></span>

9.  <span data-ttu-id="35262-206">해당 계정을 선택하여 즉시 작업을 실행합니다(예: NT Authority).</span><span class="sxs-lookup"><span data-stu-id="35262-206">Choose the corresponding account to run the immediate task, for example NT Authority</span></span>

10. <span data-ttu-id="35262-207">**가장 높은 수준의 권한으로 실행** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="35262-207">Select **Run with highest privileges**.</span></span>

11. <span data-ttu-id="35262-208">Windows 10에 대한 정책을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="35262-208">Configure the policy for Windows 10.</span></span>

12. <span data-ttu-id="35262-209">**작업** 탭에서 **프로그램 시작** 작업을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="35262-209">In the **Actions** tab, select the action **Start a program**.</span></span>

13. <span data-ttu-id="35262-210">1단계에서 만든 프로그램/스크립트의 경로를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="35262-210">Enter the path to the Program/Script created in Step 1.</span></span>

14. <span data-ttu-id="35262-211">**적용** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="35262-211">Select **Apply**.</span></span>

#### <a name="adding-the-chrome-extension-to-the-forceinstall-list"></a><span data-ttu-id="35262-212">ForceInstall 목록에 Chrome 확장을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="35262-212">Adding the Chrome Extension to the ForceInstall List</span></span>

1.  <span data-ttu-id="35262-213">그룹 정책 관리 편집기에서 OU로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="35262-213">In the Group Policy Management Editor, navigate to your OU.</span></span>

2.  <span data-ttu-id="35262-214">다음 경로를 확장합니다. **컴퓨터/사용자 구성** > **정책** > **관리 서식 파일** > **클래식 관리 서식 파일** > **Google** > **Google Chrome** > **확장**.</span><span class="sxs-lookup"><span data-stu-id="35262-214">Expand the following path **Computer/User configuration** > **Policies** > **Administrative templates** > **Classic administrative templates** > **Google** > **Google Chrome** > **Extensions**.</span></span> <span data-ttu-id="35262-215">이 경로는 구성에 따라 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35262-215">This path may vary depending on your configuration.</span></span>

3.  <span data-ttu-id="35262-216">**강제로 설치된 확장 목록을 구성** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="35262-216">Select **Configure the list of force-installed extensions**.</span></span>

4.  <span data-ttu-id="35262-217">마우스 오른쪽 단추를 클릭하고 **편집** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="35262-217">Right click and select **Edit**.</span></span>

5.  <span data-ttu-id="35262-218">**사용하도록 설정** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="35262-218">Select **Enabled**.</span></span>

6.  <span data-ttu-id="35262-219">**표시** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="35262-219">Select **Show**.</span></span>

7.  <span data-ttu-id="35262-220">**값** 에서 다음 입력을 추가합니다. `echcggldkblhodogklpincgchnpgcdco;https://clients2.google.com/service/update2/crx`</span><span class="sxs-lookup"><span data-stu-id="35262-220">Under **Value**, add the following entry: `echcggldkblhodogklpincgchnpgcdco;https://clients2.google.com/service/update2/crx`</span></span>

8.  <span data-ttu-id="35262-221">**확인**, **적용** 을 차례로 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="35262-221">Select **OK** and then **Apply**.</span></span>

### <a name="test-the-extension"></a><span data-ttu-id="35262-222">확장 테스트</span><span class="sxs-lookup"><span data-stu-id="35262-222">Test the Extension</span></span>

#### <a name="upload-to-cloud-service-or-access-by-unallowed-browsers-cloud-egress"></a><span data-ttu-id="35262-223">클라우드 서비스로 업로드 또는 허용되지 않은 브라우저 Cloud Egress에서 액세스</span><span class="sxs-lookup"><span data-stu-id="35262-223">Upload to cloud service, or access by unallowed browsers Cloud Egress</span></span>  

1. <span data-ttu-id="35262-224">중요한 항목을 만들거나 가져오고 조직의 제한된 서비스 도메인 중 하나에 파일을 업로드합니다.</span><span class="sxs-lookup"><span data-stu-id="35262-224">Create or get a sensitive item and, try to upload a file to one of your organization’s restricted service domains.</span></span> <span data-ttu-id="35262-225">중요한 데이터는 기본 제공되는 [중요한 정보 유형](sensitive-information-type-entity-definitions.md) 또는 조직의 중요한 정보 유형 중 하나와 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="35262-225">The sensitive data must match one of our built-in [Sensitive Info Types](sensitive-information-type-entity-definitions.md), or one of your organization’s sensitive information types.</span></span> <span data-ttu-id="35262-226">파일이 열려 있을 경우 이 작업이 허용되지 않는다는 것을 보여주는 DLP 토스트 알림을 테스트하는 장치에서 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="35262-226">You should get a DLP toast notification on the device you are testing from that shows that this action is not allowed when the file is open.</span></span>

#### <a name="testing-other-dlp-scenarios-in-chrome"></a><span data-ttu-id="35262-227">Chrome에서 다른 DLP 테스트 시나리오</span><span class="sxs-lookup"><span data-stu-id="35262-227">Testing other DLP scenarios in Chrome</span></span> 

<span data-ttu-id="35262-228">이제 허용되지 않는 브라우저/앱 목록에서 Chrome을 제거했으므로 아래 시나리오를 테스트하여 조직의 요구 사항을 충족하는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35262-228">Now that you’ve removed Chrome from the disallowed browsers/apps list, you can test the scenarios below to confirm the behavior meets your organization’s requirements:</span></span>

- <span data-ttu-id="35262-229">클립보드를 사용하여 중요한 항목의 데이터를 다른 문서로 복사</span><span class="sxs-lookup"><span data-stu-id="35262-229">Copy data from a sensitive item to another document using the Clipboard</span></span>
    - <span data-ttu-id="35262-230">테스트하려면 Chrome 브라우저에서 클립보드 작업에 복사되지 않도록 보호된 파일을 열고 파일에서 데이터를 복사하려고 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="35262-230">To test, open a file that is protected against copy to clipboard actions in the Chrome browser and attempt to copy data from the file.</span></span>
    - <span data-ttu-id="35262-231">예상 결과: 파일이 열려 있는 경우 이 작업이 허용되지 않는 경우를 보여 주는 DLP 토스트 알림을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="35262-231">Expected Result: A DLP toast notification showing that this action is not allowed when the file is open.</span></span>
- <span data-ttu-id="35262-232">문서 인쇄</span><span class="sxs-lookup"><span data-stu-id="35262-232">Print a document</span></span>
    - <span data-ttu-id="35262-233">테스트하려면 Chrome 브라우저에서 인쇄 작업으로부터 보호되는 파일을 열고 파일을 인쇄합니다.</span><span class="sxs-lookup"><span data-stu-id="35262-233">To test, open a file that is protected against print actions in the Chrome browser and attempt to print the file.</span></span>
    - <span data-ttu-id="35262-234">예상 결과: 파일이 열려 있는 경우 이 작업이 허용되지 않는 경우를 보여 주는 DLP 토스트 알림을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="35262-234">Expected Result: A DLP toast notification showing that this action is not allowed when the file is open.</span></span>
- <span data-ttu-id="35262-235">USB 이동식 미디어에 복사</span><span class="sxs-lookup"><span data-stu-id="35262-235">Copy to USB Removeable Media</span></span>
    - <span data-ttu-id="35262-236">테스트하려면 파일을 이동식 미디어 저장소에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="35262-236">To test, try to save the file to a removeable media storage.</span></span>
    - <span data-ttu-id="35262-237">예상 결과: 파일이 열려 있는 경우 이 작업이 허용되지 않는 경우를 보여 주는 DLP 토스트 알림을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="35262-237">Expected Result: A DLP toast notification showing that this action is not allowed when the file is open.</span></span>
- <span data-ttu-id="35262-238">네트워크 공유 위치에 복사</span><span class="sxs-lookup"><span data-stu-id="35262-238">Copy to Network Share</span></span>
    - <span data-ttu-id="35262-239">테스트하려면 파일을 네트워크 공유 위치에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="35262-239">To test, try to save the file to a network share.</span></span>
    - <span data-ttu-id="35262-240">예상 결과: 파일이 열려 있는 경우 이 작업이 허용되지 않는 경우를 보여 주는 DLP 토스트 알림을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="35262-240">Expected Result: A DLP toast notification showing that this action is not allowed when the file is open.</span></span>


### <a name="use-the-alerts-management-dashboard-to-viewing-chrome-dlp-alerts"></a><span data-ttu-id="35262-241">경고 관리 대시보드를 사용하여 Chrome DLP 경고 보기</span><span class="sxs-lookup"><span data-stu-id="35262-241">Use the Alerts Management Dashboard to viewing Chrome DLP alerts</span></span>

1. <span data-ttu-id="35262-242">[Microsoft 365 규정 준수 센터](https://compliance.microsoft.com)에서 **데이터 손실 방지** 페이지를 열고 **경고** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="35262-242">Open the **Data loss prevention** page in the [Microsoft 365 Compliance center](https://compliance.microsoft.com) and select **Alerts**.</span></span>

2. <span data-ttu-id="35262-243">엔드포인트 DLP 정책에 대한 경고를 보려면 [DLP 정책을 구성하고 경고를 보는 방법](dlp-configure-view-alerts-policies.md)의 절차를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="35262-243">Refer to the procedures in [How to configure and view alerts for your DLP policies](dlp-configure-view-alerts-policies.md) to view alerts for your Endpoint DLP policies.</span></span>


### <a name="viewing-chrome-dlp-data-in-activity-explorer"></a><span data-ttu-id="35262-244">활동 탐색기에서 Chrome DLP 데이터 보기</span><span class="sxs-lookup"><span data-stu-id="35262-244">Viewing Chrome DLP data in activity explorer</span></span>

1. <span data-ttu-id="35262-245">Microsoft 365 규정 준수 센터에서 도메인에 대한 [데이터 분류 페이지](https://compliance.microsoft.com/dataclassification?viewid=overview)를 열고 **활동 탐색기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="35262-245">Open the [Data classification page](https://compliance.microsoft.com/dataclassification?viewid=overview) for your domain in the Microsoft 365 Compliance center and choose **Activity explorer**.</span></span>

2. <span data-ttu-id="35262-246">[활동 탐색기 시작하기](data-classification-activity-explorer.md)의 절차를 참조하여 엔드포인트 장치에 대한 모든 데이터에 액세스하고 테이터를 필터링합니다.</span><span class="sxs-lookup"><span data-stu-id="35262-246">Refer to the procedures in [Get started with Activity explorer](data-classification-activity-explorer.md) to access and filter all the data for your Endpoint devices.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="35262-247">![엔드포인트 장치에 대한 활동 탐색기 필터](../media/endpoint-dlp-4-getting-started-activity-explorer.png)</span><span class="sxs-lookup"><span data-stu-id="35262-247">![activity explorer filter for endpoint devices](../media/endpoint-dlp-4-getting-started-activity-explorer.png)</span></span>

### <a name="known-issues-and-limitations"></a><span data-ttu-id="35262-248">알려진 문제점 및 제한 사항</span><span class="sxs-lookup"><span data-stu-id="35262-248">Known Issues and Limitations</span></span>

1. <span data-ttu-id="35262-249">폴더 업로드에 대한 끌어서 놓기 실행은 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="35262-249">Drag & Drop enforcement for folder upload is not supported.</span></span>
2. <span data-ttu-id="35262-250">클라우드 송신에 대한 오버라이드 실행은 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="35262-250">Block Override enforcement for cloud egress is not supported.</span></span>
3. <span data-ttu-id="35262-251">Incognito 모드는 지원되지 않으며 사용하지 않도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="35262-251">Incognito mode is not supported and must be disabled.</span></span>

## <a name="next-steps"></a><span data-ttu-id="35262-252">다음 단계</span><span class="sxs-lookup"><span data-stu-id="35262-252">Next steps</span></span>
<span data-ttu-id="35262-253">이제 온보딩된 장치가 있고 활동 탐색기에서 활동 데이터를 볼 수 있으므로 중요한 항목을 보호하는 DLP 정책을 만드는 다음 단계를 진행할 준비가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="35262-253">Now that you have onboarded devices and can view the activity data in Activity explorer, you are ready to move on to your next step where you create DLP policies that protect your sensitive items.</span></span>

- [<span data-ttu-id="35262-254">엔드포인트 데이터 손실 방지 사용</span><span class="sxs-lookup"><span data-stu-id="35262-254">Using Endpoint data loss prevention</span></span>](endpoint-dlp-using.md)

## <a name="see-also"></a><span data-ttu-id="35262-255">참고 항목</span><span class="sxs-lookup"><span data-stu-id="35262-255">See also</span></span>

- [<span data-ttu-id="35262-256">끝점 데이터 손실 방지에 대한 자세한 정보</span><span class="sxs-lookup"><span data-stu-id="35262-256">Learn about Endpoint data loss prevention </span></span>](endpoint-dlp-learn-about.md)
- [<span data-ttu-id="35262-257">끝점 데이터 손실 방지 사용</span><span class="sxs-lookup"><span data-stu-id="35262-257">Using Endpoint data loss prevention </span></span>](endpoint-dlp-using.md)
- [<span data-ttu-id="35262-258">데이터 손실 방지에 대해 알아보기</span><span class="sxs-lookup"><span data-stu-id="35262-258">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)
- [<span data-ttu-id="35262-259">DLP 정책 만들기, 테스트 및 조정</span><span class="sxs-lookup"><span data-stu-id="35262-259">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="35262-260">활동 탐색기 시작하기</span><span class="sxs-lookup"><span data-stu-id="35262-260">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="35262-261">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="35262-261">Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/)
- [<span data-ttu-id="35262-262">Windows 10 컴퓨터용 온보딩 도구 및 방법</span><span class="sxs-lookup"><span data-stu-id="35262-262">Onboarding tools and methods for Windows 10 machines</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)
- [<span data-ttu-id="35262-263">Microsoft 365 구독</span><span class="sxs-lookup"><span data-stu-id="35262-263">Microsoft 365 subscription</span></span>](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)
- [<span data-ttu-id="35262-264">Azure AD 가입 장치</span><span class="sxs-lookup"><span data-stu-id="35262-264">Azure AD joined devices</span></span>](https://docs.microsoft.com/azure/active-directory/devices/concept-azure-ad-join)
- [<span data-ttu-id="35262-265">Chromium 기반 새 Microsoft Edge 다운로드하기</span><span class="sxs-lookup"><span data-stu-id="35262-265">Download the new Microsoft Edge based on Chromium</span></span>](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium)
