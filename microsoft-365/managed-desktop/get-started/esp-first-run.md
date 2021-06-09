---
title: Autopilot 및 등록 상태 페이지의 첫 실행 환경
description: ESP 환경, 사용되는 설정 및 구성 변경 내용을 배포하는 방법
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 문서
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
audience: ITpro
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: b65ad2a6ac1a9b9abe06cc108a980be21152bc86
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844961"
---
# <a name="first-run-experience-with-autopilot-and-the-enrollment-status-page"></a><span data-ttu-id="cf5e9-104">Autopilot 및 등록 상태 페이지의 첫 실행 환경</span><span class="sxs-lookup"><span data-stu-id="cf5e9-104">First-run experience with Autopilot and the Enrollment Status Page</span></span>

<span data-ttu-id="cf5e9-105">Microsoft Managed Desktop [Windows Autopilot과](/windows/deployment/windows-autopilot/windows-autopilot) Microsoft Intune [ESP(등록](/windows/deployment/windows-autopilot/enrollment-status) 상태 페이지)를 모두 사용하여 사용자에게 최상의 첫 실행 환경을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="cf5e9-105">Microsoft Managed Desktop uses both [Windows Autopilot](/windows/deployment/windows-autopilot/windows-autopilot) and Microsoft Intune's [Enrollment Status Page (ESP)](/windows/deployment/windows-autopilot/enrollment-status) to provide the best possible first-run experience to your users.</span></span>

<span data-ttu-id="cf5e9-106">등록 상태 페이지가 현재 공개 미리 보기에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf5e9-106">The Enrollment Status Page is currently in public preview.</span></span>

## <a name="initial-deployment"></a><span data-ttu-id="cf5e9-107">초기 배포</span><span class="sxs-lookup"><span data-stu-id="cf5e9-107">Initial deployment</span></span>

<span data-ttu-id="cf5e9-108">ESP 환경을 제공하려면 서비스에서 장치를 Microsoft Managed Desktop 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf5e9-108">To provide the ESP experience, you must register devices in the Microsoft Managed Desktop service.</span></span> <span data-ttu-id="cf5e9-109">등록에 대한 자세한 [](../get-started/register-devices-self.md) 내용은 직접 새 장치 등록 또는 장치를 등록하는 파트너 단계를 [참조하세요.](../get-started/register-devices-partner.md)</span><span class="sxs-lookup"><span data-stu-id="cf5e9-109">For more about registration, see [Register new devices yourself](../get-started/register-devices-self.md) or [Steps for Partners to register devices](../get-started/register-devices-partner.md).</span></span>

