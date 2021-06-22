---
title: Quarantine policies
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
ROBOTS: NOINDEX
description: 관리자는 사용자가 자신의 검사된 메시지에 대해 할 수 있는 작업을 제어하기 위해 검지 정책을 사용하는 방법을 배울 수 있습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 96dc1e2158787457884ca6a3c6f27bf76e83a369
ms.sourcegitcommit: fa9efab24a84f71fec7d001f2ad8949125fa8eee
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/22/2021
ms.locfileid: "53055212"
---
# <a name="quarantine-policies"></a><span data-ttu-id="70fb5-103">Quarantine policies</span><span class="sxs-lookup"><span data-stu-id="70fb5-103">Quarantine policies</span></span>

> [!NOTE]
> <span data-ttu-id="70fb5-104">이 문서에서 설명하는 기능은 현재 미리 보기로 제공되어 있으며 모든 사람이 사용할 수 있으며 변경될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-104">The features that are described in this article are currently in Preview, aren't available to everyone, and are subject to change.</span></span>

<span data-ttu-id="70fb5-105">EOP(Exchange Online Protection)의 검사 정책(이전의 Quarantine tags)을 사용하면 관리자가 메시지가 검사에 도착한 방식에 따라 사용자가 자신의 검지된 메시지에 대해 할 수 있는 작업을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-105">Quarantine policies (formerly known as quarantine tags) in Exchange Online Protection (EOP) allow admins to control what users are able to do to their quarantined messages based on how the message arrived in quarantine.</span></span>

