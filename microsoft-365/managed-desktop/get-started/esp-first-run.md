---
title: Autopilot 및 등록 상태 페이지의 첫 실행 환경
description: ESP 환경, 사용되는 설정 및 구성 변경을 배포하는 방법
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 문서
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
audience: ITpro
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 5e2340c7c0bf00165bb43740d3d095b5b0402fc0
ms.sourcegitcommit: 0402d3275632fceda9137b6abc3ce48c8020172a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/17/2020
ms.locfileid: "49126628"
---
# <a name="first-run-experience-with-autopilot-and-the-enrollment-status-page"></a><span data-ttu-id="fbcfd-104">Autopilot 및 등록 상태 페이지의 첫 실행 환경</span><span class="sxs-lookup"><span data-stu-id="fbcfd-104">First-run experience with Autopilot and the Enrollment Status Page</span></span>

<span data-ttu-id="fbcfd-105">Microsoft Managed Desktop은 [Windows Autopilot과](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot) Microsoft Intune의 [ESP(등록 상태 페이지)를](https://docs.microsoft.com/windows/deployment/windows-autopilot/enrollment-status) 모두 사용하여 사용자에게 최상의 첫 실행 환경을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="fbcfd-105">Microsoft Managed Desktop uses both [Windows Autopilot](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot) and Microsoft Intune's [Enrollment Status Page (ESP)](https://docs.microsoft.com/windows/deployment/windows-autopilot/enrollment-status) to provide the best possible first-run experience to your users.</span></span>

<span data-ttu-id="fbcfd-106">등록 상태 페이지가 현재 공개 미리 보기 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="fbcfd-106">The Enrollment Status Page is currently in public preview.</span></span>

## <a name="initial-deployment"></a><span data-ttu-id="fbcfd-107">초기 배포</span><span class="sxs-lookup"><span data-stu-id="fbcfd-107">Initial deployment</span></span>

<span data-ttu-id="fbcfd-108">ESP 환경을 제공하려면 Microsoft Managed Desktop 서비스에 장치를 등록해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbcfd-108">To provide the ESP experience, you must register devices in the Microsoft Managed Desktop service.</span></span> <span data-ttu-id="fbcfd-109">등록에 대한 자세한 [](../get-started/register-devices-self.md) 내용은 새 디바이스를 직접 등록하거나 파트너가 디바이스를 등록하는 [단계를 참조하세요.](../get-started/register-devices-partner.md)</span><span class="sxs-lookup"><span data-stu-id="fbcfd-109">For more about registration, see [Register new devices yourself](../get-started/register-devices-self.md) or [Steps for Partners to register devices](../get-started/register-devices-partner.md).</span></span>

<span data-ttu-id="fbcfd-110">디바이스가 서비스에 등록된 후 관리 포털을 통해 지원 티켓을 작성하여 Microsoft Managed Desktop 디바이스에 대해 ESP를 사용하도록 설정할 [수 있습니다.](https://portal.azure.com/)</span><span class="sxs-lookup"><span data-stu-id="fbcfd-110">Once your devices are registered with the service, you can enable ESP for your Microsoft Managed Desktop devices by filing a support ticket through the [Admin Portal](https://portal.azure.com/).</span></span> <span data-ttu-id="fbcfd-111">처음에 티켓을 제출할 때 테스트 그룹에 ESP 구성을 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="fbcfd-111">We will initially deploy the ESP configuration to the Test group when you file the ticket.</span></span> <span data-ttu-id="fbcfd-112">24시간마다 다른 후속 배포 그룹(첫 번째, 빠르기 및 광범위)에 배포됩니다.</span><span class="sxs-lookup"><span data-stu-id="fbcfd-112">It is deployed to the other subsequent deployment groups (First, Fast, and Broad) each 24 hours.</span></span> <span data-ttu-id="fbcfd-113">배포를 일시 중지하기 위해 Operations에 보류를 요청하는 다른 티켓을 제출합니다.</span><span class="sxs-lookup"><span data-stu-id="fbcfd-113">To pause the deployment, file another ticket asking Operations to hold.</span></span>

## <a name="autopilot-profile-settings"></a><span data-ttu-id="fbcfd-114">Autopilot 프로필 설정</span><span class="sxs-lookup"><span data-stu-id="fbcfd-114">Autopilot profile settings</span></span>

<span data-ttu-id="fbcfd-115">Microsoft Managed Desktop은 사용자 장치에 사용되는 Autopilot 프로필에서 다음 설정을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="fbcfd-115">Microsoft Managed Desktop uses these settings in the Autopilot profile used for your users' devices:</span></span>


|<span data-ttu-id="fbcfd-116">설정</span><span class="sxs-lookup"><span data-stu-id="fbcfd-116">Setting</span></span>  |<span data-ttu-id="fbcfd-117">값</span><span class="sxs-lookup"><span data-stu-id="fbcfd-117">Value</span></span>  |
|---------|---------|
|<span data-ttu-id="fbcfd-118">배포 모드</span><span class="sxs-lookup"><span data-stu-id="fbcfd-118">Deployment mode</span></span> |  <span data-ttu-id="fbcfd-119">사용자 기반</span><span class="sxs-lookup"><span data-stu-id="fbcfd-119">User Driven</span></span>       |
|<span data-ttu-id="fbcfd-120">Azure AD에 다음으로 가입</span><span class="sxs-lookup"><span data-stu-id="fbcfd-120">Join to Azure AD as</span></span>     |  <span data-ttu-id="fbcfd-121">Azure AD 가입</span><span class="sxs-lookup"><span data-stu-id="fbcfd-121">Azure AD joined</span></span>       |
|<span data-ttu-id="fbcfd-122">언어(지역)</span><span class="sxs-lookup"><span data-stu-id="fbcfd-122">Language (Region)</span></span>     | <span data-ttu-id="fbcfd-123">운영 체제 기본값</span><span class="sxs-lookup"><span data-stu-id="fbcfd-123">Operating system default</span></span>        |
|<span data-ttu-id="fbcfd-124">키보드 자동 구성</span><span class="sxs-lookup"><span data-stu-id="fbcfd-124">Automatically configure keyboard</span></span>     | <span data-ttu-id="fbcfd-125">아니요</span><span class="sxs-lookup"><span data-stu-id="fbcfd-125">No</span></span>        |
|<span data-ttu-id="fbcfd-126">Microsoft 소프트웨어 사용 조건</span><span class="sxs-lookup"><span data-stu-id="fbcfd-126">Microsoft Software License Terms</span></span>     |  <span data-ttu-id="fbcfd-127">숨기기</span><span class="sxs-lookup"><span data-stu-id="fbcfd-127">Hide</span></span>       |
|<span data-ttu-id="fbcfd-128">개인 정보 설정</span><span class="sxs-lookup"><span data-stu-id="fbcfd-128">Privacy settings</span></span>     | <span data-ttu-id="fbcfd-129">숨기기</span><span class="sxs-lookup"><span data-stu-id="fbcfd-129">Hide</span></span>        |
|<span data-ttu-id="fbcfd-130">변경 계정 옵션 숨기기</span><span class="sxs-lookup"><span data-stu-id="fbcfd-130">Hide change account options</span></span>     | <span data-ttu-id="fbcfd-131">표시</span><span class="sxs-lookup"><span data-stu-id="fbcfd-131">Show</span></span>        |
|<span data-ttu-id="fbcfd-132">사용자 계정 유형</span><span class="sxs-lookup"><span data-stu-id="fbcfd-132">User account type</span></span>     |  <span data-ttu-id="fbcfd-133">Standard</span><span class="sxs-lookup"><span data-stu-id="fbcfd-133">Standard</span></span>       |
|<span data-ttu-id="fbcfd-134">화이트 글러브 OOBE 허용</span><span class="sxs-lookup"><span data-stu-id="fbcfd-134">Allow White Glove OOBE</span></span>     |  <span data-ttu-id="fbcfd-135">예</span><span class="sxs-lookup"><span data-stu-id="fbcfd-135">Yes</span></span>       |
|<span data-ttu-id="fbcfd-136">장치 이름 템플릿 적용</span><span class="sxs-lookup"><span data-stu-id="fbcfd-136">Apply device name template</span></span>     | <span data-ttu-id="fbcfd-137">예</span><span class="sxs-lookup"><span data-stu-id="fbcfd-137">Yes</span></span>        |
|<span data-ttu-id="fbcfd-138">이름 입력</span><span class="sxs-lookup"><span data-stu-id="fbcfd-138">Enter a name</span></span>     | <span data-ttu-id="fbcfd-139">MMD-%RAND:11%</span><span class="sxs-lookup"><span data-stu-id="fbcfd-139">MMD-%RAND:11%</span></span>        |

> [!NOTE]
> <span data-ttu-id="fbcfd-140">"흰색 글러브" 프로비저닝은 ESP가 켜져 있는 고객에 한해 사용하도록 설정되어 있는 동안에는 현재 Microsoft Managed Desktop에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fbcfd-140">While "white glove" provisioning is only enabled for customers with ESP turned on, it is not currently supported in Microsoft Managed Desktop.</span></span>

## <a name="enrollment-status-page-settings"></a><span data-ttu-id="fbcfd-141">등록 상태 페이지 설정</span><span class="sxs-lookup"><span data-stu-id="fbcfd-141">Enrollment Status Page settings</span></span>

<span data-ttu-id="fbcfd-142">Microsoft Managed Desktop은 등록 상태 페이지 경험에 대해 다음 설정을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="fbcfd-142">Microsoft Managed Desktop uses these settings for the Enrollment Status Page experience:</span></span>


|<span data-ttu-id="fbcfd-143">설정</span><span class="sxs-lookup"><span data-stu-id="fbcfd-143">Setting</span></span>  |<span data-ttu-id="fbcfd-144">값</span><span class="sxs-lookup"><span data-stu-id="fbcfd-144">Value</span></span>  |
|---------|---------|
|<span data-ttu-id="fbcfd-145">앱 및 프로필 구성 진행률 표시</span><span class="sxs-lookup"><span data-stu-id="fbcfd-145">Show app and profile configuration progress</span></span>     | <span data-ttu-id="fbcfd-146">예</span><span class="sxs-lookup"><span data-stu-id="fbcfd-146">Yes</span></span>        |
|<span data-ttu-id="fbcfd-147">지정된 시간(분)보다 설치 시간이 오래 걸리는 경우 오류 표시</span><span class="sxs-lookup"><span data-stu-id="fbcfd-147">Show an error when installation takes longer than specified number of minutes</span></span>     |  <span data-ttu-id="fbcfd-148">60</span><span class="sxs-lookup"><span data-stu-id="fbcfd-148">60</span></span>       |
|<span data-ttu-id="fbcfd-149">시간 제한 오류가 발생할 때 사용자 지정 메시지 표시</span><span class="sxs-lookup"><span data-stu-id="fbcfd-149">Show custom message when time limit error occurs</span></span>     |  <span data-ttu-id="fbcfd-150">예</span><span class="sxs-lookup"><span data-stu-id="fbcfd-150">Yes</span></span>       |
|<span data-ttu-id="fbcfd-151">오류 메시지</span><span class="sxs-lookup"><span data-stu-id="fbcfd-151">Error message</span></span>     | <span data-ttu-id="fbcfd-152">예. 장치를 예상보다 설정하는 데 시간이 좀 더 오래 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="fbcfd-152">Yes, It's taking a little longer to set up your device than expected.</span></span> <span data-ttu-id="fbcfd-153">시작하려면 아래를 클릭하면 백그라운드에서 설정이 완료됩니다.</span><span class="sxs-lookup"><span data-stu-id="fbcfd-153">Click below to get started and we'll finish setting up in the background</span></span>        |
|<span data-ttu-id="fbcfd-154">사용자가 설치 오류에 대한 로그를 수집하도록 허용</span><span class="sxs-lookup"><span data-stu-id="fbcfd-154">Allow users to collect logs about installation errors</span></span>     |  <span data-ttu-id="fbcfd-155">예</span><span class="sxs-lookup"><span data-stu-id="fbcfd-155">Yes</span></span>       |
|<span data-ttu-id="fbcfd-156">OOBE(Out-of-Box Experience)를 통해 프로비전된 장치에만 페이지 표시</span><span class="sxs-lookup"><span data-stu-id="fbcfd-156">Only show page to devices provisioned by out-of-box experience (OOBE)</span></span>     | <span data-ttu-id="fbcfd-157">예</span><span class="sxs-lookup"><span data-stu-id="fbcfd-157">Yes</span></span>        |
|<span data-ttu-id="fbcfd-158">모든 앱 및 프로필이 설치될 때까지 디바이스 사용 차단</span><span class="sxs-lookup"><span data-stu-id="fbcfd-158">Block device use until all apps and profiles are installed</span></span>     |  <span data-ttu-id="fbcfd-159">예</span><span class="sxs-lookup"><span data-stu-id="fbcfd-159">Yes</span></span>       |
|<span data-ttu-id="fbcfd-160">설치 오류가 발생하는 경우 사용자가 디바이스를 초기화하도록 허용</span><span class="sxs-lookup"><span data-stu-id="fbcfd-160">Allow users to reset device if installation error occurs</span></span>     |  <span data-ttu-id="fbcfd-161">예</span><span class="sxs-lookup"><span data-stu-id="fbcfd-161">Yes</span></span>       |
|<span data-ttu-id="fbcfd-162">설치 오류가 발생하는 경우 사용자가 디바이스를 사용할 수 있도록 허용</span><span class="sxs-lookup"><span data-stu-id="fbcfd-162">Allow users to use device if installation error occurs</span></span>     |  <span data-ttu-id="fbcfd-163">예</span><span class="sxs-lookup"><span data-stu-id="fbcfd-163">Yes</span></span>       |
|<span data-ttu-id="fbcfd-164">사용자/장치에 할당된 필수 앱이 설치될 때까지 장치 사용 차단</span><span class="sxs-lookup"><span data-stu-id="fbcfd-164">Block device use until these required apps are installed if they are assigned to the user/device</span></span>     |  <span data-ttu-id="fbcfd-165">최신 작업 공간 - 시간 수정</span><span class="sxs-lookup"><span data-stu-id="fbcfd-165">Modern Workplace - Time Correction</span></span>       |



<span data-ttu-id="fbcfd-166">등록 상태 페이지 환경은 세 단계로 진행됩니다.</span><span class="sxs-lookup"><span data-stu-id="fbcfd-166">The Enrollment Status Page experience occurs in three phases.</span></span> <span data-ttu-id="fbcfd-167">자세한 내용은 [등록 상태 페이지 추적 정보를 참조하세요.](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status#enrollment-status-page-tracking-information)</span><span class="sxs-lookup"><span data-stu-id="fbcfd-167">For more, see [Enrollment Status Page tracking information](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status#enrollment-status-page-tracking-information).</span></span>

<span data-ttu-id="fbcfd-168">환경은 다음과 같이 진행됩니다.</span><span class="sxs-lookup"><span data-stu-id="fbcfd-168">The experience proceeds as follows:</span></span>

1. <span data-ttu-id="fbcfd-169">Autopilot 환경이 시작되면 사용자가 자격 증명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="fbcfd-169">The Autopilot experience starts and the user enters their credentials.</span></span>
2. <span data-ttu-id="fbcfd-170">장치가 등록 상태 페이지를 열고 장치 준비 및 장치 설정 단계를 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="fbcfd-170">The device opens the Enrollment Status Page and proceeds through Device Preparation and Device Setup phases.</span></span> <span data-ttu-id="fbcfd-171">사용자 ESP가 사용하지  않도록 설정되어 있기 때문에 세 번째 단계(계정 설정)는 현재 Microsoft Managed Desktop 구성에서 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="fbcfd-171">The third step (Account Setup) is *currently skipped* in the Microsoft Managed Desktop configuration because User ESP is disabled.</span></span> <span data-ttu-id="fbcfd-172">장치가 다시 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="fbcfd-172">The device restarts.</span></span>
3. <span data-ttu-id="fbcfd-173">다시 시작하면 장치가 다른 사용자와 함께 Windows 로그인 **페이지를 니다.**</span><span class="sxs-lookup"><span data-stu-id="fbcfd-173">After restart, the device opens the Windows sign-in page with **Other user**.</span></span>
4. <span data-ttu-id="fbcfd-174">사용자가 자격 증명을 다시 입력하면 바탕 화면이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="fbcfd-174">The users enter their credentials again and the desktop opens.</span></span>

> [!NOTE]
> <span data-ttu-id="fbcfd-175">Windows 10 버전이 1903 이상인 경우 Win32 앱은 ESP 중에만 배포됩니다.</span><span class="sxs-lookup"><span data-stu-id="fbcfd-175">Win32 apps are only deployed during ESP if the Windows 10 version is 1903 or later.</span></span>

!["장치 준비" 및 "장치 설정" 단계를 보여주는 Autopilot 설치의 시작 페이지입니다.](../../media/mmd-autopilot-screenshot.png)

## <a name="white-glove-provisioning"></a><span data-ttu-id="fbcfd-177">흰색 글러브 프로비전</span><span class="sxs-lookup"><span data-stu-id="fbcfd-177">White glove provisioning</span></span>

<span data-ttu-id="fbcfd-178">Microsoft Managed Desktop은 현재 Windows Autopilot의 "흰색 글러브" 기능을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fbcfd-178">Microsoft Managed Desktop doesn't currently support the "white glove" feature of Windows Autopilot.</span></span>

## <a name="change-to-autopilot-and-enrollment-status-page-settings"></a><span data-ttu-id="fbcfd-179">Autopilot 및 등록 상태 페이지 설정 변경</span><span class="sxs-lookup"><span data-stu-id="fbcfd-179">Change to Autopilot and Enrollment Status Page settings</span></span>

<span data-ttu-id="fbcfd-180">Microsoft Managed Desktop에서 사용하는 설정이 요구와 정확히 일치하지 않는 경우 관리 포털을 통해 지원 티켓을 [제출할 수 있습니다.](https://portal.azure.com/)</span><span class="sxs-lookup"><span data-stu-id="fbcfd-180">If the setup used by Microsoft Managed Desktop doesn't exactly match your needs, you can  file a support ticket through the [Admin Portal](https://portal.azure.com/).</span></span> <span data-ttu-id="fbcfd-181">다음은 필요할 수 있는 구성 유형의 몇 가지 예입니다.</span><span class="sxs-lookup"><span data-stu-id="fbcfd-181">Here are some examples of the types of configuration you might need:</span></span>

### <a name="autopilot-settings-change"></a><span data-ttu-id="fbcfd-182">Autopilot 설정 변경</span><span class="sxs-lookup"><span data-stu-id="fbcfd-182">Autopilot settings change</span></span>

<span data-ttu-id="fbcfd-183">다른 장치 이름 템플릿을 요청할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbcfd-183">You might want to request a different device name template.</span></span> <span data-ttu-id="fbcfd-184">그러나 배포 모드, Azure AD As에 가입, 개인 정보 설정 또는 사용자 계정 유형을 변경할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fbcfd-184">You cannot, however, change Deployment Mode, Join to Azure AD As, Privacy Settings, or User Account Type.</span></span>

### <a name="enrollment-status-page-settings-change"></a><span data-ttu-id="fbcfd-185">등록 상태 페이지 설정 변경</span><span class="sxs-lookup"><span data-stu-id="fbcfd-185">Enrollment Status Page settings change</span></span>

- <span data-ttu-id="fbcfd-186">"지정한 시간(분)보다 오래 걸리는 경우 오류 표시" 설정의 시간(분)이 길습니다.</span><span class="sxs-lookup"><span data-stu-id="fbcfd-186">A longer number of minutes for the "Show an error when installation takes longer than specified number of minutes" setting.</span></span>
- <span data-ttu-id="fbcfd-187">표시된 오류 메시지</span><span class="sxs-lookup"><span data-stu-id="fbcfd-187">The error message displayed</span></span>
- <span data-ttu-id="fbcfd-188">"사용자/장치에 할당된 필수 앱이 설치될 때까지 장치 사용 차단" 설정에서 응용 프로그램을 추가하거나 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="fbcfd-188">Adding or removing applications in the "Block device use until these required apps are installed if they are assigned to the user/device" setting.</span></span>

## <a name="required-applications"></a><span data-ttu-id="fbcfd-189">필수 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="fbcfd-189">Required applications</span></span>

- <span data-ttu-id="fbcfd-190">최신 작업 공간 장치 그룹 *Test,* First, Fast 및 Broad에서 응용 프로그램을 대상으로 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbcfd-190">You must target applications in the Modern Workplace *device groups* Test, First, Fast, and Broad.</span></span> <span data-ttu-id="fbcfd-191">응용 프로그램은 "시스템" 컨텍스트에서 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbcfd-191">Applications must install in the "System" context.</span></span> <span data-ttu-id="fbcfd-192">모든 그룹에 ESP를 할당하기 전에 테스트 그룹에서 ESP로 테스트를 완료해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbcfd-192">Make sure to complete testing with ESP in the Test group before you assign them to all groups.</span></span>
- <span data-ttu-id="fbcfd-193">어떤 응용 프로그램도 장치를 다시 시작할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fbcfd-193">No applications should require the device to restart.</span></span> <span data-ttu-id="fbcfd-194">응용 프로그램을 다시 시작해야 하는 경우 응용 프로그램 패키지를 빌드할 때 응용 프로그램을 "아무 것도 하지 말 것"으로 설정하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="fbcfd-194">We recommend that applications be set to "Do nothing" when you build the application package if they will require a restart.</span></span>
- <span data-ttu-id="fbcfd-195">필요한 응용 프로그램을 사용자가 장치에 로그인할 때 즉시 필요한 핵심 응용 프로그램으로만 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="fbcfd-195">Limit required applications to only the core applications that a user needs immediately when they sign in to the device.</span></span>
- <span data-ttu-id="fbcfd-196">응용 프로그램 설치 단계의 시간 제한을 방지하기 위해 모든 응용 프로그램의 총 크기를 1GB 미만으로 유지하십시오.</span><span class="sxs-lookup"><span data-stu-id="fbcfd-196">Keep the total size of all applications collectively under 1 GB to avoid timeouts during the application installation phase.</span></span>
- <span data-ttu-id="fbcfd-197">앱에 종속되지 않는 것이 가장 이상적입니다.</span><span class="sxs-lookup"><span data-stu-id="fbcfd-197">Ideally, apps should not have any dependencies.</span></span> <span data-ttu-id="fbcfd-198">종속성 있어야  하는 앱이 있는 경우 ESP 평가의 일부로 앱을 구성, 테스트 및 유효성을 검사해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbcfd-198">If you have apps that *must* have dependencies, be sure you configure, test, and validate them as part of your ESP evaluation.</span></span>
- <span data-ttu-id="fbcfd-199">"사용자" 컨텍스트(예: Teams)가 필요한 응용 프로그램은 ESP의 공개 미리 보기에 포함될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fbcfd-199">No applications that require the "user" context (for example, Teams) can be included in the public preview of ESP.</span></span>
