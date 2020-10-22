---
title: 준비 상태 평가 도구에서 발견 된 문제 해결
description: 도구에서 발견 되는 각 문제에 대해 수행할 세부 작업
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 문서
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 2c9638dc7b8c6d095b87cf81114f3812c8362597
ms.sourcegitcommit: 3b1bd8aa1430bc9565743a446bbc27b199f30f73
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2020
ms.locfileid: "48656154"
---
# <a name="fix-issues-found-by-the-readiness-assessment-tool"></a><span data-ttu-id="96fed-104">준비 상태 평가 도구에서 발견 된 문제 해결</span><span class="sxs-lookup"><span data-stu-id="96fed-104">Fix issues found by the readiness assessment tool</span></span>

<span data-ttu-id="96fed-105">각 검사에 대해이 도구는 다음과 같은 세 가지 가능한 결과 중 하나를 보고 합니다.</span><span class="sxs-lookup"><span data-stu-id="96fed-105">For each check, the tool will report one of three possible results:</span></span>


|<span data-ttu-id="96fed-106">결과</span><span class="sxs-lookup"><span data-stu-id="96fed-106">Result</span></span>  |<span data-ttu-id="96fed-107">의미</span><span class="sxs-lookup"><span data-stu-id="96fed-107">Meaning</span></span>  |
|---------|---------|
|<span data-ttu-id="96fed-108">맞춤형</span><span class="sxs-lookup"><span data-stu-id="96fed-108">Ready</span></span>     | <span data-ttu-id="96fed-109">등록을 완료 하기 전에 작업을 수행할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="96fed-109">No action is required before completing enrollment.</span></span>        |
|<span data-ttu-id="96fed-110">조언</span><span class="sxs-lookup"><span data-stu-id="96fed-110">Advisory</span></span>    | <span data-ttu-id="96fed-111">등록 및 사용자를 위한 최상의 환경을 위해서는이 도구 또는이 문서에 나와 있는 단계를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="96fed-111">Follow the steps in the tool or this article for the best experience with enrollment and for users.</span></span> <span data-ttu-id="96fed-112">등록을 완료할 *수* 있지만 첫 번째 장치를 배포 하기 전에 이러한 문제를 해결 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="96fed-112">You *can* complete enrollment, but you must fix these issues before you deploy your first device.</span></span>        |
|<span data-ttu-id="96fed-113">준비되지 않음</span><span class="sxs-lookup"><span data-stu-id="96fed-113">Not ready</span></span> | <span data-ttu-id="96fed-114">*이러한 문제를 해결 하지 않으면 등록에 실패 합니다.*</span><span class="sxs-lookup"><span data-stu-id="96fed-114">*Enrollment will fail if you don't fix these issues.*</span></span> <span data-ttu-id="96fed-115">도구 또는이 문서의 단계에 따라 문제를 해결 합니다.</span><span class="sxs-lookup"><span data-stu-id="96fed-115">Follow the steps in the tool or this article to resolve them.</span></span>        |

## <a name="microsoft-intune-settings"></a><span data-ttu-id="96fed-116">Microsoft Intune 설정</span><span class="sxs-lookup"><span data-stu-id="96fed-116">Microsoft Intune settings</span></span>

### <a name="autopilot-deployment-profile"></a><span data-ttu-id="96fed-117">Autopilot 배포 프로필</span><span class="sxs-lookup"><span data-stu-id="96fed-117">Autopilot deployment profile</span></span>

<span data-ttu-id="96fed-118">할당 된 또는 동적 그룹을 대상으로 하는 기존 Autopilot 프로필은 Microsoft Managed Desktop에서 사용 하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="96fed-118">You shouldn't have any existing Autopilot profiles that target assigned or dynamic groups used by Microsoft Managed Desktop.</span></span> <span data-ttu-id="96fed-119">Microsoft Managed Desktop은 Autopilot를 사용 하 여 새 장치를 프로 비전 합니다.</span><span class="sxs-lookup"><span data-stu-id="96fed-119">Microsoft Managed Desktop uses Autopilot to provision new devices.</span></span>

<span data-ttu-id="96fed-120">**준비되지 않음**</span><span class="sxs-lookup"><span data-stu-id="96fed-120">**Not ready**</span></span>