<span data-ttu-id="70fb5-106">EOP는 일반적으로 메시지에 대해 특정 수준의 대화형 작업 [](find-and-release-quarantined-messages-as-a-user.md) 수준을 허용하거나 차단하고 있으며, 이러한 대화형 작업 수준은 최종 사용자 스팸 [알림에서 허용되거나 차단되었습니다.](use-spam-notifications-to-release-and-report-quarantined-messages.md)</span><span class="sxs-lookup"><span data-stu-id="70fb5-106">EOP has traditionally allowed or prevented certain levels of interactivity for messages in [quarantine](find-and-release-quarantined-messages-as-a-user.md) and in [end-user spam notifications](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span></span> <span data-ttu-id="70fb5-107">예를 들어 사용자는 스팸 방지 필터링에 의해 스팸 또는 대량으로 검색된 메시지를 보고 해제할 수 있지만 높은 신뢰도 피싱으로 분류된 메시지를 보거나 해제할 수 없습니다(관리자만 이 작업을 할 수 있습니다).</span><span class="sxs-lookup"><span data-stu-id="70fb5-107">For example, users can view and release messages that were quarantined by anti-spam filtering as spam or bulk, but they can't view or release messages that were quarantined as high confidence phishing (only admins can do that).</span></span>

<span data-ttu-id="70fb5-108">[지원되는](#step-2-assign-a-quarantine-policy-to-supported-features)보호 기능의 경우, 검역 정책은 최종 사용자 스팸 알림 메시지 및 사용자가 받는 사람인 메시지에 대해 검역소에서 사용자가 할 수 있는 작업을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-108">For [supported protection features](#step-2-assign-a-quarantine-policy-to-supported-features), quarantine policies specify what users are allowed to do in end-user spam notification messages and in their quarantined messages in quarantine (messages where the user is a recipient).</span></span> <span data-ttu-id="70fb5-109">기본 검역 정책은 사용자가 검역된 메시지에 기록 기능을 적용하기 위해 자동으로 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-109">Default quarantine policies are automatically assigned to enforce the historical capabilities for users on quarantined messages.</span></span> <span data-ttu-id="70fb5-110">또는 최종 사용자가 분리된 메시지에 대해 특정 작업을 수행할 수 있도록 허용하거나 금지하는 사용자 지정 검지 정책을 만들고 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-110">Or, you can create and assign custom quarantine policies to allow or prevent end users from performing specific actions on quarantined messages.</span></span>

<span data-ttu-id="70fb5-111">개별 사용 권한은 미리 설정한 다음 사용 권한 그룹에 결합됩니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-111">The individual permissions are combined into the following preset permission groups:</span></span>

- <span data-ttu-id="70fb5-112">권한 없음</span><span class="sxs-lookup"><span data-stu-id="70fb5-112">No access</span></span>
- <span data-ttu-id="70fb5-113">제한된 액세스</span><span class="sxs-lookup"><span data-stu-id="70fb5-113">Limited access</span></span>
- <span data-ttu-id="70fb5-114">모든 액세스</span><span class="sxs-lookup"><span data-stu-id="70fb5-114">Full access</span></span>

<span data-ttu-id="70fb5-115">사용 가능한 개별 사용 권한 및 미리 설정한 권한 그룹에 포함되거나 포함되지 않은 사용 권한에 대한 설명은 다음 표에 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-115">The available individual permissions and what's included or not included in the preset permission groups are described in the following table:</span></span>

<br>

****

|<span data-ttu-id="70fb5-116">사용 권한</span><span class="sxs-lookup"><span data-stu-id="70fb5-116">Permission</span></span>|<span data-ttu-id="70fb5-117">권한 없음</span><span class="sxs-lookup"><span data-stu-id="70fb5-117">No access</span></span>|<span data-ttu-id="70fb5-118">제한된 액세스</span><span class="sxs-lookup"><span data-stu-id="70fb5-118">Limited access</span></span>|<span data-ttu-id="70fb5-119">모든 액세스</span><span class="sxs-lookup"><span data-stu-id="70fb5-119">Full access</span></span>|
|---|:---:|:---:|:---:|
|<span data-ttu-id="70fb5-120">**보낸 사람 허용(** _PermissionToAllowSender_)</span><span class="sxs-lookup"><span data-stu-id="70fb5-120">**Allow sender** (_PermissionToAllowSender_)</span></span>|||![확인 표시](../../media/checkmark.png)|
|<span data-ttu-id="70fb5-122">**보낸 사람 차단(** _PermissionToBlockSender_)</span><span class="sxs-lookup"><span data-stu-id="70fb5-122">**Block sender** (_PermissionToBlockSender_)</span></span>||![확인 표시](../../media/checkmark.png)|![확인 표시](../../media/checkmark.png)|
|<span data-ttu-id="70fb5-125">**Delete(** _PermissionToDelete_)</span><span class="sxs-lookup"><span data-stu-id="70fb5-125">**Delete** (_PermissionToDelete_)</span></span>||![확인 표시](../../media/checkmark.png)|![확인 표시](../../media/checkmark.png)|
|<span data-ttu-id="70fb5-128">**미리 보기(** _PermissionToPreview_)</span><span class="sxs-lookup"><span data-stu-id="70fb5-128">**Preview** (_PermissionToPreview_)</span></span>||![확인 표시](../../media/checkmark.png)|![확인 표시](../../media/checkmark.png)|
|<span data-ttu-id="70fb5-131">받는 사람이 메시지를 **검지에서** 해제할 수 있도록 허용(_PermissionToRelease_)</span><span class="sxs-lookup"><span data-stu-id="70fb5-131">**Allow recipients to release a message from quarantine** (_PermissionToRelease_)</span></span>|||![확인 표시](../../media/checkmark.png)|
|<span data-ttu-id="70fb5-133">받는 사람이 메시지를 검지에서 릴리스하도록 **요청하도록 허용(** _PermissionToRequestRelease_)</span><span class="sxs-lookup"><span data-stu-id="70fb5-133">**Allow recipients to request a message to be released from quarantine** (_PermissionToRequestRelease_)</span></span>||![확인 표시](../../media/checkmark.png)||
|

<span data-ttu-id="70fb5-135">미리 설정한 권한 그룹의 기본 사용 권한이 원하지 않는 경우 사용자 지정 검지 정책을 만들거나 수정할 때 사용자 지정 권한을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-135">If you don't like the default permissions in the preset permission groups, you can use custom permissions when you create or modify custom quarantine policies.</span></span> <span data-ttu-id="70fb5-136">각 사용 권한의 작동에 대한 자세한 내용은 이 문서 의 부분에 있는 정책 사용 권한 세부 정보 [섹션을](#quarantine-policy-permission-details) 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="70fb5-136">For more information about what each permission does, see the [Quarantine policy permission details](#quarantine-policy-permission-details) section later in this article.</span></span>

<span data-ttu-id="70fb5-137">Microsoft 365 Defender 포털 또는 PowerShell(Exchange Online 사서함이 있는 Microsoft 365 조직용 Exchange Online PowerShell, 사서함이 없는 EOP 조직의 독립 실행형 EOP PowerShell)에서 Exchange Online 정책을 만들고 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-137">You create and assign quarantine policies in the Microsoft 365 Defender portal or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with Exchange Online Mailboxes; standalone EOP PowerShell in EOP organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="70fb5-138">시작하기 전에 알아야 할 내용은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="70fb5-138">What do you need to know before you begin?</span></span>

- <span data-ttu-id="70fb5-139"><https://security.microsoft.com>에서 Microsoft 365 Defender 포털을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-139">You open the Microsoft 365 Defender portal at <https://security.microsoft.com>.</span></span> <span data-ttu-id="70fb5-140">또는 **Quarantine policies(정책)** 페이지로 직접 이동하여 를 를 를 니다. <https://security.microsoft.com/quarantineTags></span><span class="sxs-lookup"><span data-stu-id="70fb5-140">Or to go directly to the **Quarantine policies** page, open <https://security.microsoft.com/quarantineTags>.</span></span>

- <span data-ttu-id="70fb5-141">Exchange Online PowerShell에 연결하려면 [Exchange Online PowerShell에 연결](/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="70fb5-141">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="70fb5-142">독립 실행형 EOP PowerShell에 연결하려면 [Exchange Online Protection PowerShell에 연결](/powershell/exchange/connect-to-exchange-online-protection-powershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="70fb5-142">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="70fb5-143">검역 정책을 보거나 만들거나 수정하거나 제거하려면 조직 포털에서 조직  관리  또는 보안 관리자 역할의 구성원 Microsoft 365 Defender 합니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-143">To view, create, modify, or remove quarantine policies, you need to be a member of the **Organization Management** or **Security Administrator** roles in the Microsoft 365 Defender portal.</span></span> <span data-ttu-id="70fb5-144">자세한 내용은 [Microsoft 365 Defender 포털 권한](permissions-microsoft-365-security-center.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="70fb5-144">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-microsoft-365-security-center.md).</span></span>

## <a name="step-1-create-quarantine-policies-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="70fb5-145">1단계: 사이트 포털에서 Microsoft 365 Defender 만들기</span><span class="sxs-lookup"><span data-stu-id="70fb5-145">Step 1: Create quarantine policies in the Microsoft 365 Defender portal</span></span>

1. <span data-ttu-id="70fb5-146">Microsoft 365 Defender 포털에서 전자 메일 &  위협 정책 규칙 섹션으로 이동한 다음 정책 검지 \>  \>  \>  **를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="70fb5-146">In the Microsoft 365 Defender portal, go to **Email & collaboration** \>**Threat policies** \> **Rules** section \> **Quarantine policies** and then select **Quarantine policies**.</span></span>

2. <span data-ttu-id="70fb5-147">**Quarantine policy 페이지에서** Add custom policy icon Add custom policy (사용자 지정 정책 추가)를 ![ ](../../media/m365-cc-sc-create-icon.png) **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="70fb5-147">On the **Quarantine policy** page, click ![Add custom policy icon](../../media/m365-cc-sc-create-icon.png) **Add custom policy**.</span></span>

3. <span data-ttu-id="70fb5-148">새 **정책 마법사가** 열립니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-148">The **New policy** wizard opens.</span></span> <span data-ttu-id="70fb5-149">정책 **이름 페이지의** 정책 이름 상자에 간략하지만 고유한 **이름을 입력합니다.**</span><span class="sxs-lookup"><span data-stu-id="70fb5-149">On the **Policy name** page, enter a brief but unique name in the **Policy name** box.</span></span> <span data-ttu-id="70fb5-150">다음 단계에서 이름으로 정책을 식별하고 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-150">You'll need to identify and select the quarantine policy by name in upcoming steps.</span></span> <span data-ttu-id="70fb5-151">작업을 마친 후 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-151">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="70fb5-152">받는 **사람 메시지 액세스 페이지에서** 다음 값 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-152">On the **Recipient message access** page, select one of the following values:</span></span>
   - <span data-ttu-id="70fb5-153">**액세스 금지**</span><span class="sxs-lookup"><span data-stu-id="70fb5-153">**No access**</span></span>
   - <span data-ttu-id="70fb5-154">**제한된 액세스**</span><span class="sxs-lookup"><span data-stu-id="70fb5-154">**Limited access**</span></span>
   - <span data-ttu-id="70fb5-155">**모든 액세스**</span><span class="sxs-lookup"><span data-stu-id="70fb5-155">**Full access**</span></span>

   <span data-ttu-id="70fb5-156">이러한 사용 권한 그룹에 포함된 개별 사용 권한에 대한 설명은 이 문서 앞부분에 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-156">The individual permissions that are included in these permission groups are described earlier in this article.</span></span>

   <span data-ttu-id="70fb5-157">사용자 지정 권한을 지정하려면 특정 액세스 **설정(고급)을** 선택하고 나타나는 다음 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-157">To specify custom permissions, select **Set specific access (Advanced)** and the configure the following settings that appear:</span></span>

     - <span data-ttu-id="70fb5-158">**릴리스 작업 기본 설정** 선택 : 다음 값 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-158">**Select release action preference**: Select one of the following values:</span></span>
       - <span data-ttu-id="70fb5-159">**릴리스 작업 없음:** 이 값은 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-159">**No release action**: This is the default value.</span></span>
       - <span data-ttu-id="70fb5-160">**받는 사람이 메시지를 검지에서 해제할 수 있도록 허용**</span><span class="sxs-lookup"><span data-stu-id="70fb5-160">**Allow recipients to release a message from quarantine**</span></span>
       - <span data-ttu-id="70fb5-161">**받는 사람이 메시지를 검지에서 릴리스하도록 요청하도록 허용**</span><span class="sxs-lookup"><span data-stu-id="70fb5-161">**Allow recipients to request a message to be released from quarantine**</span></span>
     - <span data-ttu-id="70fb5-162">**받는 사람이** 다음의 값 중 일부 또는 전체를 선택하거나, 모두 또는 전혀 선택하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-162">**Select additional actions recipients can take on quarantined messages**: Select some, all, or none of the following values:</span></span>
       - <span data-ttu-id="70fb5-163">**삭제**</span><span class="sxs-lookup"><span data-stu-id="70fb5-163">**Delete**</span></span>
       - <span data-ttu-id="70fb5-164">**미리 보기**</span><span class="sxs-lookup"><span data-stu-id="70fb5-164">**Preview**</span></span>
       - <span data-ttu-id="70fb5-165">**보낸 사람 차단**</span><span class="sxs-lookup"><span data-stu-id="70fb5-165">**Block sender**</span></span>

   <span data-ttu-id="70fb5-166">이러한 사용 권한 및 이러한 사용 권한 및 최종 사용자 스팸 알림에 대한 [](#quarantine-policy-permission-details) 영향은 이 문서 의 부분에 있는 정책 사용 권한 세부 정보 섹션에 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-166">These permissions and their effect on quarantined messages and in end-user spam notifications are described in the [Quarantine policy permission details](#quarantine-policy-permission-details) section later in this article.</span></span>

   <span data-ttu-id="70fb5-167">작업을 마친 후 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-167">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="70fb5-168">정책 **검토 페이지가** 나타나면 설정을 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-168">On the **Review policy** page that appears, review your settings.</span></span> <span data-ttu-id="70fb5-169">각 섹션에서 **편집** 선택하여 섹션 내의 설정을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-169">You can select **Edit** in each section to modify the settings within the section.</span></span> <span data-ttu-id="70fb5-170">또는 **뒤로** 를 클릭하거나 마법사에서 특정 페이지를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-170">Or you can click **Back** or select the specific page in the wizard.</span></span>

   <span data-ttu-id="70fb5-171">완료되면 제출을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="70fb5-171">When you're finished, click **Submit**.</span></span>

6. <span data-ttu-id="70fb5-172">표시되는 확인 페이지에서 **완료** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-172">On the confirmation page that appears, click **Done**.</span></span>

<span data-ttu-id="70fb5-173">이제 [2단계](#step-2-assign-a-quarantine-policy-to-supported-features) 섹션에 설명된 바와 같이 검지 기능에 검지 정책을 할당할 준비가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-173">Now you're ready to assign the quarantine policy to a quarantine feature as described in the [Step 2](#step-2-assign-a-quarantine-policy-to-supported-features) section.</span></span>

### <a name="create-quarantine-policies-in-powershell"></a><span data-ttu-id="70fb5-174">PowerShell에서 검사 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="70fb5-174">Create quarantine policies in PowerShell</span></span>

<span data-ttu-id="70fb5-175">PowerShell을 사용하여 정책을 만드는 것이 더 능한 경우 powerShell 또는 Exchange Online PowerShell에 Exchange Online Protection **New-QuarantineTag** cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-175">If you'd rather use PowerShell to create quarantine policies, connect to Exchange Online PowerShell or Exchange Online Protection PowerShell and use the **New-QuarantineTag** cmdlet.</span></span> <span data-ttu-id="70fb5-176">다음 두 가지 방법으로 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-176">You have two different methods to choose from:</span></span>

- <span data-ttu-id="70fb5-177">_EndUserQuarantinePermissionsValue 매개 변수를_ 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-177">Use the _EndUserQuarantinePermissionsValue_ parameter.</span></span>
- <span data-ttu-id="70fb5-178">_EndUserQuarantinePermissions 매개 변수를_ 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-178">Use the _EndUserQuarantinePermissions_ parameter.</span></span>

<span data-ttu-id="70fb5-179">이러한 메서드에 대한 설명은 다음 섹션에 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-179">These methods are described in the following sections.</span></span>

#### <a name="use-the-enduserquarantinepermissionsvalue-parameter"></a><span data-ttu-id="70fb5-180">EndUserQuarantinePermissionsValue 매개 변수 사용</span><span class="sxs-lookup"><span data-stu-id="70fb5-180">Use the EndUserQuarantinePermissionsValue parameter</span></span>

<span data-ttu-id="70fb5-181">_EndUserQuarantinePermissionsValue_ 매개 변수를 사용하여 검지 정책을 만들 경우 다음 구문을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-181">To create a quarantine policy using the _EndUserQuarantinePermissionsValue_ parameter, use the following syntax:</span></span>

```powershell
New-QuarantineTag -Name "<UniqueName>" -EndUserQuarantinePermissionsValue <0 to 236>
```

<span data-ttu-id="70fb5-182">_EndUserQuarantinePermissionsValue_ 매개 변수는 이진 값에서 변환된 소수 값을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-182">The _EndUserQuarantinePermissionsValue_ parameter uses a decimal value that's converted from a binary value.</span></span> <span data-ttu-id="70fb5-183">이진 값은 특정 순서로 사용 가능한 최종 사용자 검지 권한에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-183">The binary value corresponds to the available end-user quarantine permissions in a specific order.</span></span> <span data-ttu-id="70fb5-184">각 사용 권한에 대해 값 1은 True, 값 0은 False입니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-184">For each permission, the value 1 equals True and the value 0 equals False.</span></span>

<span data-ttu-id="70fb5-185">다음 표에서는 미리 설정한 사용 권한 그룹의 각 개별 권한에 필요한 순서와 값을 설명하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-185">The required order and values for each individual permission in preset permission groups are described in the following table:</span></span>

<br>

****

|<span data-ttu-id="70fb5-186">사용 권한</span><span class="sxs-lookup"><span data-stu-id="70fb5-186">Permission</span></span>|<span data-ttu-id="70fb5-187">권한 없음</span><span class="sxs-lookup"><span data-stu-id="70fb5-187">No access</span></span>|<span data-ttu-id="70fb5-188">제한된 액세스</span><span class="sxs-lookup"><span data-stu-id="70fb5-188">Limited access</span></span>|<span data-ttu-id="70fb5-189">모든 액세스</span><span class="sxs-lookup"><span data-stu-id="70fb5-189">Full access</span></span>|
|---|:---:|:---:|:---:|
|<span data-ttu-id="70fb5-190">PermissionToAllowSender</span><span class="sxs-lookup"><span data-stu-id="70fb5-190">PermissionToAllowSender</span></span>|<span data-ttu-id="70fb5-191">0</span><span class="sxs-lookup"><span data-stu-id="70fb5-191">0</span></span>|<span data-ttu-id="70fb5-192">0</span><span class="sxs-lookup"><span data-stu-id="70fb5-192">0</span></span>|<span data-ttu-id="70fb5-193">1</span><span class="sxs-lookup"><span data-stu-id="70fb5-193">1</span></span>|
|<span data-ttu-id="70fb5-194">PermissionToBlockSender</span><span class="sxs-lookup"><span data-stu-id="70fb5-194">PermissionToBlockSender</span></span>|<span data-ttu-id="70fb5-195">0</span><span class="sxs-lookup"><span data-stu-id="70fb5-195">0</span></span>|<span data-ttu-id="70fb5-196">1</span><span class="sxs-lookup"><span data-stu-id="70fb5-196">1</span></span>|<span data-ttu-id="70fb5-197">1</span><span class="sxs-lookup"><span data-stu-id="70fb5-197">1</span></span>|
|<span data-ttu-id="70fb5-198">PermissionToDelete</span><span class="sxs-lookup"><span data-stu-id="70fb5-198">PermissionToDelete</span></span>|<span data-ttu-id="70fb5-199">0</span><span class="sxs-lookup"><span data-stu-id="70fb5-199">0</span></span>|<span data-ttu-id="70fb5-200">1</span><span class="sxs-lookup"><span data-stu-id="70fb5-200">1</span></span>|<span data-ttu-id="70fb5-201">1</span><span class="sxs-lookup"><span data-stu-id="70fb5-201">1</span></span>|
|<span data-ttu-id="70fb5-202">PermissionToDownload<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="70fb5-202">PermissionToDownload<sup>\*</sup></span></span>|<span data-ttu-id="70fb5-203">0</span><span class="sxs-lookup"><span data-stu-id="70fb5-203">0</span></span>|<span data-ttu-id="70fb5-204">0</span><span class="sxs-lookup"><span data-stu-id="70fb5-204">0</span></span>|<span data-ttu-id="70fb5-205">0</span><span class="sxs-lookup"><span data-stu-id="70fb5-205">0</span></span>|
|<span data-ttu-id="70fb5-206">PermissionToPreview</span><span class="sxs-lookup"><span data-stu-id="70fb5-206">PermissionToPreview</span></span>|<span data-ttu-id="70fb5-207">0</span><span class="sxs-lookup"><span data-stu-id="70fb5-207">0</span></span>|<span data-ttu-id="70fb5-208">1</span><span class="sxs-lookup"><span data-stu-id="70fb5-208">1</span></span>|<span data-ttu-id="70fb5-209">1</span><span class="sxs-lookup"><span data-stu-id="70fb5-209">1</span></span>|
|<span data-ttu-id="70fb5-210">PermissionToRelease<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="70fb5-210">PermissionToRelease<sup>\*\*</sup></span></span>|<span data-ttu-id="70fb5-211">0</span><span class="sxs-lookup"><span data-stu-id="70fb5-211">0</span></span>|<span data-ttu-id="70fb5-212">0</span><span class="sxs-lookup"><span data-stu-id="70fb5-212">0</span></span>|<span data-ttu-id="70fb5-213">1</span><span class="sxs-lookup"><span data-stu-id="70fb5-213">1</span></span>|
|<span data-ttu-id="70fb5-214">PermissionToRequestRelease<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="70fb5-214">PermissionToRequestRelease<sup>\*\*</sup></span></span>|<span data-ttu-id="70fb5-215">0</span><span class="sxs-lookup"><span data-stu-id="70fb5-215">0</span></span>|<span data-ttu-id="70fb5-216">1</span><span class="sxs-lookup"><span data-stu-id="70fb5-216">1</span></span>|<span data-ttu-id="70fb5-217">0</span><span class="sxs-lookup"><span data-stu-id="70fb5-217">0</span></span>|
|<span data-ttu-id="70fb5-218">PermissionToViewHeader<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="70fb5-218">PermissionToViewHeader<sup>\*</sup></span></span>|<span data-ttu-id="70fb5-219">0</span><span class="sxs-lookup"><span data-stu-id="70fb5-219">0</span></span>|<span data-ttu-id="70fb5-220">0</span><span class="sxs-lookup"><span data-stu-id="70fb5-220">0</span></span>|<span data-ttu-id="70fb5-221">0</span><span class="sxs-lookup"><span data-stu-id="70fb5-221">0</span></span>|
|<span data-ttu-id="70fb5-222">이진 값</span><span class="sxs-lookup"><span data-stu-id="70fb5-222">Binary value</span></span>|<span data-ttu-id="70fb5-223">00000000</span><span class="sxs-lookup"><span data-stu-id="70fb5-223">00000000</span></span>|<span data-ttu-id="70fb5-224">01101010</span><span class="sxs-lookup"><span data-stu-id="70fb5-224">01101010</span></span>|<span data-ttu-id="70fb5-225">11101100</span><span class="sxs-lookup"><span data-stu-id="70fb5-225">11101100</span></span>|
|<span data-ttu-id="70fb5-226">사용할 10진수 값</span><span class="sxs-lookup"><span data-stu-id="70fb5-226">Decimal value to use</span></span>|<span data-ttu-id="70fb5-227">0</span><span class="sxs-lookup"><span data-stu-id="70fb5-227">0</span></span>|<span data-ttu-id="70fb5-228">106</span><span class="sxs-lookup"><span data-stu-id="70fb5-228">106</span></span>|<span data-ttu-id="70fb5-229">236</span><span class="sxs-lookup"><span data-stu-id="70fb5-229">236</span></span>|
|

<span data-ttu-id="70fb5-230"><sup>\*</sup> 현재 이 값은 항상 0입니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-230"><sup>\*</sup> Currently, this value is always 0.</span></span> <span data-ttu-id="70fb5-231">PermissionToViewHeader의 경우 값 0은 분리된 메시지의 세부 정보에서 메시지 헤더 보기 단추를 숨기지 않습니다(단추는 항상 사용 가능). </span><span class="sxs-lookup"><span data-stu-id="70fb5-231">For PermissionToViewHeader, the value 0 doesn't hide the **View message header** button in the details of the quarantined message (the button is always available).</span></span>

<span data-ttu-id="70fb5-232"><sup>\*\*</sup> 이 두 값을 모두 1로 설정하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-232"><sup>\*\*</sup> Don't set both of these values to 1.</span></span> <span data-ttu-id="70fb5-233">1을 1로 설정하고 다른 하나는 0으로 설정하거나 둘 다 0으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-233">Set one to 1 and the other to 0, or set both to 0.</span></span>

<span data-ttu-id="70fb5-234">이 예에서는 이전 표에 설명된 바와 같이 액세스 권한 없음 권한을 할당하는 새 검지 정책 이름 NoAccess를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-234">This example creates a new quarantine policy name NoAccess that assigns the No access permissions as described in the previous table.</span></span>

```powershell
New-QuarantineTag -Name NoAccess -EndUserQuarantinePermissionsValue 0
```

<span data-ttu-id="70fb5-235">제한된 액세스 권한의 경우 값 106을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-235">For Limited access permissions, use the value 106.</span></span> <span data-ttu-id="70fb5-236">모든 액세스 권한의 경우 값 236을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-236">For Full access permissions, use the value 236.</span></span>

<span data-ttu-id="70fb5-237">사용자 지정 권한의 경우 앞의 표를 사용하여 원하는 사용 권한에 해당하는 이진 값을 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-237">For custom permissions, use the previous table to get the binary value that corresponds to the permissions you want.</span></span> <span data-ttu-id="70fb5-238">이진 값을 10진수 값으로 변환하고 _EndUserQuarantinePermissionsValue_ 매개 변수에 소수 값을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-238">Convert the binary value to a decimal value and use the decimal value for the _EndUserQuarantinePermissionsValue_ parameter.</span></span>

<span data-ttu-id="70fb5-239">구문과 매개 변수에 대한 자세한 내용은 [New-QuarantineTag 를 참조하십시오.](/powershell/module/exchange/new-quarantinetag)</span><span class="sxs-lookup"><span data-stu-id="70fb5-239">For detailed syntax and parameter information, see [New-QuarantineTag](/powershell/module/exchange/new-quarantinetag).</span></span>

#### <a name="use-the-enduserquarantinepermissions-parameter"></a><span data-ttu-id="70fb5-240">EndUserQuarantinePermissions 매개 변수 사용</span><span class="sxs-lookup"><span data-stu-id="70fb5-240">Use the EndUserQuarantinePermissions parameter</span></span>

<span data-ttu-id="70fb5-241">_EndUserQuarantinePermissionsValue_ 매개 변수를 사용하여 검지 정책을 만들 경우 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-241">To create a quarantine policy using the _EndUserQuarantinePermissionsValue_ parameter, do the following steps:</span></span>

<span data-ttu-id="70fb5-242">대답.</span><span class="sxs-lookup"><span data-stu-id="70fb5-242">A.</span></span> <span data-ttu-id="70fb5-243">**New-QuarantinePermissions** cmdlet을 사용하여 변수에 quarantine permissions 개체를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-243">Store a quarantine permissions object in a variable using the **New-QuarantinePermissions** cmdlet.</span></span>

<p>

<span data-ttu-id="70fb5-244">B.</span><span class="sxs-lookup"><span data-stu-id="70fb5-244">B.</span></span> <span data-ttu-id="70fb5-245">**변수를 New-QuarantineTag** 명령에서 _EndUserQuarantinePermissions_ 값으로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-245">Use the variable as the _EndUserQuarantinePermissions_ value in the **New-QuarantineTag** command.</span></span>

##### <a name="step-a-store-a-quarantine-permissions-object-in-a-variable"></a><span data-ttu-id="70fb5-246">A단계: 변수에 검지 권한 개체 저장</span><span class="sxs-lookup"><span data-stu-id="70fb5-246">Step A: Store a quarantine permissions object in a variable</span></span>

<span data-ttu-id="70fb5-247">다음 구문을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-247">Use the following syntax:</span></span>

```powershell
$<VariableName> = New-QuarantinePermissions [-PermissionToAllowSender <$true | $False>] [-PermissionToBlockSender <$true | $False>] [-PermissionToDelete <$true | $False>] [-PermissionToPreview <$true | $False>] [-PermissionToRelease <$true | $False>] [-PermissionToRequestRelease <$true | $False>]
```

<span data-ttu-id="70fb5-248">사용되지 않는 매개 변수의 기본값은 입니다. 따라서 값을 설정하려는 매개 변수만 `$false` 사용하면 `$true` 됩니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-248">The default value for any unused parameters is `$false`, so you only need to use the parameters where you want to set value to `$true`.</span></span>

<span data-ttu-id="70fb5-249">다음 예에서는 미리 설정한 사용 권한 그룹에 해당하는 사용 권한 개체를 만드는 방법을 보여 주며,</span><span class="sxs-lookup"><span data-stu-id="70fb5-249">The following examples show how to create permission objects that correspond to the preset permissions groups:</span></span>

- <span data-ttu-id="70fb5-250">**액세스 권한이 없습니다.**</span><span class="sxs-lookup"><span data-stu-id="70fb5-250">**No access**:</span></span>

  ```powershell
  $NoAccess = New-QuarantinePermissions
  ```

- <span data-ttu-id="70fb5-251">**제한된 액세스**:</span><span class="sxs-lookup"><span data-stu-id="70fb5-251">**Limited access**:</span></span>

  ```powershell
  $LimitedAccess = New-QuarantinePermissions -PermissionToBlockSender $true -PermissionToDelete $true -PermissionToPreview $true -PermissionToRequestRelease $true
  ```

- <span data-ttu-id="70fb5-252">**모든 액세스**:</span><span class="sxs-lookup"><span data-stu-id="70fb5-252">**Full access**:</span></span>

  ```powershell
  $FullAccess = New-QuarantinePermissions -PermissionToAllowSender $true -PermissionToBlockSender $true -PermissionToDelete $true -PermissionToPreview $true -PermissionToRelease $true
  ```

<span data-ttu-id="70fb5-253">설정한 값을 표시하기 위해 변수 이름을 명령으로 실행합니다(예: 명령을 `$NoAccess` 실행).</span><span class="sxs-lookup"><span data-stu-id="70fb5-253">To see the values that you've set, run the variable name as a command (for example, run the command `$NoAccess`).</span></span>

<span data-ttu-id="70fb5-254">사용자 지정 권한의 경우 _PermissionToRelease_ 및 _PermissionToRequestRelease_ 매개 변수를 로 설정하지 `$true` 않습니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-254">For custom permissions, don't set both the _PermissionToRelease_ and _PermissionToRequestRelease_ parameters to `$true`.</span></span> <span data-ttu-id="70fb5-255">를 로 설정하고 다른 를 로 설정하거나 두 가지 모두 로 `$true` `$false` 를 그대로 . `$false`</span><span class="sxs-lookup"><span data-stu-id="70fb5-255">Set one to `$true` and leave the other as `$false`, or leave both as `$false`.</span></span>

<span data-ttu-id="70fb5-256">**Set-QuarantinePermissions** cmdlet을 사용하여 기존 사용 권한 개체 변수를 만든 후 사용하기 전에 수정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-256">You can also modify an existing permissions object variable after you create but before you use it by using the **Set-QuarantinePermissions** cmdlet.</span></span>

<span data-ttu-id="70fb5-257">구문과 매개 변수에 대한 자세한 내용은 [New-QuarantinePermissions](/powershell/module/exchange/new-quarantinepermissions) 및 [Set-QuarantinePermissions를 참조하십시오.](/powershell/module/exchange/set-quarantinepermissions)</span><span class="sxs-lookup"><span data-stu-id="70fb5-257">For detailed syntax and parameter information, see [New-QuarantinePermissions](/powershell/module/exchange/new-quarantinepermissions) and [Set-QuarantinePermissions](/powershell/module/exchange/set-quarantinepermissions).</span></span>

##### <a name="step-b-use-the-variable-in-the-new-quarantinetag-command"></a><span data-ttu-id="70fb5-258">B단계: 다음 명령에서 변수 New-QuarantineTag 사용</span><span class="sxs-lookup"><span data-stu-id="70fb5-258">Step B: Use the variable in the New-QuarantineTag command</span></span>

<span data-ttu-id="70fb5-259">사용 권한 개체를 만들어 변수에 저장한 후 다음 **New-QuarantineTag** 명령에서 _EndUserQuarantinePermission_ 매개 변수 값에 변수를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-259">After you've created and stored the permissions object in a variable, use the variable for the _EndUserQuarantinePermission_ parameter value in the following **New-QuarantineTag** command:</span></span>

```powershell
New-QuarantineTag -Name "<UniqueName>" -EndUserQuarantinePermissions $<VariableName>
```

<span data-ttu-id="70fb5-260">이 예에서는 이전 단계에서 설명하고 만든 permissions 개체를 사용하여 LimitedAccess라는 새 검지 정책을 `$LimitedAccess` 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-260">This example creates a new quarantine policy named LimitedAccess using the `$LimitedAccess` permissions object that was described and created in the previous step.</span></span>

```powershell
New-QuarantineTag -Name LimitedAccess -EndUserQuarantinePermissions $LimitedAccess
```

<span data-ttu-id="70fb5-261">구문과 매개 변수에 대한 자세한 내용은 [New-QuarantineTag 를 참조하십시오.](/powershell/module/exchange/new-quarantinetag)</span><span class="sxs-lookup"><span data-stu-id="70fb5-261">For detailed syntax and parameter information, see [New-QuarantineTag](/powershell/module/exchange/new-quarantinetag).</span></span>

## <a name="step-2-assign-a-quarantine-policy-to-supported-features"></a><span data-ttu-id="70fb5-262">2단계: 지원되는 기능에 검지 정책 할당</span><span class="sxs-lookup"><span data-stu-id="70fb5-262">Step 2: Assign a quarantine policy to supported features</span></span>

<span data-ttu-id="70fb5-263">메시지 _또는_ 파일을 자동으로 또는 구성 가능한 작업으로 검역하는 지원되는 보호 기능에서 사용 가능한 검역 작업에 검역 정책을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-263">In _supported_ protection features that quarantine messages or files (automatically or as a configurable action), you can assign a quarantine policy to the available quarantine actions.</span></span> <span data-ttu-id="70fb5-264">다음 표에는 메시지를 검사하는 기능과 검지 정책의 가용성이 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-264">Features that quarantine messages and the availability of quarantine policies are described in the following table:</span></span>

<br>

****

|<span data-ttu-id="70fb5-265">기능</span><span class="sxs-lookup"><span data-stu-id="70fb5-265">Feature</span></span>|<span data-ttu-id="70fb5-266">지원되는 정책은 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="70fb5-266">Quarantine policies supported?</span></span>|<span data-ttu-id="70fb5-267">사용되는 기본 검지 정책</span><span class="sxs-lookup"><span data-stu-id="70fb5-267">Default quarantine policies used</span></span>|
|---|:---:|---|
|<span data-ttu-id="70fb5-268">[스팸 방지 정책](configure-your-spam-filter-policies.md):</span><span class="sxs-lookup"><span data-stu-id="70fb5-268">[Anti-spam policies](configure-your-spam-filter-policies.md):</span></span> <ul><li><span data-ttu-id="70fb5-269">**Spam(** _SpamAction_)</span><span class="sxs-lookup"><span data-stu-id="70fb5-269">**Spam** (_SpamAction_)</span></span></li><li><span data-ttu-id="70fb5-270">**높은 지수 스팸(** _HighConfidenceSpamAction_)</span><span class="sxs-lookup"><span data-stu-id="70fb5-270">**High confidence spam** (_HighConfidenceSpamAction_)</span></span></li><li><span data-ttu-id="70fb5-271">**피싱(** _PhishSpamAction_)</span><span class="sxs-lookup"><span data-stu-id="70fb5-271">**Phishing** (_PhishSpamAction_)</span></span></li><li><span data-ttu-id="70fb5-272">**높은 신뢰도 피싱(** _HighConfidencePhishAction_)</span><span class="sxs-lookup"><span data-stu-id="70fb5-272">**High confidence phishing** (_HighConfidencePhishAction_)</span></span></li><li><span data-ttu-id="70fb5-273">**Bulk(** _BulkSpamAction_)</span><span class="sxs-lookup"><span data-stu-id="70fb5-273">**Bulk** (_BulkSpamAction_)</span></span></li></ul>|<span data-ttu-id="70fb5-274">예</span><span class="sxs-lookup"><span data-stu-id="70fb5-274">Yes</span></span>|<ul><li><span data-ttu-id="70fb5-275">DefaultSpamTag(모든 액세스)</span><span class="sxs-lookup"><span data-stu-id="70fb5-275">DefaultSpamTag (Full access)</span></span></li><li><span data-ttu-id="70fb5-276">DefaultHighConfSpamTag(모든 액세스)</span><span class="sxs-lookup"><span data-stu-id="70fb5-276">DefaultHighConfSpamTag (Full access)</span></span></li><li><span data-ttu-id="70fb5-277">DefaultPhishTag(모든 액세스)</span><span class="sxs-lookup"><span data-stu-id="70fb5-277">DefaultPhishTag (Full access)</span></span></li><li><span data-ttu-id="70fb5-278">DefaultHighConfPhishTag(액세스 없음)</span><span class="sxs-lookup"><span data-stu-id="70fb5-278">DefaultHighConfPhishTag (No access)</span></span></li><li><span data-ttu-id="70fb5-279">DefaultBulkTag(모든 액세스)</span><span class="sxs-lookup"><span data-stu-id="70fb5-279">DefaultBulkTag (Full access)</span></span></li></ul>
|<span data-ttu-id="70fb5-280">피싱 방지 정책:</span><span class="sxs-lookup"><span data-stu-id="70fb5-280">Anti-phishing policies:</span></span> <ul><li><span data-ttu-id="70fb5-281">[스푸핑 인텔리전스 보호(](set-up-anti-phishing-policies.md#spoof-settings) _AuthenticationFailAction_)</span><span class="sxs-lookup"><span data-stu-id="70fb5-281">[Spoof intelligence protection](set-up-anti-phishing-policies.md#spoof-settings) (_AuthenticationFailAction_)</span></span></li><li><span data-ttu-id="70fb5-282">[가장 보호](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365):<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="70fb5-282">[Impersonation protection](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365):<sup>\*</sup></span></span> <ul><li><span data-ttu-id="70fb5-283">**가장된** 사용자로 메시지가 검색된 경우(_TargetedUserProtectionAction_)</span><span class="sxs-lookup"><span data-stu-id="70fb5-283">**If message is detected as an impersonated user** (_TargetedUserProtectionAction_)</span></span></li><li><span data-ttu-id="70fb5-284">**가장된** 도메인으로 메시지가 검색된 경우(_TargetedDomainProtectionAction_)</span><span class="sxs-lookup"><span data-stu-id="70fb5-284">**If message is detected as an impersonated domain** (_TargetedDomainProtectionAction_)</span></span></li><li><span data-ttu-id="70fb5-285">**사서함 인텔리전스가** 사용자를 검색하고 가장하는 경우(_MailboxIntelligenceProtectionAction_)</span><span class="sxs-lookup"><span data-stu-id="70fb5-285">**If mailbox intelligence detects and impersonated user** (_MailboxIntelligenceProtectionAction_)</span></span></li></ul></li></ul></ul>|<span data-ttu-id="70fb5-286">아니요</span><span class="sxs-lookup"><span data-stu-id="70fb5-286">No</span></span>|<span data-ttu-id="70fb5-287">해당 없음</span><span class="sxs-lookup"><span data-stu-id="70fb5-287">n/a</span></span>|
|<span data-ttu-id="70fb5-288">[맬웨어 방지 정책:](configure-anti-malware-policies.md)검색된 모든 메시지는 항상 차단됩니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-288">[Anti-malware policies](configure-anti-malware-policies.md): All detected messages are always quarantined.</span></span>|<span data-ttu-id="70fb5-289">아니요</span><span class="sxs-lookup"><span data-stu-id="70fb5-289">No</span></span>|<span data-ttu-id="70fb5-290">해당 없음</span><span class="sxs-lookup"><span data-stu-id="70fb5-290">n/a</span></span>|
|[<span data-ttu-id="70fb5-291">SharePoint, OneDrive 및 Microsoft Teams용 안전한 첨부 파일</span><span class="sxs-lookup"><span data-stu-id="70fb5-291">Safe Attachments for SharePoint, OneDrive, and Microsoft Teams</span></span>](mdo-for-spo-odb-and-teams.md)|<span data-ttu-id="70fb5-292">아니요</span><span class="sxs-lookup"><span data-stu-id="70fb5-292">No</span></span>|<span data-ttu-id="70fb5-293">해당 없음</span><span class="sxs-lookup"><span data-stu-id="70fb5-293">n/a</span></span>|
|<span data-ttu-id="70fb5-294">[메일 흐름 규칙(전송](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) 규칙)에 다음  작업을 수행하여 메시지를 호스팅된 검사(_Quarantine)로 배달합니다._</span><span class="sxs-lookup"><span data-stu-id="70fb5-294">[Mail flow rules](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (also known as transport rules) with the action: **Deliver the message to the hosted quarantine** (_Quarantine_).</span></span>|<span data-ttu-id="70fb5-295">아니요</span><span class="sxs-lookup"><span data-stu-id="70fb5-295">No</span></span>|<span data-ttu-id="70fb5-296">해당 없음</span><span class="sxs-lookup"><span data-stu-id="70fb5-296">n/a</span></span>|
|

<span data-ttu-id="70fb5-297"><sup>\*</sup>가장 보호 설정은 Microsoft Defender에서 피싱 방지 정책에서만 사용할 수 Office 365.</span><span class="sxs-lookup"><span data-stu-id="70fb5-297"><sup>\*</sup> Impersonation protection settings are available only in anti-phishing policies in Microsoft Defender for Office 365.</span></span>

<span data-ttu-id="70fb5-298">기본 Quarantine 정책에서 제공하는 최종 사용자 권한에 만족하는 경우 아무 것도 할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-298">If you're happy with the end-user permissions that are provided by the default quarantine policies, you don't need to do anything.</span></span> <span data-ttu-id="70fb5-299">최종 사용자 스팸 알림 또는 검지된 메시지 세부 정보에서 최종 사용자 기능(사용 가능한 단추)을 사용자 지정하려는 경우 사용자 지정 검지 정책을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-299">If you want to customize the end-user capabilities (available buttons) in end-user spam notifications or in quarantined message details, you can assign a custom quarantine policy.</span></span>

### <a name="assign-quarantine-policies-in-anti-spam-policies-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="70fb5-300">스팸 방지 포털에서 스팸 방지 정책에 Microsoft 365 Defender 할당</span><span class="sxs-lookup"><span data-stu-id="70fb5-300">Assign quarantine policies in anti-spam policies in the Microsoft 365 Defender portal</span></span>

<span data-ttu-id="70fb5-301">스팸 방지 정책을 만들고 수정하기 위한 전체 지침은 [EOP에서 스팸 방지 정책 구성에 설명되어 있습니다.](configure-your-spam-filter-policies.md)</span><span class="sxs-lookup"><span data-stu-id="70fb5-301">Full instructions for creating and modifying anti-spam policies are described in [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

1. <span data-ttu-id="70fb5-302">Microsoft 365 Defender 포털에서 전자 메일 & **정책** & 규칙 정책 섹션 스팸 \>  \>  \> **방지로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="70fb5-302">In the Microsoft 365 Defender portal, go to **Email & collaboration** \> **Policies & rules** \> **Policies** section \> **Anti-spam**.</span></span> <span data-ttu-id="70fb5-303">또는 를 열 <https://security.microsoft.com/antispam> 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-303">Or, open <https://security.microsoft.com/antispam>.</span></span>

2. <span data-ttu-id="70fb5-304">스팸 **방지 정책 페이지에서** 다음 단계 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-304">On the **Anti-spam policies** page, do one of the following steps:</span></span>
   - <span data-ttu-id="70fb5-305">기존 인바운드 스팸 **방지** 정책을 찾아 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-305">Find and select an existing **inbound** anti-spam policy.</span></span>
   - <span data-ttu-id="70fb5-306">새 **인바운드 스팸** 방지 정책을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-306">Create a new **inbound** anti-spam policy.</span></span>

3. <span data-ttu-id="70fb5-307">다음 단계 중 하나를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-307">Do one of the following steps:</span></span>
   - <span data-ttu-id="70fb5-308">**기존 스팸 방지 정책** 편집: 정책 세부 정보 플라이아웃에서 작업 섹션으로 **이동한** 다음 작업 **편집을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="70fb5-308">**Edit existing anti-spam policy**: In the policy details flyout, go to the **Actions** section and then click **Edit actions**.</span></span>
   - <span data-ttu-id="70fb5-309">**새 스팸 방지 정책 만들기:** 새 정책 마법사에서 작업 **페이지로** 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-309">**Create new anti-spam policy**: In the new policy wizard, go to the **Actions** page.</span></span>

4. <span data-ttu-id="70fb5-310">작업 **페이지에서**</span><span class="sxs-lookup"><span data-stu-id="70fb5-310">On the **Actions** page.</span></span> <span data-ttu-id="70fb5-311">또한 **Quarantine message** action이 있는 모든 판결에는 해당하는 **Quarantine 정책을** 선택할 수 있는 선택 정책 상자도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-311">every verdict that has the **Quarantine message** action will also have the **Select quarantine policy** box for you to select a corresponding quarantine policy.</span></span>

   <span data-ttu-id="70fb5-312">**참고:** 새 정책을 만들 때 비어 있는 Select **quarantine policy value는** 해당 결과에 대한 기본 Quarantine 정책이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-312">**Note**: When you create a new policy, a blank **Select quarantine policy** value indicates the default quarantine policy for that verdict is used.</span></span> <span data-ttu-id="70fb5-313">나중에 정책을 편집하면 빈 값이 이전 표에 설명된 실제 기본 검지 정책 이름으로 대체됩니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-313">When you later edit the policy, the blank values are replaced by the actual default quarantine policy names as described in the previous table.</span></span>

   ![스팸 방지 정책에서 정책 선택을 차단합니다.](../../media/quarantine-tags-in-anti-spam-policies.png)

5. <span data-ttu-id="70fb5-315">작업을 마쳤으면 **저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-315">When you're finished, click **Save**.</span></span>

#### <a name="assign-quarantine-policies-in-anti-spam-policies-in-powershell"></a><span data-ttu-id="70fb5-316">PowerShell에서 스팸 방지 정책에 검지 정책 할당</span><span class="sxs-lookup"><span data-stu-id="70fb5-316">Assign quarantine policies in anti-spam policies in PowerShell</span></span>

<span data-ttu-id="70fb5-317">대신 PowerShell을 사용하여 스팸 방지 정책에서 스팸 방지 정책을 할당하는 경우 powerShell 또는 Exchange Online PowerShell에 Exchange Online Protection 다음 구문을 사용하십시오.</span><span class="sxs-lookup"><span data-stu-id="70fb5-317">If you'd rather use PowerShell to assign quarantine policies in anti-spam policies, connect to Exchange Online PowerShell or Exchange Online Protection PowerShell and use the following syntax:</span></span>

```powershell
<New-HostedContentFilterPolicy -Name "<Unique name>" | Set-HostedContentFilterPolicy -Identity "<Policy name>">  [-SpamAction Quarantine] [-SpamQuarantineTag <QuarantineTagName>] [-HighConfidenceSpamAction Quarantine] [-HighConfidenceSpamQuarantineTag <QuarantineTagName>] [-PhishSpamAction Quarantine] [-PhishQuarantineTag <QuarantineTagName>] [-HighConfidencePhishQuarantineTag <QuarantineTagName>] [-BulkSpamAction Quarantine] [-BulkQuarantineTag <QuarantineTagName>] ...
```

<span data-ttu-id="70fb5-318">**참고:**</span><span class="sxs-lookup"><span data-stu-id="70fb5-318">**Notes**:</span></span>

- <span data-ttu-id="70fb5-319">_HighConfidencePhishAction_ 매개 변수의 기본값은 Quarantine이기 때문에 새로운 스팸 방지 정책에서 높은 신뢰도의 피싱 검색에 대해 Quarantine 작업을 설정할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-319">The default value for the _HighConfidencePhishAction_ parameter is Quarantine, so you don't need to set the Quarantine action for high confidence phishing detections in new anti-spam policies.</span></span> <span data-ttu-id="70fb5-320">새 스팸 방지 정책 또는 기존 스팸 방지 정책의 다른 모든 스팸 필터링 판정에 대해, 작업 값이 Quarantine인 경우만 검지 정책이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-320">For all other spam filtering verdicts in new or existing anti-spam policies, the quarantine policy is only effective if the action value is Quarantine.</span></span> <span data-ttu-id="70fb5-321">기존 스팸 방지 정책의 작업 값을 표시하기 위해 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-321">To see the action values in existing anti-spam policies, run the following command:</span></span>

  ```powershell
  Get-HostedContentFilterPolicy | Format-Table Name,*SpamAction,HighConfidencePhishAction
  ```

  <span data-ttu-id="70fb5-322">Standard 및 Strict의 기본 작업 값 및 권장 작업 값에 대한 자세한 내용은 EOP 스팸 방지 정책 [설정 을 참조하세요.](recommended-settings-for-eop-and-office365.md#eop-anti-spam-policy-settings)</span><span class="sxs-lookup"><span data-stu-id="70fb5-322">For information about the default action values and the recommended action values for Standard and Strict, see [EOP anti-spam policy settings](recommended-settings-for-eop-and-office365.md#eop-anti-spam-policy-settings).</span></span>

- <span data-ttu-id="70fb5-323">해당하는 스팸 필터링 정책 매개 변수가 없는 스팸 [](#step-2-assign-a-quarantine-policy-to-supported-features) 필터링 판정은 해당 판정에 대한 기본 검지 정책이 사용되는 경우를 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-323">A spam filtering verdict without a corresponding quarantine policy parameter means the [default quarantine policy](#step-2-assign-a-quarantine-policy-to-supported-features) for that verdict is used.</span></span>

  <span data-ttu-id="70fb5-324">quarantined messages의 기본 최종 사용자 기능을 변경하려는 경우 기본 정책만 사용자 지정 검지 정책으로 바꾸면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-324">You only need to replace a default quarantine policy with a custom quarantine policy if you want to change the default end-user capabilities on quarantined messages.</span></span>

- <span data-ttu-id="70fb5-325">PowerShell의 새 스팸 방지 정책에는 **New-HostedContentFilterPolicy** cmdlet을 사용하는 스팸 필터 정책(설정)과 **New-HostedContentFilterRule** cmdlet을 사용하는 새 스팸 필터 규칙(받는 사람 필터)이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-325">A new anti-spam policy in PowerShell requires a spam filter policy (settings) using the **New-HostedContentFilterPolicy** cmdlet and a new spam filter rule (recipient filters) using the **New-HostedContentFilterRule** cmdlet.</span></span> <span data-ttu-id="70fb5-326">자세한 내용은 [PowerShell을 사용하여 스팸 방지 정책 만들기를 참조하세요.](configure-your-spam-filter-policies.md#use-powershell-to-create-anti-spam-policies)</span><span class="sxs-lookup"><span data-stu-id="70fb5-326">For instructions, see [Use PowerShell to create anti-spam policies](configure-your-spam-filter-policies.md#use-powershell-to-create-anti-spam-policies).</span></span>

<span data-ttu-id="70fb5-327">이 예에서는 다음 설정을 사용하여 Research Department라는 새 스팸 필터 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-327">This example creates a new spam filter policy named Research Department with the following settings:</span></span>

- <span data-ttu-id="70fb5-328">모든 스팸 필터링 판정에 대한 작업은 Quarantine으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-328">The action for all spam filtering verdicts is set to Quarantine.</span></span>
- <span data-ttu-id="70fb5-329">액세스 권한을 할당하지 않는 NoAccess라는  사용자 지정 검열 정책은 기본적으로 액세스 권한 없음을  할당하지 않은 모든 기본 검열 정책을 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-329">The custom quarantine policy named NoAccess that assigns **No access** permissions replaces any default quarantine policies that don't already assign **No access** permissions by default.</span></span>

```powershell
New-HostedContentFilterPolicy -Name Research Department -SpamAction Quarantine -SpamQuarantineTag NoAccess -HighConfidenceSpamAction Quarantine -HighConfidenceSpamQuarantineTag NoAction -PhishSpamAction Quarantine -PhishQuarantineTag NoAction -BulkSpamAction Quarantine -BulkQuarantineTag NoAccess
```

<span data-ttu-id="70fb5-330">자세한 구문 및 매개 변수 정보는 [New-HostedContentFilterPolicy](/powershell/module/exchange/new-hostedcontentfilterpolicy)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="70fb5-330">For detailed syntax and parameter information, see [New-HostedContentFilterPolicy](/powershell/module/exchange/new-hostedcontentfilterpolicy).</span></span>

<span data-ttu-id="70fb5-331">이 예에서는 Human Resources라는 기존 스팸 필터 정책을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-331">This example modifies the existing spam filter policy named Human Resources.</span></span> <span data-ttu-id="70fb5-332">스팸 차단 판정에 대한 작업은 Quarantine으로 설정되어 있으며 NoAccess라는 사용자 지정 검열 정책이 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-332">The action for the spam quarantine verdict is set to Quarantine, and the custom quarantine policy named NoAccess is assigned.</span></span>

```powershell
Set-HostedContentFilterPolicy -Identity "Human Resources" -SpamAction Quarantine -SpamQuarantineTag NoAccess
```

<span data-ttu-id="70fb5-333">자세한 구문 및 매개 변수 정보는 [Set-HostedContentFilterPolicy](/powershell/module/exchange/set-hostedcontentfilterpolicy)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="70fb5-333">For detailed syntax and parameter information, see [Set-HostedContentFilterPolicy](/powershell/module/exchange/set-hostedcontentfilterpolicy).</span></span>

## <a name="configure-global-quarantine-notification-settings-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="70fb5-334">사이트 포털에서 전역 Microsoft 365 Defender 설정 구성</span><span class="sxs-lookup"><span data-stu-id="70fb5-334">Configure global quarantine notification settings in the Microsoft 365 Defender portal</span></span>

<span data-ttu-id="70fb5-335">차단 정책에 대한 전역 설정을 사용하면 메시지를 받는 사람에게 전송되는 최종 사용자 스팸 알림을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-335">The global settings for quarantine policies allow you to customize the end-user spam notifications that are sent to recipients of messages that were quarantined.</span></span> <span data-ttu-id="70fb5-336">이러한 알림에 대한 자세한 내용은 최종 사용자 스팸 알림 [을 참조하세요.](use-spam-notifications-to-release-and-report-quarantined-messages.md)</span><span class="sxs-lookup"><span data-stu-id="70fb5-336">For more information about these notifications, see [End-user spam notifications](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span></span>

1. <span data-ttu-id="70fb5-337">Microsoft 365 Defender 포털에서 전자 메일 &  위협 정책 규칙 섹션으로 이동한 다음 정책 검지 \>  \>  \>  **를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="70fb5-337">In the Microsoft 365 Defender portal, go to **Email & collaboration** \>**Threat policies** \> **Rules** section \> **Quarantine policies** and then select **Quarantine policies**.</span></span>

2. <span data-ttu-id="70fb5-338">**Quarantine policy 페이지에서** 전역 설정을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="70fb5-338">On the **Quarantine policy** page, select **Global settings**.</span></span>

3. <span data-ttu-id="70fb5-339">열 수 있는 **Quarantine notification settings** flyout에서 다음 설정의 일부 또는 전체를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-339">In the **Quarantine notification settings** flyout that opens, configure some or all of the following settings:</span></span>

   - <span data-ttu-id="70fb5-340">**표시 이름:** 최종 사용자 스팸 알림에 사용되는 보낸 사람 표시 이름을 사용자 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-340">**Display name**: Customize the sender's display name that's used in end-user spam notifications.</span></span>

     <span data-ttu-id="70fb5-341">추가한 각 언어에 대해 두 번째 언어 상자에서 언어를 선택하고(X를 클릭하지 말고) 표시 이름 상자에 원하는 텍스트 값을 **입력합니다.**</span><span class="sxs-lookup"><span data-stu-id="70fb5-341">For each language that you've added, select the language in the second language box (don't click on the X) and enter the text value you want in the **Display name** box.</span></span>

     <span data-ttu-id="70fb5-342">다음 스크린샷은 최종 사용자 스팸 알림의 사용자 지정된 표시 이름을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-342">The following screenshot shows the customized display name in an end-user spam notification:</span></span>

     ![최종 사용자 스팸 알림의 사용자 지정된 보낸 사람 표시 이름](../../media/quarantine-tags-esn-customization-display-name.png)

   - <span data-ttu-id="70fb5-344">**고지 사항:** 최종 사용자 스팸 알림의 맨 아래에 사용자 지정 고지 사항 추가</span><span class="sxs-lookup"><span data-stu-id="70fb5-344">**Disclaimer**: Add a custom disclaimer to the bottom of end-user spam notifications.</span></span> <span data-ttu-id="70fb5-345">지역화된 텍스트인 조직의 고지 **사항:** 은 항상 먼저 포함되는 다음에 지정한 텍스트가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-345">The localized text, **A disclaimer from your organization:** is always included first, followed by the text you specify.</span></span>

     <span data-ttu-id="70fb5-346">추가한 각 언어에 대해 두 번째 언어 상자에서 언어를 선택하고(X를 클릭하지 말고) 고지지 상자에 원하는 텍스트 값을 **입력합니다.**</span><span class="sxs-lookup"><span data-stu-id="70fb5-346">For each language that you've added, select the language in the second language box  (don't click the X) and enter the text value you want in the **Disclaimer** box.</span></span>

     <span data-ttu-id="70fb5-347">다음 스크린샷은 최종 사용자 스팸 알림의 사용자 지정된 고지 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-347">The following screenshot shows the customized disclaimer in an end-user spam notification:</span></span>

     ![최종 사용자 스팸 알림의 맨 아래에 있는 사용자 지정 고지](../../media/quarantine-tags-esn-customization-disclaimer.png)

   - <span data-ttu-id="70fb5-349">**언어 선택:** 최종 사용자 스팸 알림은 받는 사람의 언어 설정에 따라 이미 지역화되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-349">**Choose language**: End-user spam notifications are already localized based on the recipient's language settings.</span></span> <span data-ttu-id="70fb5-350">표시 이름 및 고지지 값에 대해 사용자 지정된 텍스트를 다른 언어로 지정할 **수** 있습니다. </span><span class="sxs-lookup"><span data-stu-id="70fb5-350">You can specify customized text in different languages for the **Display name** and **Disclaimer** values.</span></span>

     <span data-ttu-id="70fb5-351">첫 번째 언어 상자에서 언어를 하나 이상 선택하고 추가를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="70fb5-351">Select at least one language from the first language box and then click **Add**.</span></span> <span data-ttu-id="70fb5-352">각 언어 다음에 추가를 클릭하여 여러 **언어를** 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-352">You can select multiple languages by clicking **Add** after each one.</span></span> <span data-ttu-id="70fb5-353">섹션 언어 상자에는 선택한 모든 언어가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-353">A section language box shows all of the languages that you've selected:</span></span>

     ![두 번째 언어 상자에 있는 선택된 언어에 대한 글로벌 검지 정책의 전역 알림 설정](../../media/quarantine-tags-esn-customization-selected-languages.png)

   - <span data-ttu-id="70fb5-355">**회사 로고 사용:** 최종 사용자 스팸 알림의 맨 위에 있는 기본 Microsoft 로고를 대체하려면 이 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-355">**Use my company logo**: Select this option to replace the default Microsoft logo that's use at the top of end-user spam notifications.</span></span> <span data-ttu-id="70fb5-356">이 작업을 수행하기 전에 조직에서 [](../../admin/setup/customize-your-organization-theme.md) 사용자 지정 로고를 업로드할 Microsoft 365 테마 사용자 지정의 지침을 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-356">Before you do this, you need to follow the instructions in [Customize the Microsoft 365 theme for your organization](../../admin/setup/customize-your-organization-theme.md) to upload your custom logo.</span></span>

     <span data-ttu-id="70fb5-357">다음 스크린샷은 최종 사용자 스팸 알림의 사용자 지정 로고를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-357">The following screenshot shows a custom logo in an end-user spam notification:</span></span>

     ![최종 사용자 스팸 알림의 사용자 지정 로고](../../media/quarantine-tags-esn-customization-logo.png)

## <a name="view-quarantine-policies-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="70fb5-359">사이트 포털에서 Microsoft 365 Defender 보기</span><span class="sxs-lookup"><span data-stu-id="70fb5-359">View quarantine policies in the Microsoft 365 Defender portal</span></span>

1. <span data-ttu-id="70fb5-360">Microsoft 365 Defender 포털에서 전자 메일 &  위협 정책 규칙 섹션으로 이동한 다음 정책 검지 \>  \>  \>  **를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="70fb5-360">In the Microsoft 365 Defender portal, go to **Email & collaboration** \>**Threat policies** \> **Rules** section \> **Quarantine policies** and then select **Quarantine policies**.</span></span>

2. <span data-ttu-id="70fb5-361">**Quarantine policy** page shows the list of policies by **Name** and **Last updated** date.</span><span class="sxs-lookup"><span data-stu-id="70fb5-361">The **Quarantine policy** page shows the list of policies by **Name** and **Last updated** date.</span></span>

3. <span data-ttu-id="70fb5-362">기본 제공 정책 또는 사용자 지정 검지 정책의 설정을 보려면 이름을 클릭하여 목록에서 검지 정책을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-362">To view the settings of built-in or custom quarantine policies, select the quarantine policy from the list by clicking on the name.</span></span>

4. <span data-ttu-id="70fb5-363">전역 설정을 보려면 전역 **설정을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="70fb5-363">To view the global settings, click **Global settings**</span></span>

### <a name="view-quarantine-policies-in-powershell"></a><span data-ttu-id="70fb5-364">PowerShell에서 Quarantine policies 보기</span><span class="sxs-lookup"><span data-stu-id="70fb5-364">View quarantine policies in PowerShell</span></span>

<span data-ttu-id="70fb5-365">PowerShell을 사용하여 정책을 보시고자 하는 경우 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-365">If you'd rather use PowerShell to view quarantine policies, do any of the following steps:</span></span>

- <span data-ttu-id="70fb5-366">모든 기본 제공 정책 또는 사용자 지정 정책의 요약 목록을 표시하기 위해 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-366">To view a summary list of all built-in or custom policies, run the following command:</span></span>

  ```powershell
  Get-QuarantineTag | Format-Table Name
  ```

- <span data-ttu-id="70fb5-367">기본 제공 또는 사용자 지정 검지 정책의 설정을 보시고, 정책의 이름으로 바꾸고 다음 명령을 \<QuarantinePolicyName\> 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-367">To view the settings of built-in or custom quarantine policies, replace \<QuarantinePolicyName\> with the name of the quarantine policy, and run the following command:</span></span>

  ```powershell
  Get-QuarantineTag -Identity "<QuarantinePolicyName>"
  ```

- <span data-ttu-id="70fb5-368">전역 설정을 보기 위해 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-368">To view the global settings, run the following command:</span></span>

  ```powershell
  Get-QuarantineTag -QuarantineTagType GlobalQuarantineTag
  ```

<span data-ttu-id="70fb5-369">자세한 구문 및 매개 변수 정보는 [Get-HostedContentFilterPolicy](/powershell/module/exchange/get-hostedcontentfilterpolicy)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="70fb5-369">For detailed syntax and parameter information, see [Get-HostedContentFilterPolicy](/powershell/module/exchange/get-hostedcontentfilterpolicy).</span></span>

## <a name="modify-quarantine-policies-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="70fb5-370">사이트 포털에서 Microsoft 365 Defender 수정</span><span class="sxs-lookup"><span data-stu-id="70fb5-370">Modify quarantine policies in the Microsoft 365 Defender portal</span></span>

1. <span data-ttu-id="70fb5-371">Microsoft 365 Defender 포털에서 전자 메일 &  위협 정책 규칙 섹션으로 이동한 다음 정책 검지 \>  \>  \>  **를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="70fb5-371">In the Microsoft 365 Defender portal, go to **Email & collaboration** \>**Threat policies** \> **Rules** section \> **Quarantine policies** and then select **Quarantine policies**.</span></span>

2. <span data-ttu-id="70fb5-372">**Quarantine policies 페이지에서** 이름을 클릭하여 정책을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-372">On the **Quarantine policies** page, select the policy by clicking on the name.</span></span>

3. <span data-ttu-id="70fb5-373">정책을 선택한 후 나타나는 정책 편집 아이콘 정책 편집 ![ ](../../media/m365-cc-sc-edit-icon.png)  아이콘을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-373">After you select the policy, click the ![Edit policy icon](../../media/m365-cc-sc-edit-icon.png) **Edit policy** icon that appears.</span></span>

4. <span data-ttu-id="70fb5-374">열리게 하는 정책 편집 마법사는  이 문서 앞부분의 Microsoft 365 Defender 포털에서 정책 만들기 섹션에 설명된 대로 새 정책 마법사와 거의 동일합니다.  [](#step-1-create-quarantine-policies-in-the-microsoft-365-defender-portal)</span><span class="sxs-lookup"><span data-stu-id="70fb5-374">The **Edit policy** wizard that opens is virtually identical to the **New policy** wizard as described in the [Create quarantine policies in the Microsoft 365 Defender portal](#step-1-create-quarantine-policies-in-the-microsoft-365-defender-portal) section earlier in this article.</span></span>

   <span data-ttu-id="70fb5-375">주요 차이점은 기존 정책의 이름을 변경하지 못하다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-375">The main difference is: you can't rename an existing policy.</span></span>

5. <span data-ttu-id="70fb5-376">정책 수정을 마치면 요약 페이지로 **이동하여** 제출을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="70fb5-376">When you're finished modifying the policy, go to the **Summary** page and click **Submit**.</span></span>

### <a name="modify-quarantine-policies-in-powershell"></a><span data-ttu-id="70fb5-377">PowerShell에서 검지 정책 수정</span><span class="sxs-lookup"><span data-stu-id="70fb5-377">Modify quarantine policies in PowerShell</span></span>

<span data-ttu-id="70fb5-378">PowerShell을 사용하여 사용자 지정 검단 정책을 수정하려면 을(를) 사용하여 검지 정책의 이름으로 바꾸고 다음 구문을 \<QuarantinePolicyName\> 사용하십시오.</span><span class="sxs-lookup"><span data-stu-id="70fb5-378">If you'd rather use PowerShell to modify a custom quarantine policy, replace \<QuarantinePolicyName\> with the name of the quarantine policy, and use the following syntax:</span></span>

```powershell
Set-QuarantineTag -Identity "<QuarantinePolicyName>" [Settings]
```

<span data-ttu-id="70fb5-379">사용 가능한 설정은 이 문서 앞부분에 있는 검지 정책을 만들기 위해 설명한 설정과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-379">The available settings are the same as described for creating quarantine policies earlier in this article.</span></span>

<span data-ttu-id="70fb5-380">구문과 매개 변수에 대한 자세한 내용은 [Set-QuarantineTag 를 참조하십시오.](/powershell/module/exchange/set-quarantinetag)</span><span class="sxs-lookup"><span data-stu-id="70fb5-380">For detailed syntax and parameter information, see [Set-QuarantineTag](/powershell/module/exchange/set-quarantinetag).</span></span>

## <a name="remove-quarantine-policies-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="70fb5-381">사이트 포털에서 Microsoft 365 Defender 제거</span><span class="sxs-lookup"><span data-stu-id="70fb5-381">Remove quarantine policies in the Microsoft 365 Defender portal</span></span>

<span data-ttu-id="70fb5-382">**참고:**</span><span class="sxs-lookup"><span data-stu-id="70fb5-382">**Notes**:</span></span>

- <span data-ttu-id="70fb5-383">기본 제공 분리 정책은 제거할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-383">You can't remove built-in quarantine policies.</span></span>
- <span data-ttu-id="70fb5-384">사용자 지정 분리 정책을 제거하기 전에 정책이 사용되지 않는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-384">Before you remove a custom quarantine policy, verify that it's not being used.</span></span> <span data-ttu-id="70fb5-385">예를 들어 PowerShell에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-385">For example, run the following command in PowerShell:</span></span>

  ```powershell
  Get-HostedContentFilterPolicy | Format-List Name,*QuarantineTag
  ```

  <span data-ttu-id="70fb5-386">정책을 사용 중이면 할당된 [](#step-2-assign-a-quarantine-policy-to-supported-features) 분리 정책을 제거하기 전에 바꾸어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-386">If the quarantine policy is being used, [replace the assigned quarantine policy](#step-2-assign-a-quarantine-policy-to-supported-features) before you remove it.</span></span>

1. <span data-ttu-id="70fb5-387">Microsoft 365 Defender 포털에서 전자 메일 &  위협 정책 규칙 섹션으로 이동한 다음 정책 검지 \>  \>  \>  **를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="70fb5-387">In the Microsoft 365 Defender portal, go to **Email & collaboration** \>**Threat policies** \> **Rules** section \> **Quarantine policies** and then select **Quarantine policies**.</span></span>

2. <span data-ttu-id="70fb5-388">**Quarantine policy 페이지에서** 이름을 클릭하여 제거할 사용자 지정 분리 정책을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-388">On the **Quarantine policy** page, select the custom quarantine policy that you want to remove by clicking on the name.</span></span>

3. <span data-ttu-id="70fb5-389">정책을 선택한 후 정책 삭제 아이콘 나타나는 정책 삭제 ![ ](../../media/m365-cc-sc-delete-icon.png)  아이콘을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-389">After you select the policy, click the ![Delete policy icon](../../media/m365-cc-sc-delete-icon.png) **Delete policy** icon that appears.</span></span>

4. <span data-ttu-id="70fb5-390">나타나는 **확인 대화** 상자에서 정책 제거를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-390">Click **Remove policy** in the confirmation dialog that appears.</span></span>

### <a name="remove-quarantine-policies-in-powershell"></a><span data-ttu-id="70fb5-391">PowerShell에서 분리 정책 제거</span><span class="sxs-lookup"><span data-stu-id="70fb5-391">Remove quarantine policies in PowerShell</span></span>

<span data-ttu-id="70fb5-392">PowerShell을 사용하여 사용자 지정 검지 정책을 제거하려면, 을(를) Quarantine policy의 이름으로 바꾸고 다음 명령을 \<QuarantinePolicyName\> 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-392">If you'd rather use PowerShell to remove a custom quarantine policy, replace \<QuarantinePolicyName\> with the name of the quarantine policy, and run the following command:</span></span>

```powershell
Remove-QuarantineTag -Identity "<QuarantinePolicyName>"
```

<span data-ttu-id="70fb5-393">구문과 매개 변수에 대한 자세한 내용은 [Remove-QuarantineTag 를 참조하십시오.](/powershell/module/exchange/remove-quarantinetag)</span><span class="sxs-lookup"><span data-stu-id="70fb5-393">For detailed syntax and parameter information, see [Remove-QuarantineTag](/powershell/module/exchange/remove-quarantinetag).</span></span>

## <a name="quarantine-policy-permission-details"></a><span data-ttu-id="70fb5-394">정책 사용 권한 세부 정보 검량</span><span class="sxs-lookup"><span data-stu-id="70fb5-394">Quarantine policy permission details</span></span>

<span data-ttu-id="70fb5-395">다음 섹션에서는 미리 설정한 사용 권한 그룹 및 개별 사용 권한의 영향에 대해 자세히 설명하고 최종 사용자 스팸 알림에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-395">The following sections describe the effects of preset permission groups and individual permissions in the details of quarantined messages and in end-user spam notifications.</span></span>

### <a name="preset-permissions-groups"></a><span data-ttu-id="70fb5-396">미리 설정 권한 그룹</span><span class="sxs-lookup"><span data-stu-id="70fb5-396">Preset permissions groups</span></span>

<span data-ttu-id="70fb5-397">미리 설정한 사용 권한 그룹에 포함된 개별 사용 권한은 이 문서의 시작부에 있는 표에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-397">The individual permissions that are included in preset permission groups are listed in the table at the beginning of this article.</span></span>

#### <a name="no-access"></a><span data-ttu-id="70fb5-398">권한 없음</span><span class="sxs-lookup"><span data-stu-id="70fb5-398">No access</span></span>

<span data-ttu-id="70fb5-399">검지 정책에 액세스 권한  없음(사용 권한 없음)을 할당하는 경우 사용자는 여전히 몇 가지 기준 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-399">If the quarantine policy assigns the **No access** permissions (no permissions), users still get some baseline capabilities:</span></span>

- <span data-ttu-id="70fb5-400">**Quarantined message details:** View **message header(메시지** 헤더 보기) 단추는 항상 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-400">**Quarantined message details**: The **View message header** button is always available.</span></span>

  ![사용자에게 액세스 권한이 없음을 제공하는 경우, 검지된 메시지 세부 정보에서 사용 가능한 단추](../../media/quarantine-tags-quarantined-message-details-no-access.png)

- <span data-ttu-id="70fb5-402">**최종 사용자 스팸 알림:** 사용자를 메시지로 전송하는 검토 단추는 항상 사용할 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="70fb5-402">**End-user spam notifications**: The **Review** button that takes the user to the message in quarantine is always available.</span></span>

  ![사용자에게 액세스 권한이 없음을 제공하는 경우 최종 사용자 스팸 알림의 사용 가능한 단추](../../media/quarantine-tags-esn-no-access.png)

#### <a name="limited-access"></a><span data-ttu-id="70fb5-404">제한된 액세스</span><span class="sxs-lookup"><span data-stu-id="70fb5-404">Limited access</span></span>

<span data-ttu-id="70fb5-405">정책을 통해 제한된 액세스 권한을  할당할 경우 사용자는 다음과 같은 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-405">If the quarantine policy assigns the **Limited access** permissions, users get the following capabilities:</span></span>

- <span data-ttu-id="70fb5-406">**Quarantined message details:** 다음 단추를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-406">**Quarantined message details**: The following buttons are available:</span></span>
  - <span data-ttu-id="70fb5-407">**릴리스 요청**</span><span class="sxs-lookup"><span data-stu-id="70fb5-407">**Request release**</span></span>
  - <span data-ttu-id="70fb5-408">**메시지 헤더 보기**</span><span class="sxs-lookup"><span data-stu-id="70fb5-408">**View message header**</span></span>
  - <span data-ttu-id="70fb5-409">**메시지 미리 보기**</span><span class="sxs-lookup"><span data-stu-id="70fb5-409">**Preview message**</span></span>
  - <span data-ttu-id="70fb5-410">**보낸 사람 차단**</span><span class="sxs-lookup"><span data-stu-id="70fb5-410">**Block sender**</span></span>
  - <span data-ttu-id="70fb5-411">**Quarantine에서 제거**</span><span class="sxs-lookup"><span data-stu-id="70fb5-411">**Remove from quarantine**</span></span>

  ![사용자에게 제한된 액세스 권한을 부여하는 경우, 검지된 메시지 세부 정보에서 사용 가능한 단추](../../media/quarantine-tags-quarantined-message-details-limited-access.png)

- <span data-ttu-id="70fb5-413">**최종 사용자 스팸 알림:** 다음 단추를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-413">**End-user spam notifications**: The following buttons are available:</span></span>
  - <span data-ttu-id="70fb5-414">**보낸 사람 차단**</span><span class="sxs-lookup"><span data-stu-id="70fb5-414">**Block sender**</span></span>
  - <span data-ttu-id="70fb5-415">**검토**</span><span class="sxs-lookup"><span data-stu-id="70fb5-415">**Review**</span></span>

  ![사용자에게 제한된 액세스 권한을 부여하는 경우 최종 사용자 스팸 알림의 사용 가능한 단추](../../media/quarantine-tags-esn-limited-access.png)

#### <a name="full-access"></a><span data-ttu-id="70fb5-417">모든 액세스</span><span class="sxs-lookup"><span data-stu-id="70fb5-417">Full access</span></span>

<span data-ttu-id="70fb5-418">정책을 통해 모든 액세스 권한(사용 가능한 모든 사용 권한)이 할당된 경우 사용자는 다음 기능을 사용할 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="70fb5-418">If the quarantine policy assigns the **Full access** permissions (all available permissions), users get the following capabilities:</span></span>

- <span data-ttu-id="70fb5-419">**Quarantined message details:** 다음 단추를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-419">**Quarantined message details**: The following buttons are available:</span></span>
  - <span data-ttu-id="70fb5-420">**릴리스 메시지**</span><span class="sxs-lookup"><span data-stu-id="70fb5-420">**Release message**</span></span>
  - <span data-ttu-id="70fb5-421">**메시지 헤더 보기**</span><span class="sxs-lookup"><span data-stu-id="70fb5-421">**View message header**</span></span>
  - <span data-ttu-id="70fb5-422">**메시지 미리 보기**</span><span class="sxs-lookup"><span data-stu-id="70fb5-422">**Preview message**</span></span>
  - <span data-ttu-id="70fb5-423">**보낸 사람 차단**</span><span class="sxs-lookup"><span data-stu-id="70fb5-423">**Block sender**</span></span>
  - <span data-ttu-id="70fb5-424">**보낸 사람 허용**</span><span class="sxs-lookup"><span data-stu-id="70fb5-424">**Allow sender**</span></span>
  - <span data-ttu-id="70fb5-425">**Quarantine에서 제거**</span><span class="sxs-lookup"><span data-stu-id="70fb5-425">**Remove from quarantine**</span></span>

  ![사용자에게 모든 액세스 권한이 부여된 경우, 검지된 메시지 세부 정보에서 사용 가능한 단추](../../media/quarantine-tags-quarantined-message-details-full-access.png)

- <span data-ttu-id="70fb5-427">**최종 사용자 스팸 알림:** 다음 단추를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-427">**End-user spam notifications**: The following buttons are available:</span></span>
  - <span data-ttu-id="70fb5-428">**보낸 사람 차단**</span><span class="sxs-lookup"><span data-stu-id="70fb5-428">**Block sender**</span></span>
  - <span data-ttu-id="70fb5-429">**릴리스**</span><span class="sxs-lookup"><span data-stu-id="70fb5-429">**Release**</span></span>
  - <span data-ttu-id="70fb5-430">**검토**</span><span class="sxs-lookup"><span data-stu-id="70fb5-430">**Review**</span></span>

  ![사용자에게 모든 액세스 권한을 부여하는 경우 최종 사용자 스팸 알림의 사용 가능한 단추](../../media/quarantine-tags-esn-full-access.png)

### <a name="individual-permissions"></a><span data-ttu-id="70fb5-432">개별 사용 권한</span><span class="sxs-lookup"><span data-stu-id="70fb5-432">Individual permissions</span></span>

> [!NOTE]
> <span data-ttu-id="70fb5-433">사용자는 액세스 금지 섹션에 설명된 단추를 항상 [얻게](#no-access) 됩니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-433">Remember, users always get the buttons described in the [No access](#no-access) section.</span></span> <span data-ttu-id="70fb5-434">이러한 단추는 개별 사용 권한 설명에 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-434">These buttons are not included in the individual permission descriptions.</span></span>

#### <a name="allow-sender-permission"></a><span data-ttu-id="70fb5-435">보낸 사람 권한 허용</span><span class="sxs-lookup"><span data-stu-id="70fb5-435">Allow sender permission</span></span>

<span data-ttu-id="70fb5-436">보낸 **사람 허용** 권한(_PermissionToAllowSender)은_ 사용자가 자신의 보낸 사람 목록에 quarantined message sender를 편리하게 추가할 수 있도록 단추에 대한 금고 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-436">The **Allow sender** permission (_PermissionToAllowSender_) controls access to the button that allows users to conveniently add the quarantined message sender to their Safe Senders list.</span></span>

- <span data-ttu-id="70fb5-437">**Quarantined message details**:</span><span class="sxs-lookup"><span data-stu-id="70fb5-437">**Quarantined message details**:</span></span>
  - <span data-ttu-id="70fb5-438">**보낸 사람 권한 허용** 사용: 보낸 **사람 허용** 단추를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-438">**Allow sender** permission enabled: The **Allow sender** button is available.</span></span>
  - <span data-ttu-id="70fb5-439">**보낸 사람 권한 허용** 사용 안 하도록 설정: 보낸 **사람 허용** 단추를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-439">**Allow sender** permission disabled: The **Allow sender** button is not available.</span></span>

- <span data-ttu-id="70fb5-440">**최종 사용자 스팸 알림:** 효과가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-440">**End-user spam notifications**: No effect.</span></span>

<span data-ttu-id="70fb5-441">보낸 사람 금고 대한 자세한 내용은 신뢰할 [](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379666) 수 있는 보낸 사람이 차단되지 않도록 방지 및 Exchange Online [PowerShell을](configure-junk-email-settings-on-exo-mailboxes.md#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox)사용하여 사서함에 수신 목록 모음 구성을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="70fb5-441">For more information about the Safe Senders list, see [Prevent trusted senders from being blocked](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379666) and [Use Exchange Online PowerShell to configure the safelist collection on a mailbox](configure-junk-email-settings-on-exo-mailboxes.md#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox).</span></span>

#### <a name="block-sender-permission"></a><span data-ttu-id="70fb5-442">보낸 사람 권한 차단</span><span class="sxs-lookup"><span data-stu-id="70fb5-442">Block sender permission</span></span>

<span data-ttu-id="70fb5-443">보낸 **사람 차단** 권한(_PermissionToBlockSender)은_ 사용자가 차단된 메시지 보낸 사람 목록에 편리하게 메시지 보낸 사람 목록을 추가할 수 있도록 단추에 대한 액세스를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-443">The **Block sender** permission (_PermissionToBlockSender_) controls access to the button that allows users to conveniently add the quarantined message sender to their Blocked Senders list.</span></span>

- <span data-ttu-id="70fb5-444">**Quarantined message details**:</span><span class="sxs-lookup"><span data-stu-id="70fb5-444">**Quarantined message details**:</span></span>
  - <span data-ttu-id="70fb5-445">**보낸 사람 권한 차단** 사용: 보낸 **사람 차단** 단추를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-445">**Block sender** permission enabled: The **Block sender** button is available.</span></span>
  - <span data-ttu-id="70fb5-446">**보낸 사람 사용** 권한 차단 사용 안 하세요: 보낸 **사람** 차단 단추를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-446">**Block sender** permission disabled: The **Block sender** button is not available.</span></span>

- <span data-ttu-id="70fb5-447">**최종 사용자 스팸 알림**:</span><span class="sxs-lookup"><span data-stu-id="70fb5-447">**End-user spam notifications**:</span></span>
  - <span data-ttu-id="70fb5-448">**보낸 사람 사용** 권한 차단 사용 안 하세요: 보낸 **사람** 차단 단추를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-448">**Block sender** permission disabled: The **Block sender** button is not available.</span></span>
  - <span data-ttu-id="70fb5-449">**보낸 사람 권한 차단** 사용: 보낸 **사람 차단** 단추를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-449">**Block sender** permission enabled: The **Block sender** button is available.</span></span>

<span data-ttu-id="70fb5-450">수신 차단된 보낸 사람 목록에 대한 자세한 내용은 [누군가의](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379667) 메시지 차단 및 Exchange Online [PowerShell을](configure-junk-email-settings-on-exo-mailboxes.md#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox)사용하여 사서함에 수신 목록 모음 구성을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="70fb5-450">For more information about the Blocked Senders list, see [Block messages from someone](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379667) and [Use Exchange Online PowerShell to configure the safelist collection on a mailbox](configure-junk-email-settings-on-exo-mailboxes.md#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox).</span></span>

#### <a name="delete-permission"></a><span data-ttu-id="70fb5-451">삭제 권한</span><span class="sxs-lookup"><span data-stu-id="70fb5-451">Delete permission</span></span>

<span data-ttu-id="70fb5-452">**Delete 권한(** _PermissionToDelete)은_ 사용자가 메시지(사용자가 받는 사람인 메시지)를 검사에서 삭제할 수 있는 기능을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-452">The **Delete** permission (_PermissionToDelete_) controls the ability to of users to delete their messages (messages where the user is a recipient) from quarantine.</span></span>

- <span data-ttu-id="70fb5-453">**Quarantined message details**:</span><span class="sxs-lookup"><span data-stu-id="70fb5-453">**Quarantined message details**:</span></span>
  - <span data-ttu-id="70fb5-454">**사용** 권한 삭제 사용: **분리에서** 제거 단추를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-454">**Delete** permission enabled: The **Remove from quarantine** button is available.</span></span>
  - <span data-ttu-id="70fb5-455">**사용** 권한 삭제 사용 안함: **분리에서** 제거 단추를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-455">**Delete** permission disabled: The **Remove from quarantine** button is not available.</span></span>

- <span data-ttu-id="70fb5-456">**최종 사용자 스팸 알림:** 효과가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-456">**End-user spam notifications**: No effect.</span></span>

#### <a name="preview-permission"></a><span data-ttu-id="70fb5-457">미리 보기 권한</span><span class="sxs-lookup"><span data-stu-id="70fb5-457">Preview permission</span></span>

<span data-ttu-id="70fb5-458">미리 **보기** 권한(_PermissionToPreview)은_ 사용자가 메시지를 미리 볼 수 있는 기능을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-458">The **Preview** permission (_PermissionToPreview_) controls the ability to of users to preview their messages in quarantine.</span></span>

- <span data-ttu-id="70fb5-459">**Quarantined message details**:</span><span class="sxs-lookup"><span data-stu-id="70fb5-459">**Quarantined message details**:</span></span>
  - <span data-ttu-id="70fb5-460">**미리** 보기 권한 사용: **미리 보기 메시지** 단추를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-460">**Preview** permission enabled: The **Preview message** button is available.</span></span>
  - <span data-ttu-id="70fb5-461">**미리** 보기 권한이 사용되지 않도록 설정: **미리 보기 메시지** 단추를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-461">**Preview** permission disabled: The **Preview message** button is not available.</span></span>

- <span data-ttu-id="70fb5-462">**최종 사용자 스팸 알림:** 효과가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-462">**End-user spam notifications**: No effect.</span></span>

#### <a name="allow-recipients-to-release-a-message-from-quarantine-permission"></a><span data-ttu-id="70fb5-463">받는 사람이 메시지를 검지 권한에서 해제하도록 허용</span><span class="sxs-lookup"><span data-stu-id="70fb5-463">Allow recipients to release a message from quarantine permission</span></span>

<span data-ttu-id="70fb5-464">받는 **사람이** 메시지를 검지 권한에서 해제할 수 있도록 허용(_PermissionToRelease)는_ 사용자가 관리자의 승인 없이 직접 또는 직접 메시지를 릴리스할 수 있는 기능을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-464">The **Allow recipients to release a message from quarantine** permission (_PermissionToRelease_) controls the ability of users to release their quarantined messages directly and without the approval of an admin.</span></span>

- <span data-ttu-id="70fb5-465">**Quarantined message details**:</span><span class="sxs-lookup"><span data-stu-id="70fb5-465">**Quarantined message details**:</span></span>
  - <span data-ttu-id="70fb5-466">사용 권한 사용: **메시지 해제** 단추를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-466">Permission enabled: The **Release message** button is available.</span></span>
  - <span data-ttu-id="70fb5-467">사용 권한 사용 안 하세요: **메시지 릴리스** 단추를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-467">Permission disabled: The **Release message** button is not available.</span></span>

- <span data-ttu-id="70fb5-468">**최종 사용자 스팸 알림**:</span><span class="sxs-lookup"><span data-stu-id="70fb5-468">**End-user spam notifications**:</span></span>
  - <span data-ttu-id="70fb5-469">사용 권한 사용: **릴리스 단추를** 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-469">Permission enabled: The **Release** button is available.</span></span>
  - <span data-ttu-id="70fb5-470">사용 권한 사용 안 하세요: **해제** 단추를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-470">Permission disabled: The **Release** button is not available.</span></span>

#### <a name="allow-recipients-to-request-a-message-to-be-released-from-quarantine-permission"></a><span data-ttu-id="70fb5-471">받는 사람이 메시지를 검사 권한에서 릴리스하도록 요청하도록 허용</span><span class="sxs-lookup"><span data-stu-id="70fb5-471">Allow recipients to request a message to be released from quarantine permission</span></span>

<span data-ttu-id="70fb5-472">받는 **사람이** 메시지를 검지 권한(PermissionToRequestRelease)에서 해제하도록 요청하도록 허용은 사용자가 자신의  검지된 메시지 릴리스를 요청할 수 있는 기능을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-472">The **Allow recipients to request a message to be released from quarantine** permission (_PermissionToRequestRelease_) controls the ability of users to _request_ the release of their quarantined messages.</span></span> <span data-ttu-id="70fb5-473">메시지는 관리자가 요청을 승인한 후에만 릴리스됩니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-473">The message is only released after an admin approves the request.</span></span>

- <span data-ttu-id="70fb5-474">**Quarantined message details**:</span><span class="sxs-lookup"><span data-stu-id="70fb5-474">**Quarantined message details**:</span></span>
  - <span data-ttu-id="70fb5-475">사용 권한 사용: **릴리스 요청 단추를** 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-475">Permission enabled: The **Request release** button is available.</span></span>
  - <span data-ttu-id="70fb5-476">사용 권한 사용 안 하게: 릴리스 **요청** 단추를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-476">Permission disabled: The **Request release** button is not available.</span></span>

- <span data-ttu-id="70fb5-477">**최종 사용자 스팸 알림:** 릴리스 **단추를** 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="70fb5-477">**End-user spam notifications**: The **Release** button is not available.</span></span>
