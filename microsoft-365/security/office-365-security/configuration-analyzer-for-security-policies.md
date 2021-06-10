---
title: 보안 정책에 대한 구성 분석기
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: ''
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: 관리자는 구성 분석기를 사용하여 표준 보호 및 엄격한 보호 미리 설정 보안 정책 아래에 있는 보안 정책을 찾아 수정하는 방법을 배울 수 있습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 0d2ad1449730f392adc27c8ed2a8fc8e9ecc7a04
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2021
ms.locfileid: "52789319"
---
# <a name="configuration-analyzer-for-protection-policies-in-eop-and-microsoft-defender-for-office-365"></a><span data-ttu-id="f0c2c-103">EOP 및 Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="f0c2c-103">Configuration analyzer for protection policies in EOP and Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="f0c2c-104">**적용 대상**</span><span class="sxs-lookup"><span data-stu-id="f0c2c-104">**Applies to**</span></span>
- [<span data-ttu-id="f0c2c-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="f0c2c-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="f0c2c-106">Office 365용 Microsoft Defender 플랜 1 및 플랜 2</span><span class="sxs-lookup"><span data-stu-id="f0c2c-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="f0c2c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f0c2c-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="f0c2c-108">Microsoft 365 보안 센터의 구성 분석기는 설정이 미리 설정된 보안 정책의 표준 보호 및 엄격한 보호 프로필 설정 아래에 있는 보안 정책을 찾고 수정할 수 있는 중앙 [위치를 제공합니다.](preset-security-policies.md)</span><span class="sxs-lookup"><span data-stu-id="f0c2c-108">Configuration analyzer in the Microsoft 365 security center provides a central location to find and fix security policies where the settings are below the Standard protection and Strict protection profile settings in [preset security policies](preset-security-policies.md).</span></span>

<span data-ttu-id="f0c2c-109">구성 분석기에서는 다음과 같은 유형의 정책을 분석합니다.</span><span class="sxs-lookup"><span data-stu-id="f0c2c-109">The following types of policies are analyzed by the configuration analyzer:</span></span>

- <span data-ttu-id="f0c2c-110">**Exchange Online Protection(EOP)** 정책: Microsoft 365 사서함이 없는 Exchange Online 독립 실행형 EOP Exchange Online 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0c2c-110">**Exchange Online Protection (EOP) policies**: This includes Microsoft 365 organizations with Exchange Online mailboxes and standalone EOP organizations without Exchange Online mailboxes:</span></span>

  - <span data-ttu-id="f0c2c-111">[스팸 방지 정책](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="f0c2c-111">[Anti-spam policies](configure-your-spam-filter-policies.md).</span></span>
  - <span data-ttu-id="f0c2c-112">[맬웨어 방지 정책](configure-anti-malware-policies.md).</span><span class="sxs-lookup"><span data-stu-id="f0c2c-112">[Anti-malware policies](configure-anti-malware-policies.md).</span></span>
  - <span data-ttu-id="f0c2c-113">[EOP 피싱 방지 정책](set-up-anti-phishing-policies.md#spoof-settings).</span><span class="sxs-lookup"><span data-stu-id="f0c2c-113">[EOP anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

- <span data-ttu-id="f0c2c-114">**Microsoft Defender for Office 365** 정책: Microsoft 365 E5 추가 기능 구독에 대한 Office 365 조직이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0c2c-114">**Microsoft Defender for Office 365 policies**: This includes organizations with Microsoft 365 E5 or Defender for Office 365 add-on subscriptions:</span></span>

  - <span data-ttu-id="f0c2c-115">Microsoft Defender for Office 365 피싱 방지 정책에는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0c2c-115">Anti-phishing policies in Microsoft Defender for Office 365, which include:</span></span>
    - <span data-ttu-id="f0c2c-116">EOP [](set-up-anti-phishing-policies.md#spoof-settings) 피싱 방지 정책에서 사용할 수 있는 동일한 스푸핑 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="f0c2c-116">The same [spoof settings](set-up-anti-phishing-policies.md#spoof-settings) that are available in the EOP anti-phishing policies.</span></span>
    - [<span data-ttu-id="f0c2c-117">가장 설정</span><span class="sxs-lookup"><span data-stu-id="f0c2c-117">Impersonation settings</span></span>](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
    - [<span data-ttu-id="f0c2c-118">고급 피싱 임계값</span><span class="sxs-lookup"><span data-stu-id="f0c2c-118">Advanced phishing thresholds</span></span>](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
  - <span data-ttu-id="f0c2c-119">[안전한 링크 정책](set-up-safe-links-policies.md).</span><span class="sxs-lookup"><span data-stu-id="f0c2c-119">[Safe Links policies](set-up-safe-links-policies.md).</span></span>
  - <span data-ttu-id="f0c2c-120">[안전한 첨부 파일 정책](set-up-safe-attachments-policies.md).</span><span class="sxs-lookup"><span data-stu-id="f0c2c-120">[Safe Attachments policies](set-up-safe-attachments-policies.md).</span></span>

<span data-ttu-id="f0c2c-121">기준으로  사용되는 **표준** 및 엄격한 정책 설정 값은 EOP 및 Microsoft Defender for [Office 365 설정에 설명되어 있습니다.](recommended-settings-for-eop-and-office365.md)</span><span class="sxs-lookup"><span data-stu-id="f0c2c-121">The **Standard** and **Strict** policy setting values that are used as baselines are described in [Recommended settings for EOP and Microsoft Defender for Office 365 security](recommended-settings-for-eop-and-office365.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="f0c2c-122">시작하기 전에 알아야 할 내용은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="f0c2c-122">What do you need to know before you begin?</span></span>

- <span data-ttu-id="f0c2c-123"><https://security.microsoft.com>에서 보안 센터를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="f0c2c-123">You open the security center at <https://security.microsoft.com>.</span></span> <span data-ttu-id="f0c2c-124">구성 분석기 **페이지로** 직접 이동하려면 를 <https://security.microsoft.com/configurationAnalyzer> 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="f0c2c-124">To go directly to the **Configuration analyzer** page, use <https://security.microsoft.com/configurationAnalyzer>.</span></span>

- <span data-ttu-id="f0c2c-125">Exchange Online PowerShell에 연결하려면 [Exchange Online PowerShell에 연결](/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f0c2c-125">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="f0c2c-126">이 문서의 절차를 수행하려면 먼저 보안 센터에서 사용 권한을 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0c2c-126">You need to be assigned permissions in the security center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="f0c2c-127">구성 분석기를 **사용하여** 보안 정책을 업데이트하려면 조직 관리 또는 보안  관리자 역할 그룹의 **구성원이** 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0c2c-127">To use the configuration analyzer **and** make updates to security policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="f0c2c-128">구성 분석기에 대한 읽기 전용 액세스의 경우 전역  읽기 사용자 또는 보안 읽기 권한이 있는 역할 그룹의 **구성원이** 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0c2c-128">For read-only access to the configuration analyzer, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="f0c2c-129">자세한 내용은 보안 센터의 사용 [Microsoft 365 참조하세요.](permissions-microsoft-365-security-center.md)</span><span class="sxs-lookup"><span data-stu-id="f0c2c-129">For more information, see [Permissions in the Microsoft 365 security center](permissions-microsoft-365-security-center.md).</span></span>

  > [!NOTE]
  >  
  > - <span data-ttu-id="f0c2c-130">해당 Azure Active Directory 역할에 사용자를 추가하면 사용자에게 보안 센터에서 필요한  사용 권한과 보안 센터의 다른 기능에 대한 Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f0c2c-130">Adding users to the corresponding Azure Active Directory role gives users the required permissions in the security center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="f0c2c-131">자세한 내용은 [관리자 역할 정보](../../admin/add-users/about-admin-roles.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f0c2c-131">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  >
  > - <span data-ttu-id="f0c2c-132">[Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups)의 **보기 전용 조직 관리** 역할 그룹에도 기능에 대한 읽기 전용 권한을 부여합니다.</span><span class="sxs-lookup"><span data-stu-id="f0c2c-132">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

## <a name="use-the-configuration-analyzer-in-the-security-center"></a><span data-ttu-id="f0c2c-133">보안 센터에서 구성 분석기 사용</span><span class="sxs-lookup"><span data-stu-id="f0c2c-133">Use the configuration analyzer in the security center</span></span>

<span data-ttu-id="f0c2c-134">보안 센터에서 전자 메일 & **공동** 작업 정책 & 정책 템플릿 \>  \>  \> **기반 정책** 섹션 \> **구성 분석기 로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="f0c2c-134">In the security center, go to **Email & collaboration** \> **Policies & rules** \> **Threat policies** \> **Templated policies** section \> **Configuration analyzer**.</span></span>

<span data-ttu-id="f0c2c-135">구성 분석기에는 두 개의 기본 탭이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0c2c-135">The configuration analyzer has two main tabs:</span></span>

- <span data-ttu-id="f0c2c-136">**설정 및 권장** 사항: **표준** 또는 엄격을 선택하고 이러한 설정을 기존 보안 정책과 비교합니다. </span><span class="sxs-lookup"><span data-stu-id="f0c2c-136">**Settings and recommendations**: You pick **Standard** or **Strict** and compare those settings to your existing security policies.</span></span> <span data-ttu-id="f0c2c-137">결과에서 표준 또는 엄격과 같은 수준으로 설정 값을 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0c2c-137">In the results, you can adjust the values of your settings to bring them up to the same level as Standard or Strict.</span></span>
- <span data-ttu-id="f0c2c-138">**구성 드리프트 분석 및 기록:** 이 보기를 통해 시간이 지난 정책 변경 내용을 추적할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0c2c-138">**Configuration drift analysis and history**: This view allows you to track policy changes over time.</span></span>

### <a name="setting-and-recommendations-tab-in-the-configuration-analyzer"></a><span data-ttu-id="f0c2c-139">구성 분석기에서 설정 및 추천 탭</span><span class="sxs-lookup"><span data-stu-id="f0c2c-139">Setting and recommendations tab in the configuration analyzer</span></span>

<span data-ttu-id="f0c2c-140">기본적으로 표준 보호 프로필과 비교할 때 탭이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="f0c2c-140">By default, the tab opens on the comparison to the Standard protection profile.</span></span> <span data-ttu-id="f0c2c-141">엄격한 권장 사항 보기를 선택하여 Strict protection 프로필 비교로 **전환할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="f0c2c-141">You can switch to the comparison of the Strict protection profile by selecting **View Strict recommendations**.</span></span> <span data-ttu-id="f0c2c-142">다시 전환하려면 표준 권장 **사항 보기 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="f0c2c-142">To switch back, select **View Standard recommendations**.</span></span>

![설정 분석기에서 보기 및 추천 보기](../../media/configuration-analyzer-settings-and-recommendations-view.png)

<span data-ttu-id="f0c2c-144">기본적으로 정책 **그룹/설정** 이름 열에는 다양한 유형의 보안 정책 및 개선이 필요한 설정 수(있는 경우)의 축소된 보기가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0c2c-144">By default, the **Policy group/setting name** column contains a collapsed view of the different types of security policies and the number of settings that need improvement (if any).</span></span> <span data-ttu-id="f0c2c-145">정책의 유형은 다음입니다.</span><span class="sxs-lookup"><span data-stu-id="f0c2c-145">The types of policies are:</span></span>

- <span data-ttu-id="f0c2c-146">**스팸 방지**</span><span class="sxs-lookup"><span data-stu-id="f0c2c-146">**Anti-spam**</span></span>
- <span data-ttu-id="f0c2c-147">**피싱 방지**</span><span class="sxs-lookup"><span data-stu-id="f0c2c-147">**Anti-phishing**</span></span>
- <span data-ttu-id="f0c2c-148">**맬웨어 방지**</span><span class="sxs-lookup"><span data-stu-id="f0c2c-148">**Anti-malware**</span></span>
- <span data-ttu-id="f0c2c-149">**안전한 첨부** 파일(구독에 Microsoft Defender for Office 365)</span><span class="sxs-lookup"><span data-stu-id="f0c2c-149">**Safe Attachments** (if your subscription includes Microsoft Defender for Office 365)</span></span>
- <span data-ttu-id="f0c2c-150">**안전한** 링크(구독에 Microsoft Defender for Office 365)</span><span class="sxs-lookup"><span data-stu-id="f0c2c-150">**Safe Links** (if your subscription includes Microsoft Defender for Office 365)</span></span>

<span data-ttu-id="f0c2c-151">기본 보기에서는 모든 것이 축소됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0c2c-151">In the default view, everything is collapsed.</span></span> <span data-ttu-id="f0c2c-152">각 정책 옆에는 정책(수정할 수 있는)과 표준 또는 엄격한 보호 프로필에 대한 해당 정책의 설정(수정할 수 없는)의 비교 결과가 요약됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0c2c-152">Next to each policy, there's a summary of comparison results from your policies (which you can modify) and the settings in the corresponding policies for the Standard or Strict protection profiles (which you can't modify).</span></span> <span data-ttu-id="f0c2c-153">비교할 보호 프로필에 대한 다음 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0c2c-153">You'll see the following information for the protection profile that you're comparing to:</span></span>

- <span data-ttu-id="f0c2c-154">**녹색:** 모든 기존 정책의 모든 설정은 최소한 보호 프로필만큼 안전합니다.</span><span class="sxs-lookup"><span data-stu-id="f0c2c-154">**Green**: All settings in all existing policies are at least as secure as the protection profile.</span></span>
- <span data-ttu-id="f0c2c-155">**Amber:** 기존 정책의 소수의 설정은 보호 프로필만큼 안전하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f0c2c-155">**Amber**: A small number of settings in the existing policies are not as secure as the protection profile.</span></span>
- <span data-ttu-id="f0c2c-156">**빨간색:** 기존 정책의 많은 설정이 보호 프로필만큼 안전하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f0c2c-156">**Red**: A significant number of settings in the existing policies are not as secure as the protection profile.</span></span> <span data-ttu-id="f0c2c-157">여러 정책의 몇 가지 설정이나 하나의 정책에 있는 여러 설정일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0c2c-157">This could be a few settings in many policies or many settings in one policy.</span></span>

<span data-ttu-id="f0c2c-158">선호하는 비교를 위해 다음 텍스트를 볼 수 있습니다. **모든 설정은 권장 사항을** \<**Standard** or **Strict**\> **따르는 입니다.**</span><span class="sxs-lookup"><span data-stu-id="f0c2c-158">For favorable comparisons, you'll see the text: **All settings follow** \<**Standard** or **Strict**\> **recommendations**.</span></span> <span data-ttu-id="f0c2c-159">그렇지 않으면 변경할 권장 설정 수가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0c2c-159">Otherwise, you'll see the number of recommended settings to change.</span></span>

<span data-ttu-id="f0c2c-160">정책 **그룹/설정** 이름을 확장하면 주의가 필요한 각 특정 정책의 모든 정책 및 관련 설정이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0c2c-160">If you expand **Policy group/setting name**, all of the policies and the associated settings in each specific policy that require attention are revealed.</span></span> <span data-ttu-id="f0c2c-161">또는 특정 유형의 정책(예: 스팸 방지)을 확장하여 주의가 필요한 정책 유형에서 해당 설정만 볼 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="f0c2c-161">Or, you can expand a specific type of policy (for example, **Anti-spam**) to see just those settings in those types of policies that require your attention.</span></span>

<span data-ttu-id="f0c2c-162">비교에 개선에 대한 권장 사항(녹색)이 없는 경우 정책을 확장하면 아무 것도 표시하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f0c2c-162">If the comparison has no recommendations for improvement (green), expanding the policy reveals nothing.</span></span> <span data-ttu-id="f0c2c-163">개선에 대한 권장 사항(오목 또는 빨간색)이 있는 경우 주의가 필요한 설정이 표시될 수 있으며 해당 정보는 다음 열에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0c2c-163">If there are any number of recommendations for improvement (amber or red), the settings that require attention are revealed, and corresponding information is revealed in the following columns:</span></span>

- <span data-ttu-id="f0c2c-164">**정책 그룹/설정 이름:** 주의가 필요한 설정의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="f0c2c-164">**Policy group/setting name**: The name of the setting that requires your attention.</span></span> <span data-ttu-id="f0c2c-165">예를 들어 이전 스크린샷에서는 기본 스팸 방지 정책의 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="f0c2c-165">For example, in the previous screenshot, it's the settings in the default anti-spam policy.</span></span>
- <span data-ttu-id="f0c2c-166">**정책:** 설정이 포함된 영향을 받는 정책의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="f0c2c-166">**Policy**: The name of the affected policy that contains the setting.</span></span>
- <span data-ttu-id="f0c2c-167">**적용:** 영향을 받는 정책이 적용되는 사용자 수입니다.</span><span class="sxs-lookup"><span data-stu-id="f0c2c-167">**Applied to**: The number of users that the affected policies are applied to.</span></span>
- <span data-ttu-id="f0c2c-168">**현재 구성:** 설정의 현재 값입니다.</span><span class="sxs-lookup"><span data-stu-id="f0c2c-168">**Current configuration**: The current value of the setting.</span></span> <span data-ttu-id="f0c2c-169">모든 받는 사람에게 적용되는 해당 유형의 기본 정책의 경우 이 값은 비어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0c2c-169">For the default policy of that type that applies to all recipients, this value is blank.</span></span>
- <span data-ttu-id="f0c2c-170">**마지막으로 수정한** 날짜: 정책이 마지막으로 수정된 날짜입니다.</span><span class="sxs-lookup"><span data-stu-id="f0c2c-170">**Last modified**: The date that the policy was last modified.</span></span>
- <span data-ttu-id="f0c2c-171">**권장 사항**: 표준 또는 엄격한 보호 프로필의 설정 값입니다.</span><span class="sxs-lookup"><span data-stu-id="f0c2c-171">**Recommendations**: The value of the setting in the Standard or Strict protection profile.</span></span> <span data-ttu-id="f0c2c-172">정책의 설정 값을 보호 프로필의 권장 값과 일치하게 변경하려면 채택을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="f0c2c-172">To change the value of the setting in your policy to match the recommended value in the protection profile, click **Adopt**.</span></span> <span data-ttu-id="f0c2c-173">변경에 성공하면 다음 메시지가 **표시됩니다. 권장 사항 성공적으로 채택했습니다.**</span><span class="sxs-lookup"><span data-stu-id="f0c2c-173">If the change is successful, you'll see the message: **Recommendations successfully adopted**.</span></span> <span data-ttu-id="f0c2c-174">새로 **고침을** 클릭하여 감소된 권장 사항 수와 결과에서 특정 설정/정책 행을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="f0c2c-174">Click **Refresh** to see the reduced number of recommendations, and the removal of the specific setting/policy row from the results.</span></span>

### <a name="configuration-drift-analysis-and-history-tab-in-the-configuration-analyzer"></a><span data-ttu-id="f0c2c-175">구성 분석기에서 구성 드리프트 분석 및 기록 탭</span><span class="sxs-lookup"><span data-stu-id="f0c2c-175">Configuration drift analysis and history tab in the configuration analyzer</span></span>

<span data-ttu-id="f0c2c-176">이 탭에서는 사용자 지정 보안 정책에 적용한 변경 내용을 추적할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0c2c-176">This tab allows you to track the changes that you've made to your custom security policies.</span></span> <span data-ttu-id="f0c2c-177">기본적으로 다음과 같은 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0c2c-177">By default, the following information is displayed:</span></span>

- <span data-ttu-id="f0c2c-178">**마지막으로 수정한 날짜**</span><span class="sxs-lookup"><span data-stu-id="f0c2c-178">**Last modified**</span></span>
- <span data-ttu-id="f0c2c-179">**수정한 사용자**</span><span class="sxs-lookup"><span data-stu-id="f0c2c-179">**Modified by**</span></span>
- <span data-ttu-id="f0c2c-180">**설정 이름**</span><span class="sxs-lookup"><span data-stu-id="f0c2c-180">**Setting Name**</span></span>
- <span data-ttu-id="f0c2c-181">**정책**</span><span class="sxs-lookup"><span data-stu-id="f0c2c-181">**Policy**</span></span>
- <span data-ttu-id="f0c2c-182">**유형**</span><span class="sxs-lookup"><span data-stu-id="f0c2c-182">**Type**</span></span>
- <span data-ttu-id="f0c2c-183">**구성 변경 내용**</span><span class="sxs-lookup"><span data-stu-id="f0c2c-183">**Configuration change**</span></span>
- <span data-ttu-id="f0c2c-184">**구성 드리프트**: Increase 또는 **Decrease 값입니다.** </span><span class="sxs-lookup"><span data-stu-id="f0c2c-184">**Configuration drift**: The value **Increase** or **Decrease**.</span></span>

<span data-ttu-id="f0c2c-185">결과를 필터링하려면 **필터** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f0c2c-185">To filter the results, click **Filter**.</span></span> <span data-ttu-id="f0c2c-186">필터 **플라이아웃이** 나타나면 다음 필터에서 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0c2c-186">In the **Filters** flyout that appears, you can select from the following filters:</span></span>

- <span data-ttu-id="f0c2c-187">**시작 시간** 및 **종료 시간(날짜)**</span><span class="sxs-lookup"><span data-stu-id="f0c2c-187">**Start time** and **End time** (date)</span></span>
- <span data-ttu-id="f0c2c-188">**표준 보호** 또는 **엄격한 보호**</span><span class="sxs-lookup"><span data-stu-id="f0c2c-188">**Standard protection** or **Strict protection**</span></span>

<span data-ttu-id="f0c2c-189">결과를 파일로 내보내려면 .csv 를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="f0c2c-189">To export the results to a .csv file, click **Export**.</span></span>

![구성 분석기에서 구성 드리프트 분석 및 기록 보기](../../media/configuration-analyzer-configuration-drift-analysis-view.png)