<span data-ttu-id="96fed-121">모든 장치에 할당 된 Autopilot 프로필이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="96fed-121">You have an Autopilot profile that is assigned to all devices.</span></span> <span data-ttu-id="96fed-122">자세한 단계는 [Windows Autopilot을 사용 하 여 Intune에서 windows 장치 등록](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="96fed-122">For steps, see [Enroll Windows devices in Intune by using Windows Autopilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot).</span></span> <span data-ttu-id="96fed-123">Microsoft Managed Desktop 등록 후에는 Autopilot 정책을 설정 하 여 **최신 작업 공간 장치 (All** Azure AD 그룹)를 제외 합니다.</span><span class="sxs-lookup"><span data-stu-id="96fed-123">After Microsoft Managed Desktop enrollment, set your Autopilot policy to exclude the **Modern Workplace Devices -All** Azure AD group.</span></span>

<span data-ttu-id="96fed-124">**조언**</span><span class="sxs-lookup"><span data-stu-id="96fed-124">**Advisory**</span></span>

<span data-ttu-id="96fed-125">Autopilot 프로필이 등록 시 만들 Microsoft Managed Desktop devices를 포함 하지 않는 할당 된 또는 동적 Azure AD 그룹을 대상으로 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="96fed-125">Make sure that your Autopilot profiles target an assigned or dynamic Azure AD group that doesn't include Microsoft Managed Desktop devices that will be created at enrollment.</span></span> <span data-ttu-id="96fed-126">자세한 단계는 [Windows Autopilot을 사용 하 여 Intune에서 windows 장치 등록](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="96fed-126">For steps, see [Enroll Windows devices in Intune by using Windows Autopilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot).</span></span> <span data-ttu-id="96fed-127">Microsoft Managed Desktop 등록 후에는 Autopilot 정책을 설정 하 여 **최신 작업 공간 장치 (All** Azure AD 그룹)를 제외 합니다.</span><span class="sxs-lookup"><span data-stu-id="96fed-127">After Microsoft Managed Desktop enrollment, set your Autopilot policy to exclude the **Modern Workplace Devices -All** Azure AD group.</span></span>


### <a name="certificate-connectors"></a><span data-ttu-id="96fed-128">인증서 커넥터</span><span class="sxs-lookup"><span data-stu-id="96fed-128">Certificate connectors</span></span>

<span data-ttu-id="96fed-129">Microsoft Managed Desktop에서 등록 하려는 장치에서 사용 하는 인증서 커넥터가 있으면 커넥터에 오류가 발생 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="96fed-129">If you have any certificate connectors used by the devices you want to enroll in Microsoft Managed Desktop, the connectors cannot have any errors.</span></span> <span data-ttu-id="96fed-130">다음 권고 중 하나만 상황에 맞게 적용 되므로 신중 하 게 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="96fed-130">Only one of the following advisories will apply to your situation, so check them carefully.</span></span>

<span data-ttu-id="96fed-131">**조언**</span><span class="sxs-lookup"><span data-stu-id="96fed-131">**Advisory**</span></span>

<span data-ttu-id="96fed-132">인증서 커넥터가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="96fed-132">No certificate connectors are present.</span></span> <span data-ttu-id="96fed-133">커넥터가 필요 하지 않을 수 있지만 Microsoft Managed Desktop 장치에 대 한 네트워크 연결에 대 한 몇 가지 필요 여부를 평가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="96fed-133">It's possible you don't need any connectors, but you should evaluate whether you might need some for network connectivity to Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="96fed-134">자세한 내용은 [Microsoft Managed Desktop에 대 한 인증서 및 네트워크 프로필 준비](certs-wifi-lan.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="96fed-134">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>

<span data-ttu-id="96fed-135">**조언**</span><span class="sxs-lookup"><span data-stu-id="96fed-135">**Advisory**</span></span>

<span data-ttu-id="96fed-136">하나 이상의 인증서 커넥터에 오류가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96fed-136">At least one certificate connector has an error.</span></span> <span data-ttu-id="96fed-137">Microsoft Managed Desktop 장치에 연결 하기 위해이 커넥터가 필요한 경우 오류를 해결 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="96fed-137">If you need this connector for connectivity to Microsoft Managed Desktop devices, you must resolve the error.</span></span> <span data-ttu-id="96fed-138">자세한 내용은 [Microsoft Managed Desktop에 대 한 인증서 및 네트워크 프로필 준비](certs-wifi-lan.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="96fed-138">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>


<span data-ttu-id="96fed-139">**조언**</span><span class="sxs-lookup"><span data-stu-id="96fed-139">**Advisory**</span></span>

<span data-ttu-id="96fed-140">하나 이상의 인증서 커넥터가 있고 오류가 보고 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="96fed-140">You have at least one certificate connector and no errors are reported.</span></span> <span data-ttu-id="96fed-141">그러나 Microsoft Managed Desktop 장치에 대 한 커넥터를 다시 사용 하려면 프로필을 만들어야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96fed-141">However, you might need to create a profile to reuse the connector for Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="96fed-142">자세한 내용은 [Microsoft Managed Desktop에 대 한 인증서 및 네트워크 프로필 준비](certs-wifi-lan.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="96fed-142">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>


### <a name="conditional-access-policies"></a><span data-ttu-id="96fed-143">조건부 액세스 정책</span><span class="sxs-lookup"><span data-stu-id="96fed-143">Conditional access policies</span></span>

<span data-ttu-id="96fed-144">Azure AD 조직의 조건부 액세스 정책은 Microsoft 관리 데스크톱 사용자를 대상으로 하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="96fed-144">Conditional access policies in your Azure AD organization must not target any Microsoft Manage Desktop users.</span></span>

<span data-ttu-id="96fed-145">**준비되지 않음**</span><span class="sxs-lookup"><span data-stu-id="96fed-145">**Not ready**</span></span>

<span data-ttu-id="96fed-146">모든 사용자를 대상으로 하는 하나 이상의 조건부 액세스 정책이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="96fed-146">You have at least one conditional access policy that targets all users.</span></span> <span data-ttu-id="96fed-147">등록할 때 생성 되는 Microsoft Managed Desktop service 계정의 Azure AD 그룹을 포함 하지 않는 특정 Azure AD 그룹을 대상으로 하도록 정책을 다시 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="96fed-147">Reset the policy to target a specific Azure AD group that does not include the Azure AD group of Microsoft Managed Desktop service accounts that will be created at enrollment.</span></span> <span data-ttu-id="96fed-148">단계에 대 한 자세한 내용은 [조건부 액세스: 사용자 및 그룹](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="96fed-148">For steps, see [Conditional Access: Users and groups](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups).</span></span>

<span data-ttu-id="96fed-149">**조언**</span><span class="sxs-lookup"><span data-stu-id="96fed-149">**Advisory**</span></span>

<span data-ttu-id="96fed-150">모든 조건부 액세스 정책에서 **최신 직장의 작업 공간 서비스 계정** Azure AD 그룹을 제외 했는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="96fed-150">Make sure that any conditional access policies you have exclude the **Modern Workplace Service Accounts** Azure AD group.</span></span> <span data-ttu-id="96fed-151">단계에 대 한 자세한 내용은 [조건부 액세스 조정을](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/conditional-access)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="96fed-151">For steps, see [Adjust conditional access](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/conditional-access).</span></span> <span data-ttu-id="96fed-152">**최신 작업 공간 서비스 계정** Azure AD 그룹은 등록할 때 서비스를 위해 만드는 동적 그룹입니다.</span><span class="sxs-lookup"><span data-stu-id="96fed-152">The **Modern Workplace Service Accounts** Azure AD group is a dynamic group that we create for the service when you enroll.</span></span> <span data-ttu-id="96fed-153">등록 한 후에는이 그룹을 제외 하려면 다시 방문 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="96fed-153">You'll have to come back to exclude this group after enrollment.</span></span> <span data-ttu-id="96fed-154">이러한 서비스 계정에 대 한 자세한 내용은 [표준 운영 절차](../service-description/operations-and-monitoring.md#standard-operating-procedures)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="96fed-154">For more about these service accounts, see [Standard operating procedures](../service-description/operations-and-monitoring.md#standard-operating-procedures).</span></span>


### <a name="device-compliance-policies"></a><span data-ttu-id="96fed-155">장치 준수 정책</span><span class="sxs-lookup"><span data-stu-id="96fed-155">Device Compliance policies</span></span>

<span data-ttu-id="96fed-156">Azure AD 조직의 Intune 장치 준수 정책은 Microsoft Managed Desktop 사용자를 대상으로 하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="96fed-156">Intune Device Compliance policies in your Azure AD organization must not target any Microsoft Managed Desktop users.</span></span>

<span data-ttu-id="96fed-157">**준비되지 않음**</span><span class="sxs-lookup"><span data-stu-id="96fed-157">**Not ready**</span></span>

<span data-ttu-id="96fed-158">모든 사용자를 대상으로 하는 준수 정책이 하나 이상 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="96fed-158">You have at least one compliance policy that targets all users.</span></span> <span data-ttu-id="96fed-159">Microsoft Managed Desktop users를 포함 하지 않는 특정 Azure AD 그룹을 대상으로 하도록 정책을 다시 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="96fed-159">Reset the policy to target a specific Azure AD group that does not include any Microsoft Managed Desktop users.</span></span> <span data-ttu-id="96fed-160">자세한 단계는 [Microsoft Intune에서 준수 정책 만들기](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="96fed-160">For steps, see [Create a compliance policy in Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy).</span></span>

<span data-ttu-id="96fed-161">**조언**</span><span class="sxs-lookup"><span data-stu-id="96fed-161">**Advisory**</span></span>

<span data-ttu-id="96fed-162">준수 정책에 Microsoft Managed Desktop users가 포함 되어 있지 않은지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="96fed-162">Make sure that any compliance policies you have don't include any Microsoft Managed Desktop users.</span></span> <span data-ttu-id="96fed-163">자세한 단계는 [Microsoft Intune에서 준수 정책 만들기](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="96fed-163">For steps, see [Create a compliance policy in Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy).</span></span>



### <a name="device-configuration-policies"></a><span data-ttu-id="96fed-164">장치 구성 정책</span><span class="sxs-lookup"><span data-stu-id="96fed-164">Device Configuration policies</span></span>

<span data-ttu-id="96fed-165">Azure AD 조직의 Intune 장치 구성 정책은 Microsoft 관리 데스크톱 장치 또는 사용자를 대상으로 하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="96fed-165">Intune Device Configuration policies in your Azure AD organization must not target any Microsoft Manage Desktop devices or users.</span></span>

<span data-ttu-id="96fed-166">**준비되지 않음**</span><span class="sxs-lookup"><span data-stu-id="96fed-166">**Not ready**</span></span>

<span data-ttu-id="96fed-167">모든 사용자, 모든 장치 또는 둘 다를 대상으로 하는 구성 정책이 하나 이상 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="96fed-167">You have at least one configuration policy that targets all users, all devices, or both.</span></span> <span data-ttu-id="96fed-168">Microsoft Managed Desktop 장치를 포함 하지 않는 특정 Azure AD 그룹을 대상으로 하도록 정책을 다시 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="96fed-168">Reset the policy to target a specific Azure AD group that does not include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="96fed-169">자세한 단계는 [Microsoft Intune에서 준수 정책 만들기](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="96fed-169">For steps, see [Create a compliance policy in Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure).</span></span>

<span data-ttu-id="96fed-170">**조언**</span><span class="sxs-lookup"><span data-stu-id="96fed-170">**Advisory**</span></span>

<span data-ttu-id="96fed-171">준수 정책에 Microsoft 관리 되는 데스크톱 장치 또는 사용자가 포함 되어 있지 않은지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="96fed-171">Make sure that any compliance policies you have don't include any Microsoft Managed Desktop devices or users.</span></span> <span data-ttu-id="96fed-172">자세한 단계는 [Microsoft Intune에서 준수 정책 만들기](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="96fed-172">For steps, see [Create a compliance policy in Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure).</span></span>



### <a name="device-type-restrictions"></a><span data-ttu-id="96fed-173">장치 유형 제한</span><span class="sxs-lookup"><span data-stu-id="96fed-173">Device type restrictions</span></span>

<span data-ttu-id="96fed-174">Microsoft Managed Desktop 장치는 Intune에서 등록할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="96fed-174">Microsoft Managed Desktop devices must be allowed to enroll in Intune.</span></span>

<span data-ttu-id="96fed-175">**준비되지 않음**</span><span class="sxs-lookup"><span data-stu-id="96fed-175">**Not ready**</span></span>

<span data-ttu-id="96fed-176">[등록 제한 설정](https://docs.microsoft.com/mem/intune/enrollment/enrollment-restrictions-set) 의 단계에 따라 설정을 **허용**으로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="96fed-176">Follow the steps in [Set enrollment restrictions](https://docs.microsoft.com/mem/intune/enrollment/enrollment-restrictions-set) to change the setting to **Allow**.</span></span>


### <a name="enrollment-status-page"></a><span data-ttu-id="96fed-177">등록 상태 페이지</span><span class="sxs-lookup"><span data-stu-id="96fed-177">Enrollment Status Page</span></span>

<span data-ttu-id="96fed-178">현재 ESP (등록 상태 페이지)를 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="96fed-178">You currently have the Enrollment Status Page (ESP) enabled.</span></span> <span data-ttu-id="96fed-179">이 기능의 공개 미리 보기에 참여 하는 경우에는이 항목을 무시 해도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="96fed-179">If you are participating in the public preview of this feature, you can ignore this item.</span></span> <span data-ttu-id="96fed-180">자세한 내용은 [Autopilot 및 등록 상태 페이지를 사용 하 여 첫 실행 환경을](../get-started/esp-first-run.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="96fed-180">For more information, see [First-run experience with Autopilot and the Enrollment Status Page](../get-started/esp-first-run.md).</span></span>

<span data-ttu-id="96fed-181">**준비되지 않음**</span><span class="sxs-lookup"><span data-stu-id="96fed-181">**Not ready**</span></span>

<span data-ttu-id="96fed-182">**앱 및 프로필 구성 진행률을 표시**하도록 ESP 기본 프로필을 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="96fed-182">You have the ESP default profile set to **Show app and profile configuration progress**.</span></span> <span data-ttu-id="96fed-183">[등록 상태 설정 페이지](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status)의 단계를 수행 하 여이 설정을 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="96fed-183">Disable this setting by following the steps in [Set up the Enrollment Status Page](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status).</span></span>

<span data-ttu-id="96fed-184">**조언**</span><span class="sxs-lookup"><span data-stu-id="96fed-184">**Advisory**</span></span>

<span data-ttu-id="96fed-185">**앱 및 프로필 구성 진행률** 설정이 있는 모든 프로필이 Microsoft Managed Desktop 장치를 포함 하는 Azure AD 그룹에 할당 되어 있지 않은지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="96fed-185">Make sure that any profiles that have the **Show app and profile configuration progress** setting are not assigned to any Azure AD group that includes Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="96fed-186">자세한 내용은 [등록 상태 설정 페이지](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="96fed-186">For more information, see [Set up the Enrollment Status Page](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status).</span></span>

### <a name="intune-enrollment"></a><span data-ttu-id="96fed-187">Intune 등록</span><span class="sxs-lookup"><span data-stu-id="96fed-187">Intune enrollment</span></span>

<span data-ttu-id="96fed-188">Azure AD 조직의 Windows 10 장치는 Intune에서 자동으로 등록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="96fed-188">Windows 10 devices in your Azure AD organization must be automatically enrolled in Intune.</span></span>

<span data-ttu-id="96fed-189">**준비되지 않음**</span><span class="sxs-lookup"><span data-stu-id="96fed-189">**Not ready**</span></span>

<span data-ttu-id="96fed-190">Azure AD 조직의 사용자는 Microsoft Intune에 자동으로 등록 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="96fed-190">Users in your Azure AD organization aren't automatically enrolled in Microsoft Intune.</span></span> <span data-ttu-id="96fed-191">MDM 사용자 범위를 **일부** 또는 **모두**로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="96fed-191">Change the MDM User scope to **Some** or **All**.</span></span> <span data-ttu-id="96fed-192">을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="96fed-192">If you choose.</span></span> <span data-ttu-id="96fed-193">일부 \* \*는 등록 후에 다시 돌아와서 **그룹**에 대 한 **최신 직장 작업 공간 (All** Azure AD 그룹)을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="96fed-193">Some\*\*, come back after enrollment and select the **Modern Workplace -All** Azure AD group for **Groups**.</span></span>


### <a name="microsoft-store-for-business"></a><span data-ttu-id="96fed-194">비즈니스용 Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="96fed-194">Microsoft Store for Business</span></span>

<span data-ttu-id="96fed-195">회사 포털을 다운로드 하 여 Microsoft Project 및 Microsoft Visio와 같은 일부 앱을 배포할 수 있도록 Microsoft Store for Business를 사용 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96fed-195">We use Microsoft Store for Business so that you can download Company Portal to deploy some apps, such as Microsoft Project and Microsoft Visio.</span></span>

<span data-ttu-id="96fed-196">**준비되지 않음**</span><span class="sxs-lookup"><span data-stu-id="96fed-196">**Not ready**</span></span>

<span data-ttu-id="96fed-197">비즈니스용 Microsoft Store가 사용 하도록 설정 되지 않았거나 Intune과 동기화 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="96fed-197">Microsoft Store for Business either isn't enabled or isn't synced with Intune.</span></span> <span data-ttu-id="96fed-198">자세한 내용은 microsoft [intune을 사용 하 여 비즈니스용 Microsoft 스토어에서 구입한 볼륨 구입 앱을 관리](https://docs.microsoft.com/mem/intune/apps/windows-store-for-business) 하 고 [장치에 Intune 회사 포털을 설치](../get-started/company-portal.md)하는 방법을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="96fed-198">For more information, see [How to manage volume purchased apps from the Microsoft Store for Business with Microsoft Intune](https://docs.microsoft.com/mem/intune/apps/windows-store-for-business) and [Install Intune Company Portal on on devices](../get-started/company-portal.md).</span></span>

### <a name="multi-factor-authentication"></a><span data-ttu-id="96fed-199">다단계 인증</span><span class="sxs-lookup"><span data-stu-id="96fed-199">Multi-factor authentication</span></span>

<span data-ttu-id="96fed-200">Microsoft Managed Desktop 서비스 계정에는 실수로 다단계 인증을 적용 해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="96fed-200">Multi-factor authentication must not accidentally be applied to Microsoft Managed Desktop service accounts.</span></span>


<span data-ttu-id="96fed-201">**준비되지 않음**</span><span class="sxs-lookup"><span data-stu-id="96fed-201">**Not ready**</span></span>

<span data-ttu-id="96fed-202">일부 MFA (multi-factor authentication) 정책이 모든 사용자에 게 할당 된 조건부 액세스 정책에 대해 "필수"로 설정 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="96fed-202">You have some multi-factor authentication (MFA) policies set as "required" for conditional access policies that are assigned to all users.</span></span> <span data-ttu-id="96fed-203">Microsoft Managed Desktop 장치를 포함 하지 않는 특정 Azure AD 그룹을 대상으로 하는 할당을 사용 하도록 정책을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="96fed-203">Change the policy to use an Assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="96fed-204">자세한 내용은 [조건부 액세스 정책](#conditional-access-policies) 및 [조건부 액세스: 모든 사용자에 대해 MFA 필요](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="96fed-204">For more information, see [Conditional access policies](#conditional-access-policies) and [Conditional Access: Require MFA for all users](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa).</span></span>

<span data-ttu-id="96fed-205">**조언**</span><span class="sxs-lookup"><span data-stu-id="96fed-205">**Advisory**</span></span>

<span data-ttu-id="96fed-206">MFA가 필요한 조건부 액세스 정책이 **최신 직장의 모든** Azure AD 그룹을 제외 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="96fed-206">Make sure that any conditional access policies that require MFA exclude the **Modern Workplace -All** Azure AD group.</span></span> <span data-ttu-id="96fed-207">자세한 내용은 [조건부 액세스 정책](#conditional-access-policies) 및 [조건부 액세스: 모든 사용자에 대해 MFA 필요](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="96fed-207">For more information, see [Conditional access policies](#conditional-access-policies) and [Conditional Access: Require MFA for all users](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa).</span></span> <span data-ttu-id="96fed-208">**최신 작업 회사-All** Azure AD 그룹은 Microsoft Managed Desktop에 등록할 때 작성 하는 동적 그룹으로, 등록 후에이 그룹을 제외 하려면 다시 방문 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="96fed-208">The **Modern Workplace -All** Azure AD group is a dynamic group that we create when you enroll in Microsoft Managed Desktop, so you'll have to come back to exclude this group after enrollment.</span></span>



### <a name="powershell-scripts"></a><span data-ttu-id="96fed-209">PowerShell 스크립트</span><span class="sxs-lookup"><span data-stu-id="96fed-209">PowerShell scripts</span></span>

<span data-ttu-id="96fed-210">Microsoft Managed Desktop 장치를 대상으로 하는 방식으로 Windows PowerShell 스크립트를 할당할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="96fed-210">Windows PowerShell scripts can't be assigned in a way that would target Microsoft Managed Desktop devices.</span></span>  

<span data-ttu-id="96fed-211">**조언**</span><span class="sxs-lookup"><span data-stu-id="96fed-211">**Advisory**</span></span>

<span data-ttu-id="96fed-212">Azure AD 조직의 Windows PowerShell 스크립트에서 어떤 Microsoft 데스크톱 장치나 사용자도 관리 하지 않는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="96fed-212">Make sure that Windows PowerShell scripts in your Azure AD organization don't target any Microsoft Manage Desktop devices or users.</span></span> <span data-ttu-id="96fed-213">자세한 내용은 [Intune에서 Windows 10 장치에서 PowerShell 스크립트 사용](https://docs.microsoft.com/mem/intune/apps/intune-management-extension)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="96fed-213">For more information, see [Use PowerShell scripts on Windows 10 devices in Intune](https://docs.microsoft.com/mem/intune/apps/intune-management-extension).</span></span>

### <a name="region"></a><span data-ttu-id="96fed-214">지역</span><span class="sxs-lookup"><span data-stu-id="96fed-214">Region</span></span>

<span data-ttu-id="96fed-215">사용자의 지역을 Microsoft Managed Desktop에서 지원 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="96fed-215">Your region must be supported by Microsoft Managed Desktop.</span></span>

<span data-ttu-id="96fed-216">**준비되지 않음**</span><span class="sxs-lookup"><span data-stu-id="96fed-216">**Not ready**</span></span>

<span data-ttu-id="96fed-217">현재 Azure AD 조직 지역이 Microsoft Managed Desktop에서 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="96fed-217">Your Azure AD organization region isn't currently supported by Microsoft Managed Desktop.</span></span> <span data-ttu-id="96fed-218">자세한 내용은 [Microsoft Managed Desktop 지원 지역 및 언어](../service-description/regions-languages.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="96fed-218">For more information, see [Microsoft Managed Desktop supported regions and languages](../service-description/regions-languages.md).</span></span>

<span data-ttu-id="96fed-219">**조언**</span><span class="sxs-lookup"><span data-stu-id="96fed-219">**Advisory**</span></span>

<span data-ttu-id="96fed-220">Azure AD 조직이 있는 하나 이상의 국가는 Microsoft Managed Desktop에서 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="96fed-220">One or more of the countries where your Azure AD organization is located isn't supported by Microsoft Managed Desktop.</span></span> <span data-ttu-id="96fed-221">자세한 내용은 [Microsoft Managed Desktop 지원 지역 및 언어](../service-description/regions-languages.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="96fed-221">For more information, see [Microsoft Managed Desktop supported regions and languages](../service-description/regions-languages.md).</span></span>


### <a name="security-baselines"></a><span data-ttu-id="96fed-222">보안 기준</span><span class="sxs-lookup"><span data-stu-id="96fed-222">Security baselines</span></span>

<span data-ttu-id="96fed-223">보안 기본 정책은 Microsoft 관리 되는 데스크톱 장치를 대상으로 지정 해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="96fed-223">Security baseline policies should not target any Microsoft Managed Desktop devices.</span></span>

<span data-ttu-id="96fed-224">**준비되지 않음**</span><span class="sxs-lookup"><span data-stu-id="96fed-224">**Not ready**</span></span>

<span data-ttu-id="96fed-225">모든 사용자, 모든 장치 또는 둘 다를 대상으로 하는 보안 기준 프로필을 보유 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96fed-225">You have a security baseline profile that targets all users, all devices or both.</span></span> <span data-ttu-id="96fed-226">Microsoft Managed Desktop 장치를 포함 하지 않는 특정 Azure AD 그룹을 대상으로 하는 할당을 사용 하도록 정책을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="96fed-226">Change the policy to use an Assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="96fed-227">자세한 단계는 [security 기준선이 Use To Windows 10 devices In Intune](https://docs.microsoft.com/mem/intune/protect/security-baselines)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="96fed-227">For steps, see [Use security baselines to configure Windows 10 devices in Intune](https://docs.microsoft.com/mem/intune/protect/security-baselines).</span></span>

<span data-ttu-id="96fed-228">**조언**</span><span class="sxs-lookup"><span data-stu-id="96fed-228">**Advisory**</span></span>

<span data-ttu-id="96fed-229">Microsoft Managed Desktop 장치를 제외 하는 보안 기본 정책이 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="96fed-229">Make sure that any security baseline policies you have exclude Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="96fed-230">자세한 단계는 [security 기준선이 Use To Windows 10 devices In Intune](https://docs.microsoft.com/mem/intune/protect/security-baselines)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="96fed-230">For steps, see [Use security baselines to configure Windows 10 devices in Intune](https://docs.microsoft.com/mem/intune/protect/security-baselines).</span></span> <span data-ttu-id="96fed-231">**최신 작업 공간 장치-모든** Azure AD 그룹은 Microsoft Managed Desktop에 등록할 때 만든 동적 그룹으로, 등록 후에이 그룹을 제외 하려면 다시 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="96fed-231">The **Modern Workplace Devices -All** Azure AD group is a dynamic group that we create when you enroll in Microsoft Managed Desktop, so you'll have to come back to exclude this group after enrollment.</span></span>


### <a name="windows-apps"></a><span data-ttu-id="96fed-232">Windows 앱</span><span class="sxs-lookup"><span data-stu-id="96fed-232">Windows apps</span></span>

<span data-ttu-id="96fed-233">Microsoft Managed Desktop 사용자에 게 부여할 앱을 검토 합니다.</span><span class="sxs-lookup"><span data-stu-id="96fed-233">Review apps you want your Microsoft Managed Desktop users to have.</span></span>

<span data-ttu-id="96fed-234">**조언**</span><span class="sxs-lookup"><span data-stu-id="96fed-234">**Advisory**</span></span>

<span data-ttu-id="96fed-235">Microsoft Managed Desktop 사용자에 게 부여할 앱의 인벤토리를 준비 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="96fed-235">You should prepare an inventory of the apps that you want your Microsoft Managed Desktop users to have.</span></span> <span data-ttu-id="96fed-236">Intune을 통해 이러한 앱을 배포할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="96fed-236">Make sure these apps can be deployed by Intune.</span></span> <span data-ttu-id="96fed-237">자세한 내용은 [Microsoft Managed Desktop의 앱](apps.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="96fed-237">For more information, see [Apps in Microsoft Managed Desktop](apps.md).</span></span>

<span data-ttu-id="96fed-238">Microsoft 계정 담당자에 게 문의 하 여 Intune으로 마이그레이션하거나, 조정이 필요한 앱을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96fed-238">You can ask your Microsoft account representative for a query in Microsoft Endpoint Configuration Manager to identify those apps that are ready to migrate to Intune or need adjustment.</span></span>


### <a name="windows-hello-for-business"></a><span data-ttu-id="96fed-239">비즈니스용 Windows Hello</span><span class="sxs-lookup"><span data-stu-id="96fed-239">Windows Hello for Business</span></span>

<span data-ttu-id="96fed-240">Microsoft Managed Desktop을 사용 하려면 비즈니스용 Windows Hello가 설정 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="96fed-240">Microsoft Managed Desktop requires Windows Hello for Business to be enabled.</span></span>

<span data-ttu-id="96fed-241">**준비되지 않음**</span><span class="sxs-lookup"><span data-stu-id="96fed-241">**Not ready**</span></span>

<span data-ttu-id="96fed-242">비즈니스용 Windows Hello가 사용 하지 않도록 설정 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="96fed-242">Windows Hello for Business is disabled.</span></span> <span data-ttu-id="96fed-243">[비즈니스용 Windows Hello 정책 만들기](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy) 의 단계를 수행 하 여이 기능을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="96fed-243">Enable it by following the steps in [Create a Windows Hello for Business policy](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)</span></span>

<span data-ttu-id="96fed-244">**조언**</span><span class="sxs-lookup"><span data-stu-id="96fed-244">**Advisory**</span></span>

<span data-ttu-id="96fed-245">비즈니스용 Windows Hello가 설정 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="96fed-245">Windows Hello for Business is not set up.</span></span> <span data-ttu-id="96fed-246">[비즈니스용 Windows Hello 정책 만들기](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)의 단계를 수행 하 여이 기능을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="96fed-246">Enable it by following the steps in [Create a Windows Hello for Business policy](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy).</span></span>


### <a name="windows-10-update-rings"></a><span data-ttu-id="96fed-247">Windows 10 업데이트 링</span><span class="sxs-lookup"><span data-stu-id="96fed-247">Windows 10 update rings</span></span>

<span data-ttu-id="96fed-248">Intune의 "Windows 10 업데이트 링" 정책은 Microsoft Managed Desktop 장치를 대상으로 하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="96fed-248">Your "Windows 10 update ring" policy in Intune must not target any Microsoft Managed Desktop devices.</span></span>

<span data-ttu-id="96fed-249">**준비되지 않음**</span><span class="sxs-lookup"><span data-stu-id="96fed-249">**Not ready**</span></span>

<span data-ttu-id="96fed-250">모든 장치, 모든 사용자 또는 둘 다를 대상으로 하는 "업데이트 링" 정책이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96fed-250">You have an "update ring" policy that targets all devices, all users, or both.</span></span> <span data-ttu-id="96fed-251">Microsoft Managed Desktop 장치를 포함 하지 않는 특정 Azure AD 그룹을 대상으로 하는 할당을 사용 하도록 정책을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="96fed-251">Change the policy to use an Assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="96fed-252">자세한 단계는 [Intune에서 Windows 10 소프트웨어 업데이트 관리](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="96fed-252">For steps, see [Manage Windows 10 software updates in Intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure).</span></span>

<span data-ttu-id="96fed-253">**조언**</span><span class="sxs-lookup"><span data-stu-id="96fed-253">**Advisory**</span></span>

<span data-ttu-id="96fed-254">업데이트 링 정책에서 **최신 직장의 작업 공간-All** Azure AD 그룹을 제외 했는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="96fed-254">Make sure that any update ring policies you have exclude the **Modern Workplace -All** Azure AD group.</span></span> <span data-ttu-id="96fed-255">자세한 단계는 [Intune에서 Windows 10 소프트웨어 업데이트 관리](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="96fed-255">For steps, see [Manage Windows 10 software updates in Intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure).</span></span> <span data-ttu-id="96fed-256">**최신 작업 공간 장치-모든** Azure AD 그룹은 Microsoft Managed Desktop에 등록할 때 만든 동적 그룹으로, 등록 후에이 그룹을 제외 하려면 다시 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="96fed-256">The **Modern Workplace Devices -All** Azure AD group is a dynamic group that we create when you enroll in Microsoft Managed Desktop, so you'll have to come back to exclude this group after enrollment.</span></span>


## <a name="azure-active-directory-settings"></a><span data-ttu-id="96fed-257">Azure Active Directory 설정</span><span class="sxs-lookup"><span data-stu-id="96fed-257">Azure Active Directory settings</span></span>


### <a name="ad-hoc-subscriptions"></a><span data-ttu-id="96fed-258">임시 구독</span><span class="sxs-lookup"><span data-stu-id="96fed-258">Ad hoc subscriptions</span></span>

<span data-ttu-id="96fed-259">"False"로 설정 된 경우 엔터프라이즈 상태 로밍이 제대로 작동 하지 않을 수 있는 설정을 확인 하는 방법을 제안 합니다.</span><span class="sxs-lookup"><span data-stu-id="96fed-259">Advises how to check a setting that (if set to "false") might prevent Enterprise State Roaming from working correctly.</span></span>

<span data-ttu-id="96fed-260">**조언**</span><span class="sxs-lookup"><span data-stu-id="96fed-260">**Advisory**</span></span>

<span data-ttu-id="96fed-261">**AllowAdHocSubscriptions** 이 **True**로 설정 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="96fed-261">Ensure that **AllowAdHocSubscriptions** is set to **True**.</span></span> <span data-ttu-id="96fed-262">그렇지 않으면 엔터프라이즈 상태 로밍이 작동 하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96fed-262">Otherwise, Enterprise State Roaming might not work.</span></span> <span data-ttu-id="96fed-263">자세한 내용은 [set-msolcompanysettings](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="96fed-263">For more information, see [Set-MsolCompanySettings](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0).</span></span>


### <a name="enterprise-state-roaming"></a><span data-ttu-id="96fed-264">Enterprise State Roaming</span><span class="sxs-lookup"><span data-stu-id="96fed-264">Enterprise State Roaming</span></span>

<span data-ttu-id="96fed-265">엔터프라이즈 상태 로밍을 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="96fed-265">Enterprise State Roaming should be enabled.</span></span>

<span data-ttu-id="96fed-266">**조언**</span><span class="sxs-lookup"><span data-stu-id="96fed-266">**Advisory**</span></span>

<span data-ttu-id="96fed-267">**모든** 또는 **선택한** 그룹에 대해 엔터프라이즈 상태 로밍을 사용 하도록 설정 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="96fed-267">Make sure that Enterprise State Roaming is enabled for **All** or for **Selected** groups.</span></span> <span data-ttu-id="96fed-268">자세한 내용은 [Azure Active Directory에서 엔터프라이즈 상태 로밍을 사용 하도록 설정을](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-enable)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="96fed-268">For more information, see [Enable Enterprise State Roaming in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-enable).</span></span>

### <a name="licenses"></a><span data-ttu-id="96fed-269">라이선스</span><span class="sxs-lookup"><span data-stu-id="96fed-269">Licenses</span></span>

<span data-ttu-id="96fed-270">Microsoft Managed Desktop을 사용 하려면 많은 라이선스가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="96fed-270">A number of licenses are required to use Microsoft Managed Desktop.</span></span>

<span data-ttu-id="96fed-271">**준비 되지 않음**</span><span class="sxs-lookup"><span data-stu-id="96fed-271">**Not Ready**</span></span>

<span data-ttu-id="96fed-272">Microsoft Managed Desktop을 사용 하는 데 필요한 라이선스가 모두 없습니다.</span><span class="sxs-lookup"><span data-stu-id="96fed-272">You don't have all the licenses you need to use Microsoft Managed Desktop.</span></span> <span data-ttu-id="96fed-273">자세한 내용은 [Microsoft Managed Desktop 기술](../intro/technologies.md) 및 [라이선스에 대 한 추가](prerequisites.md#more-about-licenses)정보를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="96fed-273">For more information, see [Microsoft Managed Desktop technologies](../intro/technologies.md) and [More about licenses](prerequisites.md#more-about-licenses).</span></span>


### <a name="security-account-names"></a><span data-ttu-id="96fed-274">보안 계정 이름</span><span class="sxs-lookup"><span data-stu-id="96fed-274">Security account names</span></span>

<span data-ttu-id="96fed-275">특정 보안 계정 이름이 Microsoft Managed Desktop에서 만든 이름과 충돌할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96fed-275">Certain security account names could conflict with ones created by Microsoft Managed Desktop.</span></span>

<span data-ttu-id="96fed-276">**준비되지 않음**</span><span class="sxs-lookup"><span data-stu-id="96fed-276">**Not ready**</span></span>

<span data-ttu-id="96fed-277">Microsoft Managed Desktop에서 만든 계정 이름과 충돌 하는 계정이 하나 이상 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="96fed-277">You have at least one account name that will conflict with ones created by Microsoft Managed Desktop.</span></span> <span data-ttu-id="96fed-278">Microsoft 계정 담당자와 협력 하 여 이러한 계정 이름을 제외 합니다.</span><span class="sxs-lookup"><span data-stu-id="96fed-278">Work with your Microsoft account representative to exclude these account names.</span></span>


### <a name="security-administrator-roles"></a><span data-ttu-id="96fed-279">보안 관리자 역할</span><span class="sxs-lookup"><span data-stu-id="96fed-279">Security administrator roles</span></span>

<span data-ttu-id="96fed-280">특정 보안 역할을 가진 사용자에 게는 끝점에 대해 Microsoft Defender에서 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="96fed-280">Users with certain security roles must have those assigned in Microsoft Defender for Endpoint.</span></span>

<span data-ttu-id="96fed-281">**조언**</span><span class="sxs-lookup"><span data-stu-id="96fed-281">**Advisory**</span></span>

<span data-ttu-id="96fed-282">Azure AD 조직에 이러한 역할이 할당 되어 있는 경우이 역할에도 Microsoft Defender for Endpoint에 할당 된 이러한 역할이 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="96fed-282">If you have any of these roles assigned in your Azure AD organization, make sure they also have these roles assigned in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="96fed-283">그렇지 않으면 이러한 역할을 가진 관리자가 관리자 포털에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="96fed-283">Otherwise, administrators with these roles won't be able to access the Admin portal.</span></span>

- <span data-ttu-id="96fed-284">보안 읽기 권한자</span><span class="sxs-lookup"><span data-stu-id="96fed-284">Security Reader</span></span>
- <span data-ttu-id="96fed-285">보안 운영자</span><span class="sxs-lookup"><span data-stu-id="96fed-285">Security Operator</span></span>
- <span data-ttu-id="96fed-286">전역 읽기 권한자</span><span class="sxs-lookup"><span data-stu-id="96fed-286">Global Reader</span></span>

<span data-ttu-id="96fed-287">자세한 내용은 [역할 기반 액세스 제어에 대 한 역할 만들기 및 관리](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="96fed-287">For more information, see [Create and manage roles for role-based access control](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles).</span></span>


### <a name="security-default"></a><span data-ttu-id="96fed-288">보안 기본값</span><span class="sxs-lookup"><span data-stu-id="96fed-288">Security default</span></span>

<span data-ttu-id="96fed-289">Azure Active Directory의 보안 기본값을 설정 하면 Microsoft Managed Desktop에서 장치를 관리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="96fed-289">Security defaults in Azure Active Directory will prevent Microsoft Managed Desktop from managing your devices.</span></span>

<span data-ttu-id="96fed-290">**준비되지 않음**</span><span class="sxs-lookup"><span data-stu-id="96fed-290">**Not ready**</span></span>

<span data-ttu-id="96fed-291">보안 기본값이 설정 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="96fed-291">You have Security defaults turned on.</span></span> <span data-ttu-id="96fed-292">보안 기본값을 해제 하 고 조건부 액세스 정책을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="96fed-292">Turn off Security defaults and set up conditional access policies.</span></span> <span data-ttu-id="96fed-293">자세한 내용은 [일반 조건부 액세스 정책](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="96fed-293">For more information, see [Common Conditional Access policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common).</span></span>

### <a name="self-service-password-reset"></a><span data-ttu-id="96fed-294">셀프 서비스 암호 재설정</span><span class="sxs-lookup"><span data-stu-id="96fed-294">Self-service Password Reset</span></span>

<span data-ttu-id="96fed-295">셀프 서비스 암호 재설정 (SSPR)을 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="96fed-295">Self-service Password Reset (SSPR) must be enabled.</span></span>

<span data-ttu-id="96fed-296">**준비되지 않음**</span><span class="sxs-lookup"><span data-stu-id="96fed-296">**Not ready**</span></span>

<span data-ttu-id="96fed-297">모든 사용자에 대해 SSPR를 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="96fed-297">SSPR must be enabled for all users.</span></span> <span data-ttu-id="96fed-298">그렇지 않으면 Microsoft Managed Desktop service 계정이 작동할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="96fed-298">If it isn't, the Microsoft Managed Desktop service accounts can't work.</span></span> <span data-ttu-id="96fed-299">자세한 내용은 [Tutorial: 사용자가 Azure Active Directory 셀프 서비스 암호 재설정을 사용 하 여 계정의 잠금을 해제 하거나 암호를 재설정할 수 있도록](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-enable-sspr)합니다 .를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="96fed-299">For more information, see [Tutorial: Enable users to unlock their account or reset passwords using Azure Active Directory self-service password reset](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-enable-sspr).</span></span>

<span data-ttu-id="96fed-300">**조언**</span><span class="sxs-lookup"><span data-stu-id="96fed-300">**Advisory**</span></span>

<span data-ttu-id="96fed-301">SSPR **Selected** 설정에 Microsoft Managed Desktop devices가 포함 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="96fed-301">Make sure that the SSPR **Selected** setting includes Microsoft Managed Desktop devices.</span></span>

### <a name="standard-user-role"></a><span data-ttu-id="96fed-302">표준 사용자 역할</span><span class="sxs-lookup"><span data-stu-id="96fed-302">Standard user role</span></span>

<span data-ttu-id="96fed-303">Microsoft Managed Desktop 사용자는 로컬 관리자 권한이 없는 표준 사용자 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="96fed-303">Microsoft Managed Desktop users should be standard users without local administrator privileges.</span></span> <span data-ttu-id="96fed-304">Microsoft Managed Desktop 장치를 시작할 때 표준 사용자 역할이 할당 될 예정입니다.</span><span class="sxs-lookup"><span data-stu-id="96fed-304">They'll be assigned a standard user role when they start their Microsoft Managed Desktop device.</span></span>

<span data-ttu-id="96fed-305">**조언**</span><span class="sxs-lookup"><span data-stu-id="96fed-305">**Advisory**</span></span>

<span data-ttu-id="96fed-306">Microsoft Managed Desktop 사용자에 게 등록 하기 전에 로컬 관리자 권한이 없어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="96fed-306">Microsoft Managed Desktop users shouldn't have local administrator privileges prior to enrolling.</span></span>

## <a name="microsoft-365-apps-for-enterprise"></a><span data-ttu-id="96fed-307">엔터프라이즈용 Microsoft 365 앱</span><span class="sxs-lookup"><span data-stu-id="96fed-307">Microsoft 365 Apps for enterprise</span></span>

### <a name="onedrive-for-business"></a><span data-ttu-id="96fed-308">비즈니스용 OneDrive</span><span class="sxs-lookup"><span data-stu-id="96fed-308">OneDrive for Business</span></span>

<span data-ttu-id="96fed-309">**특정 도메인에 가입 된 pc 에서만 동기화 허용** 설정은 Microsoft Managed Desktop과 충돌 합니다.</span><span class="sxs-lookup"><span data-stu-id="96fed-309">The **Allow syncing only on PCs joined to specific domains** setting will conflict with Microsoft Managed Desktop.</span></span>

<span data-ttu-id="96fed-310">**조언**</span><span class="sxs-lookup"><span data-stu-id="96fed-310">**Advisory**</span></span>

<span data-ttu-id="96fed-311">**특정 도메인에 가입 된 pc 에서만 동기화 허용** 설정을 사용 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96fed-311">You're using the **Allow syncing only on PCs joined to specific domains** setting.</span></span> <span data-ttu-id="96fed-312">이 설정은 Microsoft Managed Desktop에서는 작동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="96fed-312">This setting won't work with Microsoft Managed Desktop.</span></span> <span data-ttu-id="96fed-313">이 설정을 사용 하지 않고 비즈니스용 OneDrive에서 조건부 액세스 정책을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="96fed-313">Disable this setting, and instead set up OneDrive for Business to use a conditional access policy.</span></span> <span data-ttu-id="96fed-314">도움말을 보려면 [조건부 액세스 배포 계획을](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="96fed-314">See [Plan a Conditional Access deployment](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access) for help.</span></span>

