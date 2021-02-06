---
title: 준비 평가 도구에서 발견한 문제 해결
description: 도구에서 찾은 각 문제의 세부 작업
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 문서
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: ff2ef15f93cef5255e8c8113facf51b833eff77d
ms.sourcegitcommit: 719b89baca1bae14455acf2e517ec18fc473636c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/05/2021
ms.locfileid: "50122363"
---
# <a name="fix-issues-found-by-the-readiness-assessment-tool"></a><span data-ttu-id="38df6-104">준비 평가 도구에서 발견한 문제 해결</span><span class="sxs-lookup"><span data-stu-id="38df6-104">Fix issues found by the readiness assessment tool</span></span>

<span data-ttu-id="38df6-105">각 검사에 대해 도구는 다음 네 가지 결과 중 하나를 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="38df6-105">For each check, the tool will report one of four possible results:</span></span>


|<span data-ttu-id="38df6-106">결과</span><span class="sxs-lookup"><span data-stu-id="38df6-106">Result</span></span>  |<span data-ttu-id="38df6-107">의미</span><span class="sxs-lookup"><span data-stu-id="38df6-107">Meaning</span></span>  |
|---------|---------|
|<span data-ttu-id="38df6-108">준비</span><span class="sxs-lookup"><span data-stu-id="38df6-108">Ready</span></span>     | <span data-ttu-id="38df6-109">등록을 완료하기 전에 필요한 작업은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="38df6-109">No action is required before completing enrollment.</span></span>        |
|<span data-ttu-id="38df6-110">권고</span><span class="sxs-lookup"><span data-stu-id="38df6-110">Advisory</span></span>    | <span data-ttu-id="38df6-111">등록과 사용자에 대한 최상의 환경을 위해 도구 또는 이 문서의 단계를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="38df6-111">Follow the steps in the tool or this article for the best experience with enrollment and for users.</span></span> <span data-ttu-id="38df6-112">*등록을* 완료할 수 있지만 첫 번째 장치를 배포하기 전에 이러한 문제를 해결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="38df6-112">You *can* complete enrollment, but you must fix these issues before you deploy your first device.</span></span>        |
|<span data-ttu-id="38df6-113">준비되지 않음</span><span class="sxs-lookup"><span data-stu-id="38df6-113">Not ready</span></span> | <span data-ttu-id="38df6-114">*이러한 문제를 해결하지 않는 경우 등록이 실패합니다.*</span><span class="sxs-lookup"><span data-stu-id="38df6-114">*Enrollment will fail if you don't fix these issues.*</span></span> <span data-ttu-id="38df6-115">도구 또는 이 문서의 단계에 따라 문제를 해결합니다.</span><span class="sxs-lookup"><span data-stu-id="38df6-115">Follow the steps in the tool or this article to resolve them.</span></span>        |
|<span data-ttu-id="38df6-116">오류</span><span class="sxs-lookup"><span data-stu-id="38df6-116">Error</span></span> | <span data-ttu-id="38df6-117">사용중인 Azure AD(Active Directory) 역할에는 이 검사를 실행할 수 있는 권한이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="38df6-117">The Azure Active Directory (AD) role you're using doesn't have sufficient permission to run this check.</span></span> |

> [!NOTE]
> <span data-ttu-id="38df6-118">이 도구에서 보고한 결과에는 설정이 실행된 특정 시점에만 설정 상태가 반영됩니다.</span><span class="sxs-lookup"><span data-stu-id="38df6-118">The results reported by this tool reflect the status of your settings only at the specific point in time that you ran it.</span></span> <span data-ttu-id="38df6-119">나중에 Microsoft Intune, Azure Active Directory 또는 Microsoft 365에서 정책을 변경하면 "준비되지 않은" 항목이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38df6-119">If you later make any changes to policies in Microsoft Intune, Azure Active Directory, or Microsoft 365, items that were "Ready" can become "Not ready."</span></span> <span data-ttu-id="38df6-120">Microsoft Managed Desktop 작업의 문제를 방지하려면 정책을 변경하기 전에 이 문서에 설명된 특정 설정을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="38df6-120">To avoid problems with Microsoft Managed Desktop operations, check the specific settings described in this article before you change any policies.</span></span>

## <a name="microsoft-intune-settings"></a><span data-ttu-id="38df6-121">Microsoft Intune 설정</span><span class="sxs-lookup"><span data-stu-id="38df6-121">Microsoft Intune settings</span></span>

