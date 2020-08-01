---
title: 보안 정책에 대 한 구성 분석기
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: ''
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: 관리자는 구성 분석기를 사용 하 여 표준 보호 및 엄격한 보호 사전 설정 보안 정책 아래에 있는 설정을 포함 하는 보안 정책을 찾고 해결 하는 방법을 확인할 수 있습니다.
ms.openlocfilehash: 259d498646ecf893a57a608a37e3b771083716cc
ms.sourcegitcommit: fab425ea4580d1924fb421e6db233d135f5b7d19
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/31/2020
ms.locfileid: "46533992"
---
# <a name="configuration-analyzer-for-protection-policies-in-eop-and-office-365-atp"></a><span data-ttu-id="e6c2b-103">EOP 및 Office 365 ATP의 보호 정책에 대 한 구성 분석기</span><span class="sxs-lookup"><span data-stu-id="e6c2b-103">Configuration analyzer for protection policies in EOP and Office 365 ATP</span></span>

> [!NOTE]
> <span data-ttu-id="e6c2b-104">이 항목에서 설명 하는 기능은 미리 보기 상태 이며, 모든 조직에서 사용할 수 있는 것은 아니며, 변경 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6c2b-104">The features described in this topic are in Preview, aren't available in all organizations, and are subject to change.</span></span>

<span data-ttu-id="e6c2b-105">보안 & 준수 센터의 구성 분석기는 [미리 설정 된 보안 정책](preset-security-policies.md)에서 표준 보호 및 엄격한 보호 프로필 설정 아래에 있는 설정을 포함 하는 모든 보안 정책을 찾고 수정 하는 데 사용할 수 있는 중앙 위치를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6c2b-105">Configuration analyzer in the Security & Compliance center provides a central location to find and fix any of your security policies that contain settings that are below the Standard protection and Strict protection profile settings in [preset security policies](preset-security-policies.md).</span></span>

<span data-ttu-id="e6c2b-106">구성 분석기에서는 다음과 같은 유형의 정책을 분석 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6c2b-106">The following types of policies are analyzed by the configuration analyzer:</span></span>

