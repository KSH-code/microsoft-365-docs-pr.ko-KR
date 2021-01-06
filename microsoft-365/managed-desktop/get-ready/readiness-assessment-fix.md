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
ms.openlocfilehash: 3c3c0d21ca93c0d93d17cefbc6ce630d00a16d09
ms.sourcegitcommit: 222fb7fe2b26dde3d8591b61cc02113d6135012c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/06/2021
ms.locfileid: "49760127"
---
# <a name="fix-issues-found-by-the-readiness-assessment-tool"></a><span data-ttu-id="b28cc-104">준비 평가 도구에서 발견한 문제 해결</span><span class="sxs-lookup"><span data-stu-id="b28cc-104">Fix issues found by the readiness assessment tool</span></span>

<span data-ttu-id="b28cc-105">각 검사에 대해 도구는 다음 네 가지 결과 중 하나를 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="b28cc-105">For each check, the tool will report one of four possible results:</span></span>


|<span data-ttu-id="b28cc-106">결과</span><span class="sxs-lookup"><span data-stu-id="b28cc-106">Result</span></span>  |<span data-ttu-id="b28cc-107">의미</span><span class="sxs-lookup"><span data-stu-id="b28cc-107">Meaning</span></span>  |
|---------|---------|
|<span data-ttu-id="b28cc-108">준비</span><span class="sxs-lookup"><span data-stu-id="b28cc-108">Ready</span></span>     | <span data-ttu-id="b28cc-109">등록을 완료하기 전에 필요한 작업은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b28cc-109">No action is required before completing enrollment.</span></span>        |
|<span data-ttu-id="b28cc-110">권고</span><span class="sxs-lookup"><span data-stu-id="b28cc-110">Advisory</span></span>    | <span data-ttu-id="b28cc-111">등록과 사용자에 대한 최상의 환경을 위해 도구 또는 이 문서의 단계를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="b28cc-111">Follow the steps in the tool or this article for the best experience with enrollment and for users.</span></span> <span data-ttu-id="b28cc-112">*등록을* 완료할 수 있지만 첫 번째 장치를 배포하기 전에 이러한 문제를 해결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b28cc-112">You *can* complete enrollment, but you must fix these issues before you deploy your first device.</span></span>        |
|<span data-ttu-id="b28cc-113">준비되지 않음</span><span class="sxs-lookup"><span data-stu-id="b28cc-113">Not ready</span></span> | <span data-ttu-id="b28cc-114">*이러한 문제를 해결하지 않는 경우 등록이 실패합니다.*</span><span class="sxs-lookup"><span data-stu-id="b28cc-114">*Enrollment will fail if you don't fix these issues.*</span></span> <span data-ttu-id="b28cc-115">도구 또는 이 문서의 단계에 따라 문제를 해결합니다.</span><span class="sxs-lookup"><span data-stu-id="b28cc-115">Follow the steps in the tool or this article to resolve them.</span></span>        |
|<span data-ttu-id="b28cc-116">오류</span><span class="sxs-lookup"><span data-stu-id="b28cc-116">Error</span></span> | <span data-ttu-id="b28cc-117">사용중인 Azure AD(Active Director) 역할에는 이 검사를 실행할 수 있는 권한이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b28cc-117">The Azure Active Director (AD) role you're using doesn't have sufficient permission to run this check.</span></span> |

> [!NOTE]
> <span data-ttu-id="b28cc-118">이 도구에서 보고한 결과에는 설정이 실행된 특정 시점에만 설정 상태가 반영됩니다.</span><span class="sxs-lookup"><span data-stu-id="b28cc-118">The results reported by this tool reflect the status of your settings only at the specific point in time that you ran it.</span></span> <span data-ttu-id="b28cc-119">나중에 Microsoft Intune, Azure Active Directory 또는 Microsoft 365에서 정책을 변경하면 "준비되지 않은" 항목이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b28cc-119">If you later make any changes to policies in Microsoft Intune, Azure Active Directory, or Microsoft 365, items that were "Ready" can become "Not ready."</span></span> <span data-ttu-id="b28cc-120">Microsoft Managed Desktop 작업의 문제를 방지하려면 정책을 변경하기 전에 이 문서에 설명된 특정 설정을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="b28cc-120">To avoid problems with Microsoft Managed Desktop operations, check the specific settings described in this article before you change any policies.</span></span>

## <a name="microsoft-intune-settings"></a><span data-ttu-id="b28cc-121">Microsoft Intune 설정</span><span class="sxs-lookup"><span data-stu-id="b28cc-121">Microsoft Intune settings</span></span>

