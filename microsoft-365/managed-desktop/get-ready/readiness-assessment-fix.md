---
title: 준비 평가 도구에서 발견한 문제 해결
description: 도구에서 발견 되는 각 문제에 대해 수행할 세부 작업
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 문서
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: c342ea9f662d883883755d2f67e5c25ffabddf83
ms.sourcegitcommit: c84cceb07e748969723a31b350e37f3ec79255ab
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/09/2020
ms.locfileid: "48948412"
---
# <a name="fix-issues-found-by-the-readiness-assessment-tool"></a><span data-ttu-id="da73e-104">준비 평가 도구에서 발견한 문제 해결</span><span class="sxs-lookup"><span data-stu-id="da73e-104">Fix issues found by the readiness assessment tool</span></span>

<span data-ttu-id="da73e-105">각 검사에 대해이 도구는 다음과 같은 네 가지 가능한 결과 중 하나를 보고 합니다.</span><span class="sxs-lookup"><span data-stu-id="da73e-105">For each check, the tool will report one of four possible results:</span></span>


|<span data-ttu-id="da73e-106">결과</span><span class="sxs-lookup"><span data-stu-id="da73e-106">Result</span></span>  |<span data-ttu-id="da73e-107">의미</span><span class="sxs-lookup"><span data-stu-id="da73e-107">Meaning</span></span>  |
|---------|---------|
|<span data-ttu-id="da73e-108">맞춤형</span><span class="sxs-lookup"><span data-stu-id="da73e-108">Ready</span></span>     | <span data-ttu-id="da73e-109">등록을 완료 하기 전에 작업을 수행할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="da73e-109">No action is required before completing enrollment.</span></span>        |
|<span data-ttu-id="da73e-110">조언</span><span class="sxs-lookup"><span data-stu-id="da73e-110">Advisory</span></span>    | <span data-ttu-id="da73e-111">등록 및 사용자를 위한 최상의 환경을 위해서는이 도구 또는이 문서에 나와 있는 단계를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="da73e-111">Follow the steps in the tool or this article for the best experience with enrollment and for users.</span></span> <span data-ttu-id="da73e-112">등록을 완료할 *수* 있지만 첫 번째 장치를 배포 하기 전에 이러한 문제를 해결 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="da73e-112">You *can* complete enrollment, but you must fix these issues before you deploy your first device.</span></span>        |
|<span data-ttu-id="da73e-113">준비되지 않음</span><span class="sxs-lookup"><span data-stu-id="da73e-113">Not ready</span></span> | <span data-ttu-id="da73e-114">*이러한 문제를 해결 하지 않으면 등록에 실패 합니다.*</span><span class="sxs-lookup"><span data-stu-id="da73e-114">*Enrollment will fail if you don't fix these issues.*</span></span> <span data-ttu-id="da73e-115">도구 또는이 문서의 단계에 따라 문제를 해결 합니다.</span><span class="sxs-lookup"><span data-stu-id="da73e-115">Follow the steps in the tool or this article to resolve them.</span></span>        |
|<span data-ttu-id="da73e-116">오류</span><span class="sxs-lookup"><span data-stu-id="da73e-116">Error</span></span> | <span data-ttu-id="da73e-117">사용 중인 Azure 활성 디렉터 (AD) 역할에이 검사를 실행할 수 있는 충분 한 권한이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="da73e-117">The Azure Active Director (AD) role you're using doesn't have sufficient permission to run this check.</span></span> |

## <a name="microsoft-intune-settings"></a><span data-ttu-id="da73e-118">Microsoft Intune 설정</span><span class="sxs-lookup"><span data-stu-id="da73e-118">Microsoft Intune settings</span></span>

### <a name="autopilot-deployment-profile"></a><span data-ttu-id="da73e-119">Autopilot 배포 프로필</span><span class="sxs-lookup"><span data-stu-id="da73e-119">Autopilot deployment profile</span></span>

<span data-ttu-id="da73e-120">할당 된 또는 동적 그룹을 대상으로 하는 기존 Autopilot 프로필은 Microsoft Managed Desktop에서 사용 하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="da73e-120">You shouldn't have any existing Autopilot profiles that target assigned or dynamic groups used by Microsoft Managed Desktop.</span></span> <span data-ttu-id="da73e-121">Microsoft Managed Desktop은 Autopilot를 사용 하 여 새 장치를 프로 비전 합니다.</span><span class="sxs-lookup"><span data-stu-id="da73e-121">Microsoft Managed Desktop uses Autopilot to provision new devices.</span></span>

<span data-ttu-id="da73e-122">**준비되지 않음**</span><span class="sxs-lookup"><span data-stu-id="da73e-122">**Not ready**</span></span>