<span data-ttu-id="cf5e9-110">장치가 서비스에 등록된 후 관리 포털을 통해 지원 티켓을 Microsoft Managed Desktop 디바이스에 대해 ESP를 사용하도록 설정할 [수 있습니다.](https://portal.azure.com/)</span><span class="sxs-lookup"><span data-stu-id="cf5e9-110">Once your devices are registered with the service, you can enable ESP for your Microsoft Managed Desktop devices by filing a support ticket through the [Admin Portal](https://portal.azure.com/).</span></span> <span data-ttu-id="cf5e9-111">티켓을 제출할 때 처음에 테스트 그룹에 ESP 구성을 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="cf5e9-111">We will initially deploy the ESP configuration to the Test group when you file the ticket.</span></span> <span data-ttu-id="cf5e9-112">24시간마다 다른 후속 배포 그룹(첫 번째, 빠르기 및 광범위)에 배포됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf5e9-112">It is deployed to the other subsequent deployment groups (First, Fast, and Broad) each 24 hours.</span></span> <span data-ttu-id="cf5e9-113">배포를 일시 중지하기 위해 Operations에 보류를 요청하는 다른 티켓을 제출합니다.</span><span class="sxs-lookup"><span data-stu-id="cf5e9-113">To pause the deployment, file another ticket asking Operations to hold.</span></span>

## <a name="autopilot-profile-settings"></a><span data-ttu-id="cf5e9-114">Autopilot 프로필 설정</span><span class="sxs-lookup"><span data-stu-id="cf5e9-114">Autopilot profile settings</span></span>

<span data-ttu-id="cf5e9-115">Microsoft Managed Desktop 사용자 장치에 사용되는 Autopilot 프로필에서 다음 설정을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="cf5e9-115">Microsoft Managed Desktop uses these settings in the Autopilot profile used for your users' devices:</span></span>

<br>

****

|<span data-ttu-id="cf5e9-116">설정</span><span class="sxs-lookup"><span data-stu-id="cf5e9-116">Setting</span></span>|<span data-ttu-id="cf5e9-117">값</span><span class="sxs-lookup"><span data-stu-id="cf5e9-117">Value</span></span>|
|---|---|
|<span data-ttu-id="cf5e9-118">배포 모드</span><span class="sxs-lookup"><span data-stu-id="cf5e9-118">Deployment mode</span></span>|<span data-ttu-id="cf5e9-119">사용자 기반</span><span class="sxs-lookup"><span data-stu-id="cf5e9-119">User Driven</span></span>|
|<span data-ttu-id="cf5e9-120">Azure AD에 다음으로 가입</span><span class="sxs-lookup"><span data-stu-id="cf5e9-120">Join to Azure AD as</span></span>|<span data-ttu-id="cf5e9-121">Azure AD 가입</span><span class="sxs-lookup"><span data-stu-id="cf5e9-121">Azure AD joined</span></span>|
|<span data-ttu-id="cf5e9-122">언어(지역)</span><span class="sxs-lookup"><span data-stu-id="cf5e9-122">Language (Region)</span></span>|<span data-ttu-id="cf5e9-123">사용자 선택</span><span class="sxs-lookup"><span data-stu-id="cf5e9-123">User Select</span></span>|
|<span data-ttu-id="cf5e9-124">키보드 자동 구성</span><span class="sxs-lookup"><span data-stu-id="cf5e9-124">Automatically configure keyboard</span></span>|<span data-ttu-id="cf5e9-125">아니요.</span><span class="sxs-lookup"><span data-stu-id="cf5e9-125">No</span></span>|
|<span data-ttu-id="cf5e9-126">Microsoft 소프트웨어 사용 조건</span><span class="sxs-lookup"><span data-stu-id="cf5e9-126">Microsoft Software License Terms</span></span>|<span data-ttu-id="cf5e9-127">숨기기</span><span class="sxs-lookup"><span data-stu-id="cf5e9-127">Hide</span></span>|
|<span data-ttu-id="cf5e9-128">개인 정보 설정</span><span class="sxs-lookup"><span data-stu-id="cf5e9-128">Privacy settings</span></span>|<span data-ttu-id="cf5e9-129">숨기기</span><span class="sxs-lookup"><span data-stu-id="cf5e9-129">Hide</span></span>|
|<span data-ttu-id="cf5e9-130">계정 변경 옵션 숨기기</span><span class="sxs-lookup"><span data-stu-id="cf5e9-130">Hide change account options</span></span>|<span data-ttu-id="cf5e9-131">표시</span><span class="sxs-lookup"><span data-stu-id="cf5e9-131">Show</span></span>|
|<span data-ttu-id="cf5e9-132">사용자 계정 유형</span><span class="sxs-lookup"><span data-stu-id="cf5e9-132">User account type</span></span>|<span data-ttu-id="cf5e9-133">Standard</span><span class="sxs-lookup"><span data-stu-id="cf5e9-133">Standard</span></span>|
|<span data-ttu-id="cf5e9-134">흰색 글러브 OOBE 허용</span><span class="sxs-lookup"><span data-stu-id="cf5e9-134">Allow White Glove OOBE</span></span>|<span data-ttu-id="cf5e9-135">네.</span><span class="sxs-lookup"><span data-stu-id="cf5e9-135">Yes</span></span>|
|<span data-ttu-id="cf5e9-136">장치 이름 템플릿 적용</span><span class="sxs-lookup"><span data-stu-id="cf5e9-136">Apply device name template</span></span>|<span data-ttu-id="cf5e9-137">네.</span><span class="sxs-lookup"><span data-stu-id="cf5e9-137">Yes</span></span>|
|<span data-ttu-id="cf5e9-138">이름 입력</span><span class="sxs-lookup"><span data-stu-id="cf5e9-138">Enter a name</span></span>|<span data-ttu-id="cf5e9-139">MMD-%RAND:11%</span><span class="sxs-lookup"><span data-stu-id="cf5e9-139">MMD-%RAND:11%</span></span>|
|

## <a name="enrollment-status-page-settings"></a><span data-ttu-id="cf5e9-140">등록 상태 페이지 설정</span><span class="sxs-lookup"><span data-stu-id="cf5e9-140">Enrollment Status Page settings</span></span>

<span data-ttu-id="cf5e9-141">Microsoft Managed Desktop 상태 페이지 환경의 경우 다음 설정을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="cf5e9-141">Microsoft Managed Desktop uses these settings for the Enrollment Status Page experience:</span></span>

<br>

****

|<span data-ttu-id="cf5e9-142">설정</span><span class="sxs-lookup"><span data-stu-id="cf5e9-142">Setting</span></span>|<span data-ttu-id="cf5e9-143">값</span><span class="sxs-lookup"><span data-stu-id="cf5e9-143">Value</span></span>|
|---|---|
|<span data-ttu-id="cf5e9-144">앱 및 프로필 구성 진행률 표시</span><span class="sxs-lookup"><span data-stu-id="cf5e9-144">Show app and profile configuration progress</span></span>|<span data-ttu-id="cf5e9-145">네.</span><span class="sxs-lookup"><span data-stu-id="cf5e9-145">Yes</span></span>|
|<span data-ttu-id="cf5e9-146">지정한 시간(분)보다 설치 시간이 오래 걸리는 경우 오류 표시</span><span class="sxs-lookup"><span data-stu-id="cf5e9-146">Show an error when installation takes longer than specified number of minutes</span></span>|<span data-ttu-id="cf5e9-147">60</span><span class="sxs-lookup"><span data-stu-id="cf5e9-147">60</span></span>|
|<span data-ttu-id="cf5e9-148">시간 제한 오류가 발생할 때 사용자 지정 메시지 표시</span><span class="sxs-lookup"><span data-stu-id="cf5e9-148">Show custom message when time limit error occurs</span></span>|<span data-ttu-id="cf5e9-149">네.</span><span class="sxs-lookup"><span data-stu-id="cf5e9-149">Yes</span></span>|
|<span data-ttu-id="cf5e9-150">오류 메시지</span><span class="sxs-lookup"><span data-stu-id="cf5e9-150">Error message</span></span>|<span data-ttu-id="cf5e9-151">예. 장치를 예상보다 설정하는 데 시간이 좀 더 오래 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="cf5e9-151">Yes, It's taking a little longer to set up your device than expected.</span></span> <span data-ttu-id="cf5e9-152">시작하려면 아래를 클릭하면 백그라운드에서 설정이 완료됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf5e9-152">Click below to get started and we'll finish setting up in the background</span></span>|
|<span data-ttu-id="cf5e9-153">사용자가 설치 오류에 대한 로그를 수집하도록 허용</span><span class="sxs-lookup"><span data-stu-id="cf5e9-153">Allow users to collect logs about installation errors</span></span>|<span data-ttu-id="cf5e9-154">네.</span><span class="sxs-lookup"><span data-stu-id="cf5e9-154">Yes</span></span>|
|<span data-ttu-id="cf5e9-155">OOBE(Out-of-Box Experience)에서 프로비전한 장치에만 페이지 표시</span><span class="sxs-lookup"><span data-stu-id="cf5e9-155">Only show page to devices provisioned by out-of-box experience (OOBE)</span></span>|<span data-ttu-id="cf5e9-156">네.</span><span class="sxs-lookup"><span data-stu-id="cf5e9-156">Yes</span></span>|
|<span data-ttu-id="cf5e9-157">모든 앱 및 프로필이 설치될 때까지 장치 사용 차단</span><span class="sxs-lookup"><span data-stu-id="cf5e9-157">Block device use until all apps and profiles are installed</span></span>|<span data-ttu-id="cf5e9-158">네.</span><span class="sxs-lookup"><span data-stu-id="cf5e9-158">Yes</span></span>|
|<span data-ttu-id="cf5e9-159">설치 오류가 발생하는 경우 사용자가 디바이스를 초기화할 수 있도록 허용</span><span class="sxs-lookup"><span data-stu-id="cf5e9-159">Allow users to reset device if installation error occurs</span></span>|<span data-ttu-id="cf5e9-160">네.</span><span class="sxs-lookup"><span data-stu-id="cf5e9-160">Yes</span></span>|
|<span data-ttu-id="cf5e9-161">설치 오류가 발생하는 경우 사용자가 디바이스를 사용할 수 있도록 허용</span><span class="sxs-lookup"><span data-stu-id="cf5e9-161">Allow users to use device if installation error occurs</span></span>|<span data-ttu-id="cf5e9-162">네.</span><span class="sxs-lookup"><span data-stu-id="cf5e9-162">Yes</span></span>|
|<span data-ttu-id="cf5e9-163">사용자/장치에 할당된 필수 앱이 설치될 때까지 장치 사용 차단</span><span class="sxs-lookup"><span data-stu-id="cf5e9-163">Block device use until these required apps are installed if they are assigned to the user/device</span></span>|<span data-ttu-id="cf5e9-164">최신 작업 공간 - 시간 수정</span><span class="sxs-lookup"><span data-stu-id="cf5e9-164">Modern Workplace - Time Correction</span></span>|
|

<span data-ttu-id="cf5e9-165">등록 상태 페이지 환경은 세 단계로 진행됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf5e9-165">The Enrollment Status Page experience occurs in three phases.</span></span> <span data-ttu-id="cf5e9-166">자세한 내용은 등록 상태 [페이지 추적 정보를 참조하세요.](/mem/intune/enrollment/windows-enrollment-status#enrollment-status-page-tracking-information)</span><span class="sxs-lookup"><span data-stu-id="cf5e9-166">For more, see [Enrollment Status Page tracking information](/mem/intune/enrollment/windows-enrollment-status#enrollment-status-page-tracking-information).</span></span>

<span data-ttu-id="cf5e9-167">환경은 다음과 같이 진행됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf5e9-167">The experience proceeds as follows:</span></span>

1. <span data-ttu-id="cf5e9-168">Autopilot 환경이 시작되면 사용자가 자격 증명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="cf5e9-168">The Autopilot experience starts and the user enters their credentials.</span></span>
2. <span data-ttu-id="cf5e9-169">장치가 등록 상태 페이지를 열고 장치 준비 및 장치 설정 단계를 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="cf5e9-169">The device opens the Enrollment Status Page and proceeds through Device Preparation and Device Setup phases.</span></span> <span data-ttu-id="cf5e9-170">사용자 ESP가 사용하지  않도록 설정되어 있기 때문에 Microsoft Managed Desktop 구성에서 세 번째 단계(계정 설정)를 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="cf5e9-170">The third step (Account Setup) is *currently skipped* in the Microsoft Managed Desktop configuration because User ESP is disabled.</span></span> <span data-ttu-id="cf5e9-171">장치가 다시 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf5e9-171">The device restarts.</span></span>
3. <span data-ttu-id="cf5e9-172">다시 시작하면 장치가 다른 사용자와 Windows 로그인 페이지를 **니다.**</span><span class="sxs-lookup"><span data-stu-id="cf5e9-172">After restart, the device opens the Windows sign-in page with **Other user**.</span></span>
4. <span data-ttu-id="cf5e9-173">사용자가 자격 증명을 다시 입력하면 바탕 화면이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="cf5e9-173">The users enter their credentials again and the desktop opens.</span></span>

> [!NOTE]
> <span data-ttu-id="cf5e9-174">Win32 앱은 ESP 중에만 배포됩니다Windows 10 버전이 1903 이상인 경우.</span><span class="sxs-lookup"><span data-stu-id="cf5e9-174">Win32 apps are only deployed during ESP if the Windows 10 version is 1903 or later.</span></span>

!["장치 준비" 및 "장치 설정" 단계를 보여준 Autopilot 설치의 시작 페이지입니다.](../../media/mmd-autopilot-screenshot.png)

## <a name="autopilot-for-pre-provisioned-deployment"></a><span data-ttu-id="cf5e9-176">사전 프로비전된 배포용 Autopilot</span><span class="sxs-lookup"><span data-stu-id="cf5e9-176">Autopilot for pre-provisioned deployment</span></span>

> [!NOTE]
> <span data-ttu-id="cf5e9-177">현재 공개 미리 보기에서 Microsoft Managed Desktop 배포용 Autopilot</span><span class="sxs-lookup"><span data-stu-id="cf5e9-177">Autopilot for pre-provisioned deployment in Microsoft Managed Desktop is currently in public preview.</span></span>

## <a name="additional-prerequisites-for-autopilot-for-pre-provisioned-deployment"></a><span data-ttu-id="cf5e9-178">사전 프로비전된 배포를 위한 Autopilot의 추가 선행 구성</span><span class="sxs-lookup"><span data-stu-id="cf5e9-178">Additional prerequisites for Autopilot for pre-provisioned deployment</span></span>

- <span data-ttu-id="cf5e9-179">ESP(등록 상태 페이지)를 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf5e9-179">You must have Enrollment Status Page (ESP) enabled.</span></span> <span data-ttu-id="cf5e9-180">자세한 내용은 초기 [배포를 참조하세요.](#initial-deployment)</span><span class="sxs-lookup"><span data-stu-id="cf5e9-180">For more information, see [Initial deployment](#initial-deployment).</span></span>
- <span data-ttu-id="cf5e9-181">장치에 유선 네트워크 연결이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf5e9-181">Device must have a wired network connection.</span></span>
- <span data-ttu-id="cf5e9-182">2020년 8월 전에 Microsoft Managed Desktop 포털을 사용하여 등록한 장치가 있는 경우 등록을 다시 해지하고 다시 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="cf5e9-182">If you have devices that were registered using the Microsoft Managed Desktop portal before August 2020, de-register and register them again.</span></span>
- <span data-ttu-id="cf5e9-183">장치에는 적절한 설치로 2020년 11월 누적 업데이트 [19H1/19H2 2020.11C](https://support.microsoft.com/topic/november-19-2020-kb4586819-os-builds-18362-1237-and-18363-1237-preview-25cbb849-74af-b8b8-29b8-68aa925e8cc3) 또는 [20H1 2020.11C가](https://support.microsoft.com/topic/november-30-2020-kb4586853-os-builds-19041-662-and-19042-662-preview-8fb07fb8-a7dd-ea62-d65e-3305da09f92e) 포함된 출하 시 이미지가 있어야 합니다. 또는 최신 Microsoft Managed Desktop 이미지로 이미지를 다시 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf5e9-183">Devices must must have a factory image that includes the November 2020 cumulative update [19H1/19H2 2020.11C](https://support.microsoft.com/topic/november-19-2020-kb4586819-os-builds-18362-1237-and-18363-1237-preview-25cbb849-74af-b8b8-29b8-68aa925e8cc3) or [20H1 2020.11C](https://support.microsoft.com/topic/november-30-2020-kb4586853-os-builds-19041-662-and-19042-662-preview-8fb07fb8-a7dd-ea62-d65e-3305da09f92e) as appropriate installed or must be reimaged with the latest Microsoft Managed Desktop image.</span></span>
- <span data-ttu-id="cf5e9-184">실제 장치는 TPM 2.0 및 장치 attestation을 지원해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf5e9-184">Physical devices must support TPM 2.0 and device attestation.</span></span> <span data-ttu-id="cf5e9-185">가상 컴퓨터는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cf5e9-185">Virtual machines aren't supported.</span></span> <span data-ttu-id="cf5e9-186">사전 프로비전 프로세스에서는 Autopilot 자체 Windows 기능을 사용하게 있으므로 TPM 2.0이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="cf5e9-186">The pre-provisioning process uses Windows Autopilot self-deploying capabilities, so TPM 2.0 is required.</span></span> <span data-ttu-id="cf5e9-187">또한 TPM 확인 프로세스를 수행하려면 각 TPM 공급자에 고유한 HTTPS URL 집합에 액세스해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf5e9-187">The TPM attestation process also requires access to a set of HTTPS URLs that are unique for each TPM provider.</span></span> <span data-ttu-id="cf5e9-188">자세한 내용은 Autopilot 자체 배포 모드 및 Autopilot의 사전 프로비전된 배포에 대한 항목을 Windows [참조하세요.](/mem/autopilot/networking-requirements#tpm)</span><span class="sxs-lookup"><span data-stu-id="cf5e9-188">For more information, see the entry for Autopilot self-deploying mode and Autopilot pre-provisioned deployment in [Windows Autopilot networking requirements](/mem/autopilot/networking-requirements#tpm).</span></span>

## <a name="sequence-of-events-in-autopilot-for-pre-provisioned-deployment"></a><span data-ttu-id="cf5e9-189">사전 프로비전된 배포를 위한 Autopilot의 이벤트 시퀀스</span><span class="sxs-lookup"><span data-stu-id="cf5e9-189">Sequence of events in Autopilot for pre-provisioned deployment</span></span>

1. <span data-ttu-id="cf5e9-190">IT 관리자는 필요한 경우 장치를 다시 설치하거나 다시 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="cf5e9-190">IT Admin reimages or resets the device if needed.</span></span>
2. <span data-ttu-id="cf5e9-191">IT 관리자는 장치를 부팅하고, 첫 경험에 도달하고, Windows 키를 니다.</span><span class="sxs-lookup"><span data-stu-id="cf5e9-191">IT Admin boots the device, reaches the out-of-box-experience, and presses the Windows key five times.</span></span>
3. <span data-ttu-id="cf5e9-192">IT 관리자는 Autopilot Windows 선택한 다음 계속을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="cf5e9-192">IT Admin selects Windows Autopilot Provisioning and then selects **Continue**.</span></span> <span data-ttu-id="cf5e9-193">Autopilot Windows 화면에 장치에 대한 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf5e9-193">On the Windows Autopilot configuration screen, information will be displayed about the device.</span></span>
4. <span data-ttu-id="cf5e9-194">IT 관리자가 **프로비전을 선택하여** 프로비저닝 프로세스를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="cf5e9-194">IT admin selects **Provision** to start the provisioning process.</span></span>
5. <span data-ttu-id="cf5e9-195">디바이스가 ESP를 시작하고 장치 준비 및 설정 단계를 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="cf5e9-195">Device starts ESP and goes through device preparation and setup phases.</span></span> <span data-ttu-id="cf5e9-196">장치 설정 단계에서는 ESP 프로필의 정확한 구성에 따라 x의 앱 설치 **x가** 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf5e9-196">During the device setup phase, you'll see **App installation x of x** displayed (depending on the exact configuration of the ESP profile).</span></span>
6. <span data-ttu-id="cf5e9-197">사용자 ESP를 사용하지 않도록 설정하기 때문에 현재 Microsoft Managed Desktop 구성에서 계정 설정 단계를 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="cf5e9-197">The account setup step is currently skipped in the Microsoft Managed Desktop configuration, since we disable User ESP.</span></span>
7. <span data-ttu-id="cf5e9-198">장치가 다시 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf5e9-198">The device restarts.</span></span>

<span data-ttu-id="cf5e9-199">다시 시작하면 디바이스에 다시 연결 단추와 함께 녹색 상태 **화면이** 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf5e9-199">After it restarts, the device will show the green status screen, with a **Reseal** button.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cf5e9-200">알려진 문제:</span><span class="sxs-lookup"><span data-stu-id="cf5e9-200">Known issues:</span></span>
>
> - <span data-ttu-id="cf5e9-201">미리 프로비전된 배포 재시도 기능에 대한 Autopilot이 실행된 후에도 ESP가 다시 실행되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cf5e9-201">ESP does not run again after the Autopilot for pre-provisioned deployment reseal function.</span></span>
> - <span data-ttu-id="cf5e9-202">사전 프로비전된 배포를 위해 Autopilot에서 디바이스의 이름을 바치지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cf5e9-202">Device are not being renamed by Autopilot for pre-provisioned deployment.</span></span> <span data-ttu-id="cf5e9-203">ESP 사용자 흐름을 거치고 나면 디바이스의 이름만 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf5e9-203">The device will only be renamed after going through the ESP user flow.</span></span>

## <a name="change-to-autopilot-and-enrollment-status-page-settings"></a><span data-ttu-id="cf5e9-204">Autopilot 및 등록 상태 페이지 설정으로 변경</span><span class="sxs-lookup"><span data-stu-id="cf5e9-204">Change to Autopilot and Enrollment Status Page settings</span></span>

<span data-ttu-id="cf5e9-205">사용자가 사용하는 설정이 Microsoft Managed Desktop 정확히 일치하지 않는 경우 관리 포털을 통해 지원 티켓을 [제출할 수 있습니다.](https://portal.azure.com/)</span><span class="sxs-lookup"><span data-stu-id="cf5e9-205">If the setup used by Microsoft Managed Desktop doesn't exactly match your needs, you can  file a support ticket through the [Admin Portal](https://portal.azure.com/).</span></span> <span data-ttu-id="cf5e9-206">다음은 필요할 수 있는 구성 유형의 몇 가지 예입니다.</span><span class="sxs-lookup"><span data-stu-id="cf5e9-206">Here are some examples of the types of configuration you might need:</span></span>

### <a name="autopilot-settings-change"></a><span data-ttu-id="cf5e9-207">Autopilot 설정 변경</span><span class="sxs-lookup"><span data-stu-id="cf5e9-207">Autopilot settings change</span></span>

<span data-ttu-id="cf5e9-208">다른 장치 이름 템플릿을 요청할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf5e9-208">You might want to request a different device name template.</span></span> <span data-ttu-id="cf5e9-209">그러나 배포 모드, Azure AD As에 가입, 개인 정보 보호 또는 사용자 계정 설정 변경할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cf5e9-209">You cannot, however, change Deployment Mode, Join to Azure AD As, Privacy Settings, or User Account Type.</span></span>

### <a name="enrollment-status-page-settings-change"></a><span data-ttu-id="cf5e9-210">등록 상태 페이지 설정 변경</span><span class="sxs-lookup"><span data-stu-id="cf5e9-210">Enrollment Status Page settings change</span></span>

- <span data-ttu-id="cf5e9-211">"설치에 지정된 시간(분) 보다 오래 걸리는 경우 오류 표시" 설정의 시간(분)이 길습니다.</span><span class="sxs-lookup"><span data-stu-id="cf5e9-211">A longer number of minutes for the "Show an error when installation takes longer than specified number of minutes" setting.</span></span>
- <span data-ttu-id="cf5e9-212">표시된 오류 메시지</span><span class="sxs-lookup"><span data-stu-id="cf5e9-212">The error message displayed</span></span>
- <span data-ttu-id="cf5e9-213">"사용자/디바이스에 할당된 경우 이러한 필수 앱이 설치될 때까지 장치 사용 차단" 설정에서 응용 프로그램을 추가하거나 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="cf5e9-213">Adding or removing applications in the "Block device use until these required apps are installed if they are assigned to the user/device" setting.</span></span>

## <a name="required-applications"></a><span data-ttu-id="cf5e9-214">필수 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="cf5e9-214">Required applications</span></span>

- <span data-ttu-id="cf5e9-215">최신 작업 공간 장치 그룹 *Test,* First, Fast 및 Broad에서 응용 프로그램을 대상으로 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf5e9-215">You must target applications in the Modern Workplace *device groups* Test, First, Fast, and Broad.</span></span> <span data-ttu-id="cf5e9-216">응용 프로그램은 "시스템" 컨텍스트에서 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf5e9-216">Applications must install in the "System" context.</span></span> <span data-ttu-id="cf5e9-217">모든 그룹에 할당하기 전에 테스트 그룹에서 ESP로 테스트를 완료해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf5e9-217">Make sure to complete testing with ESP in the Test group before you assign them to all groups.</span></span>
- <span data-ttu-id="cf5e9-218">어떤 응용 프로그램도 장치를 다시 시작해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf5e9-218">No applications should require the device to restart.</span></span> <span data-ttu-id="cf5e9-219">응용 프로그램을 다시 시작해야 하는 경우 응용 프로그램 패키지를 빌드할 때 응용 프로그램을 "아무 것도 하지 말 것"으로 설정하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="cf5e9-219">We recommend that applications be set to "Do nothing" when you build the application package if they will require a restart.</span></span>
- <span data-ttu-id="cf5e9-220">필요한 응용 프로그램을 사용자가 장치에 로그인할 때 즉시 필요한 핵심 응용 프로그램으로만 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="cf5e9-220">Limit required applications to only the core applications that a user needs immediately when they sign in to the device.</span></span>
- <span data-ttu-id="cf5e9-221">응용 프로그램 설치 단계의 시간 제한을 방지하기 위해 모든 응용 프로그램의 총 크기를 1GB 미만으로 유지하십시오.</span><span class="sxs-lookup"><span data-stu-id="cf5e9-221">Keep the total size of all applications collectively under 1 GB to avoid timeouts during the application installation phase.</span></span>
- <span data-ttu-id="cf5e9-222">앱에 종속성은 없는 것이 가장 이상적입니다.</span><span class="sxs-lookup"><span data-stu-id="cf5e9-222">Ideally, apps should not have any dependencies.</span></span> <span data-ttu-id="cf5e9-223">종속성 있는  앱이 있는 경우 ESP 평가의 일부로 앱을 구성, 테스트 및 유효성 검사해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf5e9-223">If you have apps that *must* have dependencies, be sure you configure, test, and validate them as part of your ESP evaluation.</span></span>
- <span data-ttu-id="cf5e9-224">"사용자" 컨텍스트가 필요한 응용 프로그램(예: Teams)은 ESP의 공개 미리 보기에 포함될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cf5e9-224">No applications that require the "user" context (for example, Teams) can be included in the public preview of ESP.</span></span>