<span data-ttu-id="b28cc-122">Microsoft Endpoint Manager 관리 센터에서 Intune 설정에 [액세스할 수 있습니다.](https://endpoint.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="b28cc-122">You can access Intune settings at the Microsoft Endpoint Manager [admin center](https://endpoint.microsoft.com).</span></span>

### <a name="autopilot-deployment-profile"></a><span data-ttu-id="b28cc-123">Autopilot 배포 프로필</span><span class="sxs-lookup"><span data-stu-id="b28cc-123">Autopilot deployment profile</span></span>

<span data-ttu-id="b28cc-124">Microsoft Managed Desktop에서 사용하는 할당된 그룹 또는 동적 그룹을 대상으로 하는 기존 Autopilot 프로필은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b28cc-124">You shouldn't have any existing Autopilot profiles that target assigned or dynamic groups used by Microsoft Managed Desktop.</span></span> <span data-ttu-id="b28cc-125">Microsoft Managed Desktop은 Autopilot을 사용하여 새 장치를 프로비전합니다.</span><span class="sxs-lookup"><span data-stu-id="b28cc-125">Microsoft Managed Desktop uses Autopilot to provision new devices.</span></span>

<span data-ttu-id="b28cc-126">**준비되지 않음**</span><span class="sxs-lookup"><span data-stu-id="b28cc-126">**Not ready**</span></span>

<span data-ttu-id="b28cc-127">모든 장치에 할당된 Autopilot 프로필이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b28cc-127">You have an Autopilot profile that is assigned to all devices.</span></span> <span data-ttu-id="b28cc-128">단계는 Windows [Autopilot을 사용하여 Intune에서 Windows 장치 등록을 참조하세요.](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot)</span><span class="sxs-lookup"><span data-stu-id="b28cc-128">For steps, see [Enroll Windows devices in Intune by using Windows Autopilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot).</span></span> <span data-ttu-id="b28cc-129">Microsoft Managed Desktop 등록 후 Autopilot 정책을 설정하여 최신 작업 공간 장치 **- 모든** Azure AD 그룹을 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="b28cc-129">After Microsoft Managed Desktop enrollment, set your Autopilot policy to exclude the **Modern Workplace Devices -All** Azure AD group.</span></span>

<span data-ttu-id="b28cc-130">**권고**</span><span class="sxs-lookup"><span data-stu-id="b28cc-130">**Advisory**</span></span>

<span data-ttu-id="b28cc-131">Autopilot 프로필이 등록 시 생성되는 Microsoft Managed Desktop 장치를 포함하지 않는 할당되거나 동적 Azure AD 그룹을 대상으로 하는지 확인</span><span class="sxs-lookup"><span data-stu-id="b28cc-131">Make sure that your Autopilot profiles target an assigned or dynamic Azure AD group that doesn't include Microsoft Managed Desktop devices that will be created at enrollment.</span></span> <span data-ttu-id="b28cc-132">단계는 Windows [Autopilot을 사용하여 Intune에서 Windows 장치 등록을 참조하세요.](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot)</span><span class="sxs-lookup"><span data-stu-id="b28cc-132">For steps, see [Enroll Windows devices in Intune by using Windows Autopilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot).</span></span> <span data-ttu-id="b28cc-133">Microsoft Managed Desktop 등록 후 Autopilot 정책을 설정하여 최신 작업 공간 장치 **- 모든** Azure AD 그룹을 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="b28cc-133">After Microsoft Managed Desktop enrollment, set your Autopilot policy to exclude the **Modern Workplace Devices -All** Azure AD group.</span></span>


### <a name="certificate-connectors"></a><span data-ttu-id="b28cc-134">인증서 커넥터</span><span class="sxs-lookup"><span data-stu-id="b28cc-134">Certificate connectors</span></span>

<span data-ttu-id="b28cc-135">Microsoft Managed Desktop에 등록하려는 장치에서 사용하는 인증서 커넥터가 있는 경우 커넥터에 오류가 있을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b28cc-135">If you have any certificate connectors used by the devices you want to enroll in Microsoft Managed Desktop, the connectors cannot have any errors.</span></span> <span data-ttu-id="b28cc-136">다음 권고 중 하나만 상황에 적용될 것이기 때문에 신중하게 검토하십시오.</span><span class="sxs-lookup"><span data-stu-id="b28cc-136">Only one of the following advisories will apply to your situation, so check them carefully.</span></span>

<span data-ttu-id="b28cc-137">**권고**</span><span class="sxs-lookup"><span data-stu-id="b28cc-137">**Advisory**</span></span>

<span data-ttu-id="b28cc-138">인증서 커넥터가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b28cc-138">No certificate connectors are present.</span></span> <span data-ttu-id="b28cc-139">커넥터가 필요하지 않을 수도 있지만 Microsoft Managed Desktop 장치에 대한 네트워크 연결에 일부 커넥터가 필요한지 평가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b28cc-139">It's possible you don't need any connectors, but you should evaluate whether you might need some for network connectivity to Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="b28cc-140">자세한 내용은 Microsoft Managed Desktop에 대한 인증서 및 네트워크 프로필 [준비를 참조하세요.](certs-wifi-lan.md)</span><span class="sxs-lookup"><span data-stu-id="b28cc-140">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>

<span data-ttu-id="b28cc-141">**권고**</span><span class="sxs-lookup"><span data-stu-id="b28cc-141">**Advisory**</span></span>

<span data-ttu-id="b28cc-142">하나 이상의 인증서 커넥터에 오류가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b28cc-142">At least one certificate connector has an error.</span></span> <span data-ttu-id="b28cc-143">Microsoft Managed Desktop 장치에 연결하기 위해 이 커넥터가 필요한 경우 오류를 해결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b28cc-143">If you need this connector for connectivity to Microsoft Managed Desktop devices, you must resolve the error.</span></span> <span data-ttu-id="b28cc-144">자세한 내용은 Microsoft Managed Desktop에 대한 인증서 및 네트워크 프로필 [준비를 참조하세요.](certs-wifi-lan.md)</span><span class="sxs-lookup"><span data-stu-id="b28cc-144">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>


<span data-ttu-id="b28cc-145">**권고**</span><span class="sxs-lookup"><span data-stu-id="b28cc-145">**Advisory**</span></span>

<span data-ttu-id="b28cc-146">인증서 커넥터가 하나 이상 있으며 오류가 보고되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b28cc-146">You have at least one certificate connector and no errors are reported.</span></span> <span data-ttu-id="b28cc-147">그러나 Microsoft Managed Desktop 디바이스용 커넥터를 다시 사용하려면 프로필을 만들어야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b28cc-147">However, you might need to create a profile to reuse the connector for Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="b28cc-148">자세한 내용은 Microsoft Managed Desktop에 대한 인증서 및 네트워크 프로필 [준비를 참조하세요.](certs-wifi-lan.md)</span><span class="sxs-lookup"><span data-stu-id="b28cc-148">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>


### <a name="conditional-access-policies"></a><span data-ttu-id="b28cc-149">조건부 액세스 정책</span><span class="sxs-lookup"><span data-stu-id="b28cc-149">Conditional access policies</span></span>

<span data-ttu-id="b28cc-150">Azure AD 조직의 조건부 액세스 정책은 Microsoft Manage Desktop 사용자를 대상으로 지정하지 말아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b28cc-150">Conditional access policies in your Azure AD organization must not target any Microsoft Manage Desktop users.</span></span>

<span data-ttu-id="b28cc-151">**준비되지 않음**</span><span class="sxs-lookup"><span data-stu-id="b28cc-151">**Not ready**</span></span>

<span data-ttu-id="b28cc-152">모든 사용자를 대상으로 하는 조건부 액세스 정책이 하나 이상 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b28cc-152">You have at least one conditional access policy that targets all users.</span></span> <span data-ttu-id="b28cc-153">등록 시 생성될 Microsoft Managed Desktop 서비스 계정의 Azure AD 그룹을 포함하지 않는 특정 Azure AD 그룹을 대상으로 지정하도록 정책을 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="b28cc-153">Reset the policy to target a specific Azure AD group that does not include the Azure AD group of Microsoft Managed Desktop service accounts that will be created at enrollment.</span></span> <span data-ttu-id="b28cc-154">단계는 조건부 [액세스: 사용자 및 그룹을 참조하세요.](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups)</span><span class="sxs-lookup"><span data-stu-id="b28cc-154">For steps, see [Conditional Access: Users and groups](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups).</span></span>

<span data-ttu-id="b28cc-155">**권고**</span><span class="sxs-lookup"><span data-stu-id="b28cc-155">**Advisory**</span></span>

<span data-ttu-id="b28cc-156">최신 작업 공간 서비스 계정 **Azure** AD 그룹을 제외한 조건부 액세스 정책이 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="b28cc-156">Make sure that any conditional access policies you have exclude the **Modern Workplace Service Accounts** Azure AD group.</span></span> <span data-ttu-id="b28cc-157">단계는 [조건부 액세스 조정을 참조하세요.](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/conditional-access)</span><span class="sxs-lookup"><span data-stu-id="b28cc-157">For steps, see [Adjust conditional access](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/conditional-access).</span></span> <span data-ttu-id="b28cc-158">최신 **Workplace Service 계정** Azure AD 그룹은 등록 시 서비스를 위해 만드는 동적 그룹입니다.</span><span class="sxs-lookup"><span data-stu-id="b28cc-158">The **Modern Workplace Service Accounts** Azure AD group is a dynamic group that we create for the service when you enroll.</span></span> <span data-ttu-id="b28cc-159">등록 후 이 그룹을 제외하기 위해 돌아와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b28cc-159">You'll have to come back to exclude this group after enrollment.</span></span> <span data-ttu-id="b28cc-160">이러한 서비스 계정에 대한 자세한 내용은 Standard 운영 [절차를 참조합니다.](../service-description/operations-and-monitoring.md#standard-operating-procedures)</span><span class="sxs-lookup"><span data-stu-id="b28cc-160">For more about these service accounts, see [Standard operating procedures](../service-description/operations-and-monitoring.md#standard-operating-procedures).</span></span>

<span data-ttu-id="b28cc-161">**오류**</span><span class="sxs-lookup"><span data-stu-id="b28cc-161">**Error**</span></span>

<span data-ttu-id="b28cc-162">Intune 관리자 역할에는 이 검사에 대한 충분한 권한이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b28cc-162">The Intune Administrator role doesn't have sufficient permissions for this check.</span></span> <span data-ttu-id="b28cc-163">이 검사를 실행하려면 다음 Azure AD 역할도 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b28cc-163">You'll also need any of these Azure AD roles assigned to run this check:</span></span>

- <span data-ttu-id="b28cc-164">보안 읽기 권한자</span><span class="sxs-lookup"><span data-stu-id="b28cc-164">Security Reader</span></span>
- <span data-ttu-id="b28cc-165">보안 관리자</span><span class="sxs-lookup"><span data-stu-id="b28cc-165">Security Administrator</span></span>
- <span data-ttu-id="b28cc-166">조건부 액세스 관리자</span><span class="sxs-lookup"><span data-stu-id="b28cc-166">Conditional Access Administrator</span></span>
- <span data-ttu-id="b28cc-167">전역 읽기 권한자</span><span class="sxs-lookup"><span data-stu-id="b28cc-167">Global Reader</span></span>
- <span data-ttu-id="b28cc-168">장치 관리자</span><span class="sxs-lookup"><span data-stu-id="b28cc-168">Devices Administrator</span></span>


### <a name="device-compliance-policies"></a><span data-ttu-id="b28cc-169">장치 준수 정책</span><span class="sxs-lookup"><span data-stu-id="b28cc-169">Device Compliance policies</span></span>

<span data-ttu-id="b28cc-170">Azure AD 조직의 Intune 장치 준수 정책은 Microsoft Managed Desktop 사용자를 대상으로 지정하지 말아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b28cc-170">Intune Device Compliance policies in your Azure AD organization must not target any Microsoft Managed Desktop users.</span></span>

<span data-ttu-id="b28cc-171">**준비되지 않음**</span><span class="sxs-lookup"><span data-stu-id="b28cc-171">**Not ready**</span></span>

<span data-ttu-id="b28cc-172">모든 사용자를 대상으로 하는 규정 준수 정책이 하나 이상 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b28cc-172">You have at least one compliance policy that targets all users.</span></span> <span data-ttu-id="b28cc-173">정책을 다시 설정하여 Microsoft Managed Desktop 사용자를 포함하지 않는 특정 Azure AD 그룹을 대상으로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b28cc-173">Reset the policy to target a specific Azure AD group that does not include any Microsoft Managed Desktop users.</span></span> <span data-ttu-id="b28cc-174">자세한 단계는 [Microsoft Intune에서](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy)준수 정책 만들기를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b28cc-174">For steps, see [Create a compliance policy in Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy).</span></span>

<span data-ttu-id="b28cc-175">**권고**</span><span class="sxs-lookup"><span data-stu-id="b28cc-175">**Advisory**</span></span>

<span data-ttu-id="b28cc-176">준수 정책에 Microsoft Managed Desktop 사용자를 포함하지 않는지 확인</span><span class="sxs-lookup"><span data-stu-id="b28cc-176">Make sure that any compliance policies you have don't include any Microsoft Managed Desktop users.</span></span> <span data-ttu-id="b28cc-177">자세한 단계는 [Microsoft Intune에서](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy)준수 정책 만들기를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b28cc-177">For steps, see [Create a compliance policy in Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy).</span></span>



### <a name="device-configuration-policies"></a><span data-ttu-id="b28cc-178">장치 구성 정책</span><span class="sxs-lookup"><span data-stu-id="b28cc-178">Device Configuration policies</span></span>

<span data-ttu-id="b28cc-179">Azure AD 조직의 Intune 장치 구성 정책은 Microsoft Manage Desktop 장치 또는 사용자를 대상으로 지정하지 말아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b28cc-179">Intune Device Configuration policies in your Azure AD organization must not target any Microsoft Manage Desktop devices or users.</span></span>

<span data-ttu-id="b28cc-180">**준비되지 않음**</span><span class="sxs-lookup"><span data-stu-id="b28cc-180">**Not ready**</span></span>

<span data-ttu-id="b28cc-181">모든 사용자, 모든 장치 또는 둘 다를 대상으로 하는 구성 정책이 하나 이상 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b28cc-181">You have at least one configuration policy that targets all users, all devices, or both.</span></span> <span data-ttu-id="b28cc-182">정책을 다시 설정하여 Microsoft Managed Desktop 장치를 포함하지 않는 특정 Azure AD 그룹을 대상으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="b28cc-182">Reset the policy to target a specific Azure AD group that does not include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="b28cc-183">자세한 단계는 [Microsoft Intune에서](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure)준수 정책 만들기를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b28cc-183">For steps, see [Create a compliance policy in Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure).</span></span>

<span data-ttu-id="b28cc-184">**권고**</span><span class="sxs-lookup"><span data-stu-id="b28cc-184">**Advisory**</span></span>

<span data-ttu-id="b28cc-185">Microsoft Managed Desktop 장치 또는 사용자를 포함하지 않은 준수 정책이 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="b28cc-185">Make sure that any compliance policies you have don't include any Microsoft Managed Desktop devices or users.</span></span> <span data-ttu-id="b28cc-186">자세한 단계는 [Microsoft Intune에서](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure)준수 정책 만들기를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b28cc-186">For steps, see [Create a compliance policy in Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure).</span></span>



### <a name="device-type-restrictions"></a><span data-ttu-id="b28cc-187">장치 유형 제한</span><span class="sxs-lookup"><span data-stu-id="b28cc-187">Device type restrictions</span></span>

<span data-ttu-id="b28cc-188">Microsoft Managed Desktop 장치는 Intune에 등록할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b28cc-188">Microsoft Managed Desktop devices must be allowed to enroll in Intune.</span></span>

<span data-ttu-id="b28cc-189">**준비되지 않음**</span><span class="sxs-lookup"><span data-stu-id="b28cc-189">**Not ready**</span></span>

<span data-ttu-id="b28cc-190">등록 제한 [설정의 단계에 따라](https://docs.microsoft.com/mem/intune/enrollment/enrollment-restrictions-set) 설정을 허용으로 **변경합니다.**</span><span class="sxs-lookup"><span data-stu-id="b28cc-190">Follow the steps in [Set enrollment restrictions](https://docs.microsoft.com/mem/intune/enrollment/enrollment-restrictions-set) to change the setting to **Allow**.</span></span>


### <a name="enrollment-status-page"></a><span data-ttu-id="b28cc-191">등록 상태 페이지</span><span class="sxs-lookup"><span data-stu-id="b28cc-191">Enrollment Status Page</span></span>

<span data-ttu-id="b28cc-192">현재 ESP(등록 상태 페이지)를 사용하도록 설정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b28cc-192">You currently have the Enrollment Status Page (ESP) enabled.</span></span> <span data-ttu-id="b28cc-193">이 기능의 공개 미리 보기에 참여하는 경우 이 항목을 무시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b28cc-193">If you are participating in the public preview of this feature, you can ignore this item.</span></span> <span data-ttu-id="b28cc-194">자세한 내용은 Autopilot 및 등록 상태 페이지의 첫 실행 [환경을 참조하세요.](../get-started/esp-first-run.md)</span><span class="sxs-lookup"><span data-stu-id="b28cc-194">For more information, see [First-run experience with Autopilot and the Enrollment Status Page](../get-started/esp-first-run.md).</span></span>

<span data-ttu-id="b28cc-195">**준비되지 않음**</span><span class="sxs-lookup"><span data-stu-id="b28cc-195">**Not ready**</span></span>

<span data-ttu-id="b28cc-196">ESP 기본 프로필이 앱 및 프로필 구성 진행률 **표시로 설정되어 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="b28cc-196">You have the ESP default profile set to **Show app and profile configuration progress**.</span></span> <span data-ttu-id="b28cc-197">이 설정을 사용하지 않도록 설정하거나 등록 상태 설정 페이지의 단계에 따라 Azure AD 그룹에 대한 할당에 Microsoft Managed Desktop 장치가 포함되어 [있지 않은지 확인하십시오.](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status)</span><span class="sxs-lookup"><span data-stu-id="b28cc-197">Disable this setting or make sure that assignments to any Azure AD group do not include Microsoft Managed Desktop devices by following the steps in [Set up the Enrollment Status Page](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status).</span></span>

<span data-ttu-id="b28cc-198">**권고**</span><span class="sxs-lookup"><span data-stu-id="b28cc-198">**Advisory**</span></span>

<span data-ttu-id="b28cc-199">앱 및 프로필 구성 진행률 표시 설정이 있는 프로필이 Microsoft Managed Desktop 장치를 포함하는 Azure AD 그룹에 할당되어 있지 않은지 확인 </span><span class="sxs-lookup"><span data-stu-id="b28cc-199">Make sure that any profiles that have the **Show app and profile configuration progress** setting are not assigned to any Azure AD group that includes Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="b28cc-200">자세한 내용은 등록 상태 페이지 [설정을 참조하십시오.](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status)</span><span class="sxs-lookup"><span data-stu-id="b28cc-200">For more information, see [Set up the Enrollment Status Page](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status).</span></span>

### <a name="intune-enrollment"></a><span data-ttu-id="b28cc-201">Intune 등록</span><span class="sxs-lookup"><span data-stu-id="b28cc-201">Intune enrollment</span></span>

<span data-ttu-id="b28cc-202">Azure AD 조직의 Windows 10 장치는 Intune에 자동으로 등록되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b28cc-202">Windows 10 devices in your Azure AD organization must be automatically enrolled in Intune.</span></span>

<span data-ttu-id="b28cc-203">**권고**</span><span class="sxs-lookup"><span data-stu-id="b28cc-203">**Advisory**</span></span>

<span data-ttu-id="b28cc-204">MDM 사용자 범위가 **없음이** 아닌 일부 또는 **모두로** 설정되어 있는지 **확인**</span><span class="sxs-lookup"><span data-stu-id="b28cc-204">Make sure the MDM User scope is set to **Some** or **All**, not **None**.</span></span> <span data-ttu-id="b28cc-205">If you choose **Some**, come back after enrollment and select the **Modern Workplace -All** Azure AD group for **Groups.**</span><span class="sxs-lookup"><span data-stu-id="b28cc-205">If you choose **Some**, come back after enrollment and select the **Modern Workplace -All** Azure AD group for **Groups**.</span></span>


### <a name="microsoft-store-for-business"></a><span data-ttu-id="b28cc-206">비즈니스용 Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="b28cc-206">Microsoft Store for Business</span></span>

<span data-ttu-id="b28cc-207">Microsoft Project 및 Microsoft Visio와 같은 일부 앱을 배포하기 위해 회사 포털을 다운로드할 수 있도록 비즈니스용 Microsoft Store를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b28cc-207">We use Microsoft Store for Business so that you can download Company Portal to deploy some apps, such as Microsoft Project and Microsoft Visio.</span></span>

<span data-ttu-id="b28cc-208">**준비되지 않음**</span><span class="sxs-lookup"><span data-stu-id="b28cc-208">**Not ready**</span></span>

<span data-ttu-id="b28cc-209">비즈니스용 Microsoft Store를 사용하도록 설정하지 않은 경우 또는 Intune과 동기화되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b28cc-209">Microsoft Store for Business either isn't enabled or isn't synced with Intune.</span></span> <span data-ttu-id="b28cc-210">자세한 내용은 장치에서 [Microsoft Intune 및 Intune](https://docs.microsoft.com/mem/intune/apps/windows-store-for-business) 회사 포털을 설치하여 비즈니스용 Microsoft Store에서 대량 구매 앱을 관리하는 [방법을 참조하세요.](../get-started/company-portal.md)</span><span class="sxs-lookup"><span data-stu-id="b28cc-210">For more information, see [How to manage volume purchased apps from the Microsoft Store for Business with Microsoft Intune](https://docs.microsoft.com/mem/intune/apps/windows-store-for-business) and [Install Intune Company Portal on on devices](../get-started/company-portal.md).</span></span>

### <a name="multifactor-authentication"></a><span data-ttu-id="b28cc-211">다단계 인증</span><span class="sxs-lookup"><span data-stu-id="b28cc-211">Multifactor authentication</span></span>

<span data-ttu-id="b28cc-212">다단계 인증을 실수로 Microsoft Managed Desktop 서비스 계정에 적용하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b28cc-212">Multifactor authentication must not accidentally be applied to Microsoft Managed Desktop service accounts.</span></span>


<span data-ttu-id="b28cc-213">**준비되지 않음**</span><span class="sxs-lookup"><span data-stu-id="b28cc-213">**Not ready**</span></span>

<span data-ttu-id="b28cc-214">모든 사용자에게 할당된 조건부 액세스 정책에 대해 일부 MFA(다단계 인증) 정책이 "필수"로 설정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b28cc-214">You have some multifactor authentication (MFA) policies set as "required" for conditional access policies that are assigned to all users.</span></span> <span data-ttu-id="b28cc-215">Microsoft Managed Desktop 장치를 포함하지 않는 특정 Azure AD 그룹을 대상으로 하는 할당을 사용하도록 정책을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="b28cc-215">Change the policy to use an Assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="b28cc-216">자세한 내용은 [조건부 액세스](#conditional-access-policies) 정책 및 [조건부 액세스: 모든 사용자에 대해 MFA 필요를 참조하세요.](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)</span><span class="sxs-lookup"><span data-stu-id="b28cc-216">For more information, see [Conditional access policies](#conditional-access-policies) and [Conditional Access: Require MFA for all users](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa).</span></span>

<span data-ttu-id="b28cc-217">**권고**</span><span class="sxs-lookup"><span data-stu-id="b28cc-217">**Advisory**</span></span>

<span data-ttu-id="b28cc-218">MFA가 필요한 조건부 액세스 정책이 **최신 Workplace -All** Azure AD 그룹을 제외하는지 확인</span><span class="sxs-lookup"><span data-stu-id="b28cc-218">Make sure that any conditional access policies that require MFA exclude the **Modern Workplace -All** Azure AD group.</span></span> <span data-ttu-id="b28cc-219">자세한 내용은 [조건부 액세스](#conditional-access-policies) 정책 및 [조건부 액세스: 모든 사용자에 대해 MFA 필요를 참조하세요.](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)</span><span class="sxs-lookup"><span data-stu-id="b28cc-219">For more information, see [Conditional access policies](#conditional-access-policies) and [Conditional Access: Require MFA for all users](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa).</span></span> <span data-ttu-id="b28cc-220">최신 **Workplace -All** Azure AD 그룹은 Microsoft Managed Desktop에 등록할 때 만드는 동적 그룹이기 때문에 등록 후 이 그룹을 제외하기 위해 돌아와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b28cc-220">The **Modern Workplace -All** Azure AD group is a dynamic group that we create when you enroll in Microsoft Managed Desktop, so you'll have to come back to exclude this group after enrollment.</span></span>

<span data-ttu-id="b28cc-221">**오류**</span><span class="sxs-lookup"><span data-stu-id="b28cc-221">**Error**</span></span>

<span data-ttu-id="b28cc-222">Intune 관리자 역할에는 이 검사에 대한 충분한 권한이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b28cc-222">The Intune Administrator role doesn't have sufficient permissions for this check.</span></span> <span data-ttu-id="b28cc-223">이 검사를 실행하려면 다음 Azure AD 역할도 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b28cc-223">You'll also need any of these Azure AD roles assigned to run this check:</span></span>

- <span data-ttu-id="b28cc-224">보안 읽기 권한자</span><span class="sxs-lookup"><span data-stu-id="b28cc-224">Security Reader</span></span>
- <span data-ttu-id="b28cc-225">보안 관리자</span><span class="sxs-lookup"><span data-stu-id="b28cc-225">Security Administrator</span></span>
- <span data-ttu-id="b28cc-226">조건부 액세스 관리자</span><span class="sxs-lookup"><span data-stu-id="b28cc-226">Conditional Access Administrator</span></span>
- <span data-ttu-id="b28cc-227">전역 읽기 권한자</span><span class="sxs-lookup"><span data-stu-id="b28cc-227">Global Reader</span></span>
- <span data-ttu-id="b28cc-228">장치 관리자</span><span class="sxs-lookup"><span data-stu-id="b28cc-228">Devices Administrator</span></span>


### <a name="powershell-scripts"></a><span data-ttu-id="b28cc-229">PowerShell 스크립트</span><span class="sxs-lookup"><span data-stu-id="b28cc-229">PowerShell scripts</span></span>

<span data-ttu-id="b28cc-230">Windows PowerShell Microsoft Managed Desktop 장치를 대상으로 하는 방식으로 스크립트를 할당할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b28cc-230">Windows PowerShell scripts can't be assigned in a way that would target Microsoft Managed Desktop devices.</span></span>  

<span data-ttu-id="b28cc-231">**권고**</span><span class="sxs-lookup"><span data-stu-id="b28cc-231">**Advisory**</span></span>

<span data-ttu-id="b28cc-232">Azure AD Windows PowerShell 스크립트가 Microsoft Manage Desktop 장치 또는 사용자를 대상으로 하지 않는지 확인</span><span class="sxs-lookup"><span data-stu-id="b28cc-232">Make sure that Windows PowerShell scripts in your Azure AD organization don't target any Microsoft Manage Desktop devices or users.</span></span> <span data-ttu-id="b28cc-233">모든 사용자, 모든 장치 또는 둘 다를 대상으로 하는 PowerShell 스크립트를 할당하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b28cc-233">Do not assign a PowerShell script to target all users, all devices, or both.</span></span> <span data-ttu-id="b28cc-234">Microsoft Managed Desktop 장치를 포함하지 않는 특정 Azure AD 그룹을 대상으로 하는 할당을 사용하도록 정책을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="b28cc-234">Change the policy to use an Assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="b28cc-235">자세한 내용은 [Intune의 Windows 10 장치에서 PowerShell 스크립트 사용을 참조하세요.](https://docs.microsoft.com/mem/intune/apps/intune-management-extension)</span><span class="sxs-lookup"><span data-stu-id="b28cc-235">For more information, see [Use PowerShell scripts on Windows 10 devices in Intune](https://docs.microsoft.com/mem/intune/apps/intune-management-extension).</span></span>

### <a name="region"></a><span data-ttu-id="b28cc-236">Region</span><span class="sxs-lookup"><span data-stu-id="b28cc-236">Region</span></span>

<span data-ttu-id="b28cc-237">해당 지역은 Microsoft Managed Desktop에서 지원해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b28cc-237">Your region must be supported by Microsoft Managed Desktop.</span></span>

<span data-ttu-id="b28cc-238">**준비되지 않음**</span><span class="sxs-lookup"><span data-stu-id="b28cc-238">**Not ready**</span></span>

<span data-ttu-id="b28cc-239">Azure AD 조직 지역은 현재 Microsoft Managed Desktop에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b28cc-239">Your Azure AD organization region isn't currently supported by Microsoft Managed Desktop.</span></span> <span data-ttu-id="b28cc-240">자세한 내용은 Microsoft Managed Desktop 지원 지역 및 [언어를 참조하세요.](../service-description/regions-languages.md)</span><span class="sxs-lookup"><span data-stu-id="b28cc-240">For more information, see [Microsoft Managed Desktop supported regions and languages](../service-description/regions-languages.md).</span></span>

<span data-ttu-id="b28cc-241">**권고**</span><span class="sxs-lookup"><span data-stu-id="b28cc-241">**Advisory**</span></span>

<span data-ttu-id="b28cc-242">Azure AD 조직이 있는 하나 이상의 국가는 Microsoft Managed Desktop에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b28cc-242">One or more of the countries where your Azure AD organization is located isn't supported by Microsoft Managed Desktop.</span></span> <span data-ttu-id="b28cc-243">자세한 내용은 Microsoft Managed Desktop 지원 지역 및 [언어를 참조하세요.](../service-description/regions-languages.md)</span><span class="sxs-lookup"><span data-stu-id="b28cc-243">For more information, see [Microsoft Managed Desktop supported regions and languages](../service-description/regions-languages.md).</span></span>


### <a name="security-baselines"></a><span data-ttu-id="b28cc-244">보안 기준</span><span class="sxs-lookup"><span data-stu-id="b28cc-244">Security baselines</span></span>

<span data-ttu-id="b28cc-245">보안 기준 정책은 Microsoft Managed Desktop 장치를 대상으로 하지 말아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b28cc-245">Security baseline policies should not target any Microsoft Managed Desktop devices.</span></span>

<span data-ttu-id="b28cc-246">**준비되지 않음**</span><span class="sxs-lookup"><span data-stu-id="b28cc-246">**Not ready**</span></span>

<span data-ttu-id="b28cc-247">모든 사용자, 모든 장치 또는 둘 다를 대상으로 하는 보안 기준 프로필이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b28cc-247">You have a security baseline profile that targets all users, all devices or both.</span></span> <span data-ttu-id="b28cc-248">Microsoft Managed Desktop 장치를 포함하지 않는 특정 Azure AD 그룹을 대상으로 하는 할당을 사용하도록 정책을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="b28cc-248">Change the policy to use an Assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="b28cc-249">단계는 보안 기준을 사용하여 [Intune에서 Windows 10 디바이스를 구성합니다.](https://docs.microsoft.com/mem/intune/protect/security-baselines)</span><span class="sxs-lookup"><span data-stu-id="b28cc-249">For steps, see [Use security baselines to configure Windows 10 devices in Intune](https://docs.microsoft.com/mem/intune/protect/security-baselines).</span></span>

<span data-ttu-id="b28cc-250">**권고**</span><span class="sxs-lookup"><span data-stu-id="b28cc-250">**Advisory**</span></span>

<span data-ttu-id="b28cc-251">Microsoft Managed Desktop 장치를 제외한 보안 기준 정책이 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="b28cc-251">Make sure that any security baseline policies you have exclude Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="b28cc-252">단계는 보안 기준을 사용하여 [Intune에서 Windows 10 디바이스를 구성합니다.](https://docs.microsoft.com/mem/intune/protect/security-baselines)</span><span class="sxs-lookup"><span data-stu-id="b28cc-252">For steps, see [Use security baselines to configure Windows 10 devices in Intune](https://docs.microsoft.com/mem/intune/protect/security-baselines).</span></span> <span data-ttu-id="b28cc-253">최신 작업 공간 **장치 - 모든** Azure AD 그룹은 Microsoft Managed Desktop에 등록할 때 만드는 동적 그룹이기 때문에 등록 후 이 그룹을 제외하기 위해 돌아와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b28cc-253">The **Modern Workplace Devices -All** Azure AD group is a dynamic group that we create when you enroll in Microsoft Managed Desktop, so you'll have to come back to exclude this group after enrollment.</span></span>


### <a name="windows-apps"></a><span data-ttu-id="b28cc-254">Windows 앱</span><span class="sxs-lookup"><span data-stu-id="b28cc-254">Windows apps</span></span>

<span data-ttu-id="b28cc-255">Microsoft Managed Desktop 사용자에게 필요한 앱을 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="b28cc-255">Review apps you want your Microsoft Managed Desktop users to have.</span></span>

<span data-ttu-id="b28cc-256">**권고**</span><span class="sxs-lookup"><span data-stu-id="b28cc-256">**Advisory**</span></span>

<span data-ttu-id="b28cc-257">Microsoft Managed Desktop 사용자에게 필요한 앱의 인벤토리를 준비해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b28cc-257">You should prepare an inventory of the apps that you want your Microsoft Managed Desktop users to have.</span></span> <span data-ttu-id="b28cc-258">이러한 앱은 Intune에서 배포해야 하기 때문에 기존 Intune 앱을 다시 사용하는지 평가합니다.</span><span class="sxs-lookup"><span data-stu-id="b28cc-258">Since these apps must be deployed by Intune, evaluate re-using existing Intune apps.</span></span> <span data-ttu-id="b28cc-259">회사 포털(장치에 [Intune 회사](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/company-portal) 포털 설치 및 ESP(등록 상태 페이지) 참조)을 사용하여 사용자에게 앱을 배포하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="b28cc-259">Consider using Company Portal (see [Install Intune Company Portal on devices](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/company-portal) and Enrollment Status Page (ESP) to distribute apps to your users.</span></span> <span data-ttu-id="b28cc-260">자세한 내용은 Autopilot 및 등록 상태 페이지에서 [Microsoft Managed Desktop의](apps.md) 앱 및 첫 실행 환경을 [참조하세요.](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/esp-first-run)</span><span class="sxs-lookup"><span data-stu-id="b28cc-260">For more information, see [Apps in Microsoft Managed Desktop](apps.md) and [First-run experience with Autopilot and the Enrollment Status Page](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/esp-first-run).</span></span>

<span data-ttu-id="b28cc-261">Microsoft Endpoint Configuration Manager의 쿼리를 Microsoft 계정 담당자에게 요청하여 Intune으로 마이그레이션할 준비가 되거나 조정이 필요한 앱을 식별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b28cc-261">You can ask your Microsoft account representative for a query in Microsoft Endpoint Configuration Manager to identify those apps that are ready to migrate to Intune or need adjustment.</span></span>


### <a name="windows-hello-for-business"></a><span data-ttu-id="b28cc-262">비즈니스용 Windows Hello</span><span class="sxs-lookup"><span data-stu-id="b28cc-262">Windows Hello for Business</span></span>

<span data-ttu-id="b28cc-263">Microsoft Managed Desktop을 사용하려면 비즈니스용 Windows Hello를 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b28cc-263">Microsoft Managed Desktop requires Windows Hello for Business to be enabled.</span></span>

<span data-ttu-id="b28cc-264">**준비되지 않음**</span><span class="sxs-lookup"><span data-stu-id="b28cc-264">**Not ready**</span></span>

<span data-ttu-id="b28cc-265">비즈니스용 Windows Hello를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b28cc-265">Windows Hello for Business is disabled.</span></span> <span data-ttu-id="b28cc-266">비즈니스용 [Windows Hello](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy) 만들기 정책의 단계에 따라 사용하도록 설정</span><span class="sxs-lookup"><span data-stu-id="b28cc-266">Enable it by following the steps in [Create a Windows Hello for Business policy](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)</span></span>

<span data-ttu-id="b28cc-267">**권고**</span><span class="sxs-lookup"><span data-stu-id="b28cc-267">**Advisory**</span></span>

<span data-ttu-id="b28cc-268">비즈니스용 Windows Hello가 설정되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b28cc-268">Windows Hello for Business is not set up.</span></span> <span data-ttu-id="b28cc-269">비즈니스용 Windows Hello 만들기 정책의 단계에 따라 사용하도록 [설정하십시오.](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)</span><span class="sxs-lookup"><span data-stu-id="b28cc-269">Enable it by following the steps in [Create a Windows Hello for Business policy](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy).</span></span>


### <a name="windows-10-update-rings"></a><span data-ttu-id="b28cc-270">Windows 10 업데이트 링</span><span class="sxs-lookup"><span data-stu-id="b28cc-270">Windows 10 update rings</span></span>

<span data-ttu-id="b28cc-271">Intune의 "Windows 10 업데이트 링" 정책은 Microsoft Managed Desktop 장치를 대상으로 지정하지 말아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b28cc-271">Your "Windows 10 update ring" policy in Intune must not target any Microsoft Managed Desktop devices.</span></span>

<span data-ttu-id="b28cc-272">**준비되지 않음**</span><span class="sxs-lookup"><span data-stu-id="b28cc-272">**Not ready**</span></span>

<span data-ttu-id="b28cc-273">모든 장치, 모든 사용자 또는 둘 다를 대상으로 하는 "업데이트 링" 정책이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b28cc-273">You have an "update ring" policy that targets all devices, all users, or both.</span></span> <span data-ttu-id="b28cc-274">Microsoft Managed Desktop 장치를 포함하지 않는 특정 Azure AD 그룹을 대상으로 하는 할당을 사용하도록 정책을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="b28cc-274">Change the policy to use an Assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="b28cc-275">단계는 [Intune에서 Windows 10 소프트웨어 업데이트 관리를 참조하세요.](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure)</span><span class="sxs-lookup"><span data-stu-id="b28cc-275">For steps, see [Manage Windows 10 software updates in Intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure).</span></span>

<span data-ttu-id="b28cc-276">**권고**</span><span class="sxs-lookup"><span data-stu-id="b28cc-276">**Advisory**</span></span>

<span data-ttu-id="b28cc-277">최신 작업 공간 장치 -모든 Azure AD 그룹을 제외한 모든 업데이트 **링** 정책이 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b28cc-277">Make sure that any update ring policies you have exclude the **Modern Workplace Devices -All** Azure AD group.</span></span> <span data-ttu-id="b28cc-278">이러한 정책에 Azure AD 사용자 그룹을 할당한 경우 Microsoft Managed Desktop 사용자를 포함하는 최신 **Workplace -All** Azure AD 그룹도 제외한 업데이트 링 정책이 있는지 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="b28cc-278">If you have assigned Azure AD user group to these policies, make sure that any update ring policies you have also excluded the **Modern Workplace -All** Azure AD group which includes your Microsoft Managed Desktop users.</span></span> <span data-ttu-id="b28cc-279">단계는 [Intune에서 Windows 10 소프트웨어 업데이트 관리를 참조하세요.](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure)</span><span class="sxs-lookup"><span data-stu-id="b28cc-279">For steps, see [Manage Windows 10 software updates in Intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure).</span></span> <span data-ttu-id="b28cc-280">최신 작업 공간 장치 **-All** 및 **Modern Workplace -All** Azure AD 그룹에는 Microsoft Managed Desktop에 등록할 때 만든 그룹이 할당되어 있으므로 등록 후 이 그룹을 제외하기 위해 다시 돌아와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b28cc-280">Both the **Modern Workplace Devices -All** and **Modern Workplace -All** Azure AD groups are assigned groups that we create when you enroll in Microsoft Managed Desktop, so you'll have to come back to exclude this group after enrollment.</span></span>


## <a name="azure-active-directory-settings"></a><span data-ttu-id="b28cc-281">Azure Active Directory 설정</span><span class="sxs-lookup"><span data-stu-id="b28cc-281">Azure Active Directory settings</span></span>

<span data-ttu-id="b28cc-282">Azure Portal에서 Azure Active Directory [설정에 액세스할 수 있습니다.](https://portal.azure.com)</span><span class="sxs-lookup"><span data-stu-id="b28cc-282">You can access Azure Active Directory settings at the [Azure portal](https://portal.azure.com).</span></span>

### <a name="ad-hoc-subscriptions"></a><span data-ttu-id="b28cc-283">Ad Hoc 구독</span><span class="sxs-lookup"><span data-stu-id="b28cc-283">Ad hoc subscriptions</span></span>

<span data-ttu-id="b28cc-284">"false"로 설정하면 엔터프라이즈 상태 로밍이 제대로 작동하지 않을 수 있는 설정을 검사하는 방법을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b28cc-284">Advises how to check a setting that (if set to "false") might prevent Enterprise State Roaming from working correctly.</span></span>

<span data-ttu-id="b28cc-285">**권고**</span><span class="sxs-lookup"><span data-stu-id="b28cc-285">**Advisory**</span></span>

<span data-ttu-id="b28cc-286">**AllowAdHocSubscriptions가** **True로** 설정되어 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="b28cc-286">Ensure that **AllowAdHocSubscriptions** is set to **True**.</span></span> <span data-ttu-id="b28cc-287">그렇지 않으면 엔터프라이즈 상태 로밍이 작동하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b28cc-287">Otherwise, Enterprise State Roaming might not work.</span></span> <span data-ttu-id="b28cc-288">자세한 내용은 [Set-MsolCompanySettings를 참조하십시오.](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0)</span><span class="sxs-lookup"><span data-stu-id="b28cc-288">For more information, see [Set-MsolCompanySettings](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0).</span></span>


### <a name="enterprise-state-roaming"></a><span data-ttu-id="b28cc-289">Enterprise State Roaming</span><span class="sxs-lookup"><span data-stu-id="b28cc-289">Enterprise State Roaming</span></span>

<span data-ttu-id="b28cc-290">엔터프라이즈 상태 로밍을 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b28cc-290">Enterprise State Roaming should be enabled.</span></span>

<span data-ttu-id="b28cc-291">**권고**</span><span class="sxs-lookup"><span data-stu-id="b28cc-291">**Advisory**</span></span>

<span data-ttu-id="b28cc-292">Enterprise State Roaming이 전체  또는 선택한 그룹에 대해 사용하도록 **설정되어 있는지** 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="b28cc-292">Make sure that Enterprise State Roaming is enabled for **All** or for **Selected** groups.</span></span> <span data-ttu-id="b28cc-293">자세한 내용은 Azure Active Directory에서 엔터프라이즈 상태 [로밍 사용을 참조하세요.](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-enable)</span><span class="sxs-lookup"><span data-stu-id="b28cc-293">For more information, see [Enable Enterprise State Roaming in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-enable).</span></span>

### <a name="licenses"></a><span data-ttu-id="b28cc-294">라이선스</span><span class="sxs-lookup"><span data-stu-id="b28cc-294">Licenses</span></span>

<span data-ttu-id="b28cc-295">Microsoft Managed Desktop을 사용하려면 여러 라이선스가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="b28cc-295">A number of licenses are required to use Microsoft Managed Desktop.</span></span>

<span data-ttu-id="b28cc-296">**준비되지 않은 경우**</span><span class="sxs-lookup"><span data-stu-id="b28cc-296">**Not Ready**</span></span>

<span data-ttu-id="b28cc-297">Microsoft Managed Desktop을 사용하는 데 필요한 모든 라이선스가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b28cc-297">You don't have all the licenses you need to use Microsoft Managed Desktop.</span></span> <span data-ttu-id="b28cc-298">자세한 내용은 [Microsoft Managed Desktop 기술](../intro/technologies.md) 및 [라이선스에 대한 자세한 정보를 참조하세요.](prerequisites.md#more-about-licenses)</span><span class="sxs-lookup"><span data-stu-id="b28cc-298">For more information, see [Microsoft Managed Desktop technologies](../intro/technologies.md) and [More about licenses](prerequisites.md#more-about-licenses).</span></span>


### <a name="security-account-names"></a><span data-ttu-id="b28cc-299">보안 계정 이름</span><span class="sxs-lookup"><span data-stu-id="b28cc-299">Security account names</span></span>

<span data-ttu-id="b28cc-300">특정 보안 계정 이름이 Microsoft Managed Desktop에서 만든 이름과 충돌할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b28cc-300">Certain security account names could conflict with ones created by Microsoft Managed Desktop.</span></span>

<span data-ttu-id="b28cc-301">**준비되지 않음**</span><span class="sxs-lookup"><span data-stu-id="b28cc-301">**Not ready**</span></span>

<span data-ttu-id="b28cc-302">하나 이상의 계정 이름이 Microsoft Managed Desktop에서 만든 계정 이름과 충돌합니다.</span><span class="sxs-lookup"><span data-stu-id="b28cc-302">You have at least one account name that will conflict with ones created by Microsoft Managed Desktop.</span></span> <span data-ttu-id="b28cc-303">Microsoft 계정 담당자와 함께 이러한 계정 이름을 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="b28cc-303">Work with your Microsoft account representative to exclude these account names.</span></span>


### <a name="security-administrator-roles"></a><span data-ttu-id="b28cc-304">보안 관리자 역할</span><span class="sxs-lookup"><span data-stu-id="b28cc-304">Security administrator roles</span></span>

<span data-ttu-id="b28cc-305">특정 보안 역할이 있는 사용자에게는 끝점용 Microsoft Defender에서 할당된 보안 역할이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b28cc-305">Users with certain security roles must have those assigned in Microsoft Defender for Endpoint.</span></span>

<span data-ttu-id="b28cc-306">**권고**</span><span class="sxs-lookup"><span data-stu-id="b28cc-306">**Advisory**</span></span>

<span data-ttu-id="b28cc-307">Azure AD 조직에서 이러한 역할에 할당된 사용자가 있는 경우 이러한 역할도 끝점용 Microsoft Defender에 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b28cc-307">If you have users assigned to any of these roles in your Azure AD organization, make sure they also have these roles assigned in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="b28cc-308">그렇지 않으면 이러한 역할이 있는 관리자가 관리 포털에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b28cc-308">Otherwise, administrators with these roles won't be able to access the Admin portal.</span></span>

- <span data-ttu-id="b28cc-309">보안 운영자</span><span class="sxs-lookup"><span data-stu-id="b28cc-309">Security Operator</span></span>
- <span data-ttu-id="b28cc-310">전역 읽기 권한자</span><span class="sxs-lookup"><span data-stu-id="b28cc-310">Global Reader</span></span>

<span data-ttu-id="b28cc-311">자세한 내용은 역할 기반 액세스 제어에 대한 역할 [만들기 및 관리를 참조하세요.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles)</span><span class="sxs-lookup"><span data-stu-id="b28cc-311">For more information, see [Create and manage roles for role-based access control](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles).</span></span>


### <a name="security-default"></a><span data-ttu-id="b28cc-312">보안 기본값</span><span class="sxs-lookup"><span data-stu-id="b28cc-312">Security default</span></span>

<span data-ttu-id="b28cc-313">Azure Active Directory의 보안 기본값은 Microsoft Managed Desktop이 디바이스를 관리하지 못하게 합니다.</span><span class="sxs-lookup"><span data-stu-id="b28cc-313">Security defaults in Azure Active Directory will prevent Microsoft Managed Desktop from managing your devices.</span></span>

<span data-ttu-id="b28cc-314">**준비되지 않음**</span><span class="sxs-lookup"><span data-stu-id="b28cc-314">**Not ready**</span></span>

<span data-ttu-id="b28cc-315">보안 기본값이 설정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b28cc-315">You have Security defaults turned on.</span></span> <span data-ttu-id="b28cc-316">보안 기본값을 해제하고 조건부 액세스 정책을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="b28cc-316">Turn off Security defaults and set up conditional access policies.</span></span> <span data-ttu-id="b28cc-317">자세한 내용은 [일반적인 조건부 액세스 정책을 참조하십시오.](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common)</span><span class="sxs-lookup"><span data-stu-id="b28cc-317">For more information, see [Common Conditional Access policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common).</span></span>

### <a name="self-service-password-reset"></a><span data-ttu-id="b28cc-318">셀프 서비스 암호 재설정</span><span class="sxs-lookup"><span data-stu-id="b28cc-318">Self-service Password Reset</span></span>

<span data-ttu-id="b28cc-319">Microsoft Managed Desktop 서비스 계정을 제외한 모든 Microsoft Managed Desktop 사용자에 대해 SSPR(셀프 서비스 암호 재설정)을 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b28cc-319">Self-service Password Reset (SSPR) should be enabled for all Microsoft Managed Desktop users excluding Microsoft Managed Desktop service accounts.</span></span> <span data-ttu-id="b28cc-320">자세한 내용은 [자습서: 사용자가 Azure Active Directory](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-enable-sspr)셀프 서비스 암호 재설정을 사용하여 계정 잠금을 해제하거나 암호를 재설정할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="b28cc-320">For more information, see [Tutorial: Enable users to unlock their account or reset passwords using Azure Active Directory self-service password reset](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-enable-sspr).</span></span>

<span data-ttu-id="b28cc-321">**권고**</span><span class="sxs-lookup"><span data-stu-id="b28cc-321">**Advisory**</span></span>

<span data-ttu-id="b28cc-322">**SSPR** 선택 설정에 Microsoft Managed Desktop 장치가 포함되지만 Microsoft Managed Desktop 서비스 계정은 제외해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b28cc-322">Make sure that the SSPR **Selected** setting includes Microsoft Managed Desktop devices but excludes Microsoft Managed Desktop service accounts.</span></span> <span data-ttu-id="b28cc-323">SSPR을 사용하도록 설정하면 Microsoft Managed Desktop 서비스 계정이 예상대로 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b28cc-323">Microsoft Managed Desktop service accounts cannot work as expected when SSPR is enabled.</span></span>  


### <a name="standard-user-role"></a><span data-ttu-id="b28cc-324">표준 사용자 역할</span><span class="sxs-lookup"><span data-stu-id="b28cc-324">Standard user role</span></span>

<span data-ttu-id="b28cc-325">전역 관리자 및 장치 관리자의 Azure AD 역할이 할당된 사용자 이외에 Microsoft Managed Desktop 사용자는 로컬 관리자 권한이 없는 표준 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="b28cc-325">Other than those users who are assigned Azure AD roles of Global administrator and Device administrator, Microsoft Managed Desktop users will be standard users without local administrator privileges.</span></span> <span data-ttu-id="b28cc-326">다른 모든 사용자에게는 Microsoft Managed Desktop 장치를 시작할 때 표준 사용자 역할이 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="b28cc-326">All other users will be assigned a standard user role when they start their Microsoft Managed Desktop device.</span></span>

<span data-ttu-id="b28cc-327">**권고**</span><span class="sxs-lookup"><span data-stu-id="b28cc-327">**Advisory**</span></span>

<span data-ttu-id="b28cc-328">Microsoft Managed Desktop 사용자에게는 등록 후 Microsoft Managed Desktop 디바이스에 대한 로컬 관리자 권한이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b28cc-328">Microsoft Managed Desktop users will not have local administrator privileges on their Microsoft Managed Desktop devices after enrolling.</span></span>

## <a name="microsoft-365-apps-for-enterprise"></a><span data-ttu-id="b28cc-329">엔터프라이즈용 Microsoft 365 앱</span><span class="sxs-lookup"><span data-stu-id="b28cc-329">Microsoft 365 Apps for enterprise</span></span>

### <a name="onedrive"></a><span data-ttu-id="b28cc-330">OneDrive</span><span class="sxs-lookup"><span data-stu-id="b28cc-330">OneDrive</span></span>

<span data-ttu-id="b28cc-331">특정 **도메인에 가입된 PC에서만** 동기화 허용 설정이 Microsoft Managed Desktop과 충돌합니다.</span><span class="sxs-lookup"><span data-stu-id="b28cc-331">The **Allow syncing only on PCs joined to specific domains** setting will conflict with Microsoft Managed Desktop.</span></span> <span data-ttu-id="b28cc-332">OneDrive 관리 센터에서 OneDrive 설정에 [액세스할 수 있습니다.](https://admin.onedrive.com)</span><span class="sxs-lookup"><span data-stu-id="b28cc-332">You can access OneDrive settings at the OneDrive [admin center](https://admin.onedrive.com).</span></span>

<span data-ttu-id="b28cc-333">**권고**</span><span class="sxs-lookup"><span data-stu-id="b28cc-333">**Advisory**</span></span>

<span data-ttu-id="b28cc-334">특정 도메인 설정에 가입된 PC에서만 동기화 **허용을 사용하고** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b28cc-334">You're using the **Allow syncing only on PCs joined to specific domains** setting.</span></span> <span data-ttu-id="b28cc-335">이 설정은 Microsoft Managed Desktop에서는 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b28cc-335">This setting won't work with Microsoft Managed Desktop.</span></span> <span data-ttu-id="b28cc-336">이 설정을 사용하지 않도록 설정하고 대신 조건부 액세스 정책을 사용하기 위해 OneDrive를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="b28cc-336">Disable this setting, and instead set up OneDrive to use a conditional access policy.</span></span> <span data-ttu-id="b28cc-337">도움말은 [조건부 액세스 배포](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access) 계획을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="b28cc-337">See [Plan a Conditional Access deployment](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access) for help.</span></span>