<span data-ttu-id="da73e-123">모든 장치에 할당 된 Autopilot 프로필이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="da73e-123">You have an Autopilot profile that is assigned to all devices.</span></span> <span data-ttu-id="da73e-124">자세한 단계는 [Windows Autopilot을 사용 하 여 Intune에서 windows 장치 등록](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="da73e-124">For steps, see [Enroll Windows devices in Intune by using Windows Autopilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot).</span></span> <span data-ttu-id="da73e-125">Microsoft Managed Desktop 등록 후에는 Autopilot 정책을 설정 하 여 **최신 작업 공간 장치 (All** Azure AD 그룹)를 제외 합니다.</span><span class="sxs-lookup"><span data-stu-id="da73e-125">After Microsoft Managed Desktop enrollment, set your Autopilot policy to exclude the **Modern Workplace Devices -All** Azure AD group.</span></span>

<span data-ttu-id="da73e-126">**조언**</span><span class="sxs-lookup"><span data-stu-id="da73e-126">**Advisory**</span></span>

<span data-ttu-id="da73e-127">Autopilot 프로필이 등록 시 만들 Microsoft Managed Desktop devices를 포함 하지 않는 할당 된 또는 동적 Azure AD 그룹을 대상으로 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="da73e-127">Make sure that your Autopilot profiles target an assigned or dynamic Azure AD group that doesn't include Microsoft Managed Desktop devices that will be created at enrollment.</span></span> <span data-ttu-id="da73e-128">자세한 단계는 [Windows Autopilot을 사용 하 여 Intune에서 windows 장치 등록](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="da73e-128">For steps, see [Enroll Windows devices in Intune by using Windows Autopilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot).</span></span> <span data-ttu-id="da73e-129">Microsoft Managed Desktop 등록 후에는 Autopilot 정책을 설정 하 여 **최신 작업 공간 장치 (All** Azure AD 그룹)를 제외 합니다.</span><span class="sxs-lookup"><span data-stu-id="da73e-129">After Microsoft Managed Desktop enrollment, set your Autopilot policy to exclude the **Modern Workplace Devices -All** Azure AD group.</span></span>


### <a name="certificate-connectors"></a><span data-ttu-id="da73e-130">인증서 커넥터</span><span class="sxs-lookup"><span data-stu-id="da73e-130">Certificate connectors</span></span>

<span data-ttu-id="da73e-131">Microsoft Managed Desktop에서 등록 하려는 장치에서 사용 하는 인증서 커넥터가 있으면 커넥터에 오류가 발생 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="da73e-131">If you have any certificate connectors used by the devices you want to enroll in Microsoft Managed Desktop, the connectors cannot have any errors.</span></span> <span data-ttu-id="da73e-132">다음 권고 중 하나만 상황에 맞게 적용 되므로 신중 하 게 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="da73e-132">Only one of the following advisories will apply to your situation, so check them carefully.</span></span>

<span data-ttu-id="da73e-133">**조언**</span><span class="sxs-lookup"><span data-stu-id="da73e-133">**Advisory**</span></span>

<span data-ttu-id="da73e-134">인증서 커넥터가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="da73e-134">No certificate connectors are present.</span></span> <span data-ttu-id="da73e-135">커넥터가 필요 하지 않을 수 있지만 Microsoft Managed Desktop 장치에 대 한 네트워크 연결에 대 한 몇 가지 필요 여부를 평가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="da73e-135">It's possible you don't need any connectors, but you should evaluate whether you might need some for network connectivity to Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="da73e-136">자세한 내용은 [Microsoft Managed Desktop에 대 한 인증서 및 네트워크 프로필 준비](certs-wifi-lan.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="da73e-136">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>

<span data-ttu-id="da73e-137">**조언**</span><span class="sxs-lookup"><span data-stu-id="da73e-137">**Advisory**</span></span>

<span data-ttu-id="da73e-138">하나 이상의 인증서 커넥터에 오류가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da73e-138">At least one certificate connector has an error.</span></span> <span data-ttu-id="da73e-139">Microsoft Managed Desktop 장치에 연결 하기 위해이 커넥터가 필요한 경우 오류를 해결 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="da73e-139">If you need this connector for connectivity to Microsoft Managed Desktop devices, you must resolve the error.</span></span> <span data-ttu-id="da73e-140">자세한 내용은 [Microsoft Managed Desktop에 대 한 인증서 및 네트워크 프로필 준비](certs-wifi-lan.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="da73e-140">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>


<span data-ttu-id="da73e-141">**조언**</span><span class="sxs-lookup"><span data-stu-id="da73e-141">**Advisory**</span></span>

<span data-ttu-id="da73e-142">하나 이상의 인증서 커넥터가 있고 오류가 보고 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="da73e-142">You have at least one certificate connector and no errors are reported.</span></span> <span data-ttu-id="da73e-143">그러나 Microsoft Managed Desktop 장치에 대 한 커넥터를 다시 사용 하려면 프로필을 만들어야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da73e-143">However, you might need to create a profile to reuse the connector for Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="da73e-144">자세한 내용은 [Microsoft Managed Desktop에 대 한 인증서 및 네트워크 프로필 준비](certs-wifi-lan.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="da73e-144">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>


### <a name="conditional-access-policies"></a><span data-ttu-id="da73e-145">조건부 액세스 정책</span><span class="sxs-lookup"><span data-stu-id="da73e-145">Conditional access policies</span></span>

<span data-ttu-id="da73e-146">Azure AD 조직의 조건부 액세스 정책은 Microsoft 관리 데스크톱 사용자를 대상으로 하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="da73e-146">Conditional access policies in your Azure AD organization must not target any Microsoft Manage Desktop users.</span></span>

<span data-ttu-id="da73e-147">**준비되지 않음**</span><span class="sxs-lookup"><span data-stu-id="da73e-147">**Not ready**</span></span>

<span data-ttu-id="da73e-148">모든 사용자를 대상으로 하는 하나 이상의 조건부 액세스 정책이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="da73e-148">You have at least one conditional access policy that targets all users.</span></span> <span data-ttu-id="da73e-149">등록할 때 생성 되는 Microsoft Managed Desktop service 계정의 Azure AD 그룹을 포함 하지 않는 특정 Azure AD 그룹을 대상으로 하도록 정책을 다시 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="da73e-149">Reset the policy to target a specific Azure AD group that does not include the Azure AD group of Microsoft Managed Desktop service accounts that will be created at enrollment.</span></span> <span data-ttu-id="da73e-150">단계에 대 한 자세한 내용은 [조건부 액세스: 사용자 및 그룹](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="da73e-150">For steps, see [Conditional Access: Users and groups](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups).</span></span>

<span data-ttu-id="da73e-151">**조언**</span><span class="sxs-lookup"><span data-stu-id="da73e-151">**Advisory**</span></span>

<span data-ttu-id="da73e-152">모든 조건부 액세스 정책에서 **최신 직장의 작업 공간 서비스 계정** Azure AD 그룹을 제외 했는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="da73e-152">Make sure that any conditional access policies you have exclude the **Modern Workplace Service Accounts** Azure AD group.</span></span> <span data-ttu-id="da73e-153">단계에 대 한 자세한 내용은 [조건부 액세스 조정을](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/conditional-access)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="da73e-153">For steps, see [Adjust conditional access](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/conditional-access).</span></span> <span data-ttu-id="da73e-154">**최신 작업 공간 서비스 계정** Azure AD 그룹은 등록할 때 서비스를 위해 만드는 동적 그룹입니다.</span><span class="sxs-lookup"><span data-stu-id="da73e-154">The **Modern Workplace Service Accounts** Azure AD group is a dynamic group that we create for the service when you enroll.</span></span> <span data-ttu-id="da73e-155">등록 한 후에는이 그룹을 제외 하려면 다시 방문 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="da73e-155">You'll have to come back to exclude this group after enrollment.</span></span> <span data-ttu-id="da73e-156">이러한 서비스 계정에 대 한 자세한 내용은 [표준 운영 절차](../service-description/operations-and-monitoring.md#standard-operating-procedures)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="da73e-156">For more about these service accounts, see [Standard operating procedures](../service-description/operations-and-monitoring.md#standard-operating-procedures).</span></span>

<span data-ttu-id="da73e-157">**오류**</span><span class="sxs-lookup"><span data-stu-id="da73e-157">**Error**</span></span>

<span data-ttu-id="da73e-158">Intune 관리자 역할에는이 검사에 대 한 충분 한 사용 권한이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="da73e-158">The Intune Administrator role doesn't have sufficient permissions for this check.</span></span> <span data-ttu-id="da73e-159">또한이 검사를 실행 하려면 이러한 모든 Azure AD 역할을 할당 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="da73e-159">You'll also need any of these Azure AD roles assigned to run this check:</span></span>

- <span data-ttu-id="da73e-160">보안 읽기 권한자</span><span class="sxs-lookup"><span data-stu-id="da73e-160">Security Reader</span></span>
- <span data-ttu-id="da73e-161">보안 관리자</span><span class="sxs-lookup"><span data-stu-id="da73e-161">Security Administrator</span></span>
- <span data-ttu-id="da73e-162">조건부 액세스 관리자</span><span class="sxs-lookup"><span data-stu-id="da73e-162">Conditional Access Administrator</span></span>
- <span data-ttu-id="da73e-163">전역 읽기 권한자</span><span class="sxs-lookup"><span data-stu-id="da73e-163">Global Reader</span></span>
- <span data-ttu-id="da73e-164">장치 관리자</span><span class="sxs-lookup"><span data-stu-id="da73e-164">Devices Administrator</span></span>


### <a name="device-compliance-policies"></a><span data-ttu-id="da73e-165">장치 준수 정책</span><span class="sxs-lookup"><span data-stu-id="da73e-165">Device Compliance policies</span></span>

<span data-ttu-id="da73e-166">Azure AD 조직의 Intune 장치 준수 정책은 Microsoft Managed Desktop 사용자를 대상으로 하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="da73e-166">Intune Device Compliance policies in your Azure AD organization must not target any Microsoft Managed Desktop users.</span></span>

<span data-ttu-id="da73e-167">**준비되지 않음**</span><span class="sxs-lookup"><span data-stu-id="da73e-167">**Not ready**</span></span>

<span data-ttu-id="da73e-168">모든 사용자를 대상으로 하는 준수 정책이 하나 이상 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="da73e-168">You have at least one compliance policy that targets all users.</span></span> <span data-ttu-id="da73e-169">Microsoft Managed Desktop users를 포함 하지 않는 특정 Azure AD 그룹을 대상으로 하도록 정책을 다시 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="da73e-169">Reset the policy to target a specific Azure AD group that does not include any Microsoft Managed Desktop users.</span></span> <span data-ttu-id="da73e-170">자세한 단계는 [Microsoft Intune에서 준수 정책 만들기](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="da73e-170">For steps, see [Create a compliance policy in Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy).</span></span>

<span data-ttu-id="da73e-171">**조언**</span><span class="sxs-lookup"><span data-stu-id="da73e-171">**Advisory**</span></span>

<span data-ttu-id="da73e-172">준수 정책에 Microsoft Managed Desktop users가 포함 되어 있지 않은지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="da73e-172">Make sure that any compliance policies you have don't include any Microsoft Managed Desktop users.</span></span> <span data-ttu-id="da73e-173">자세한 단계는 [Microsoft Intune에서 준수 정책 만들기](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="da73e-173">For steps, see [Create a compliance policy in Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy).</span></span>



### <a name="device-configuration-policies"></a><span data-ttu-id="da73e-174">장치 구성 정책</span><span class="sxs-lookup"><span data-stu-id="da73e-174">Device Configuration policies</span></span>

<span data-ttu-id="da73e-175">Azure AD 조직의 Intune 장치 구성 정책은 Microsoft 관리 데스크톱 장치 또는 사용자를 대상으로 하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="da73e-175">Intune Device Configuration policies in your Azure AD organization must not target any Microsoft Manage Desktop devices or users.</span></span>

<span data-ttu-id="da73e-176">**준비되지 않음**</span><span class="sxs-lookup"><span data-stu-id="da73e-176">**Not ready**</span></span>

<span data-ttu-id="da73e-177">모든 사용자, 모든 장치 또는 둘 다를 대상으로 하는 구성 정책이 하나 이상 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="da73e-177">You have at least one configuration policy that targets all users, all devices, or both.</span></span> <span data-ttu-id="da73e-178">Microsoft Managed Desktop 장치를 포함 하지 않는 특정 Azure AD 그룹을 대상으로 하도록 정책을 다시 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="da73e-178">Reset the policy to target a specific Azure AD group that does not include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="da73e-179">자세한 단계는 [Microsoft Intune에서 준수 정책 만들기](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="da73e-179">For steps, see [Create a compliance policy in Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure).</span></span>

<span data-ttu-id="da73e-180">**조언**</span><span class="sxs-lookup"><span data-stu-id="da73e-180">**Advisory**</span></span>

<span data-ttu-id="da73e-181">준수 정책에 Microsoft 관리 되는 데스크톱 장치 또는 사용자가 포함 되어 있지 않은지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="da73e-181">Make sure that any compliance policies you have don't include any Microsoft Managed Desktop devices or users.</span></span> <span data-ttu-id="da73e-182">자세한 단계는 [Microsoft Intune에서 준수 정책 만들기](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="da73e-182">For steps, see [Create a compliance policy in Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure).</span></span>



### <a name="device-type-restrictions"></a><span data-ttu-id="da73e-183">장치 유형 제한</span><span class="sxs-lookup"><span data-stu-id="da73e-183">Device type restrictions</span></span>

<span data-ttu-id="da73e-184">Microsoft Managed Desktop 장치는 Intune에서 등록할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="da73e-184">Microsoft Managed Desktop devices must be allowed to enroll in Intune.</span></span>

<span data-ttu-id="da73e-185">**준비되지 않음**</span><span class="sxs-lookup"><span data-stu-id="da73e-185">**Not ready**</span></span>

<span data-ttu-id="da73e-186">[등록 제한 설정](https://docs.microsoft.com/mem/intune/enrollment/enrollment-restrictions-set) 의 단계에 따라 설정을 **허용** 으로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="da73e-186">Follow the steps in [Set enrollment restrictions](https://docs.microsoft.com/mem/intune/enrollment/enrollment-restrictions-set) to change the setting to **Allow**.</span></span>


### <a name="enrollment-status-page"></a><span data-ttu-id="da73e-187">등록 상태 페이지</span><span class="sxs-lookup"><span data-stu-id="da73e-187">Enrollment Status Page</span></span>

<span data-ttu-id="da73e-188">현재 ESP (등록 상태 페이지)를 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="da73e-188">You currently have the Enrollment Status Page (ESP) enabled.</span></span> <span data-ttu-id="da73e-189">이 기능의 공개 미리 보기에 참여 하는 경우에는이 항목을 무시 해도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="da73e-189">If you are participating in the public preview of this feature, you can ignore this item.</span></span> <span data-ttu-id="da73e-190">자세한 내용은 [Autopilot 및 등록 상태 페이지를 사용 하 여 첫 실행 환경을](../get-started/esp-first-run.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="da73e-190">For more information, see [First-run experience with Autopilot and the Enrollment Status Page](../get-started/esp-first-run.md).</span></span>

<span data-ttu-id="da73e-191">**준비되지 않음**</span><span class="sxs-lookup"><span data-stu-id="da73e-191">**Not ready**</span></span>

<span data-ttu-id="da73e-192">**앱 및 프로필 구성 진행률을 표시** 하도록 ESP 기본 프로필을 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="da73e-192">You have the ESP default profile set to **Show app and profile configuration progress**.</span></span> <span data-ttu-id="da73e-193">이 설정을 사용 하지 않도록 설정 하거나, Azure AD 그룹에 대 한 할당에 [등록 상태 설정 페이지](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status)의 단계에 따라 Microsoft Managed Desktop devices가 포함 되지 않는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="da73e-193">Disable this setting or make sure that assignments to any Azure AD group do not include Microsoft Managed Desktop devices by following the steps in [Set up the Enrollment Status Page](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status).</span></span>

<span data-ttu-id="da73e-194">**조언**</span><span class="sxs-lookup"><span data-stu-id="da73e-194">**Advisory**</span></span>

<span data-ttu-id="da73e-195">**앱 및 프로필 구성 진행률** 설정이 있는 모든 프로필이 Microsoft Managed Desktop 장치를 포함 하는 Azure AD 그룹에 할당 되어 있지 않은지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="da73e-195">Make sure that any profiles that have the **Show app and profile configuration progress** setting are not assigned to any Azure AD group that includes Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="da73e-196">자세한 내용은 [등록 상태 설정 페이지](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="da73e-196">For more information, see [Set up the Enrollment Status Page](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status).</span></span>

### <a name="intune-enrollment"></a><span data-ttu-id="da73e-197">Intune 등록</span><span class="sxs-lookup"><span data-stu-id="da73e-197">Intune enrollment</span></span>

<span data-ttu-id="da73e-198">Azure AD 조직의 Windows 10 장치는 Intune에서 자동으로 등록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="da73e-198">Windows 10 devices in your Azure AD organization must be automatically enrolled in Intune.</span></span>

<span data-ttu-id="da73e-199">**조언**</span><span class="sxs-lookup"><span data-stu-id="da73e-199">**Advisory**</span></span>

<span data-ttu-id="da73e-200">MDM 사용자 범위가 **전혀** 또는 **모두** 로 설정 되어 **Some** 있지는 않은지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="da73e-200">Make sure the MDM User scope is set to **Some** or **All** , not **None**.</span></span> <span data-ttu-id="da73e-201">**일부** 를 선택 하는 경우 등록 후에 다시 돌아와서 **그룹** 에 대 한 **최신 작업 회사-All** Azure AD 그룹을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="da73e-201">If you choose **Some** , come back after enrollment and select the **Modern Workplace -All** Azure AD group for **Groups**.</span></span>


### <a name="microsoft-store-for-business"></a><span data-ttu-id="da73e-202">비즈니스용 Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="da73e-202">Microsoft Store for Business</span></span>

<span data-ttu-id="da73e-203">회사 포털을 다운로드 하 여 Microsoft Project 및 Microsoft Visio와 같은 일부 앱을 배포할 수 있도록 Microsoft Store for Business를 사용 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da73e-203">We use Microsoft Store for Business so that you can download Company Portal to deploy some apps, such as Microsoft Project and Microsoft Visio.</span></span>

<span data-ttu-id="da73e-204">**준비되지 않음**</span><span class="sxs-lookup"><span data-stu-id="da73e-204">**Not ready**</span></span>

<span data-ttu-id="da73e-205">비즈니스용 Microsoft Store가 사용 하도록 설정 되지 않았거나 Intune과 동기화 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="da73e-205">Microsoft Store for Business either isn't enabled or isn't synced with Intune.</span></span> <span data-ttu-id="da73e-206">자세한 내용은 microsoft [intune을 사용 하 여 비즈니스용 Microsoft 스토어에서 구입한 볼륨 구입 앱을 관리](https://docs.microsoft.com/mem/intune/apps/windows-store-for-business) 하 고 [장치에 Intune 회사 포털을 설치](../get-started/company-portal.md)하는 방법을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="da73e-206">For more information, see [How to manage volume purchased apps from the Microsoft Store for Business with Microsoft Intune](https://docs.microsoft.com/mem/intune/apps/windows-store-for-business) and [Install Intune Company Portal on on devices](../get-started/company-portal.md).</span></span>

### <a name="multi-factor-authentication"></a><span data-ttu-id="da73e-207">다단계 인증</span><span class="sxs-lookup"><span data-stu-id="da73e-207">Multi-factor authentication</span></span>

<span data-ttu-id="da73e-208">Microsoft Managed Desktop 서비스 계정에는 실수로 다단계 인증을 적용 해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="da73e-208">Multi-factor authentication must not accidentally be applied to Microsoft Managed Desktop service accounts.</span></span>


<span data-ttu-id="da73e-209">**준비되지 않음**</span><span class="sxs-lookup"><span data-stu-id="da73e-209">**Not ready**</span></span>

<span data-ttu-id="da73e-210">일부 MFA (multi-factor authentication) 정책이 모든 사용자에 게 할당 된 조건부 액세스 정책에 대해 "필수"로 설정 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="da73e-210">You have some multi-factor authentication (MFA) policies set as "required" for conditional access policies that are assigned to all users.</span></span> <span data-ttu-id="da73e-211">Microsoft Managed Desktop 장치를 포함 하지 않는 특정 Azure AD 그룹을 대상으로 하는 할당을 사용 하도록 정책을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="da73e-211">Change the policy to use an Assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="da73e-212">자세한 내용은 [조건부 액세스 정책](#conditional-access-policies) 및 [조건부 액세스: 모든 사용자에 대해 MFA 필요](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="da73e-212">For more information, see [Conditional access policies](#conditional-access-policies) and [Conditional Access: Require MFA for all users](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa).</span></span>

<span data-ttu-id="da73e-213">**조언**</span><span class="sxs-lookup"><span data-stu-id="da73e-213">**Advisory**</span></span>

<span data-ttu-id="da73e-214">MFA가 필요한 조건부 액세스 정책이 **최신 직장의 모든** Azure AD 그룹을 제외 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="da73e-214">Make sure that any conditional access policies that require MFA exclude the **Modern Workplace -All** Azure AD group.</span></span> <span data-ttu-id="da73e-215">자세한 내용은 [조건부 액세스 정책](#conditional-access-policies) 및 [조건부 액세스: 모든 사용자에 대해 MFA 필요](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="da73e-215">For more information, see [Conditional access policies](#conditional-access-policies) and [Conditional Access: Require MFA for all users](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa).</span></span> <span data-ttu-id="da73e-216">**최신 작업 회사-All** Azure AD 그룹은 Microsoft Managed Desktop에 등록할 때 작성 하는 동적 그룹으로, 등록 후에이 그룹을 제외 하려면 다시 방문 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="da73e-216">The **Modern Workplace -All** Azure AD group is a dynamic group that we create when you enroll in Microsoft Managed Desktop, so you'll have to come back to exclude this group after enrollment.</span></span>

<span data-ttu-id="da73e-217">**오류**</span><span class="sxs-lookup"><span data-stu-id="da73e-217">**Error**</span></span>

<span data-ttu-id="da73e-218">Intune 관리자 역할에는이 검사에 대 한 충분 한 사용 권한이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="da73e-218">The Intune Administrator role doesn't have sufficient permissions for this check.</span></span> <span data-ttu-id="da73e-219">또한이 검사를 실행 하려면 이러한 모든 Azure AD 역할을 할당 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="da73e-219">You'll also need any of these Azure AD roles assigned to run this check:</span></span>

- <span data-ttu-id="da73e-220">보안 읽기 권한자</span><span class="sxs-lookup"><span data-stu-id="da73e-220">Security Reader</span></span>
- <span data-ttu-id="da73e-221">보안 관리자</span><span class="sxs-lookup"><span data-stu-id="da73e-221">Security Administrator</span></span>
- <span data-ttu-id="da73e-222">조건부 액세스 관리자</span><span class="sxs-lookup"><span data-stu-id="da73e-222">Conditional Access Administrator</span></span>
- <span data-ttu-id="da73e-223">전역 읽기 권한자</span><span class="sxs-lookup"><span data-stu-id="da73e-223">Global Reader</span></span>
- <span data-ttu-id="da73e-224">장치 관리자</span><span class="sxs-lookup"><span data-stu-id="da73e-224">Devices Administrator</span></span>


### <a name="powershell-scripts"></a><span data-ttu-id="da73e-225">PowerShell 스크립트</span><span class="sxs-lookup"><span data-stu-id="da73e-225">PowerShell scripts</span></span>

<span data-ttu-id="da73e-226">Microsoft Managed Desktop 장치를 대상으로 하는 방식으로 Windows PowerShell 스크립트를 할당할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="da73e-226">Windows PowerShell scripts can't be assigned in a way that would target Microsoft Managed Desktop devices.</span></span>  

<span data-ttu-id="da73e-227">**조언**</span><span class="sxs-lookup"><span data-stu-id="da73e-227">**Advisory**</span></span>

<span data-ttu-id="da73e-228">Azure AD 조직의 Windows PowerShell 스크립트에서 어떤 Microsoft 데스크톱 장치나 사용자도 관리 하지 않는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="da73e-228">Make sure that Windows PowerShell scripts in your Azure AD organization don't target any Microsoft Manage Desktop devices or users.</span></span> <span data-ttu-id="da73e-229">모든 사용자, 모든 장치 또는 둘 다를 대상으로 하는 PowerShell 스크립트를 할당 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="da73e-229">Do not assign a PowerShell script to target all users, all devices, or both.</span></span> <span data-ttu-id="da73e-230">Microsoft Managed Desktop 장치를 포함 하지 않는 특정 Azure AD 그룹을 대상으로 하는 할당을 사용 하도록 정책을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="da73e-230">Change the policy to use an Assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="da73e-231">자세한 내용은 [Intune에서 Windows 10 장치에서 PowerShell 스크립트 사용](https://docs.microsoft.com/mem/intune/apps/intune-management-extension)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="da73e-231">For more information, see [Use PowerShell scripts on Windows 10 devices in Intune](https://docs.microsoft.com/mem/intune/apps/intune-management-extension).</span></span>

### <a name="region"></a><span data-ttu-id="da73e-232">지역</span><span class="sxs-lookup"><span data-stu-id="da73e-232">Region</span></span>

<span data-ttu-id="da73e-233">사용자의 지역을 Microsoft Managed Desktop에서 지원 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="da73e-233">Your region must be supported by Microsoft Managed Desktop.</span></span>

<span data-ttu-id="da73e-234">**준비되지 않음**</span><span class="sxs-lookup"><span data-stu-id="da73e-234">**Not ready**</span></span>

<span data-ttu-id="da73e-235">현재 Azure AD 조직 지역이 Microsoft Managed Desktop에서 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="da73e-235">Your Azure AD organization region isn't currently supported by Microsoft Managed Desktop.</span></span> <span data-ttu-id="da73e-236">자세한 내용은 [Microsoft Managed Desktop 지원 지역 및 언어](../service-description/regions-languages.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="da73e-236">For more information, see [Microsoft Managed Desktop supported regions and languages](../service-description/regions-languages.md).</span></span>

<span data-ttu-id="da73e-237">**조언**</span><span class="sxs-lookup"><span data-stu-id="da73e-237">**Advisory**</span></span>

<span data-ttu-id="da73e-238">Azure AD 조직이 있는 하나 이상의 국가는 Microsoft Managed Desktop에서 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="da73e-238">One or more of the countries where your Azure AD organization is located isn't supported by Microsoft Managed Desktop.</span></span> <span data-ttu-id="da73e-239">자세한 내용은 [Microsoft Managed Desktop 지원 지역 및 언어](../service-description/regions-languages.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="da73e-239">For more information, see [Microsoft Managed Desktop supported regions and languages](../service-description/regions-languages.md).</span></span>


### <a name="security-baselines"></a><span data-ttu-id="da73e-240">보안 기준</span><span class="sxs-lookup"><span data-stu-id="da73e-240">Security baselines</span></span>

<span data-ttu-id="da73e-241">보안 기본 정책은 Microsoft 관리 되는 데스크톱 장치를 대상으로 지정 해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="da73e-241">Security baseline policies should not target any Microsoft Managed Desktop devices.</span></span>

<span data-ttu-id="da73e-242">**준비되지 않음**</span><span class="sxs-lookup"><span data-stu-id="da73e-242">**Not ready**</span></span>

<span data-ttu-id="da73e-243">모든 사용자, 모든 장치 또는 둘 다를 대상으로 하는 보안 기준 프로필을 보유 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da73e-243">You have a security baseline profile that targets all users, all devices or both.</span></span> <span data-ttu-id="da73e-244">Microsoft Managed Desktop 장치를 포함 하지 않는 특정 Azure AD 그룹을 대상으로 하는 할당을 사용 하도록 정책을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="da73e-244">Change the policy to use an Assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="da73e-245">자세한 단계는 [security 기준선이 Use To Windows 10 devices In Intune](https://docs.microsoft.com/mem/intune/protect/security-baselines)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="da73e-245">For steps, see [Use security baselines to configure Windows 10 devices in Intune](https://docs.microsoft.com/mem/intune/protect/security-baselines).</span></span>

<span data-ttu-id="da73e-246">**조언**</span><span class="sxs-lookup"><span data-stu-id="da73e-246">**Advisory**</span></span>

<span data-ttu-id="da73e-247">Microsoft Managed Desktop 장치를 제외 하는 보안 기본 정책이 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="da73e-247">Make sure that any security baseline policies you have exclude Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="da73e-248">자세한 단계는 [security 기준선이 Use To Windows 10 devices In Intune](https://docs.microsoft.com/mem/intune/protect/security-baselines)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="da73e-248">For steps, see [Use security baselines to configure Windows 10 devices in Intune](https://docs.microsoft.com/mem/intune/protect/security-baselines).</span></span> <span data-ttu-id="da73e-249">**최신 작업 공간 장치-모든** Azure AD 그룹은 Microsoft Managed Desktop에 등록할 때 만든 동적 그룹으로, 등록 후에이 그룹을 제외 하려면 다시 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="da73e-249">The **Modern Workplace Devices -All** Azure AD group is a dynamic group that we create when you enroll in Microsoft Managed Desktop, so you'll have to come back to exclude this group after enrollment.</span></span>


### <a name="windows-apps"></a><span data-ttu-id="da73e-250">Windows 앱</span><span class="sxs-lookup"><span data-stu-id="da73e-250">Windows apps</span></span>

<span data-ttu-id="da73e-251">Microsoft Managed Desktop 사용자에 게 부여할 앱을 검토 합니다.</span><span class="sxs-lookup"><span data-stu-id="da73e-251">Review apps you want your Microsoft Managed Desktop users to have.</span></span>

<span data-ttu-id="da73e-252">**조언**</span><span class="sxs-lookup"><span data-stu-id="da73e-252">**Advisory**</span></span>

<span data-ttu-id="da73e-253">Microsoft Managed Desktop 사용자에 게 부여할 앱의 인벤토리를 준비 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="da73e-253">You should prepare an inventory of the apps that you want your Microsoft Managed Desktop users to have.</span></span> <span data-ttu-id="da73e-254">Intune을 통해 이러한 앱을 배포할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="da73e-254">Make sure these apps can be deployed by Intune.</span></span> <span data-ttu-id="da73e-255">자세한 내용은 [Microsoft Managed Desktop의 앱](apps.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="da73e-255">For more information, see [Apps in Microsoft Managed Desktop](apps.md).</span></span>

<span data-ttu-id="da73e-256">Microsoft 계정 담당자에 게 문의 하 여 Intune으로 마이그레이션하거나, 조정이 필요한 앱을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da73e-256">You can ask your Microsoft account representative for a query in Microsoft Endpoint Configuration Manager to identify those apps that are ready to migrate to Intune or need adjustment.</span></span>


### <a name="windows-hello-for-business"></a><span data-ttu-id="da73e-257">비즈니스용 Windows Hello</span><span class="sxs-lookup"><span data-stu-id="da73e-257">Windows Hello for Business</span></span>

<span data-ttu-id="da73e-258">Microsoft Managed Desktop을 사용 하려면 비즈니스용 Windows Hello가 설정 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="da73e-258">Microsoft Managed Desktop requires Windows Hello for Business to be enabled.</span></span>

<span data-ttu-id="da73e-259">**준비되지 않음**</span><span class="sxs-lookup"><span data-stu-id="da73e-259">**Not ready**</span></span>

<span data-ttu-id="da73e-260">비즈니스용 Windows Hello가 사용 하지 않도록 설정 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="da73e-260">Windows Hello for Business is disabled.</span></span> <span data-ttu-id="da73e-261">[비즈니스용 Windows Hello 정책 만들기](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy) 의 단계를 수행 하 여이 기능을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="da73e-261">Enable it by following the steps in [Create a Windows Hello for Business policy](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)</span></span>

<span data-ttu-id="da73e-262">**조언**</span><span class="sxs-lookup"><span data-stu-id="da73e-262">**Advisory**</span></span>

<span data-ttu-id="da73e-263">비즈니스용 Windows Hello가 설정 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="da73e-263">Windows Hello for Business is not set up.</span></span> <span data-ttu-id="da73e-264">[비즈니스용 Windows Hello 정책 만들기](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)의 단계를 수행 하 여이 기능을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="da73e-264">Enable it by following the steps in [Create a Windows Hello for Business policy](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy).</span></span>


### <a name="windows-10-update-rings"></a><span data-ttu-id="da73e-265">Windows 10 업데이트 링</span><span class="sxs-lookup"><span data-stu-id="da73e-265">Windows 10 update rings</span></span>

<span data-ttu-id="da73e-266">Intune의 "Windows 10 업데이트 링" 정책은 Microsoft Managed Desktop 장치를 대상으로 하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="da73e-266">Your "Windows 10 update ring" policy in Intune must not target any Microsoft Managed Desktop devices.</span></span>

<span data-ttu-id="da73e-267">**준비되지 않음**</span><span class="sxs-lookup"><span data-stu-id="da73e-267">**Not ready**</span></span>

<span data-ttu-id="da73e-268">모든 장치, 모든 사용자 또는 둘 다를 대상으로 하는 "업데이트 링" 정책이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da73e-268">You have an "update ring" policy that targets all devices, all users, or both.</span></span> <span data-ttu-id="da73e-269">Microsoft Managed Desktop 장치를 포함 하지 않는 특정 Azure AD 그룹을 대상으로 하는 할당을 사용 하도록 정책을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="da73e-269">Change the policy to use an Assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="da73e-270">자세한 단계는 [Intune에서 Windows 10 소프트웨어 업데이트 관리](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="da73e-270">For steps, see [Manage Windows 10 software updates in Intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure).</span></span>

<span data-ttu-id="da73e-271">**조언**</span><span class="sxs-lookup"><span data-stu-id="da73e-271">**Advisory**</span></span>

<span data-ttu-id="da73e-272">모든 업데이트 링 정책에서 **최신 작업 공간 장치 (모든** Azure AD 그룹)를 제외 했는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="da73e-272">Make sure that any update ring policies you have exclude the **Modern Workplace Devices -All** Azure AD group.</span></span> <span data-ttu-id="da73e-273">이러한 정책에 대해 Azure AD 사용자 그룹을 할당 한 경우에는 모든 업데이트 링 정책에서 Microsoft Managed Desktop users를 포함 하는 **최신 직장** 의 Azure AD 그룹도 제외 했는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="da73e-273">If you have assigned Azure AD user group to these policies, make sure that any update ring policies you have also excluded the **Modern Workplace -All** Azure AD group which includes your Microsoft Managed Desktop users.</span></span> <span data-ttu-id="da73e-274">자세한 단계는 [Intune에서 Windows 10 소프트웨어 업데이트 관리](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="da73e-274">For steps, see [Manage Windows 10 software updates in Intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure).</span></span> <span data-ttu-id="da73e-275">**최신 작업 공간 장치-all** 및 **현대 직장의 모든** Azure AD 그룹은 Microsoft Managed Desktop에 등록할 때 만드는 그룹에 할당 되므로 등록 후에는이 그룹을 제외 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="da73e-275">Both the **Modern Workplace Devices -All** and **Modern Workplace -All** Azure AD groups are assigned groups that we create when you enroll in Microsoft Managed Desktop, so you'll have to come back to exclude this group after enrollment.</span></span>


## <a name="azure-active-directory-settings"></a><span data-ttu-id="da73e-276">Azure Active Directory 설정</span><span class="sxs-lookup"><span data-stu-id="da73e-276">Azure Active Directory settings</span></span>


### <a name="ad-hoc-subscriptions"></a><span data-ttu-id="da73e-277">임시 구독</span><span class="sxs-lookup"><span data-stu-id="da73e-277">Ad hoc subscriptions</span></span>

<span data-ttu-id="da73e-278">"False"로 설정 된 경우 엔터프라이즈 상태 로밍이 제대로 작동 하지 않을 수 있는 설정을 확인 하는 방법을 제안 합니다.</span><span class="sxs-lookup"><span data-stu-id="da73e-278">Advises how to check a setting that (if set to "false") might prevent Enterprise State Roaming from working correctly.</span></span>

<span data-ttu-id="da73e-279">**조언**</span><span class="sxs-lookup"><span data-stu-id="da73e-279">**Advisory**</span></span>

<span data-ttu-id="da73e-280">**AllowAdHocSubscriptions** 이 **True** 로 설정 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="da73e-280">Ensure that **AllowAdHocSubscriptions** is set to **True**.</span></span> <span data-ttu-id="da73e-281">그렇지 않으면 엔터프라이즈 상태 로밍이 작동 하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da73e-281">Otherwise, Enterprise State Roaming might not work.</span></span> <span data-ttu-id="da73e-282">자세한 내용은 [set-msolcompanysettings](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="da73e-282">For more information, see [Set-MsolCompanySettings](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0).</span></span>


### <a name="enterprise-state-roaming"></a><span data-ttu-id="da73e-283">Enterprise State Roaming</span><span class="sxs-lookup"><span data-stu-id="da73e-283">Enterprise State Roaming</span></span>

<span data-ttu-id="da73e-284">엔터프라이즈 상태 로밍을 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="da73e-284">Enterprise State Roaming should be enabled.</span></span>

<span data-ttu-id="da73e-285">**조언**</span><span class="sxs-lookup"><span data-stu-id="da73e-285">**Advisory**</span></span>

<span data-ttu-id="da73e-286">**모든** 또는 **선택한** 그룹에 대해 엔터프라이즈 상태 로밍을 사용 하도록 설정 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="da73e-286">Make sure that Enterprise State Roaming is enabled for **All** or for **Selected** groups.</span></span> <span data-ttu-id="da73e-287">자세한 내용은 [Azure Active Directory에서 엔터프라이즈 상태 로밍을 사용 하도록 설정을](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-enable)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="da73e-287">For more information, see [Enable Enterprise State Roaming in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-enable).</span></span>

### <a name="licenses"></a><span data-ttu-id="da73e-288">라이선스</span><span class="sxs-lookup"><span data-stu-id="da73e-288">Licenses</span></span>

<span data-ttu-id="da73e-289">Microsoft Managed Desktop을 사용 하려면 많은 라이선스가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="da73e-289">A number of licenses are required to use Microsoft Managed Desktop.</span></span>

<span data-ttu-id="da73e-290">**준비 되지 않음**</span><span class="sxs-lookup"><span data-stu-id="da73e-290">**Not Ready**</span></span>

<span data-ttu-id="da73e-291">Microsoft Managed Desktop을 사용 하는 데 필요한 라이선스가 모두 없습니다.</span><span class="sxs-lookup"><span data-stu-id="da73e-291">You don't have all the licenses you need to use Microsoft Managed Desktop.</span></span> <span data-ttu-id="da73e-292">자세한 내용은 [Microsoft Managed Desktop 기술](../intro/technologies.md) 및 [라이선스에 대 한 추가](prerequisites.md#more-about-licenses)정보를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="da73e-292">For more information, see [Microsoft Managed Desktop technologies](../intro/technologies.md) and [More about licenses](prerequisites.md#more-about-licenses).</span></span>


### <a name="security-account-names"></a><span data-ttu-id="da73e-293">보안 계정 이름</span><span class="sxs-lookup"><span data-stu-id="da73e-293">Security account names</span></span>

<span data-ttu-id="da73e-294">특정 보안 계정 이름이 Microsoft Managed Desktop에서 만든 이름과 충돌할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da73e-294">Certain security account names could conflict with ones created by Microsoft Managed Desktop.</span></span>

<span data-ttu-id="da73e-295">**준비되지 않음**</span><span class="sxs-lookup"><span data-stu-id="da73e-295">**Not ready**</span></span>

<span data-ttu-id="da73e-296">Microsoft Managed Desktop에서 만든 계정 이름과 충돌 하는 계정이 하나 이상 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="da73e-296">You have at least one account name that will conflict with ones created by Microsoft Managed Desktop.</span></span> <span data-ttu-id="da73e-297">Microsoft 계정 담당자와 협력 하 여 이러한 계정 이름을 제외 합니다.</span><span class="sxs-lookup"><span data-stu-id="da73e-297">Work with your Microsoft account representative to exclude these account names.</span></span>


### <a name="security-administrator-roles"></a><span data-ttu-id="da73e-298">보안 관리자 역할</span><span class="sxs-lookup"><span data-stu-id="da73e-298">Security administrator roles</span></span>

<span data-ttu-id="da73e-299">특정 보안 역할을 가진 사용자에 게는 끝점에 대해 Microsoft Defender에서 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="da73e-299">Users with certain security roles must have those assigned in Microsoft Defender for Endpoint.</span></span>

<span data-ttu-id="da73e-300">**조언**</span><span class="sxs-lookup"><span data-stu-id="da73e-300">**Advisory**</span></span>

<span data-ttu-id="da73e-301">Azure AD 조직에 이러한 역할이 할당 되어 있는 경우이 역할에도 Microsoft Defender for Endpoint에 할당 된 이러한 역할이 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="da73e-301">If you have any of these roles assigned in your Azure AD organization, make sure they also have these roles assigned in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="da73e-302">그렇지 않으면 이러한 역할을 가진 관리자가 관리자 포털에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="da73e-302">Otherwise, administrators with these roles won't be able to access the Admin portal.</span></span>

- <span data-ttu-id="da73e-303">보안 읽기 권한자</span><span class="sxs-lookup"><span data-stu-id="da73e-303">Security Reader</span></span>
- <span data-ttu-id="da73e-304">보안 운영자</span><span class="sxs-lookup"><span data-stu-id="da73e-304">Security Operator</span></span>
- <span data-ttu-id="da73e-305">전역 읽기 권한자</span><span class="sxs-lookup"><span data-stu-id="da73e-305">Global Reader</span></span>

<span data-ttu-id="da73e-306">자세한 내용은 [역할 기반 액세스 제어에 대 한 역할 만들기 및 관리](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="da73e-306">For more information, see [Create and manage roles for role-based access control](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles).</span></span>


### <a name="security-default"></a><span data-ttu-id="da73e-307">보안 기본값</span><span class="sxs-lookup"><span data-stu-id="da73e-307">Security default</span></span>

<span data-ttu-id="da73e-308">Azure Active Directory의 보안 기본값을 설정 하면 Microsoft Managed Desktop에서 장치를 관리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="da73e-308">Security defaults in Azure Active Directory will prevent Microsoft Managed Desktop from managing your devices.</span></span>

<span data-ttu-id="da73e-309">**준비되지 않음**</span><span class="sxs-lookup"><span data-stu-id="da73e-309">**Not ready**</span></span>

<span data-ttu-id="da73e-310">보안 기본값이 설정 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="da73e-310">You have Security defaults turned on.</span></span> <span data-ttu-id="da73e-311">보안 기본값을 해제 하 고 조건부 액세스 정책을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="da73e-311">Turn off Security defaults and set up conditional access policies.</span></span> <span data-ttu-id="da73e-312">자세한 내용은 [일반 조건부 액세스 정책](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="da73e-312">For more information, see [Common Conditional Access policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common).</span></span>

### <a name="self-service-password-reset"></a><span data-ttu-id="da73e-313">셀프 서비스 암호 재설정</span><span class="sxs-lookup"><span data-stu-id="da73e-313">Self-service Password Reset</span></span>

<span data-ttu-id="da73e-314">Microsoft Managed Desktop service 계정을 제외한 모든 사용자에 대해 셀프 서비스 암호 재설정 (SSPR)을 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="da73e-314">Self-service Password Reset (SSPR) should be enabled for all users excluding Microsoft Managed Desktop service accounts.</span></span> <span data-ttu-id="da73e-315">자세한 내용은 [Tutorial: 사용자가 Azure Active Directory 셀프 서비스 암호 재설정을 사용 하 여 계정의 잠금을 해제 하거나 암호를 재설정할 수 있도록](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-enable-sspr)합니다 .를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="da73e-315">For more information, see [Tutorial: Enable users to unlock their account or reset passwords using Azure Active Directory self-service password reset](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-enable-sspr).</span></span>

<span data-ttu-id="da73e-316">**조언**</span><span class="sxs-lookup"><span data-stu-id="da73e-316">**Advisory**</span></span>

<span data-ttu-id="da73e-317">SSPR **Selected** 설정에 Microsoft managed desktop devices가 포함 되어 있지만 Microsoft managed desktop service 계정은 제외 되지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="da73e-317">Make sure that the SSPR **Selected** setting includes Microsoft Managed Desktop devices but excludes Microsoft Managed Desktop service accounts.</span></span> <span data-ttu-id="da73e-318">SSPR가 사용 하도록 설정 되어 있으면 Microsoft Managed Desktop service 계정이 예상 대로 작동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="da73e-318">Microsoft Managed Desktop service accounts cannot work as expected when SSPR is enabled.</span></span>  


### <a name="standard-user-role"></a><span data-ttu-id="da73e-319">표준 사용자 역할</span><span class="sxs-lookup"><span data-stu-id="da73e-319">Standard user role</span></span>

<span data-ttu-id="da73e-320">전역 관리자 및 장치 관리자의 Azure AD 역할이 할당 된 사용자를 제외 하 고, Microsoft Managed Desktop 사용자는 로컬 관리자 권한이 없는 표준 사용자가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="da73e-320">Other than those users who are assigned Azure AD roles of Global administrator and Device administrator, Microsoft Managed Desktop users will be standard users without local administrator privileges.</span></span> <span data-ttu-id="da73e-321">다른 모든 사용자는 Microsoft Managed Desktop 장치를 시작할 때 표준 사용자 역할이 할당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="da73e-321">All other users will be assigned a standard user role when they start their Microsoft Managed Desktop device.</span></span>

<span data-ttu-id="da73e-322">**조언**</span><span class="sxs-lookup"><span data-stu-id="da73e-322">**Advisory**</span></span>

<span data-ttu-id="da73e-323">Microsoft Managed Desktop users에는 등록 후에도 Microsoft Managed Desktop 장치에 대 한 로컬 관리자 권한이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="da73e-323">Microsoft Managed Desktop users will not have local administrator privileges on their Microsoft Managed Desktop devices after enrolling.</span></span>

## <a name="microsoft-365-apps-for-enterprise"></a><span data-ttu-id="da73e-324">엔터프라이즈용 Microsoft 365 앱</span><span class="sxs-lookup"><span data-stu-id="da73e-324">Microsoft 365 Apps for enterprise</span></span>

### <a name="onedrive-for-business"></a><span data-ttu-id="da73e-325">비즈니스용 OneDrive</span><span class="sxs-lookup"><span data-stu-id="da73e-325">OneDrive for Business</span></span>

<span data-ttu-id="da73e-326">**특정 도메인에 가입 된 pc 에서만 동기화 허용** 설정은 Microsoft Managed Desktop과 충돌 합니다.</span><span class="sxs-lookup"><span data-stu-id="da73e-326">The **Allow syncing only on PCs joined to specific domains** setting will conflict with Microsoft Managed Desktop.</span></span>

<span data-ttu-id="da73e-327">**조언**</span><span class="sxs-lookup"><span data-stu-id="da73e-327">**Advisory**</span></span>

<span data-ttu-id="da73e-328">**특정 도메인에 가입 된 pc 에서만 동기화 허용** 설정을 사용 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da73e-328">You're using the **Allow syncing only on PCs joined to specific domains** setting.</span></span> <span data-ttu-id="da73e-329">이 설정은 Microsoft Managed Desktop에서는 작동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="da73e-329">This setting won't work with Microsoft Managed Desktop.</span></span> <span data-ttu-id="da73e-330">이 설정을 사용 하지 않고 비즈니스용 OneDrive에서 조건부 액세스 정책을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="da73e-330">Disable this setting, and instead set up OneDrive for Business to use a conditional access policy.</span></span> <span data-ttu-id="da73e-331">도움말을 보려면 [조건부 액세스 배포 계획을](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="da73e-331">See [Plan a Conditional Access deployment](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access) for help.</span></span>

