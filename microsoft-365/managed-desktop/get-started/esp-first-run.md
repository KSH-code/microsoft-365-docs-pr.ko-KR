---
title: Autopilot 및 등록 상태 페이지를 사용 하 여 처음 실행 환경
description: ESP 환경, 사용 된 설정 및 예외를 배포 하는 방법
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 문서
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
audience: ITpro
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 84656e2f0ae9d148c61c27af2a53e157cd44c171
ms.sourcegitcommit: e6283e7c32ba9628fc45e9abc5cd4d21fb3f7ca9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2020
ms.locfileid: "48299242"
---
# <a name="first-run-experience-with-autopilot-and-the-enrollment-status-page"></a><span data-ttu-id="39343-104">Autopilot 및 등록 상태 페이지를 사용 하 여 처음 실행 환경</span><span class="sxs-lookup"><span data-stu-id="39343-104">First-run experience with Autopilot and the Enrollment Status Page</span></span>

<span data-ttu-id="39343-105">Microsoft Managed Desktop은 [Windows Autopilot](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot) 와 Microsoft Intune의 [등록 상태 페이지 (ESP)](https://docs.microsoft.com/windows/deployment/windows-autopilot/enrollment-status) 를 모두 사용 하 여 사용자에 게 최적의 첫 실행 환경을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="39343-105">Microsoft Managed Desktop uses both [Windows Autopilot](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot) and Microsoft Intune's [Enrollment Status Page (ESP)](https://docs.microsoft.com/windows/deployment/windows-autopilot/enrollment-status) to provide the best possible first-run experience to your users.</span></span>

<span data-ttu-id="39343-106">등록 상태 페이지가 현재 공개 미리 보기에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39343-106">The Enrollment Status Page is currently in public preview.</span></span>

## <a name="initial-deployment"></a><span data-ttu-id="39343-107">초기 배포</span><span class="sxs-lookup"><span data-stu-id="39343-107">Initial deployment</span></span>

<span data-ttu-id="39343-108">ESP 환경을 제공 하려면 Microsoft Managed Desktop service에서 장치를 등록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="39343-108">To provide the ESP experience, you must register devices in the Microsoft Managed Desktop service.</span></span> <span data-ttu-id="39343-109">등록에 대 한 자세한 내용은 [직접 새 장치 등록](../get-started/register-devices-self.md) 또는 [파트너가 장치를 등록 하는 단계](../get-started/register-devices-partner.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="39343-109">For more about registration, see [Register new devices yourself](../get-started/register-devices-self.md) or [Steps for Partners to register devices](../get-started/register-devices-partner.md).</span></span>

<span data-ttu-id="39343-110">장치가 서비스에 등록 되 면 [관리 포털](https://portal.azure.com/)을 통해 지원 티켓을 저장 하 여 Microsoft Managed Desktop 장치에 대해 ESP를 사용 하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39343-110">Once your devices are registered with the service, you can enable ESP for your Microsoft Managed Desktop devices by filing a support ticket through the [Admin Portal](https://portal.azure.com/).</span></span> <span data-ttu-id="39343-111">먼저 티켓을 파일 할 때 ESP 구성을 테스트 그룹에 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="39343-111">We will initially deploy the ESP configuration to the Test group when you file the ticket.</span></span> <span data-ttu-id="39343-112">이 파일은 24 시간 마다 처음, 빠르고, 광범위 한 다른 후속 배포 그룹에 배포 됩니다.</span><span class="sxs-lookup"><span data-stu-id="39343-112">It is deployed to the other subsequent deployment groups (First, Fast, and Broad) each 24 hours.</span></span> <span data-ttu-id="39343-113">배포를 일시 중지 하려면 보류할 작업을 요청 하는 다른 티켓을 파일에 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="39343-113">To pause the deployment, file another ticket asking Operations to hold.</span></span>

## <a name="autopilot-profile-settings"></a><span data-ttu-id="39343-114">Autopilot 프로필 설정</span><span class="sxs-lookup"><span data-stu-id="39343-114">Autopilot profile settings</span></span>

<span data-ttu-id="39343-115">Microsoft Managed Desktop은 사용자 장치에 사용 되는 Autopilot 프로필에서 이러한 설정을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="39343-115">Microsoft Managed Desktop uses these settings in the Autopilot profile used for your users' devices:</span></span>


|<span data-ttu-id="39343-116">설정</span><span class="sxs-lookup"><span data-stu-id="39343-116">Setting</span></span>  |<span data-ttu-id="39343-117">값</span><span class="sxs-lookup"><span data-stu-id="39343-117">Value</span></span>  |
|---------|---------|
|<span data-ttu-id="39343-118">배포 모드</span><span class="sxs-lookup"><span data-stu-id="39343-118">Deployment mode</span></span> |  <span data-ttu-id="39343-119">사용자 제어</span><span class="sxs-lookup"><span data-stu-id="39343-119">User Driven</span></span>       |
|<span data-ttu-id="39343-120">Azure AD에 연결</span><span class="sxs-lookup"><span data-stu-id="39343-120">Join to Azure AD as</span></span>     |  <span data-ttu-id="39343-121">Azure AD 가입 됨</span><span class="sxs-lookup"><span data-stu-id="39343-121">Azure AD joined</span></span>       |
|<span data-ttu-id="39343-122">언어 (지역)</span><span class="sxs-lookup"><span data-stu-id="39343-122">Language (Region)</span></span>     | <span data-ttu-id="39343-123">운영 체제 기본값</span><span class="sxs-lookup"><span data-stu-id="39343-123">Operating system default</span></span>        |
|<span data-ttu-id="39343-124">자동으로 키보드 구성</span><span class="sxs-lookup"><span data-stu-id="39343-124">Automatically configure keyboard</span></span>     | <span data-ttu-id="39343-125">아니요</span><span class="sxs-lookup"><span data-stu-id="39343-125">No</span></span>        |
|<span data-ttu-id="39343-126">Microsoft 소프트웨어 사용 조건</span><span class="sxs-lookup"><span data-stu-id="39343-126">Microsoft Software License Terms</span></span>     |  <span data-ttu-id="39343-127">숨겨지고</span><span class="sxs-lookup"><span data-stu-id="39343-127">Hide</span></span>       |
|<span data-ttu-id="39343-128">개인 정보 설정</span><span class="sxs-lookup"><span data-stu-id="39343-128">Privacy settings</span></span>     | <span data-ttu-id="39343-129">숨겨지고</span><span class="sxs-lookup"><span data-stu-id="39343-129">Hide</span></span>        |
|<span data-ttu-id="39343-130">계정 변경 옵션 숨기기</span><span class="sxs-lookup"><span data-stu-id="39343-130">Hide change account options</span></span>     | <span data-ttu-id="39343-131">나타내려면</span><span class="sxs-lookup"><span data-stu-id="39343-131">Show</span></span>        |
|<span data-ttu-id="39343-132">사용자 계정 유형</span><span class="sxs-lookup"><span data-stu-id="39343-132">User account type</span></span>     |  <span data-ttu-id="39343-133">Standard</span><span class="sxs-lookup"><span data-stu-id="39343-133">Standard</span></span>       |
|<span data-ttu-id="39343-134">흰색 Glove OOBE 허용</span><span class="sxs-lookup"><span data-stu-id="39343-134">Allow White Glove OOBE</span></span>     |  <span data-ttu-id="39343-135">예</span><span class="sxs-lookup"><span data-stu-id="39343-135">Yes</span></span>       |
|<span data-ttu-id="39343-136">장치 이름 서식 파일 적용</span><span class="sxs-lookup"><span data-stu-id="39343-136">Apply device name template</span></span>     | <span data-ttu-id="39343-137">예</span><span class="sxs-lookup"><span data-stu-id="39343-137">Yes</span></span>        |
|<span data-ttu-id="39343-138">이름 입력</span><span class="sxs-lookup"><span data-stu-id="39343-138">Enter a name</span></span>     | <span data-ttu-id="39343-139">MMD-% RAND: 11%</span><span class="sxs-lookup"><span data-stu-id="39343-139">MMD-%RAND:11%</span></span>        |

> [!NOTE]
> <span data-ttu-id="39343-140">ESP가 설정 된 고객만 "white glove" rovisioning을 사용 하도록 설정 되어 있지만 현재 Microsoft Managed Desktop에서 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="39343-140">While "white glove" rovisioning is only enabled for customers with ESP turned on, it is not currently supported in Microsoft Managed Desktop.</span></span>

## <a name="enrollment-status-page-settings"></a><span data-ttu-id="39343-141">등록 상태 페이지 설정</span><span class="sxs-lookup"><span data-stu-id="39343-141">Enrollment Status Page settings</span></span>

<span data-ttu-id="39343-142">Microsoft Managed Desktop은 등록 상태 페이지 환경에 이러한 설정을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="39343-142">Microsoft Managed Desktop uses these settings for the Enrollment Status Page experience:</span></span>


|<span data-ttu-id="39343-143">설정</span><span class="sxs-lookup"><span data-stu-id="39343-143">Setting</span></span>  |<span data-ttu-id="39343-144">값</span><span class="sxs-lookup"><span data-stu-id="39343-144">Value</span></span>  |
|---------|---------|
|<span data-ttu-id="39343-145">앱 및 프로필 구성 진행률 표시</span><span class="sxs-lookup"><span data-stu-id="39343-145">Show app and profile configuration progress</span></span>     | <span data-ttu-id="39343-146">예</span><span class="sxs-lookup"><span data-stu-id="39343-146">Yes</span></span>        |
|<span data-ttu-id="39343-147">지정 된 시간 (분) 보다 더 오래 걸릴 경우 오류 표시</span><span class="sxs-lookup"><span data-stu-id="39343-147">Show an error when installation takes longer than specified number of minutes</span></span>     |  <span data-ttu-id="39343-148">60</span><span class="sxs-lookup"><span data-stu-id="39343-148">60</span></span>       |
|<span data-ttu-id="39343-149">시간 제한 오류가 발생할 때 사용자 지정 메시지 표시</span><span class="sxs-lookup"><span data-stu-id="39343-149">Show custom message when time limit error occurs</span></span>     |  <span data-ttu-id="39343-150">예</span><span class="sxs-lookup"><span data-stu-id="39343-150">Yes</span></span>       |
|<span data-ttu-id="39343-151">오류 메시지</span><span class="sxs-lookup"><span data-stu-id="39343-151">Error message</span></span>     | <span data-ttu-id="39343-152">예, 예상 보다 더 짧은 장치를 설정 하는 데 시간이 조금 걸립니다.</span><span class="sxs-lookup"><span data-stu-id="39343-152">Yes, It's taking a little longer to set up your device than expected.</span></span> <span data-ttu-id="39343-153">시작 하려면 아래를 클릭 하 고 백그라운드에서 설정을 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="39343-153">Click below to get started and we'll finish setting up in the background</span></span>        |
|<span data-ttu-id="39343-154">사용자가 설치 오류에 대 한 로그를 수집할 수 있도록 허용</span><span class="sxs-lookup"><span data-stu-id="39343-154">Allow users to collect logs about installation errors</span></span>     |  <span data-ttu-id="39343-155">예</span><span class="sxs-lookup"><span data-stu-id="39343-155">Yes</span></span>       |
|<span data-ttu-id="39343-156">OOBE (기본 제공 경험)로 프로 비전 된 장치에만 페이지를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="39343-156">Only show page to devices provisioned by out-of-box experience (OOBE)</span></span>     | <span data-ttu-id="39343-157">예</span><span class="sxs-lookup"><span data-stu-id="39343-157">Yes</span></span>        |
|<span data-ttu-id="39343-158">모든 앱 및 프로필이 설치 될 때까지 장치 사용 차단</span><span class="sxs-lookup"><span data-stu-id="39343-158">Block device use until all apps and profiles are installed</span></span>     |  <span data-ttu-id="39343-159">예</span><span class="sxs-lookup"><span data-stu-id="39343-159">Yes</span></span>       |
|<span data-ttu-id="39343-160">설치 오류가 발생 하는 경우 사용자가 장치를 다시 설정할 수 있도록 허용</span><span class="sxs-lookup"><span data-stu-id="39343-160">Allow users to reset device if installation error occurs</span></span>     |  <span data-ttu-id="39343-161">예</span><span class="sxs-lookup"><span data-stu-id="39343-161">Yes</span></span>       |
|<span data-ttu-id="39343-162">설치 오류가 발생 하는 경우 사용자가 장치를 사용할 수 있도록 허용</span><span class="sxs-lookup"><span data-stu-id="39343-162">Allow users to use device if installation error occurs</span></span>     |  <span data-ttu-id="39343-163">예</span><span class="sxs-lookup"><span data-stu-id="39343-163">Yes</span></span>       |
|<span data-ttu-id="39343-164">사용자/장치에 할당 된 경우 이러한 필수 앱이 설치 될 때까지 장치 사용을 차단 합니다.</span><span class="sxs-lookup"><span data-stu-id="39343-164">Block device use until these required apps are installed if they are assigned to the user/device</span></span>     |  <span data-ttu-id="39343-165">현대 작업 시간 수정</span><span class="sxs-lookup"><span data-stu-id="39343-165">Modern Workplace - Time Correction</span></span>       |



<span data-ttu-id="39343-166">등록 상태 페이지 환경은 세 단계로 진행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="39343-166">The Enrollment Status Page experience occurs in three phases.</span></span> <span data-ttu-id="39343-167">자세한 내용은 [등록 상태 페이지 추적 정보](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status#enrollment-status-page-tracking-information)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="39343-167">For more, see [Enrollment Status Page tracking information](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status#enrollment-status-page-tracking-information).</span></span>

<span data-ttu-id="39343-168">환경이 다음과 같이 진행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="39343-168">The experience proceeds as follows:</span></span>

1. <span data-ttu-id="39343-169">Autopilot 환경이 시작 되 고 사용자가 자격 증명을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="39343-169">The Autopilot experience starts and the user enters their credentials.</span></span>
2. <span data-ttu-id="39343-170">장치에서 등록 상태 페이지가 열리고 장치 준비 및 장치 설정 단계가 진행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="39343-170">The device opens the Enrollment Status Page and proceeds through Device Preparation and Device Setup phases.</span></span> <span data-ttu-id="39343-171">사용자 ESP가 사용 하지 않도록 설정 되어 있기 때문에 현재 Microsoft 관리 데스크톱 구성에서 세 번째 단계 (계정 설정)가 *생략* 됩니다.</span><span class="sxs-lookup"><span data-stu-id="39343-171">The third step (Account Setup) is *currently skipped* in the Microsoft Managed Desktop configuration because User ESP is disabled.</span></span> <span data-ttu-id="39343-172">장치가 다시 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="39343-172">The device restarts.</span></span>
3. <span data-ttu-id="39343-173">다시 시작 되 면 장치에서 **다른 사용자**와의 Windows 로그인 페이지를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="39343-173">After restart, the device opens the Windows sign-in page with **Other user**.</span></span>
4. <span data-ttu-id="39343-174">사용자가 자격 증명을 다시 입력 하 고 바탕 화면이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="39343-174">The users enter their credentials again and the desktop opens.</span></span>

> [!NOTE]
> <span data-ttu-id="39343-175">Win32 앱은 Windows 10 버전이 1903 이상인 경우 ESP를 실행 하는 동안에만 배포 됩니다.</span><span class="sxs-lookup"><span data-stu-id="39343-175">Win32 apps are only deployed during ESP if the Windows 10 version is 1903 or later.</span></span>

!["장치 준비" 및 "장치 설치" 단계가 표시 되는 Autopilot 설치 프로그램의 시작 페이지입니다.](../../media/mmd-autopilot-screenshot.png)

## <a name="white-glove-provisioning"></a><span data-ttu-id="39343-177">흰색 glove 프로 비전</span><span class="sxs-lookup"><span data-stu-id="39343-177">White glove provisioning</span></span>

<span data-ttu-id="39343-178">Microsoft Managed Desktop은 현재 Windows Autopilot의 "흰색 glove" 기능을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="39343-178">Microsoft Managed Desktop doesn't currently support the "white glove" feature of Windows Autopilot.</span></span>

## <a name="exceptions"></a><span data-ttu-id="39343-179">예외</span><span class="sxs-lookup"><span data-stu-id="39343-179">Exceptions</span></span>

<span data-ttu-id="39343-180">Microsoft Managed Desktop에서 사용 하는 설치가 사용자의 요구에 정확 하 게 일치 하지 않는 경우 예외에 대 한 요청을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39343-180">If the setup used by Microsoft Managed Desktop doesn't exactly match your needs, you can file a request for an exception.</span></span> <span data-ttu-id="39343-181">이 작업을 수행 하려면 Request a [exception](../service-description/customizing.md#request-an-exception)항목을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="39343-181">To do this, see details in [Request an exception](../service-description/customizing.md#request-an-exception).</span></span> <span data-ttu-id="39343-182">다음은 필요한 예외 유형의 몇 가지 예입니다.</span><span class="sxs-lookup"><span data-stu-id="39343-182">Here are some examples of the types of exceptions you might need:</span></span>

### <a name="autopilot-exception"></a><span data-ttu-id="39343-183">Autopilot 예외</span><span class="sxs-lookup"><span data-stu-id="39343-183">Autopilot exception</span></span>

<span data-ttu-id="39343-184">다른 장치 이름 템플릿을 요청 해야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39343-184">You might want to request a different device name template.</span></span> <span data-ttu-id="39343-185">그러나 배포 모드를 변경 하 고 Azure에 Join, 개인 정보 설정 또는 사용자 계정 유형을 변경할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="39343-185">You cannot, however, change Deployment Mode, Join to Azure As, Privacy Settings, or User Account Type.</span></span>

### <a name="enrollment-status-page-exception"></a><span data-ttu-id="39343-186">등록 상태 페이지 예외</span><span class="sxs-lookup"><span data-stu-id="39343-186">Enrollment Status Page exception</span></span>

- <span data-ttu-id="39343-187">"설치가 지정 된 시간 (분) 보다 오래 걸릴 경우 오류 표시" 설정이 더 긴 시간 (분)입니다.</span><span class="sxs-lookup"><span data-stu-id="39343-187">A longer number of minutes for the "Show an error when installation takes longer than specified number of minutes" setting.</span></span>
- <span data-ttu-id="39343-188">표시 되는 오류 메시지</span><span class="sxs-lookup"><span data-stu-id="39343-188">The error message displayed</span></span>
- <span data-ttu-id="39343-189">"사용자/장치에 할당 된 경우 이러한 필수 앱이 설치 될 때까지 장치 사용 차단" 설정에서 응용 프로그램을 추가 또는 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="39343-189">Adding or removing applications in the "Block device use until these required apps are installed if they are assigned to the user/device" setting.</span></span>

## <a name="required-applications"></a><span data-ttu-id="39343-190">필수 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="39343-190">Required applications</span></span>

- <span data-ttu-id="39343-191">최신 작업 공간 *장치 그룹* 테스트, 먼저, 빠른 속도 및 광범위 한 응용 프로그램의 대상을 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="39343-191">You must target applications in the Modern Workplace *device groups* Test, First, Fast, and Broad.</span></span> <span data-ttu-id="39343-192">응용 프로그램은 "시스템" 컨텍스트에서 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="39343-192">Applications must install in the "System" context.</span></span> <span data-ttu-id="39343-193">모든 그룹에 할당 하기 전에 테스트 그룹에서 ESP를 사용 하 여 테스트를 완료 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="39343-193">Make sure to complete testing with ESP in the Test group before you assign them to all groups.</span></span>
- <span data-ttu-id="39343-194">응용 프로그램에서 장치를 다시 시작 해야 하는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="39343-194">No applications should require the device to restart.</span></span> <span data-ttu-id="39343-195">다시 시작 해야 하는 경우 응용 프로그램 패키지를 작성할 때 응용 프로그램을 "아무 작업도 하지 않음"으로 설정 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="39343-195">We recommend that applications be set to "Do nothing" when you build the application package if they will require a restart.</span></span>
- <span data-ttu-id="39343-196">필수 응용 프로그램을 사용자가 장치에 로그인 할 때 즉시 필요한 핵심 응용 프로그램 으로만 제한 합니다.</span><span class="sxs-lookup"><span data-stu-id="39343-196">Limit required applications to only the core applications that a user needs immediately when they sign in to the device.</span></span>
- <span data-ttu-id="39343-197">응용 프로그램 설치 단계가 진행 되는 동안 시간 제한을 방지 하려면 모든 응용 프로그램의 전체 크기를 집합적으로 1gb 미만으로 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="39343-197">Keep the total size of all applications collectively under 1 GB to avoid timeouts during the application installation phase.</span></span>
- <span data-ttu-id="39343-198">이상적으로는 앱에 종속성이 없어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="39343-198">Ideally, apps should not have any dependencies.</span></span> <span data-ttu-id="39343-199">종속성 *이 필요한 앱* 이 있는 경우 ESP 평가의 일부로 구성, 테스트 및 유효성 검사를 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="39343-199">If you have apps that *must* have dependencies, be sure you configure, test, and validate them as part of your ESP evaluation.</span></span>
- <span data-ttu-id="39343-200">"사용자" 컨텍스트 (예: 팀)가 필요한 응용 프로그램은 ESP 공개 미리 보기에 포함 될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="39343-200">No applications that require the "user" context (for example, Teams) can be included in the public preview of ESP.</span></span>