- <span data-ttu-id="e6c2b-107">**EOP (Exchange Online Protection) 정책**: exchange online 사서함을 사용 하는 Microsoft 365 조직과 exchange online 사서함이 없는 독립 실행형 EOP 조직이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e6c2b-107">**Exchange Online Protection (EOP) policies**: This includes Microsoft 365 organizations with Exchange Online mailboxes and standalone EOP organizations without Exchange Online mailboxes:</span></span>
  
  - <span data-ttu-id="e6c2b-108">[스팸 방지 정책](configure-your-spam-filter-policies.md)</span><span class="sxs-lookup"><span data-stu-id="e6c2b-108">[Anti-spam policies](configure-your-spam-filter-policies.md).</span></span>
  - <span data-ttu-id="e6c2b-109">[맬웨어 방지 정책](configure-anti-malware-policies.md)</span><span class="sxs-lookup"><span data-stu-id="e6c2b-109">[Anti-malware policies](configure-anti-malware-policies.md).</span></span>
  - <span data-ttu-id="e6c2b-110">[EOP 피싱 방지 정책](set-up-anti-phishing-policies.md#spoof-settings)</span><span class="sxs-lookup"><span data-stu-id="e6c2b-110">[EOP Anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

- <span data-ttu-id="e6c2b-111">**Office 365 atp (Advanced Threat Protection) 정책**: 여기에는 Microsoft 365 E5 또는 OFFICE 365 ATP 추가 기능 구독이 있는 조직이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e6c2b-111">**Office 365 Advanced Threat Protection (ATP) policies**: This includes organizations with Microsoft 365 E5 or Office 365 ATP add-on subscriptions:</span></span>

  - <span data-ttu-id="e6c2b-112">ATP 피싱 방지 정책에는 다음이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e6c2b-112">ATP anti-phishing policies, which include:</span></span>

    - <span data-ttu-id="e6c2b-113">EOP 피싱 방지 정책에서 사용할 수 있는 것과 동일한 [스푸핑 설정](set-up-anti-phishing-policies.md#spoof-settings)</span><span class="sxs-lookup"><span data-stu-id="e6c2b-113">The same [spoof settings](set-up-anti-phishing-policies.md#spoof-settings) that are available in the EOP anti-phishing policies.</span></span>
    - [<span data-ttu-id="e6c2b-114">가장 설정</span><span class="sxs-lookup"><span data-stu-id="e6c2b-114">Impersonation settings</span></span>](set-up-anti-phishing-policies.md#impersonation-settings-in-atp-anti-phishing-policies)
    - [<span data-ttu-id="e6c2b-115">고급 피싱 임계값</span><span class="sxs-lookup"><span data-stu-id="e6c2b-115">Advanced phishing thresholds</span></span>](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-atp-anti-phishing-policies)

  - <span data-ttu-id="e6c2b-116">[안전한 링크 정책](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings-in-custom-policies-for-specific-users)</span><span class="sxs-lookup"><span data-stu-id="e6c2b-116">[Safe Links policies](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings-in-custom-policies-for-specific-users).</span></span>

  - <span data-ttu-id="e6c2b-117">[안전한 첨부 파일 정책](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-policy-settings-in-custom-policies-for-specific-users)</span><span class="sxs-lookup"><span data-stu-id="e6c2b-117">[Safe Attachments policies](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-policy-settings-in-custom-policies-for-specific-users).</span></span>

<span data-ttu-id="e6c2b-118">초기 계획으로 사용 되는 **표준** 및 **엄격한** 정책 설정 값은 [EOP 및 Office 365 ATP 보안에 대 한 권장 설정](recommended-settings-for-eop-and-office365-atp.md)에 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6c2b-118">The **Standard** and **Strict** policy setting values that are used as baselines are described in [Recommended settings for EOP and Office 365 ATP security](recommended-settings-for-eop-and-office365-atp.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="e6c2b-119">시작하기 전에 알아야 할 내용은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="e6c2b-119">What do you need to know before you begin?</span></span>

- <span data-ttu-id="e6c2b-120"><https://protection.office.com/>에서 보안 및 준수 센터를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="e6c2b-120">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="e6c2b-121">**구성 분석기** 페이지로 바로 이동 하려면을 사용 <https://protection.office.com/configurationAnalyzer> 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6c2b-121">To go directly to the **Configuration analyzer** page, use <https://protection.office.com/configurationAnalyzer>.</span></span>

- <span data-ttu-id="e6c2b-122">Exchange Online PowerShell에 연결하려면 [Exchange Online PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e6c2b-122">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="e6c2b-123">이 항목의 절차를 수행하려면 먼저 사용 권한을 할당받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6c2b-123">You need to be assigned permissions before you can do the procedures in this topic:</span></span>

  - <span data-ttu-id="e6c2b-124">구성 분석기를 사용 하 **고** 보안 정책을 업데이트 하려면 다음 역할 그룹 중 하나의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6c2b-124">To use the configuration analyzer **and** make updates to security policies, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="e6c2b-125">[보안 및 준수 센터](permissions-in-the-security-and-compliance-center.md)의 **조직 관리** 또는 **보안 관리자**</span><span class="sxs-lookup"><span data-stu-id="e6c2b-125">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="e6c2b-126">[Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)의 **조직 관리** 및 **예방 조치 관리**</span><span class="sxs-lookup"><span data-stu-id="e6c2b-126">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="e6c2b-127">구성 분석기에 대 한 읽기 전용 액세스를 위해서는 다음 역할 그룹 중 하나의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6c2b-127">For read-only access to the configuration analyzer, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="e6c2b-128">[보안 및 준수 센터](permissions-in-the-security-and-compliance-center.md)의 **보안 읽기**</span><span class="sxs-lookup"><span data-stu-id="e6c2b-128">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="e6c2b-129">[Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)의 **보기 전용 조직 관리**</span><span class="sxs-lookup"><span data-stu-id="e6c2b-129">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

## <a name="use-the-configuration-analyzer-in-the-security--compliance-center"></a><span data-ttu-id="e6c2b-130">보안 & 준수 센터의 구성 분석기 사용</span><span class="sxs-lookup"><span data-stu-id="e6c2b-130">Use the configuration analyzer in the Security & Compliance Center</span></span>

<span data-ttu-id="e6c2b-131">보안 & 준수 센터에서 **위협 관리** \> **정책** \> **구성 분석기**로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6c2b-131">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Configuration analyzer**.</span></span>

![위협 관리 정책 페이지의 구성 분석기 위젯 \>](../../media/configuration-analyzer-widget.png)

<span data-ttu-id="e6c2b-133">구성 분석기에는 두 가지 주요 탭이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6c2b-133">The configuration analyzer has two main tabs:</span></span>

- <span data-ttu-id="e6c2b-134">**설정 및 권장 사항**: 표준 또는 Strict를 선택 하 고 해당 설정을 기존 보안 정책과 비교 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6c2b-134">**Settings and recommendations**: You pick Standard or Strict and compare those settings to your existing security policies.</span></span> <span data-ttu-id="e6c2b-135">결과에서 설정 값을 조정 하 여 표준 또는 Strict와 같은 수준까지 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6c2b-135">In the results, you can adjust the values of your settings to bring them up to the same level as Standard or Strict.</span></span>

- <span data-ttu-id="e6c2b-136">**구성 드리프트 분석 및 기록**:이 보기를 사용 하면 시간에 따른 구성 분석기의 결과에 따라 정책에 대해 수행한 변경 내용을 추적할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6c2b-136">**Configuration drift analysis and history**: This view allows to track the changes that you've made to your policies based on the results of the configuration analyzer over time.</span></span>

### <a name="setting-and-recommendations-tab-in-the-configuration-analyzer"></a><span data-ttu-id="e6c2b-137">구성 분석기의 설정 및 권장 사항 탭</span><span class="sxs-lookup"><span data-stu-id="e6c2b-137">Setting and recommendations tab in the configuration analyzer</span></span>

<span data-ttu-id="e6c2b-138">기본적으로 표준 보호 프로필에 대 한 비교에서 탭이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="e6c2b-138">By default, the tab opens on the comparison to the Standard protection profile.</span></span> <span data-ttu-id="e6c2b-139">엄격한 **권장 사항 보기**를 클릭 하 여 엄격한 보호 프로필 비교로 전환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6c2b-139">You can switch to the comparison of the Strict protection profile by clicking **View Strict recommendations**.</span></span> <span data-ttu-id="e6c2b-140">다시 전환 하려면 **표준 권장 사항 보기**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6c2b-140">To switch back, select **View Standard recommendations**.</span></span>

![구성 분석기의 설정 및 추천 보기](../../media/configuration-analyzer-settings-and-recommendations-view.png)

<span data-ttu-id="e6c2b-142">기본적으로 **정책 그룹/설정 이름** 열에는 다양 한 유형의 보안 정책 및 개선 해야 하는 정책 (있는 경우)의 설정 수에 대 한 축소 된 보기가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6c2b-142">By default, the **Policy group/setting name** column contains a collapsed view of the different types of security polices and the number of settings in those policies that need improvement (if any).</span></span> <span data-ttu-id="e6c2b-143">정책 유형은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e6c2b-143">The types of policies are:</span></span>

- <span data-ttu-id="e6c2b-144">**스팸 방지**</span><span class="sxs-lookup"><span data-stu-id="e6c2b-144">**Anti-spam**</span></span>
- <span data-ttu-id="e6c2b-145">**피싱 방지**</span><span class="sxs-lookup"><span data-stu-id="e6c2b-145">**Anti-phishing**</span></span>
- <span data-ttu-id="e6c2b-146">**맬웨어 방지**</span><span class="sxs-lookup"><span data-stu-id="e6c2b-146">**Anti-malware**</span></span>
- <span data-ttu-id="e6c2b-147">**Atp 안전한 첨부 파일** (구독에 ATP가 포함 된 경우)</span><span class="sxs-lookup"><span data-stu-id="e6c2b-147">**ATP Safe Attachments** (if your subscription includes ATP)</span></span>
- <span data-ttu-id="e6c2b-148">**Atp 안전한 링크** (구독에 ATP가 포함 된 경우)</span><span class="sxs-lookup"><span data-stu-id="e6c2b-148">**ATP Safe Links** (if your subscription includes ATP)</span></span>

<span data-ttu-id="e6c2b-149">기본 보기에서는 모든 항목이 축소 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e6c2b-149">In the default view, everything is collapsed.</span></span> <span data-ttu-id="e6c2b-150">각 정책 옆에는 정책에서의 비교 결과 요약 (수정할 수 있음)과 표준 또는 엄격한 보호 프로필 (수정할 수 없음)에 대 한 해당 정책의 설정이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e6c2b-150">Next to each policy, a summary of comparison results from your policies (which you can modify) and the settings in the corresponding policies for the Standard or Strict protection profiles (which you can't modify) are displayed.</span></span> <span data-ttu-id="e6c2b-151">다음 정보가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e6c2b-151">You'll see the following information:</span></span>

- <span data-ttu-id="e6c2b-152">**녹색**: 모든 기존 정책의 모든 설정은 비교 중인 보호 프로필의 보안 수준 이상 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6c2b-152">**Green**: All settings in all existing policies are at least as secure as the protection profile that you're comparing to.</span></span>
- <span data-ttu-id="e6c2b-153">**주황색**: 기존 정책의 소수의 설정이 비교 중인 보호 프로필 만큼 안전 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e6c2b-153">**Amber**: A small number of settings in the existing policies are not as secure as the protection profile that you're comparing to.</span></span>
- <span data-ttu-id="e6c2b-154">**빨강**: 기존 정책에서 상당한 수의 설정이 비교 중인 보호 프로필 만큼 안전 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e6c2b-154">**Red**: A significant number of settings in the existing policies are not as secure as the protection profile that you're comparing to.</span></span> <span data-ttu-id="e6c2b-155">이는 여러 정책에서 몇 가지 설정이 나 한 정책에서의 여러 설정이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6c2b-155">This could be a few settings in many policies or many settings in one policy.</span></span>

<span data-ttu-id="e6c2b-156">비교 시에는 **모든 설정이** \<**Standard** or **Strict**\> **권장 사항을**따릅니다.</span><span class="sxs-lookup"><span data-stu-id="e6c2b-156">For favorable comparisons, you'll see the text: **All settings follow** \<**Standard** or **Strict**\> **recommendations**.</span></span> <span data-ttu-id="e6c2b-157">그렇지 않으면 변경할 권장 설정의 수가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e6c2b-157">Otherwise, you'll see the number of recommended settings to change.</span></span>

<span data-ttu-id="e6c2b-158">**정책 그룹/설정 이름을**확장 하면 주의가 필요한 각 특정 정책의 모든 정책 및 관련 설정이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e6c2b-158">If you expand **Policy group/setting name**, all of the policies and the associated settings in each specific policy that require attention are revealed.</span></span> <span data-ttu-id="e6c2b-159">또는 특정 유형의 정책 (예: **스팸 방지**)을 확장 하 여 주의가 필요한 정책 유형에 서 해당 설정만 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6c2b-159">Or, you can expand a specific type of policy (for example, **Anti-spam**) to see just those settings in those types of policies that require your attention.</span></span>

<span data-ttu-id="e6c2b-160">비교에 대 한 권장 사항 (녹색)이 없는 경우 정책을 확장 하면 아무 것도 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e6c2b-160">If the comparison has no recommendations for improvement (green), expanding the policy reveals nothing.</span></span> <span data-ttu-id="e6c2b-161">향상에 대 한 권장 사항 (주황색 또는 빨간색)이 있는 경우 주의가 필요한 설정이 표시 되 고 해당 정보가 다음 열에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e6c2b-161">If there are any number of recommendations for improvement (amber or red), the settings that require attention are revealed, and corresponding information is revealed in the following columns:</span></span>

- <span data-ttu-id="e6c2b-162">주의가 필요한 설정의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="e6c2b-162">The name of the setting that requires your attention.</span></span> <span data-ttu-id="e6c2b-163">예를 들어 이전 스크린샷에서이는 스팸 방지 정책의 **대량 전자 메일 임계값** 입니다.</span><span class="sxs-lookup"><span data-stu-id="e6c2b-163">For example, in the previous screenshot, it's the **Bulk email threshold** in an anti-spam policy.</span></span>

- <span data-ttu-id="e6c2b-164">**정책**: 설정이 포함 된 영향을 받는 정책의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="e6c2b-164">**Policy**: The name of the affected policy that contains the setting.</span></span>

- <span data-ttu-id="e6c2b-165">**적용 대상**: 영향을 받는 정책이 적용 되는 사용자 수입니다.</span><span class="sxs-lookup"><span data-stu-id="e6c2b-165">**Applied to**: The number of user that the affected policies are applied to.</span></span>

- <span data-ttu-id="e6c2b-166">**현재 구성**: 설정의 현재 값입니다.</span><span class="sxs-lookup"><span data-stu-id="e6c2b-166">**Current configuration**: The current value of the setting.</span></span>

- <span data-ttu-id="e6c2b-167">**마지막으로 수정한**날짜: 정책을 마지막으로 수정한 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="e6c2b-167">**Last modified**: The date that the policy was last modified.</span></span>

- <span data-ttu-id="e6c2b-168">**권장 사항**: 표준 또는 엄격한 보호 프로필의 설정 값입니다.</span><span class="sxs-lookup"><span data-stu-id="e6c2b-168">**Recommendations**: The value of the setting in the Standard or Strict protection profile.</span></span> <span data-ttu-id="e6c2b-169">정책에서 설정 값을 보호 프로필의 권장 값과 일치 하도록 변경 하려면 **채택**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6c2b-169">To change the value of the setting in your policy to match the recommended value in the protection profile, click **Adopt**.</span></span> <span data-ttu-id="e6c2b-170">변경이 성공적으로 수행 되 면 **권장 사항이**적용 된 것을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6c2b-170">If the change is successful, you'll see the message: **Recommendations successfully adopted**.</span></span> <span data-ttu-id="e6c2b-171">**새로 고침** 을 클릭 하 여 추천 항목 수를 줄이고 결과에서 특정 설정/정책 행을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6c2b-171">Click **Refresh** to see the reduced number of recommendations, and the removal of the specific setting/policy row from the results.</span></span>

### <a name="configuration-drift-analysis-and-history-tab-in-the-configuration-analyzer"></a><span data-ttu-id="e6c2b-172">구성 분석기의 구성 드리프트 분석 및 기록 탭</span><span class="sxs-lookup"><span data-stu-id="e6c2b-172">Configuration drift analysis and history tab in the configuration analyzer</span></span>

<span data-ttu-id="e6c2b-173">이 탭에서는 보안 분석기의 정보를 기반으로 사용자 지정 보안 정책에 대 한 변경 내용을 추적할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6c2b-173">This tab allows you to track the changes that you've made to your custom security policies based on the information in the security analyzer.</span></span> <span data-ttu-id="e6c2b-174">기본적으로 다음과 같은 정보가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e6c2b-174">By default, the following information is displayed:</span></span>

- <span data-ttu-id="e6c2b-175">**마지막으로 수정한 날짜**</span><span class="sxs-lookup"><span data-stu-id="e6c2b-175">**Last modified**</span></span>
- <span data-ttu-id="e6c2b-176">**수정한 사람**</span><span class="sxs-lookup"><span data-stu-id="e6c2b-176">**Modified by**</span></span>
- <span data-ttu-id="e6c2b-177">**설정 이름**</span><span class="sxs-lookup"><span data-stu-id="e6c2b-177">**Setting Name**</span></span>
- <span data-ttu-id="e6c2b-178">**정책**</span><span class="sxs-lookup"><span data-stu-id="e6c2b-178">**Policy**</span></span>
- <span data-ttu-id="e6c2b-179">**Type**</span><span class="sxs-lookup"><span data-stu-id="e6c2b-179">**Type**</span></span>

<span data-ttu-id="e6c2b-180">결과를 필터링하려면 **필터**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e6c2b-180">To filter the results, click **Filter**.</span></span> <span data-ttu-id="e6c2b-181">**필터** 플라이 아웃이 나타나면 다음 필터 중에서 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6c2b-181">In the **Filters** flyout that appears, you can select from the following filters:</span></span>

- <span data-ttu-id="e6c2b-182">**시작 시간** 및 **종료 시간** (날짜)</span><span class="sxs-lookup"><span data-stu-id="e6c2b-182">**Start time** and **End time** (date)</span></span>
- <span data-ttu-id="e6c2b-183">**표준 보호** 또는 **엄격한 보호**</span><span class="sxs-lookup"><span data-stu-id="e6c2b-183">**Standard protection** or **Strict protection**</span></span>

<span data-ttu-id="e6c2b-184">결과를 .csv 파일로 내보내려면 **내보내기를**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6c2b-184">To export the results to a .csv file, click **Export**.</span></span>

![구성 분석기의 구성 드리프트 분석 및 기록 보기](../../media/configuration-analyzer-configuration-drift-analysis-view.png)
