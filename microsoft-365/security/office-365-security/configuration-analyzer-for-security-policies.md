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
ms.openlocfilehash: 6daa3ef2c3cd758022fc9dad325df4c5e4f38647
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288924"
---
# <a name="configuration-analyzer-for-protection-policies-in-eop-and-microsoft-defender-for-office-365"></a><span data-ttu-id="58ac1-103">EOP 및 Office 365용 Microsoft Defender의 보호 정책에 대한 구성 분석기</span><span class="sxs-lookup"><span data-stu-id="58ac1-103">Configuration analyzer for protection policies in EOP and Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="58ac1-104">**적용 대상**</span><span class="sxs-lookup"><span data-stu-id="58ac1-104">**Applies to**</span></span>
- [<span data-ttu-id="58ac1-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="58ac1-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="58ac1-106">Office 365용 Microsoft Defender 플랜 1 및 플랜 2</span><span class="sxs-lookup"><span data-stu-id="58ac1-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="58ac1-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="58ac1-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="58ac1-108">보안 및 준수 & 센터의 구성 분석기는 설정이 미리 설정된 보안 정책의 표준 보호 및 엄격한 보호 프로필 설정 아래에 있는 보안 정책을 찾고 수정할 수 있는 중앙 [위치를 제공합니다.](preset-security-policies.md)</span><span class="sxs-lookup"><span data-stu-id="58ac1-108">Configuration analyzer in the Security & Compliance center provides a central location to find and fix security policies where the settings are below the Standard protection and Strict protection profile settings in [preset security policies](preset-security-policies.md).</span></span>

<span data-ttu-id="58ac1-109">구성 분석기에서는 다음과 같은 유형의 정책을 분석합니다.</span><span class="sxs-lookup"><span data-stu-id="58ac1-109">The following types of policies are analyzed by the configuration analyzer:</span></span>

- <span data-ttu-id="58ac1-110">**EOP(Exchange Online Protection)** 정책: Exchange Online 사서함이 있는 Microsoft 365 조직과 Exchange Online 사서함이 없는 독립 실행형 EOP 조직이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="58ac1-110">**Exchange Online Protection (EOP) policies**: This includes Microsoft 365 organizations with Exchange Online mailboxes and standalone EOP organizations without Exchange Online mailboxes:</span></span>

  - <span data-ttu-id="58ac1-111">[스팸 방지 정책](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="58ac1-111">[Anti-spam policies](configure-your-spam-filter-policies.md).</span></span>
  - <span data-ttu-id="58ac1-112">[맬웨어 방지 정책](configure-anti-malware-policies.md).</span><span class="sxs-lookup"><span data-stu-id="58ac1-112">[Anti-malware policies](configure-anti-malware-policies.md).</span></span>
  - <span data-ttu-id="58ac1-113">[EOP 피싱 방지 정책.](set-up-anti-phishing-policies.md#spoof-settings)</span><span class="sxs-lookup"><span data-stu-id="58ac1-113">[EOP Anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

- <span data-ttu-id="58ac1-114">**Office 365용 Microsoft Defender** 정책: 여기에는 Microsoft 365 E5 또는 Office 365용 Defender 추가 기능 구독이 있는 조직이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="58ac1-114">**Microsoft Defender for Office 365 policies**: This includes organizations with Microsoft 365 E5 or Defender for Office 365 add-on subscriptions:</span></span>

  - <span data-ttu-id="58ac1-115">Office 365용 Microsoft Defender의 피싱 방지 정책에는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="58ac1-115">Anti-phishing policies in Microsoft Defender for Office 365, which include:</span></span>

    - <span data-ttu-id="58ac1-116">EOP [피싱](set-up-anti-phishing-policies.md#spoof-settings) 방지 정책에서 사용할 수 있는 동일한 스푸핑 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="58ac1-116">The same [spoof settings](set-up-anti-phishing-policies.md#spoof-settings) that are available in the EOP anti-phishing policies.</span></span>
    - [<span data-ttu-id="58ac1-117">가장 설정</span><span class="sxs-lookup"><span data-stu-id="58ac1-117">Impersonation settings</span></span>](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
    - [<span data-ttu-id="58ac1-118">고급 피싱 임계값</span><span class="sxs-lookup"><span data-stu-id="58ac1-118">Advanced phishing thresholds</span></span>](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)

  - <span data-ttu-id="58ac1-119">[안전한 링크 정책](set-up-atp-safe-links-policies.md).</span><span class="sxs-lookup"><span data-stu-id="58ac1-119">[Safe Links policies](set-up-atp-safe-links-policies.md).</span></span>

  - <span data-ttu-id="58ac1-120">[안전한 첨부 파일 정책.](set-up-atp-safe-attachments-policies.md)</span><span class="sxs-lookup"><span data-stu-id="58ac1-120">[Safe Attachments policies](set-up-atp-safe-attachments-policies.md).</span></span>

<span data-ttu-id="58ac1-121">기준으로 **사용되는** **표준** 및 엄격한 정책 설정 값은 EOP 및 [Office 365용 Microsoft Defender](recommended-settings-for-eop-and-office365-atp.md)보안에 대한 권장 설정에 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58ac1-121">The **Standard** and **Strict** policy setting values that are used as baselines are described in [Recommended settings for EOP and Microsoft Defender for Office 365 security](recommended-settings-for-eop-and-office365-atp.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="58ac1-122">시작하기 전에 알아야 할 내용은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="58ac1-122">What do you need to know before you begin?</span></span>

- <span data-ttu-id="58ac1-123"><https://protection.office.com/>에서 보안 및 준수 센터를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="58ac1-123">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="58ac1-124">구성 분석기 **페이지로** 직접 이동하려면 <https://protection.office.com/configurationAnalyzer> 다음을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="58ac1-124">To go directly to the **Configuration analyzer** page, use <https://protection.office.com/configurationAnalyzer>.</span></span>

- <span data-ttu-id="58ac1-125">Exchange Online PowerShell에 연결하려면 [Exchange Online PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="58ac1-125">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="58ac1-126">이 문서의 절차를 수행하려면 먼저 보안 및 준수 센터에서 사용 권한을 할당받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="58ac1-126">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="58ac1-127">구성 분석기를 사용하여  보안 정책을 업데이트하려면 **조직** 관리 또는 보안 관리자 역할 그룹의 **구성원이** 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="58ac1-127">To use the configuration analyzer **and** make updates to security policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="58ac1-128">구성 분석기에 대한 읽기 전용 액세스 권한을 사용하려면  전역 읽기 또는 보안 읽기 권한이 있는 역할 그룹의 **구성원이** 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="58ac1-128">For read-only access to the configuration analyzer, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="58ac1-129">자세한 내용은 [보안 및 준수 센터의 사용 권한](permissions-in-the-security-and-compliance-center.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="58ac1-129">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  > [!NOTE]
  >  
  > - <span data-ttu-id="58ac1-130">Microsoft 365 관리 센터의 해당 Azure Active Directory 역할에 사용자를 추가하면 사용자에게 보안 및 준수 센터에서 필요한 권한 _및_ Microsoft 365의 다른 기능에 대한 권한이 부여됩니다.</span><span class="sxs-lookup"><span data-stu-id="58ac1-130">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="58ac1-131">자세한 내용은 [관리자 역할 정보](../../admin/add-users/about-admin-roles.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="58ac1-131">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  >
  > - <span data-ttu-id="58ac1-132">[Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)의 **보기 전용 조직 관리** 역할 그룹에도 기능에 대한 읽기 전용 권한을 부여합니다.</span><span class="sxs-lookup"><span data-stu-id="58ac1-132">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

## <a name="use-the-configuration-analyzer-in-the-security--compliance-center"></a><span data-ttu-id="58ac1-133">보안 및 준수 센터에서 구성 & 사용</span><span class="sxs-lookup"><span data-stu-id="58ac1-133">Use the configuration analyzer in the Security & Compliance Center</span></span>

<span data-ttu-id="58ac1-134">보안 & 준수 센터에서 **위협 관리** 정책 구성 \>  \> **분석기로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="58ac1-134">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Configuration analyzer**.</span></span>

![위협 관리 정책 페이지의 구성 분석기 위젯 \>](../../media/configuration-analyzer-widget.png)

<span data-ttu-id="58ac1-136">구성 분석기에는 두 개의 기본 탭이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58ac1-136">The configuration analyzer has two main tabs:</span></span>

- <span data-ttu-id="58ac1-137">**설정 및 권장** 사항: 표준 또는 엄격을 선택하고 이러한 설정을 기존 보안 정책과 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="58ac1-137">**Settings and recommendations**: You pick Standard or Strict and compare those settings to your existing security policies.</span></span> <span data-ttu-id="58ac1-138">결과에서 표준 또는 Strict와 같은 수준으로 설정 값을 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58ac1-138">In the results, you can adjust the values of your settings to bring them up to the same level as Standard or Strict.</span></span>

- <span data-ttu-id="58ac1-139">**구성 드리프트 분석 및 기록:** 이 보기를 통해 시간이 지난 정책 변경 내용을 추적할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58ac1-139">**Configuration drift analysis and history**: This view allows you to track policy changes over time.</span></span>

### <a name="setting-and-recommendations-tab-in-the-configuration-analyzer"></a><span data-ttu-id="58ac1-140">구성 분석기에서 설정 및 추천 탭</span><span class="sxs-lookup"><span data-stu-id="58ac1-140">Setting and recommendations tab in the configuration analyzer</span></span>

<span data-ttu-id="58ac1-141">기본적으로 표준 보호 프로필과 비교할 때 탭이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="58ac1-141">By default, the tab opens on the comparison to the Standard protection profile.</span></span> <span data-ttu-id="58ac1-142">Strict 추천 보기를 클릭하여 Strict protection 프로필 비교로 **전환할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="58ac1-142">You can switch to the comparison of the Strict protection profile by clicking **View Strict recommendations**.</span></span> <span data-ttu-id="58ac1-143">다시 전환하려면 표준 권장 **사항 보기를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="58ac1-143">To switch back, select **View Standard recommendations**.</span></span>

![구성 분석기에서 설정 및 권장 사항 보기](../../media/configuration-analyzer-settings-and-recommendations-view.png)

<span data-ttu-id="58ac1-145">기본적으로 정책 **그룹/설정** 이름 열에는 다양한 유형의 보안 정책과 개선해야 하는 설정 수(있는 경우)의 축소된 보기가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58ac1-145">By default, the **Policy group/setting name** column contains a collapsed view of the different types of security policies and the number of settings that need improvement (if any).</span></span> <span data-ttu-id="58ac1-146">정책 유형은 다음입니다.</span><span class="sxs-lookup"><span data-stu-id="58ac1-146">The types of policies are:</span></span>

- <span data-ttu-id="58ac1-147">**스팸 방지**</span><span class="sxs-lookup"><span data-stu-id="58ac1-147">**Anti-spam**</span></span>
- <span data-ttu-id="58ac1-148">**피싱 방지**</span><span class="sxs-lookup"><span data-stu-id="58ac1-148">**Anti-phishing**</span></span>
- <span data-ttu-id="58ac1-149">**맬웨어 방지**</span><span class="sxs-lookup"><span data-stu-id="58ac1-149">**Anti-malware**</span></span>
- <span data-ttu-id="58ac1-150">**ATP 안전한 첨부** 파일(구독에 Office 365용 Microsoft Defender가 포함된 경우)</span><span class="sxs-lookup"><span data-stu-id="58ac1-150">**ATP Safe Attachments** (if your subscription includes Microsoft Defender for Office 365)</span></span>
- <span data-ttu-id="58ac1-151">**ATP 안전한** 링크(구독에 Office 365용 Microsoft Defender가 포함된 경우)</span><span class="sxs-lookup"><span data-stu-id="58ac1-151">**ATP Safe Links** (if your subscription includes Microsoft Defender for Office 365)</span></span>

<span data-ttu-id="58ac1-152">기본 보기에서는 모든 것이 축소됩니다.</span><span class="sxs-lookup"><span data-stu-id="58ac1-152">In the default view, everything is collapsed.</span></span> <span data-ttu-id="58ac1-153">각 정책 옆에는 정책의 비교 결과(수정할 수 있는)와 표준 또는 엄격 보호 프로필에 대한 해당 정책의 설정(수정할 수 없는)이 요약됩니다.</span><span class="sxs-lookup"><span data-stu-id="58ac1-153">Next to each policy, there's a summary of comparison results from your policies (which you can modify) and the settings in the corresponding policies for the Standard or Strict protection profiles (which you can't modify).</span></span> <span data-ttu-id="58ac1-154">비교할 보호 프로필에 대한 다음 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="58ac1-154">You'll see the following information for the protection profile that you're comparing to:</span></span>

- <span data-ttu-id="58ac1-155">**녹색:** 모든 기존 정책의 모든 설정은 최소한 보호 프로필만큼 안전합니다.</span><span class="sxs-lookup"><span data-stu-id="58ac1-155">**Green**: All settings in all existing policies are at least as secure as the protection profile.</span></span>
- <span data-ttu-id="58ac1-156">**Amber:** 기존 정책의 소수의 설정은 보호 프로필만큼 안전하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="58ac1-156">**Amber**: A small number of settings in the existing policies are not as secure as the protection profile.</span></span>
- <span data-ttu-id="58ac1-157">**빨간색:** 기존 정책의 상당수 설정은 보호 프로필만큼 안전하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="58ac1-157">**Red**: A significant number of settings in the existing policies are not as secure as the protection profile.</span></span> <span data-ttu-id="58ac1-158">이 설정은 여러 정책의 몇 가지 설정 또는 하나의 정책에 있는 여러 설정일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58ac1-158">This could be a few settings in many policies or many settings in one policy.</span></span>

<span data-ttu-id="58ac1-159">선호하는 비교의 경우 모든 설정이 권장 사항을 **따르는 텍스트가** \<**Standard** or **Strict**\> **표시됩니다.**</span><span class="sxs-lookup"><span data-stu-id="58ac1-159">For favorable comparisons, you'll see the text: **All settings follow** \<**Standard** or **Strict**\> **recommendations**.</span></span> <span data-ttu-id="58ac1-160">그렇지 않으면 변경할 권장 설정 수가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="58ac1-160">Otherwise, you'll see the number of recommended settings to change.</span></span>

<span data-ttu-id="58ac1-161">정책 **그룹/설정** 이름을 확장하면 주의가 필요한 각 특정 정책의 모든 정책 및 관련 설정이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="58ac1-161">If you expand **Policy group/setting name**, all of the policies and the associated settings in each specific policy that require attention are revealed.</span></span> <span data-ttu-id="58ac1-162">또는 특정 유형의 정책(예: 스팸 방지)을 확장하여 주의가 필요한 정책 유형에서 해당 설정만 볼 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="58ac1-162">Or, you can expand a specific type of policy (for example, **Anti-spam**) to see just those settings in those types of policies that require your attention.</span></span>

<span data-ttu-id="58ac1-163">비교에 개선에 대한 권장 사항(녹색)이 없는 경우 정책을 확장하면 아무 것도 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="58ac1-163">If the comparison has no recommendations for improvement (green), expanding the policy reveals nothing.</span></span> <span data-ttu-id="58ac1-164">개선을 위한 권장 사항(빨강 또는 빨강)이 있는 경우 주의가 필요한 설정이 표시될 수 있으며 해당 정보는 다음 열에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="58ac1-164">If there are any number of recommendations for improvement (amber or red), the settings that require attention are revealed, and corresponding information is revealed in the following columns:</span></span>

- <span data-ttu-id="58ac1-165">주의가 필요한 설정의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="58ac1-165">The name of the setting that requires your attention.</span></span> <span data-ttu-id="58ac1-166">예를 들어 이전 스크린샷에서 스팸 방지 정책의 대량 전자 메일 **임계값입니다.**</span><span class="sxs-lookup"><span data-stu-id="58ac1-166">For example, in the previous screenshot, it's the **Bulk email threshold** in an anti-spam policy.</span></span>

- <span data-ttu-id="58ac1-167">**정책**: 설정이 포함된 영향을 받는 정책의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="58ac1-167">**Policy**: The name of the affected policy that contains the setting.</span></span>

- <span data-ttu-id="58ac1-168">**적용:** 영향을 받는 정책이 적용되는 사용자 수입니다.</span><span class="sxs-lookup"><span data-stu-id="58ac1-168">**Applied to**: The number of users that the affected policies are applied to.</span></span>

- <span data-ttu-id="58ac1-169">**현재 구성**: 설정의 현재 값입니다.</span><span class="sxs-lookup"><span data-stu-id="58ac1-169">**Current configuration**: The current value of the setting.</span></span>

- <span data-ttu-id="58ac1-170">**마지막으로 수정한** 날짜: 정책을 마지막으로 수정한 날짜입니다.</span><span class="sxs-lookup"><span data-stu-id="58ac1-170">**Last modified**: The date that the policy was last modified.</span></span>

- <span data-ttu-id="58ac1-171">**권장** 사항 : 표준 또는 엄격한 보호 프로필의 설정 값입니다.</span><span class="sxs-lookup"><span data-stu-id="58ac1-171">**Recommendations**: The value of the setting in the Standard or Strict protection profile.</span></span> <span data-ttu-id="58ac1-172">정책의 설정 값을 보호 프로필의 권장 값과 일치하게 변경하려면 채택을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="58ac1-172">To change the value of the setting in your policy to match the recommended value in the protection profile, click **Adopt**.</span></span> <span data-ttu-id="58ac1-173">변경에 성공하면 다음 메시지가 **표시됩니다. 추천이 성공적으로 채택됩니다.**</span><span class="sxs-lookup"><span data-stu-id="58ac1-173">If the change is successful, you'll see the message: **Recommendations successfully adopted**.</span></span> <span data-ttu-id="58ac1-174">새로 **고침을** 클릭하여 줄어든 추천 수와 결과에서 특정 설정/정책 행을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="58ac1-174">Click **Refresh** to see the reduced number of recommendations, and the removal of the specific setting/policy row from the results.</span></span>

### <a name="configuration-drift-analysis-and-history-tab-in-the-configuration-analyzer"></a><span data-ttu-id="58ac1-175">구성 분석기에서 구성 드리프트 분석 및 기록 탭</span><span class="sxs-lookup"><span data-stu-id="58ac1-175">Configuration drift analysis and history tab in the configuration analyzer</span></span>

<span data-ttu-id="58ac1-176">이 탭에서는 사용자 지정 보안 정책에 적용한 변경 내용을 추적할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58ac1-176">This tab allows you to track the changes that you've made to your custom security policies.</span></span> <span data-ttu-id="58ac1-177">기본적으로 다음과 같은 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="58ac1-177">By default, the following information is displayed:</span></span>

- <span data-ttu-id="58ac1-178">**마지막으로 수정한 날짜**</span><span class="sxs-lookup"><span data-stu-id="58ac1-178">**Last modified**</span></span>
- <span data-ttu-id="58ac1-179">**수정한 사용자**</span><span class="sxs-lookup"><span data-stu-id="58ac1-179">**Modified by**</span></span>
- <span data-ttu-id="58ac1-180">**설정 이름**</span><span class="sxs-lookup"><span data-stu-id="58ac1-180">**Setting Name**</span></span>
- <span data-ttu-id="58ac1-181">**정책**</span><span class="sxs-lookup"><span data-stu-id="58ac1-181">**Policy**</span></span>
- <span data-ttu-id="58ac1-182">**Type**</span><span class="sxs-lookup"><span data-stu-id="58ac1-182">**Type**</span></span>

<span data-ttu-id="58ac1-183">결과를 필터링하려면 **필터** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="58ac1-183">To filter the results, click **Filter**.</span></span> <span data-ttu-id="58ac1-184">필터  플라이아웃이 나타나면 다음 필터에서 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58ac1-184">In the **Filters** flyout that appears, you can select from the following filters:</span></span>

- <span data-ttu-id="58ac1-185">**시작 시간** 및 **종료 시간(날짜)**</span><span class="sxs-lookup"><span data-stu-id="58ac1-185">**Start time** and **End time** (date)</span></span>
- <span data-ttu-id="58ac1-186">**표준 보호** 또는 **엄격한 보호**</span><span class="sxs-lookup"><span data-stu-id="58ac1-186">**Standard protection** or **Strict protection**</span></span>

<span data-ttu-id="58ac1-187">결과를 .csv 파일로 내보내려면 내보내기 를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="58ac1-187">To export the results to a .csv file, click **Export**.</span></span>

![구성 분석기에서 구성 드리프트 분석 및 기록 보기](../../media/configuration-analyzer-configuration-drift-analysis-view.png)