<span data-ttu-id="38df6-122">Microsoft Endpoint Manager 관리 센터에서 Intune 설정에 [액세스할 수 있습니다.](https://endpoint.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="38df6-122">You can access Intune settings at the Microsoft Endpoint Manager [admin center](https://endpoint.microsoft.com).</span></span>

### <a name="autopilot-deployment-profile"></a><span data-ttu-id="38df6-123">Autopilot 배포 프로필</span><span class="sxs-lookup"><span data-stu-id="38df6-123">Autopilot deployment profile</span></span>

<span data-ttu-id="38df6-124">Microsoft Managed Desktop 장치를 사용하여 할당되거나 동적 그룹을 대상으로 하는 기존 Autopilot 프로필은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="38df6-124">You shouldn't have any existing Autopilot profiles that target assigned or dynamic groups with Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="38df6-125">Microsoft Managed Desktop은 Autopilot을 사용하여 새 장치를 프로비전합니다.</span><span class="sxs-lookup"><span data-stu-id="38df6-125">Microsoft Managed Desktop uses Autopilot to provision new devices.</span></span>

<span data-ttu-id="38df6-126">**준비되지 않음**</span><span class="sxs-lookup"><span data-stu-id="38df6-126">**Not ready**</span></span>

<span data-ttu-id="38df6-127">모든 장치에 할당된 Autopilot 프로필이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38df6-127">You have an Autopilot profile that is assigned to all devices.</span></span> <span data-ttu-id="38df6-128">단계는 Windows [Autopilot을 사용하여 Intune에서 Windows 장치 등록을 참조하세요.](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot)</span><span class="sxs-lookup"><span data-stu-id="38df6-128">For steps, see [Enroll Windows devices in Intune by using Windows Autopilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot).</span></span> <span data-ttu-id="38df6-129">Microsoft Managed Desktop 등록 후 Autopilot 정책을 설정하여 최신 작업 공간 장치 **- 모든** Azure AD 그룹을 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="38df6-129">After Microsoft Managed Desktop enrollment, set your Autopilot policy to exclude the **Modern Workplace Devices -All** Azure AD group.</span></span>

<span data-ttu-id="38df6-130">**권고**</span><span class="sxs-lookup"><span data-stu-id="38df6-130">**Advisory**</span></span>

<span data-ttu-id="38df6-131">Autopilot 프로필이 Microsoft Managed Desktop 장치를 포함하지 않는 할당되거나 동적 Azure AD 그룹을 대상으로 하는지 확인</span><span class="sxs-lookup"><span data-stu-id="38df6-131">Make sure that your Autopilot profiles target an assigned or dynamic Azure AD group that doesn't include Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="38df6-132">단계는 Windows [Autopilot을 사용하여 Intune에서 Windows 장치 등록을 참조하세요.](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot)</span><span class="sxs-lookup"><span data-stu-id="38df6-132">For steps, see [Enroll Windows devices in Intune by using Windows Autopilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot).</span></span> <span data-ttu-id="38df6-133">Microsoft Managed Desktop 등록 후 Autopilot 프로필을 설정하여 최신 작업 공간 장치 **- 모든** Azure AD 그룹을 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="38df6-133">After Microsoft Managed Desktop enrollment, set your Autopilot profiles to exclude the **Modern Workplace Devices -All** Azure AD group.</span></span>


### <a name="certificate-connectors"></a><span data-ttu-id="38df6-134">인증서 커넥터</span><span class="sxs-lookup"><span data-stu-id="38df6-134">Certificate connectors</span></span>

<span data-ttu-id="38df6-135">Microsoft Managed Desktop에 등록하려는 장치에서 사용할 인증서 커넥터가 있는 경우 커넥터에 오류가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="38df6-135">If you have any certificate connectors that will be used by the devices you want to enroll in Microsoft Managed Desktop, the connectors should not have any errors.</span></span> <span data-ttu-id="38df6-136">다음 권고 중 하나만 상황에 적용될 것이기 때문에 신중하게 검토하십시오.</span><span class="sxs-lookup"><span data-stu-id="38df6-136">Only one of the following advisories will apply to your situation, so check them carefully.</span></span>

<span data-ttu-id="38df6-137">**권고**</span><span class="sxs-lookup"><span data-stu-id="38df6-137">**Advisory**</span></span>

<span data-ttu-id="38df6-138">인증서 커넥터가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="38df6-138">No certificate connectors are present.</span></span> <span data-ttu-id="38df6-139">커넥터가 필요하지 않을 수도 있지만 Microsoft Managed Desktop 장치에서 네트워크 연결을 위해 일부 커넥터가 필요한지 평가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="38df6-139">It's possible you don't need any connectors, but you should evaluate whether you might need some for network connectivity on your Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="38df6-140">자세한 내용은 Microsoft Managed Desktop에 대한 인증서 및 네트워크 프로필 [준비를 참조하세요.](certs-wifi-lan.md)</span><span class="sxs-lookup"><span data-stu-id="38df6-140">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>

<span data-ttu-id="38df6-141">**권고**</span><span class="sxs-lookup"><span data-stu-id="38df6-141">**Advisory**</span></span>

<span data-ttu-id="38df6-142">하나 이상의 인증서 커넥터에 오류가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38df6-142">At least one certificate connector has an error.</span></span> <span data-ttu-id="38df6-143">Microsoft Managed Desktop 장치에 인증서를 제공하기 위해 이 커넥터가 필요한 경우 오류를 해결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="38df6-143">If you need this connector for providing certificates to Microsoft Managed Desktop devices, you must resolve the error.</span></span> <span data-ttu-id="38df6-144">자세한 내용은 Microsoft Managed Desktop에 대한 인증서 및 네트워크 프로필 [준비를 참조하세요.](certs-wifi-lan.md)</span><span class="sxs-lookup"><span data-stu-id="38df6-144">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>


<span data-ttu-id="38df6-145">**권고**</span><span class="sxs-lookup"><span data-stu-id="38df6-145">**Advisory**</span></span>

<span data-ttu-id="38df6-146">인증서 커넥터가 하나 이상 있으며 오류가 보고되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="38df6-146">You have at least one certificate connector and no errors are reported.</span></span> <span data-ttu-id="38df6-147">그러나 배포를 준비할 때 Microsoft Managed Desktop 디바이스용 커넥터를 다시 사용할 프로필을 만들어야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38df6-147">However, in preparation for deployment, you might need to create a profile to reuse the connector for Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="38df6-148">자세한 내용은 Microsoft Managed Desktop에 대한 인증서 및 네트워크 프로필 [준비를 참조하세요.](certs-wifi-lan.md)</span><span class="sxs-lookup"><span data-stu-id="38df6-148">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>


### <a name="conditional-access-policies"></a><span data-ttu-id="38df6-149">조건부 액세스 정책</span><span class="sxs-lookup"><span data-stu-id="38df6-149">Conditional access policies</span></span>

<span data-ttu-id="38df6-150">조건부 액세스 정책은 Microsoft Managed Desktop이 Intune 및 Azure AD에서 Azure AD 조직(테넌트)을 관리하는 것을 방지하지 말아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="38df6-150">Conditional access policies must not prevent Microsoft Managed Desktop from managing your Azure AD organization (tenant) in Intune and Azure AD.</span></span>

<span data-ttu-id="38df6-151">**준비되지 않음**</span><span class="sxs-lookup"><span data-stu-id="38df6-151">**Not ready**</span></span>

<span data-ttu-id="38df6-152">모든 사용자를 대상으로 하는 조건부 액세스 정책이 하나 이상 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38df6-152">You have at least one conditional access policy that targets all users.</span></span> <span data-ttu-id="38df6-153">등록하는 동안 Microsoft Managed Desktop 서비스 계정을 관련 조건부 액세스 정책에서 제외하고 이러한 계정에 대한 액세스를 제한하기 위해 새 조건부 액세스 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="38df6-153">During enrollment, we will exclude Microsoft Managed Desktop service accounts from relevant conditional access policies and apply new conditional access policies to restrict access to these accounts.</span></span> <span data-ttu-id="38df6-154">등록 후 Microsoft Endpoint Manager에서 Microsoft Managed Desktop 조건부 액세스 정책을 검토할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38df6-154">After enrollment, you can review the Microsoft Managed Desktop conditional access policy in Microsoft Endpoint Manager.</span></span> <span data-ttu-id="38df6-155">이러한 서비스 계정에 대한 자세한 내용은 Standard 운영 [절차를 참조합니다.](../service-description/operations-and-monitoring.md#standard-operating-procedures)</span><span class="sxs-lookup"><span data-stu-id="38df6-155">For more about these service accounts, see [Standard operating procedures](../service-description/operations-and-monitoring.md#standard-operating-procedures).</span></span>

<span data-ttu-id="38df6-156">**권고**</span><span class="sxs-lookup"><span data-stu-id="38df6-156">**Advisory**</span></span>

<span data-ttu-id="38df6-157">Microsoft Managed Desktop이 Microsoft Managed Desktop 서비스를 관리하지 못하게 할 수 있는 조건부 액세스 정책이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38df6-157">You have conditional access policies that could prevent Microsoft Managed Desktop from managing the Microsoft Managed Desktop service.</span></span> <span data-ttu-id="38df6-158">등록하는 동안 Microsoft Managed Desktop 서비스 계정을 관련 조건부 액세스 정책에서 제외하고 이러한 계정에 대한 액세스를 제한하기 위해 새 조건부 액세스 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="38df6-158">During enrollment, we will exclude Microsoft Managed Desktop service accounts from relevant conditional access policies and apply new conditional access policies to restrict access to these accounts.</span></span> <span data-ttu-id="38df6-159">이러한 서비스 계정에 대한 자세한 내용은 Standard 운영 [절차를 참조합니다.](../service-description/operations-and-monitoring.md#standard-operating-procedures)</span><span class="sxs-lookup"><span data-stu-id="38df6-159">For more about these service accounts, see [Standard operating procedures](../service-description/operations-and-monitoring.md#standard-operating-procedures).</span></span>

<span data-ttu-id="38df6-160">**오류**</span><span class="sxs-lookup"><span data-stu-id="38df6-160">**Error**</span></span>

<span data-ttu-id="38df6-161">Intune 관리자 역할에는 이 검사에 대한 충분한 권한이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="38df6-161">The Intune Administrator role doesn't have sufficient permissions for this check.</span></span> <span data-ttu-id="38df6-162">이 검사를 실행하려면 다음 Azure AD 역할도 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="38df6-162">You'll also need any of these Azure AD roles assigned to run this check:</span></span>

- <span data-ttu-id="38df6-163">보안 읽기 권한자</span><span class="sxs-lookup"><span data-stu-id="38df6-163">Security Reader</span></span>
- <span data-ttu-id="38df6-164">보안 관리자</span><span class="sxs-lookup"><span data-stu-id="38df6-164">Security Administrator</span></span>
- <span data-ttu-id="38df6-165">조건부 액세스 관리자</span><span class="sxs-lookup"><span data-stu-id="38df6-165">Conditional Access Administrator</span></span>
- <span data-ttu-id="38df6-166">전역 읽기 권한자</span><span class="sxs-lookup"><span data-stu-id="38df6-166">Global Reader</span></span>
- <span data-ttu-id="38df6-167">장치 관리자</span><span class="sxs-lookup"><span data-stu-id="38df6-167">Devices Administrator</span></span>


### <a name="device-compliance-policies"></a><span data-ttu-id="38df6-168">장치 준수 정책</span><span class="sxs-lookup"><span data-stu-id="38df6-168">Device Compliance policies</span></span>

<span data-ttu-id="38df6-169">Azure AD 조직의 Intune 장치 준수 정책은 Microsoft Managed Desktop 장치에 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38df6-169">Intune Device Compliance policies in your Azure AD organization might impact Microsoft Managed Desktop devices.</span></span>

<span data-ttu-id="38df6-170">**준비되지 않음**</span><span class="sxs-lookup"><span data-stu-id="38df6-170">**Not ready**</span></span>

<span data-ttu-id="38df6-171">모든 사용자를 대상으로 하는 규정 준수 정책이 하나 이상 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38df6-171">You have at least one compliance policy that targets all users.</span></span> <span data-ttu-id="38df6-172">Microsoft Managed Desktop에는 Microsoft Managed Desktop 장치를 대상으로 하는 준수 정책이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38df6-172">Microsoft Managed Desktop includes compliance policies that will target your Microsoft Managed Desktop devices.</span></span>  <span data-ttu-id="38df6-173">Microsoft Managed Desktop 사용자 또는 장치를 포함하지 않는 특정 Azure AD 그룹을 대상으로 하는 정책을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="38df6-173">Change the policy to target a specific Azure AD group that does not include any Microsoft Managed Desktop users or devices.</span></span> <span data-ttu-id="38df6-174">자세한 단계는 [Microsoft Intune에서](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy)준수 정책 만들기를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="38df6-174">For steps, see [Create a compliance policy in Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy).</span></span>

<span data-ttu-id="38df6-175">**권고**</span><span class="sxs-lookup"><span data-stu-id="38df6-175">**Advisory**</span></span>

<span data-ttu-id="38df6-176">Microsoft Managed Desktop 사용자를 대상으로 지정하지 않은 준수 정책이 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="38df6-176">Make sure that any compliance policies you have don't target any Microsoft Managed Desktop users.</span></span> <span data-ttu-id="38df6-177">자세한 단계는 [Microsoft Intune에서](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy)준수 정책 만들기를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="38df6-177">For steps, see [Create a compliance policy in Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy).</span></span>



### <a name="device-configuration-profiles"></a><span data-ttu-id="38df6-178">장치 구성 프로필</span><span class="sxs-lookup"><span data-stu-id="38df6-178">Device Configuration profiles</span></span>

<span data-ttu-id="38df6-179">Azure AD 조직의 Intune 장치 구성 프로필은 Microsoft Manage Desktop 장치 또는 사용자를 대상으로 지정하지 말아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="38df6-179">Intune Device Configuration profiles in your Azure AD organization must not target any Microsoft Manage Desktop devices or users.</span></span>

<span data-ttu-id="38df6-180">**준비되지 않음**</span><span class="sxs-lookup"><span data-stu-id="38df6-180">**Not ready**</span></span>

<span data-ttu-id="38df6-181">모든 사용자, 모든 장치 또는 둘 다를 대상으로 하는 구성 프로필이 하나 이상 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38df6-181">You have at least one configuration profile that targets all users, all devices, or both.</span></span> <span data-ttu-id="38df6-182">프로필을 다시 설정하여 Microsoft Managed Desktop 장치를 포함하지 않는 특정 Azure AD 그룹을 대상으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="38df6-182">Reset the profile to target a specific Azure AD group that does not include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="38df6-183">단계는 Microsoft [Intune에서](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure)사용자 지정 설정을 사용하여 프로필 만들기를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="38df6-183">For steps, see [Create a profile with custom settings in Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure).</span></span>

<span data-ttu-id="38df6-184">**권고**</span><span class="sxs-lookup"><span data-stu-id="38df6-184">**Advisory**</span></span>

<span data-ttu-id="38df6-185">Microsoft Managed Desktop 장치 또는 사용자를 포함하지 않은 구성 정책이 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="38df6-185">Make sure that any configuration policies you have don't include any Microsoft Managed Desktop devices or users.</span></span> <span data-ttu-id="38df6-186">단계는 Microsoft [Intune에서](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure)사용자 지정 설정을 사용하여 프로필 만들기를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="38df6-186">For steps, see [Create a profile with custom settings in Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure).</span></span>



### <a name="device-type-restrictions"></a><span data-ttu-id="38df6-187">장치 유형 제한</span><span class="sxs-lookup"><span data-stu-id="38df6-187">Device type restrictions</span></span>

<span data-ttu-id="38df6-188">Microsoft Managed Desktop 장치는 Intune에 등록할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="38df6-188">Microsoft Managed Desktop devices must be allowed to enroll in Intune.</span></span>

<span data-ttu-id="38df6-189">**준비되지 않음**</span><span class="sxs-lookup"><span data-stu-id="38df6-189">**Not ready**</span></span>

<span data-ttu-id="38df6-190">현재 Windows 장치가 Intune에 등록되지 않도록 등록 제한 정책을 하나 이상 구성했습니다.</span><span class="sxs-lookup"><span data-stu-id="38df6-190">You currently have at least one enrollment restriction policy configured to prevent Windows devices from enrollment in Intune.</span></span> <span data-ttu-id="38df6-191">Microsoft Managed [](https://docs.microsoft.com/mem/intune/enrollment/enrollment-restrictions-set) Desktop 사용자를 대상으로 하는 각 등록 제한 정책에 대한 등록 제한 설정 단계를 따르고 **Windows(MDM)** 설정을 허용으로 **변경합니다.**</span><span class="sxs-lookup"><span data-stu-id="38df6-191">Follow the steps in [Set enrollment restrictions](https://docs.microsoft.com/mem/intune/enrollment/enrollment-restrictions-set) for each enrollment restriction policy that targets Microsoft Managed Desktop users and change the **Windows (MDM)** setting to **Allow**.</span></span> <span data-ttu-id="38df6-192">그러나 개인  **소유의 Windows(MDM)** 장치를 차단으로 설정할 수 **있습니다.**</span><span class="sxs-lookup"><span data-stu-id="38df6-192">You can, however, set any **personally owned** **Windows (MDM)** devices to **Block**.</span></span> 


### <a name="enrollment-status-page"></a><span data-ttu-id="38df6-193">등록 상태 페이지</span><span class="sxs-lookup"><span data-stu-id="38df6-193">Enrollment Status Page</span></span>

<span data-ttu-id="38df6-194">현재 ESP(등록 상태 페이지)를 사용하도록 설정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38df6-194">You currently have the Enrollment Status Page (ESP) enabled.</span></span> <span data-ttu-id="38df6-195">이 기능의 Microsoft Managed Desktop 공개 미리 보기에 참여하려는 경우 이 항목을 무시해도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="38df6-195">If you intend to participate in the Microsoft Managed Desktop public preview of this feature, you can ignore this item.</span></span> <span data-ttu-id="38df6-196">자세한 내용은 Autopilot 및 등록 상태 페이지의 첫 실행 [환경을 참조하세요.](../get-started/esp-first-run.md)</span><span class="sxs-lookup"><span data-stu-id="38df6-196">For more information, see [First-run experience with Autopilot and the Enrollment Status Page](../get-started/esp-first-run.md).</span></span>

<span data-ttu-id="38df6-197">**준비되지 않음**</span><span class="sxs-lookup"><span data-stu-id="38df6-197">**Not ready**</span></span>

<span data-ttu-id="38df6-198">ESP 기본 프로필이 앱 및 프로필 구성 진행률 **표시로 설정되어 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="38df6-198">You have the ESP default profile set to **Show app and profile configuration progress**.</span></span> <span data-ttu-id="38df6-199">이 설정을 사용하지 않도록 설정하거나 등록 상태 설정 페이지의 단계에 따라 Azure AD 그룹에 대한 할당에 Microsoft Managed Desktop 장치가 포함되어 [있지 않은지 확인하십시오.](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status)</span><span class="sxs-lookup"><span data-stu-id="38df6-199">Disable this setting or make sure that assignments to any Azure AD group do not include Microsoft Managed Desktop devices by following the steps in [Set up the Enrollment Status Page](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status).</span></span>

<span data-ttu-id="38df6-200">**권고**</span><span class="sxs-lookup"><span data-stu-id="38df6-200">**Advisory**</span></span>

<span data-ttu-id="38df6-201">앱 및 프로필 구성 진행률 표시 설정이 있는 프로필이 Microsoft Managed Desktop 장치를 포함하는 Azure AD 그룹에 할당되어 있지 않은지 확인 </span><span class="sxs-lookup"><span data-stu-id="38df6-201">Make sure that any profiles that have the **Show app and profile configuration progress** setting are not assigned to any Azure AD group that includes Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="38df6-202">자세한 내용은 등록 상태 페이지 [설정을 참조하십시오.](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status)</span><span class="sxs-lookup"><span data-stu-id="38df6-202">For more information, see [Set up the Enrollment Status Page](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status).</span></span>

### <a name="microsoft-store-for-business"></a><span data-ttu-id="38df6-203">비즈니스용 Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="38df6-203">Microsoft Store for Business</span></span>

<span data-ttu-id="38df6-204">Microsoft는 비즈니스용 Microsoft Store를 사용하며 Microsoft Managed Desktop에 회사 포털 앱을 배포하여 사용자가 Microsoft Project 및 Microsoft Visio(허용되는 경우)과 같은 일부 앱을 선택적으로 설치할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="38df6-204">We use Microsoft Store for Business and deploy the Company Portal app on Microsoft Managed Desktop to allow users to optionally install some apps, such as Microsoft Project and Microsoft Visio (where permitted).</span></span>

<span data-ttu-id="38df6-205">**준비되지 않음**</span><span class="sxs-lookup"><span data-stu-id="38df6-205">**Not ready**</span></span>

<span data-ttu-id="38df6-206">비즈니스용 Microsoft Store를 사용하도록 설정하지 않은 경우 또는 Intune과 동기화되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="38df6-206">Microsoft Store for Business either isn't enabled or isn't synced with Intune.</span></span> <span data-ttu-id="38df6-207">자세한 내용은 장치에서 [Microsoft Intune 및 Intune](https://docs.microsoft.com/mem/intune/apps/windows-store-for-business) 회사 포털을 설치하여 비즈니스용 Microsoft Store에서 대량 구매 앱을 관리하는 [방법을 참조하세요.](../get-started/company-portal.md)</span><span class="sxs-lookup"><span data-stu-id="38df6-207">For more information, see [How to manage volume purchased apps from the Microsoft Store for Business with Microsoft Intune](https://docs.microsoft.com/mem/intune/apps/windows-store-for-business) and [Install Intune Company Portal on devices](../get-started/company-portal.md).</span></span>

### <a name="multifactor-authentication"></a><span data-ttu-id="38df6-208">다단계 인증</span><span class="sxs-lookup"><span data-stu-id="38df6-208">Multifactor authentication</span></span>

<span data-ttu-id="38df6-209">다단계 인증을 통해 Microsoft Managed Desktop이 Intune 및 Azure AD에서 Azure AD 조직(테넌트)을 관리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="38df6-209">Multifactor authentication must not prevent Microsoft Managed Desktop from managing your Azure AD organization (tenant) in Intune and Azure AD.</span></span>


<span data-ttu-id="38df6-210">**준비되지 않음**</span><span class="sxs-lookup"><span data-stu-id="38df6-210">**Not ready**</span></span>

<span data-ttu-id="38df6-211">모든 사용자에게 할당된 조건부 액세스  정책에 필요한 몇 가지 다단계 인증 정책이 설정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38df6-211">You have some multifactor authentication policies set as **required** for conditional access policies that are assigned to all users.</span></span> <span data-ttu-id="38df6-212">등록하는 동안 Microsoft Managed Desktop 서비스 계정을 관련 조건부 액세스 정책에서 제외하고 이러한 계정에 대한 액세스를 제한하기 위해 새 조건부 액세스 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="38df6-212">During enrollment, we will exclude Microsoft Managed Desktop service accounts from relevant conditional access policies and apply new conditional access policies to restrict access to these accounts.</span></span> <span data-ttu-id="38df6-213">이러한 서비스 계정에 대한 자세한 내용은 Standard 운영 [절차를 참조합니다.](../service-description/operations-and-monitoring.md#standard-operating-procedures)</span><span class="sxs-lookup"><span data-stu-id="38df6-213">For more about these service accounts, see [Standard operating procedures](../service-description/operations-and-monitoring.md#standard-operating-procedures).</span></span>

<span data-ttu-id="38df6-214">**권고**</span><span class="sxs-lookup"><span data-stu-id="38df6-214">**Advisory**</span></span>

<span data-ttu-id="38df6-215">Microsoft Managed Desktop이 Microsoft Managed Desktop 서비스를 관리하지 못하도록 하는 조건부 액세스 정책에 다단계 인증이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="38df6-215">You have multifactor authentication required on conditional access policies that could prevent Microsoft Managed Desktop from managing the Microsoft Managed Desktop service.</span></span> <span data-ttu-id="38df6-216">등록하는 동안 Microsoft Managed Desktop 서비스 계정을 관련 조건부 액세스 정책에서 제외하고 이러한 계정에 대한 액세스를 제한하기 위해 새 조건부 액세스 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="38df6-216">During enrollment, we will exclude Microsoft Managed Desktop service accounts from relevant conditional access policies and apply new conditional access policies to restrict access to these accounts.</span></span> <span data-ttu-id="38df6-217">이러한 서비스 계정에 대한 자세한 내용은 Standard 운영 [절차를 참조합니다.](../service-description/operations-and-monitoring.md#standard-operating-procedures)</span><span class="sxs-lookup"><span data-stu-id="38df6-217">For more about these service accounts, see [Standard operating procedures](../service-description/operations-and-monitoring.md#standard-operating-procedures).</span></span>

<span data-ttu-id="38df6-218">**오류**</span><span class="sxs-lookup"><span data-stu-id="38df6-218">**Error**</span></span>

<span data-ttu-id="38df6-219">Intune 관리자 역할에는 이 검사에 대한 충분한 권한이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="38df6-219">The Intune Administrator role doesn't have sufficient permissions for this check.</span></span> <span data-ttu-id="38df6-220">이 검사를 실행하려면 다음 Azure AD 역할도 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="38df6-220">You'll also need any of these Azure AD roles assigned to run this check:</span></span>

- <span data-ttu-id="38df6-221">보안 읽기 권한자</span><span class="sxs-lookup"><span data-stu-id="38df6-221">Security Reader</span></span>
- <span data-ttu-id="38df6-222">보안 관리자</span><span class="sxs-lookup"><span data-stu-id="38df6-222">Security Administrator</span></span>
- <span data-ttu-id="38df6-223">조건부 액세스 관리자</span><span class="sxs-lookup"><span data-stu-id="38df6-223">Conditional Access Administrator</span></span>
- <span data-ttu-id="38df6-224">전역 읽기 권한자</span><span class="sxs-lookup"><span data-stu-id="38df6-224">Global Reader</span></span>
- <span data-ttu-id="38df6-225">장치 관리자</span><span class="sxs-lookup"><span data-stu-id="38df6-225">Devices Administrator</span></span>


### <a name="powershell-scripts"></a><span data-ttu-id="38df6-226">PowerShell 스크립트</span><span class="sxs-lookup"><span data-stu-id="38df6-226">PowerShell scripts</span></span>

<span data-ttu-id="38df6-227">Windows PowerShell Microsoft Managed Desktop 장치를 대상으로 하는 방식으로 스크립트를 할당할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="38df6-227">Windows PowerShell scripts can't be assigned in a way that would target Microsoft Managed Desktop devices.</span></span>  

<span data-ttu-id="38df6-228">**권고**</span><span class="sxs-lookup"><span data-stu-id="38df6-228">**Advisory**</span></span>

<span data-ttu-id="38df6-229">Azure AD Windows PowerShell 스크립트가 Microsoft Manage Desktop 장치 또는 사용자를 대상으로 하지 않는지 확인</span><span class="sxs-lookup"><span data-stu-id="38df6-229">Make sure that Windows PowerShell scripts in your Azure AD organization don't target any Microsoft Manage Desktop devices or users.</span></span> <span data-ttu-id="38df6-230">모든 사용자, 모든 장치 또는 둘 다를 대상으로 하는 PowerShell 스크립트를 할당하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="38df6-230">Do not assign a PowerShell script to target all users, all devices, or both.</span></span> <span data-ttu-id="38df6-231">Microsoft Managed Desktop 장치 또는 사용자를 포함하지 않는 특정 Azure AD 그룹을 대상으로 하는 할당을 사용하도록 정책을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="38df6-231">Change the policy to use an Assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices or users.</span></span> <span data-ttu-id="38df6-232">자세한 내용은 [Intune의 Windows 10 장치에서 PowerShell 스크립트 사용을 참조하세요.](https://docs.microsoft.com/mem/intune/apps/intune-management-extension)</span><span class="sxs-lookup"><span data-stu-id="38df6-232">For more information, see [Use PowerShell scripts on Windows 10 devices in Intune](https://docs.microsoft.com/mem/intune/apps/intune-management-extension).</span></span>

### <a name="region"></a><span data-ttu-id="38df6-233">Region</span><span class="sxs-lookup"><span data-stu-id="38df6-233">Region</span></span>

<span data-ttu-id="38df6-234">해당 지역은 Microsoft Managed Desktop에서 지원해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="38df6-234">Your region must be supported by Microsoft Managed Desktop.</span></span>

<span data-ttu-id="38df6-235">**준비되지 않음**</span><span class="sxs-lookup"><span data-stu-id="38df6-235">**Not ready**</span></span>

<span data-ttu-id="38df6-236">Azure AD 조직 지역은 현재 Microsoft Managed Desktop에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="38df6-236">Your Azure AD organization region isn't currently supported by Microsoft Managed Desktop.</span></span> <span data-ttu-id="38df6-237">자세한 내용은 Microsoft Managed Desktop 지원 지역 및 [언어를 참조하세요.](../service-description/regions-languages.md)</span><span class="sxs-lookup"><span data-stu-id="38df6-237">For more information, see [Microsoft Managed Desktop supported regions and languages](../service-description/regions-languages.md).</span></span>

<span data-ttu-id="38df6-238">**권고**</span><span class="sxs-lookup"><span data-stu-id="38df6-238">**Advisory**</span></span>

<span data-ttu-id="38df6-239">Azure AD 조직이 있는 하나 이상의 국가는 Microsoft Managed Desktop에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="38df6-239">One or more of the countries where your Azure AD organization is located isn't supported by Microsoft Managed Desktop.</span></span> <span data-ttu-id="38df6-240">자세한 내용은 Microsoft Managed Desktop 지원 지역 및 [언어를 참조하세요.](../service-description/regions-languages.md)</span><span class="sxs-lookup"><span data-stu-id="38df6-240">For more information, see [Microsoft Managed Desktop supported regions and languages](../service-description/regions-languages.md).</span></span>


### <a name="security-baselines"></a><span data-ttu-id="38df6-241">보안 기준</span><span class="sxs-lookup"><span data-stu-id="38df6-241">Security baselines</span></span>

<span data-ttu-id="38df6-242">보안 기준 정책은 Microsoft Managed Desktop 장치를 대상으로 하지 말아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="38df6-242">Security baseline policies should not target any Microsoft Managed Desktop devices.</span></span>

<span data-ttu-id="38df6-243">**준비되지 않음**</span><span class="sxs-lookup"><span data-stu-id="38df6-243">**Not ready**</span></span>

<span data-ttu-id="38df6-244">모든 사용자, 모든 장치 또는 둘 다를 대상으로 하는 보안 기준 프로필이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38df6-244">You have a security baseline profile that targets all users, all devices, or both.</span></span> <span data-ttu-id="38df6-245">Microsoft Managed Desktop 장치를 포함하지 않는 특정 Azure AD 그룹을 대상으로 하는 할당을 사용하도록 정책을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="38df6-245">Change the policy to use an assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="38df6-246">단계는 보안 기준을 사용하여 [Intune에서 Windows 10 디바이스를 구성합니다.](https://docs.microsoft.com/mem/intune/protect/security-baselines)</span><span class="sxs-lookup"><span data-stu-id="38df6-246">For steps, see [Use security baselines to configure Windows 10 devices in Intune](https://docs.microsoft.com/mem/intune/protect/security-baselines).</span></span> <span data-ttu-id="38df6-247">등록하는 동안 모든 Microsoft Managed Desktop 장치에 새 보안 기준을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="38df6-247">During enrollment, we apply a new security baseline to all Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="38df6-248">등록 후 Microsoft Endpoint Manager의 구성 정책 영역에  있는 Microsoft Managed Desktop 보안 기준 정책을 검토할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38df6-248">After enrollment, you can review the Microsoft Managed Desktop security baseline policy in the **Configuration policy** area of Microsoft Endpoint Manager.</span></span>

<span data-ttu-id="38df6-249">**권고**</span><span class="sxs-lookup"><span data-stu-id="38df6-249">**Advisory**</span></span>

<span data-ttu-id="38df6-250">Microsoft Managed Desktop 장치를 제외한 보안 기준 정책이 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="38df6-250">Make sure that any security baseline policies you have exclude Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="38df6-251">단계는 보안 기준을 사용하여 [Intune에서 Windows 10 디바이스를 구성합니다.](https://docs.microsoft.com/mem/intune/protect/security-baselines)</span><span class="sxs-lookup"><span data-stu-id="38df6-251">For steps, see [Use security baselines to configure Windows 10 devices in Intune](https://docs.microsoft.com/mem/intune/protect/security-baselines).</span></span> <span data-ttu-id="38df6-252">등록하는 동안 모든 Microsoft Managed Desktop 장치에 새 보안 기준을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="38df6-252">During enrollment, we apply a new security baseline to all Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="38df6-253">최신 작업 공간 **장치 - 모든** Azure AD 그룹은 Microsoft Managed Desktop에 등록할 때 만드는 동적 그룹이기 때문에 등록 후 이 그룹을 제외하기 위해 돌아와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="38df6-253">The **Modern Workplace Devices -All** Azure AD group is a dynamic group that we create when you enroll in Microsoft Managed Desktop, so you'll have to come back to exclude this group after enrollment.</span></span> 


### <a name="windows-apps"></a><span data-ttu-id="38df6-254">Windows 앱</span><span class="sxs-lookup"><span data-stu-id="38df6-254">Windows apps</span></span>

<span data-ttu-id="38df6-255">Microsoft Managed Desktop 사용자에게 필요한 앱을 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="38df6-255">Review apps you want your Microsoft Managed Desktop users to have.</span></span>

<span data-ttu-id="38df6-256">**권고**</span><span class="sxs-lookup"><span data-stu-id="38df6-256">**Advisory**</span></span>

<span data-ttu-id="38df6-257">Microsoft Managed Desktop 사용자에게 필요한 앱의 인벤토리를 준비해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="38df6-257">You should prepare an inventory of the apps that you want your Microsoft Managed Desktop users to have.</span></span> <span data-ttu-id="38df6-258">이러한 앱은 Intune에서 배포해야 하기 때문에 기존 Intune 앱을 다시 사용하는지 평가합니다.</span><span class="sxs-lookup"><span data-stu-id="38df6-258">Since these apps must be deployed by Intune, evaluate reusing existing Intune apps.</span></span> <span data-ttu-id="38df6-259">회사 포털(장치에 [Intune 회사](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/company-portal) 포털 설치 및 ESP(등록 상태 페이지) 참조)을 사용하여 사용자에게 앱을 배포하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="38df6-259">Consider using Company Portal (see [Install Intune Company Portal on devices](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/company-portal) and Enrollment Status Page (ESP) to distribute apps to your users.</span></span> <span data-ttu-id="38df6-260">자세한 내용은 Autopilot 및 등록 상태 페이지에서 [Microsoft Managed Desktop의](apps.md) 앱 및 첫 실행 환경을 [참조하세요.](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/esp-first-run)</span><span class="sxs-lookup"><span data-stu-id="38df6-260">For more information, see [Apps in Microsoft Managed Desktop](apps.md) and [First-run experience with Autopilot and the Enrollment Status Page](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/esp-first-run).</span></span>

<span data-ttu-id="38df6-261">Microsoft Endpoint Configuration Manager의 쿼리를 Microsoft 계정 담당자에게 요청하여 Intune으로 마이그레이션할 준비가 되거나 조정이 필요한 앱을 식별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38df6-261">You can ask your Microsoft account representative for a query in Microsoft Endpoint Configuration Manager to identify those apps that are ready to migrate to Intune or need adjustment.</span></span>


### <a name="windows-hello-for-business"></a><span data-ttu-id="38df6-262">비즈니스용 Windows Hello</span><span class="sxs-lookup"><span data-stu-id="38df6-262">Windows Hello for Business</span></span>

<span data-ttu-id="38df6-263">Microsoft Managed Desktop을 사용하려면 비즈니스용 Windows Hello를 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="38df6-263">Microsoft Managed Desktop requires Windows Hello for Business to be enabled.</span></span>

<span data-ttu-id="38df6-264">**준비되지 않음**</span><span class="sxs-lookup"><span data-stu-id="38df6-264">**Not ready**</span></span>

<span data-ttu-id="38df6-265">비즈니스용 Windows Hello를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="38df6-265">Windows Hello for Business is disabled.</span></span> <span data-ttu-id="38df6-266">비즈니스용 [Windows Hello](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy) 만들기 정책의 단계에 따라 사용하도록 설정</span><span class="sxs-lookup"><span data-stu-id="38df6-266">Enable it by following the steps in [Create a Windows Hello for Business policy](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)</span></span>

<span data-ttu-id="38df6-267">**권고**</span><span class="sxs-lookup"><span data-stu-id="38df6-267">**Advisory**</span></span>

<span data-ttu-id="38df6-268">비즈니스용 Windows Hello가 설정되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="38df6-268">Windows Hello for Business is not set up.</span></span> <span data-ttu-id="38df6-269">비즈니스용 Windows Hello 만들기 정책의 단계에 따라 사용하도록 [설정하십시오.](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)</span><span class="sxs-lookup"><span data-stu-id="38df6-269">Enable it by following the steps in [Create a Windows Hello for Business policy](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy).</span></span>


### <a name="windows-10-update-rings"></a><span data-ttu-id="38df6-270">Windows 10 업데이트 링</span><span class="sxs-lookup"><span data-stu-id="38df6-270">Windows 10 update rings</span></span>

<span data-ttu-id="38df6-271">Intune의 "Windows 10 업데이트 링" 정책은 Microsoft Managed Desktop 장치를 대상으로 지정하지 말아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="38df6-271">Your "Windows 10 update ring" policy in Intune must not target any Microsoft Managed Desktop devices.</span></span>

<span data-ttu-id="38df6-272">**준비되지 않음**</span><span class="sxs-lookup"><span data-stu-id="38df6-272">**Not ready**</span></span>

<span data-ttu-id="38df6-273">모든 장치, 모든 사용자 또는 둘 다를 대상으로 하는 "업데이트 링" 정책이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38df6-273">You have an "update ring" policy that targets all devices, all users, or both.</span></span> <span data-ttu-id="38df6-274">Microsoft Managed Desktop 장치를 포함하지 않는 특정 Azure AD 그룹을 대상으로 하는 할당을 사용하도록 정책을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="38df6-274">Change the policy to use an Assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="38df6-275">단계는 [Intune에서 Windows 10 소프트웨어 업데이트 관리를 참조하세요.](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure)</span><span class="sxs-lookup"><span data-stu-id="38df6-275">For steps, see [Manage Windows 10 software updates in Intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure).</span></span>

<span data-ttu-id="38df6-276">**권고**</span><span class="sxs-lookup"><span data-stu-id="38df6-276">**Advisory**</span></span>

<span data-ttu-id="38df6-277">최신 작업 공간 장치 -모든 Azure AD 그룹을 제외한 모든 업데이트 **링** 정책이 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="38df6-277">Make sure that any update ring policies you have exclude the **Modern Workplace Devices -All** Azure AD group.</span></span> <span data-ttu-id="38df6-278">이러한 정책에 Azure AD 사용자 그룹을 할당한 경우 Microsoft Managed Desktop 사용자를 추가하는 최신 **Workplace -All** Azure AD 그룹(또는 동등한 그룹)도 제외한 업데이트 링 정책이 있는지 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="38df6-278">If you have assigned Azure AD user groups to these policies, make sure that any update ring policies you have also excluded the **Modern Workplace -All** Azure AD group that you add your Microsoft Managed Desktop users to (or an equivalent group).</span></span> <span data-ttu-id="38df6-279">단계는 [Intune에서 Windows 10 소프트웨어 업데이트 관리를 참조하세요.](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure)</span><span class="sxs-lookup"><span data-stu-id="38df6-279">For steps, see [Manage Windows 10 software updates in Intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure).</span></span> <span data-ttu-id="38df6-280">최신 작업 공간 장치 **-All** 및 **Modern Workplace -All** Azure AD 그룹은 Microsoft Managed Desktop에 등록할 때 만든 그룹이기 때문에 등록 후 이 그룹을 제외하기 위해 다시 돌아와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="38df6-280">Both the **Modern Workplace Devices -All** and **Modern Workplace -All** Azure AD groups are groups that we create when you enroll in Microsoft Managed Desktop, so you'll have to come back to exclude this group after enrollment.</span></span>


## <a name="azure-active-directory-settings"></a><span data-ttu-id="38df6-281">Azure Active Directory 설정</span><span class="sxs-lookup"><span data-stu-id="38df6-281">Azure Active Directory settings</span></span>

<span data-ttu-id="38df6-282">Azure Portal에서 Azure Active Directory [설정에 액세스할 수 있습니다.](https://portal.azure.com)</span><span class="sxs-lookup"><span data-stu-id="38df6-282">You can access Azure Active Directory settings at the [Azure portal](https://portal.azure.com).</span></span>

### <a name="intune-enrollment"></a><span data-ttu-id="38df6-283">Intune 등록</span><span class="sxs-lookup"><span data-stu-id="38df6-283">Intune enrollment</span></span>

<span data-ttu-id="38df6-284">Azure AD 조직의 Windows 10 장치는 Intune에 자동으로 등록할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="38df6-284">Windows 10 devices in your Azure AD organization must be able to automatically enroll in Intune.</span></span>

<span data-ttu-id="38df6-285">**권고**</span><span class="sxs-lookup"><span data-stu-id="38df6-285">**Advisory**</span></span>

<span data-ttu-id="38df6-286">**MDM 사용자** 범위가 **없음이** 아닌 일부 또는 **모두로** 설정되어 있는지 **확인**</span><span class="sxs-lookup"><span data-stu-id="38df6-286">Make sure the **MDM User scope** is set to **Some** or **All**, not **None**.</span></span> <span data-ttu-id="38df6-287">일부를 선택하는 경우 등록 후 돌아와서 모든 Microsoft Managed  Desktop 사용자를 대상으로 하는 최신 작업 공간 **-그룹에** 대한 모든 Azure AD 그룹 또는 동등한 그룹을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="38df6-287">If you choose **Some**, come back after enrollment and select the **Modern Workplace -All** Azure AD group for **Groups** or an equivalent group targeting all of your Microsoft Managed Desktop users.</span></span>  <span data-ttu-id="38df6-288">Microsoft Intune을 사용하여 Windows 장치에 대한 등록 [설정을 참조합니다.](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)</span><span class="sxs-lookup"><span data-stu-id="38df6-288">See [Set up enrollment for Windows devices by using Microsoft Intune](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment).</span></span>


### <a name="ad-hoc-subscriptions"></a><span data-ttu-id="38df6-289">Ad Hoc 구독</span><span class="sxs-lookup"><span data-stu-id="38df6-289">Ad hoc subscriptions</span></span>

<span data-ttu-id="38df6-290">"false"로 설정하면 엔터프라이즈 상태 로밍이 제대로 작동하지 않을 수 있는 설정을 검사하는 방법을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38df6-290">Advises how to check a setting that (if set to "false") might prevent Enterprise State Roaming from working correctly.</span></span>

<span data-ttu-id="38df6-291">**권고**</span><span class="sxs-lookup"><span data-stu-id="38df6-291">**Advisory**</span></span>

<span data-ttu-id="38df6-292">**AllowAdHocSubscriptions가** **True로** 설정되어 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="38df6-292">Ensure that **AllowAdHocSubscriptions** is set to **True**.</span></span> <span data-ttu-id="38df6-293">그렇지 않으면 엔터프라이즈 상태 로밍이 작동하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38df6-293">Otherwise, Enterprise State Roaming might not work.</span></span> <span data-ttu-id="38df6-294">자세한 내용은 [Set-MsolCompanySettings를 참조하십시오.](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0)</span><span class="sxs-lookup"><span data-stu-id="38df6-294">For more information, see [Set-MsolCompanySettings](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0).</span></span>


### <a name="enterprise-state-roaming"></a><span data-ttu-id="38df6-295">Enterprise State Roaming</span><span class="sxs-lookup"><span data-stu-id="38df6-295">Enterprise State Roaming</span></span>

<span data-ttu-id="38df6-296">엔터프라이즈 상태 로밍을 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="38df6-296">Enterprise State Roaming should be enabled.</span></span>

<span data-ttu-id="38df6-297">**권고**</span><span class="sxs-lookup"><span data-stu-id="38df6-297">**Advisory**</span></span>

<span data-ttu-id="38df6-298">Enterprise State Roaming이 전체  또는 선택한 그룹에 대해 사용하도록 **설정되어 있는지** 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="38df6-298">Make sure that Enterprise State Roaming is enabled for **All** or for **Selected** groups.</span></span> <span data-ttu-id="38df6-299">자세한 내용은 Azure Active Directory에서 엔터프라이즈 상태 [로밍 사용을 참조하세요.](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-enable)</span><span class="sxs-lookup"><span data-stu-id="38df6-299">For more information, see [Enable Enterprise State Roaming in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-enable).</span></span>

### <a name="licenses"></a><span data-ttu-id="38df6-300">라이선스</span><span class="sxs-lookup"><span data-stu-id="38df6-300">Licenses</span></span>

<span data-ttu-id="38df6-301">Microsoft Managed Desktop을 사용하려면 여러 라이선스가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="38df6-301">A number of licenses are required to use Microsoft Managed Desktop.</span></span>

<span data-ttu-id="38df6-302">**준비되지 않은 경우**</span><span class="sxs-lookup"><span data-stu-id="38df6-302">**Not Ready**</span></span>

<span data-ttu-id="38df6-303">Microsoft Managed Desktop을 사용하는 데 필요한 모든 라이선스가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="38df6-303">You don't have all the licenses you need to use Microsoft Managed Desktop.</span></span> <span data-ttu-id="38df6-304">자세한 내용은 [Microsoft Managed Desktop 기술](../intro/technologies.md) 및 [라이선스에 대한 자세한 정보를 참조하세요.](prerequisites.md#more-about-licenses)</span><span class="sxs-lookup"><span data-stu-id="38df6-304">For more information, see [Microsoft Managed Desktop technologies](../intro/technologies.md) and [More about licenses](prerequisites.md#more-about-licenses).</span></span>


### <a name="microsoft-managed-desktop-service-accounts"></a><span data-ttu-id="38df6-305">Microsoft Managed Desktop 서비스 계정</span><span class="sxs-lookup"><span data-stu-id="38df6-305">Microsoft Managed Desktop service accounts</span></span>

<span data-ttu-id="38df6-306">특정 계정 이름은 Microsoft Managed Desktop에서 만든 계정 이름과 충돌하여 Microsoft Managed Desktop 서비스를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38df6-306">Certain account names could conflict with account names created by Microsoft Managed Desktop to manage the Microsoft Managed Desktop service.</span></span>

<span data-ttu-id="38df6-307">**준비되지 않음**</span><span class="sxs-lookup"><span data-stu-id="38df6-307">**Not ready**</span></span>

<span data-ttu-id="38df6-308">하나 이상의 계정 이름이 Microsoft Managed Desktop에서 만든 계정 이름과 충돌합니다.</span><span class="sxs-lookup"><span data-stu-id="38df6-308">You have at least one account name that will conflict with account names created by Microsoft Managed Desktop.</span></span> <span data-ttu-id="38df6-309">Microsoft 계정 담당자와 함께 이러한 계정 이름을 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="38df6-309">Work with your Microsoft account representative to exclude these account names.</span></span> <span data-ttu-id="38df6-310">보안 위험을 최소화하기 위해 계정 이름을 공개적으로 나열하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="38df6-310">We don't list the account names publicly to minimize security risk.</span></span> 


### <a name="security-administrator-roles"></a><span data-ttu-id="38df6-311">보안 관리자 역할</span><span class="sxs-lookup"><span data-stu-id="38df6-311">Security administrator roles</span></span>

<span data-ttu-id="38df6-312">특정 보안 역할이 있는 사용자는 끝점용 Microsoft Defender에서 해당 역할을 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="38df6-312">Users with certain security roles must have those roles assigned in Microsoft Defender for Endpoint.</span></span>

<span data-ttu-id="38df6-313">**권고**</span><span class="sxs-lookup"><span data-stu-id="38df6-313">**Advisory**</span></span>

<span data-ttu-id="38df6-314">Azure AD 조직에서 이러한 역할에 할당된 사용자가 있는 경우 이러한 역할도 끝점용 Microsoft Defender에 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="38df6-314">If you have users assigned to any of these roles in your Azure AD organization, make sure they also have these roles assigned in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="38df6-315">그렇지 않으면 이러한 역할이 있는 관리자가 관리 포털에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="38df6-315">Otherwise, administrators with these roles won't be able to access the Admin portal.</span></span>

- <span data-ttu-id="38df6-316">보안 운영자</span><span class="sxs-lookup"><span data-stu-id="38df6-316">Security Operator</span></span>
- <span data-ttu-id="38df6-317">전역 읽기 권한자</span><span class="sxs-lookup"><span data-stu-id="38df6-317">Global Reader</span></span>

<span data-ttu-id="38df6-318">자세한 내용은 역할 기반 액세스 제어에 대한 역할 [만들기 및 관리를 참조하세요.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles)</span><span class="sxs-lookup"><span data-stu-id="38df6-318">For more information, see [Create and manage roles for role-based access control](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles).</span></span>


### <a name="security-default"></a><span data-ttu-id="38df6-319">보안 기본값</span><span class="sxs-lookup"><span data-stu-id="38df6-319">Security default</span></span>

<span data-ttu-id="38df6-320">Azure Active Directory의 보안 기본값은 Microsoft Managed Desktop이 디바이스를 관리하지 못하게 합니다.</span><span class="sxs-lookup"><span data-stu-id="38df6-320">Security defaults in Azure Active Directory will prevent Microsoft Managed Desktop from managing your devices.</span></span>

<span data-ttu-id="38df6-321">**준비되지 않음**</span><span class="sxs-lookup"><span data-stu-id="38df6-321">**Not ready**</span></span>

<span data-ttu-id="38df6-322">보안 기본값이 설정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38df6-322">You have Security defaults turned on.</span></span> <span data-ttu-id="38df6-323">보안 기본값을 해제하고 조건부 액세스 정책을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="38df6-323">Turn off Security defaults and set up conditional access policies.</span></span> <span data-ttu-id="38df6-324">자세한 내용은 [일반적인 조건부 액세스 정책을 참조하십시오.](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common)</span><span class="sxs-lookup"><span data-stu-id="38df6-324">For more information, see [Common Conditional Access policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common).</span></span>

### <a name="self-service-password-reset"></a><span data-ttu-id="38df6-325">셀프 서비스 암호 재설정</span><span class="sxs-lookup"><span data-stu-id="38df6-325">Self-service Password Reset</span></span>

<span data-ttu-id="38df6-326">Microsoft Managed Desktop 서비스 계정을 제외한 모든 Microsoft Managed Desktop 사용자에 대해 SSPR(셀프 서비스 암호 재설정)을 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38df6-326">Self-service Password Reset (SSPR) can be enabled for all Microsoft Managed Desktop users excluding Microsoft Managed Desktop service accounts.</span></span> <span data-ttu-id="38df6-327">자세한 내용은 [자습서: 사용자가 Azure Active Directory](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-enable-sspr)셀프 서비스 암호 재설정을 사용하여 계정 잠금을 해제하거나 암호를 재설정할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="38df6-327">For more information, see [Tutorial: Enable users to unlock their account or reset passwords using Azure Active Directory self-service password reset](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-enable-sspr).</span></span>

<span data-ttu-id="38df6-328">**권고**</span><span class="sxs-lookup"><span data-stu-id="38df6-328">**Advisory**</span></span>

<span data-ttu-id="38df6-329">**SSPR** 선택 설정에 Microsoft Managed Desktop 사용자가 포함되지만 Microsoft Managed Desktop 서비스 계정은 제외해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="38df6-329">Make sure that the SSPR **Selected** setting includes Microsoft Managed Desktop users but excludes Microsoft Managed Desktop service accounts.</span></span> <span data-ttu-id="38df6-330">SSPR을 사용하도록 설정하면 Microsoft Managed Desktop 서비스 계정이 예상대로 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="38df6-330">Microsoft Managed Desktop service accounts cannot work as expected when SSPR is enabled.</span></span>  


### <a name="standard-user-role"></a><span data-ttu-id="38df6-331">표준 사용자 역할</span><span class="sxs-lookup"><span data-stu-id="38df6-331">Standard user role</span></span>

<span data-ttu-id="38df6-332">전역 관리자 및 장치 관리자의 Azure AD 역할이 할당된 사용자 이외에 Microsoft Managed Desktop 사용자는 로컬 관리자 권한이 없는 표준 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="38df6-332">Other than those users who are assigned Azure AD roles of Global administrator and Device administrator, Microsoft Managed Desktop users will be standard users without local administrator privileges.</span></span> <span data-ttu-id="38df6-333">다른 모든 사용자에게는 Microsoft Managed Desktop 장치를 시작할 때 표준 사용자 역할이 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="38df6-333">All other users will be assigned a standard user role when they start their Microsoft Managed Desktop device.</span></span>

<span data-ttu-id="38df6-334">**권고**</span><span class="sxs-lookup"><span data-stu-id="38df6-334">**Advisory**</span></span>

<span data-ttu-id="38df6-335">Microsoft Managed Desktop 사용자에게는 등록 후 Microsoft Managed Desktop 디바이스에 대한 로컬 관리자 권한이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="38df6-335">Microsoft Managed Desktop users will not have local administrator privileges on their Microsoft Managed Desktop devices after enrolling.</span></span>

## <a name="microsoft-365-apps-for-enterprise"></a><span data-ttu-id="38df6-336">엔터프라이즈용 Microsoft 365 앱</span><span class="sxs-lookup"><span data-stu-id="38df6-336">Microsoft 365 Apps for enterprise</span></span>

### <a name="onedrive"></a><span data-ttu-id="38df6-337">OneDrive</span><span class="sxs-lookup"><span data-stu-id="38df6-337">OneDrive</span></span>

<span data-ttu-id="38df6-338">특정 **도메인에 가입된 PC에서만** 동기화 허용 설정이 Microsoft Managed Desktop과 충돌합니다.</span><span class="sxs-lookup"><span data-stu-id="38df6-338">The **Allow syncing only on PCs joined to specific domains** setting will conflict with Microsoft Managed Desktop.</span></span> <span data-ttu-id="38df6-339">OneDrive 관리 센터에서 OneDrive 설정에 [액세스할 수 있습니다.](https://admin.onedrive.com)</span><span class="sxs-lookup"><span data-stu-id="38df6-339">You can access OneDrive settings at the OneDrive [admin center](https://admin.onedrive.com).</span></span>

<span data-ttu-id="38df6-340">**권고**</span><span class="sxs-lookup"><span data-stu-id="38df6-340">**Advisory**</span></span>

<span data-ttu-id="38df6-341">특정 도메인 설정에 가입된 PC에서만 동기화 **허용을 사용하고** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38df6-341">You're using the **Allow syncing only on PCs joined to specific domains** setting.</span></span> <span data-ttu-id="38df6-342">이 설정은 Microsoft Managed Desktop에서는 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="38df6-342">This setting won't work with Microsoft Managed Desktop.</span></span> <span data-ttu-id="38df6-343">이 설정을 사용하지 않도록 설정하고 대신 조건부 액세스 정책을 사용하기 위해 OneDrive를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="38df6-343">Disable this setting, and instead set up OneDrive to use a conditional access policy.</span></span> <span data-ttu-id="38df6-344">도움말은 [조건부 액세스 배포](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access) 계획을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="38df6-344">See [Plan a Conditional Access deployment](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access) for help.</span></span>
