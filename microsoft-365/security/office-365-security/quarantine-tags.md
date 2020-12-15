---
title: 태그를 Quarantine tags
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: ''
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
ROBOTS: NOINDEX
description: 관리자는 사용자가 자신의 메일에 대해 할 수 있는 작업을 제어하기 위해 검지 태그를 사용하는 방법을 학습할 수 있습니다.
ms.openlocfilehash: 167f147d7c74b78b1a1661b5444625fbf1cf3d41
ms.sourcegitcommit: 29eb89b8ba0628fbef350e8995d2c38369a4ffa2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/15/2020
ms.locfileid: "49683070"
---
# <a name="quarantine-tags"></a><span data-ttu-id="fa2fa-103">태그를 Quarantine tags</span><span class="sxs-lookup"><span data-stu-id="fa2fa-103">Quarantine tags</span></span>

> [!NOTE]
> <span data-ttu-id="fa2fa-104">이 문서에서 설명하는 기능은 현재 미리 보기로 제공되어 있으며 모든 사람이 사용할 수 있으며 변경될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa2fa-104">The features that are described in this article are currently in Preview, aren't available to everyone, and are subject to change.</span></span>

<span data-ttu-id="fa2fa-105">EOP(Exchange Online Protection)에서 태그를 차단하면 관리자가 메시지가 메시지에 도착한 방법에 따라 사용자가 해당 메시지에 대해 할 수 있는 작업을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa2fa-105">Quarantine tags in Exchange Online Protection (EOP) allow admins to control what users are able to do to their quarantined messages based on how the message arrived in quarantine.</span></span>

<span data-ttu-id="fa2fa-106">EOP는 일반적으로 메시지에 대한 특정 수준의 대화형 [작업(Quarantine](find-and-release-quarantined-messages-as-a-user.md) 및 최종 사용자 스팸 알림)을 허용하거나 [차단했습니다.](use-spam-notifications-to-release-and-report-quarantined-messages.md)</span><span class="sxs-lookup"><span data-stu-id="fa2fa-106">EOP has traditionally allowed or prevented certain levels of interactivity for messages in [quarantine](find-and-release-quarantined-messages-as-a-user.md) and in [end-user spam notifications](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span></span> <span data-ttu-id="fa2fa-107">예를 들어 최종 사용자는 스팸 방지 필터링에 의해 스팸 또는 대량으로 검색된 메시지를 보고 해제할 수 있지만 높은 신뢰도 피싱으로 분류된 메시지를 보거나 해제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fa2fa-107">For example, end-users can view and release messages that were quarantined by anti-spam filtering as spam or bulk, but they can't view or release messages that were quarantined as high confidence phishing.</span></span>

<span data-ttu-id="fa2fa-108">[지원되는](#step-2-assign-a-quarantine-tag-to-supported-features)보호 기능의 경우, 태그는 최종 사용자 스팸 알림 메시지 및 사용자가 받는 사람인 메시지에 있는 자신의 스팸 알림 메시지에 대해 허용되는 작업을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="fa2fa-108">For [supported protection features](#step-2-assign-a-quarantine-tag-to-supported-features), quarantine tags specify what users are allowed to do in end-user spam notification messages and in their quarantined messages in quarantine (messages where the user is a recipient).</span></span> <span data-ttu-id="fa2fa-109">최종 사용자에게 전송된 메시지의 기록 기능을 적용하기 위해 기본 검역 태그가 자동으로 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="fa2fa-109">Default quarantine tags are automatically assigned to enforce the historical capabilities for end-users on quarantined messages.</span></span> <span data-ttu-id="fa2fa-110">또는 최종 사용자가 메일로 전송된 메시지에 대해 특정 작업을 수행할 수 있도록 허용하거나 금지하는 사용자 지정 차단 태그를 만들고 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa2fa-110">Or, you can create and assign custom quarantine tags to allow or prevent end-users from performing specific actions on quarantined messages.</span></span>

<span data-ttu-id="fa2fa-111">개별 사용 권한은 미리 설정한 다음 사용 권한 그룹에 결합됩니다.</span><span class="sxs-lookup"><span data-stu-id="fa2fa-111">The individual permissions are combined into the following preset permission groups:</span></span>

- <span data-ttu-id="fa2fa-112">권한 없음</span><span class="sxs-lookup"><span data-stu-id="fa2fa-112">No access</span></span>
- <span data-ttu-id="fa2fa-113">제한된 액세스</span><span class="sxs-lookup"><span data-stu-id="fa2fa-113">Limited access</span></span>
- <span data-ttu-id="fa2fa-114">모든 액세스</span><span class="sxs-lookup"><span data-stu-id="fa2fa-114">Full access</span></span>

<span data-ttu-id="fa2fa-115">사용 가능한 개별 사용 권한 및 미리 설정한 권한 그룹에 포함되거나 포함되지 않은 사용 권한에 대한 설명은 다음 표에 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa2fa-115">The available individual permissions and what's included or not included in the preset permission groups are described in the following table:</span></span>

|<span data-ttu-id="fa2fa-116">사용 권한</span><span class="sxs-lookup"><span data-stu-id="fa2fa-116">Permission</span></span>|<span data-ttu-id="fa2fa-117">권한 없음</span><span class="sxs-lookup"><span data-stu-id="fa2fa-117">No access</span></span>|<span data-ttu-id="fa2fa-118">제한된 액세스</span><span class="sxs-lookup"><span data-stu-id="fa2fa-118">Limited access</span></span>|<span data-ttu-id="fa2fa-119">모든 액세스</span><span class="sxs-lookup"><span data-stu-id="fa2fa-119">Full access</span></span>|
|---|:---:|:---:|:---:|
|<span data-ttu-id="fa2fa-120">**보낸 사람** _허용(PermissionToAllowSender)_</span><span class="sxs-lookup"><span data-stu-id="fa2fa-120">**Allow sender** (_PermissionToAllowSender_)</span></span>|||![확인 표시](../../media/checkmark.png)|
|<span data-ttu-id="fa2fa-122">**보낸 사람** _차단(PermissionToBlockSender)_</span><span class="sxs-lookup"><span data-stu-id="fa2fa-122">**Block sender** (_PermissionToBlockSender_)</span></span>||![확인 표시](../../media/checkmark.png)|![확인 표시](../../media/checkmark.png)|
|<span data-ttu-id="fa2fa-125">**Delete(** _PermissionToDelete)_</span><span class="sxs-lookup"><span data-stu-id="fa2fa-125">**Delete** (_PermissionToDelete_)</span></span>||![확인 표시](../../media/checkmark.png)|![확인 표시](../../media/checkmark.png)|
|<span data-ttu-id="fa2fa-128">**Preview(** _PermissionToPreview)_</span><span class="sxs-lookup"><span data-stu-id="fa2fa-128">**Preview** (_PermissionToPreview_)</span></span>||![확인 표시](../../media/checkmark.png)|![확인 표시](../../media/checkmark.png)|
|<span data-ttu-id="fa2fa-131">받는 사람이 메시지를 **해제할** 수 있도록 _허용(PermissionToRelease)_</span><span class="sxs-lookup"><span data-stu-id="fa2fa-131">**Allow recipients to release a message from quarantine** (_PermissionToRelease_)</span></span>|||![확인 표시](../../media/checkmark.png)|
|<span data-ttu-id="fa2fa-133">**받는 사람이** 메시지를 검지에서 릴리스하도록 요청하도록 _허용(PermissionToRequestRelease)_</span><span class="sxs-lookup"><span data-stu-id="fa2fa-133">**Allow recipients to request a message to be released from quarantine** (_PermissionToRequestRelease_)</span></span>||![확인 표시](../../media/checkmark.png)||
|

<span data-ttu-id="fa2fa-135">미리 설정한 사용 권한 그룹의 기본 사용 권한이 원하지 않는 경우 사용자 지정 검지 태그를 만들거나 수정할 때 사용자 지정 권한을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa2fa-135">If you don't like the default permissions in the preset permission groups, you can use custom permissions when you create or modify custom quarantine tags.</span></span> <span data-ttu-id="fa2fa-136">각 사용 권한의 작동에 대한 [](#quarantine-tag-permission-details) 자세한 내용은 이 문서 의 부분에 있는 태그 사용 권한 세부 정보 섹션을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="fa2fa-136">For more information about what each permission does, see the [Quarantine tag permission details](#quarantine-tag-permission-details) section later in this article.</span></span>

<span data-ttu-id="fa2fa-137">보안 & 준수 센터 또는 PowerShell(Exchange Online 사서함이 있는 Microsoft 365 조직용 Exchange Online PowerShell, Exchange Online 사서함이 없는 EOP 조직의 독립 실행형 EOP PowerShell)에서 검역 태그를 만들고 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="fa2fa-137">You create and assign quarantine tags in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with Exchange Online Mailboxes; standalone EOP PowerShell in EOP organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="fa2fa-138">시작하기 전에 알아야 할 내용은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="fa2fa-138">What do you need to know before you begin?</span></span>

- <span data-ttu-id="fa2fa-139"><https://protection.office.com/>에서 보안 및 준수 센터를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="fa2fa-139">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="fa2fa-140">**Quarantine 태그** 페이지로 직접 이동하기 위해 를 열고 <https://protection.office.com/quarantineTags> .</span><span class="sxs-lookup"><span data-stu-id="fa2fa-140">To go directly to the **Quarantine tags** page, open <https://protection.office.com/quarantineTags>.</span></span>

- <span data-ttu-id="fa2fa-141">Exchange Online PowerShell에 연결하려면 [Exchange Online PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fa2fa-141">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="fa2fa-142">독립 실행형 EOP PowerShell에 연결하려면 [Exchange Online Protection PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fa2fa-142">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="fa2fa-143">분리 태그를 보거나 만들거나 수정하거나 제거하려면 보안 및 준수 센터에서 조직  관리 [또는 보안 관리자 역할의 & 합니다.](permissions-in-the-security-and-compliance-center.md) </span><span class="sxs-lookup"><span data-stu-id="fa2fa-143">To view, create, modify, or remove quarantine tags, you need to be a member of the **Organization Management** or **Security Administrator** roles in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="step-1-create-quarantine-tags-in-the-security--compliance-center"></a><span data-ttu-id="fa2fa-144">1단계: 보안 및 준수 센터에서 & 태그 만들기</span><span class="sxs-lookup"><span data-stu-id="fa2fa-144">Step 1: Create quarantine tags in the Security & Compliance Center</span></span>

1. <span data-ttu-id="fa2fa-145">보안 & 준수 센터에서 **위협** 관리 정책으로 이동한 다음 태그를 \>  **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="fa2fa-145">In the Security & Compliance Center, go to **Threat management** \> **Policy** and then select **Quarantine tags**.</span></span>

2. <span data-ttu-id="fa2fa-146">**Quarantine tags(태그)** 페이지에서 사용자 지정 태그 **추가를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="fa2fa-146">On the **Quarantine tags** page, select **Add custom tag**.</span></span>

3. <span data-ttu-id="fa2fa-147">새 **태그 마법사가** 열립니다.</span><span class="sxs-lookup"><span data-stu-id="fa2fa-147">The **New tag** wizard opens.</span></span> <span data-ttu-id="fa2fa-148">태그 이름 **페이지에서** 태그 이름 필드에 간략하지만 고유한 **이름을 입력합니다.**</span><span class="sxs-lookup"><span data-stu-id="fa2fa-148">On the **Tag name** page, enter a brief but unique name in the **Tag name** field.</span></span> <span data-ttu-id="fa2fa-149">예정된 단계에서 이름으로 태그를 식별하고 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa2fa-149">You'll need to identify and select the tag by name in upcoming steps.</span></span> <span data-ttu-id="fa2fa-150">작업을 마친 후 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="fa2fa-150">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="fa2fa-151">받는 사람 **메시지 액세스 페이지에서** 다음 값 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fa2fa-151">On the **Recipient message access** page, select one of the following values:</span></span>
   - <span data-ttu-id="fa2fa-152">**액세스 금지**</span><span class="sxs-lookup"><span data-stu-id="fa2fa-152">**No access**</span></span>
   - <span data-ttu-id="fa2fa-153">**제한된 액세스**</span><span class="sxs-lookup"><span data-stu-id="fa2fa-153">**Limited access**</span></span>
   - <span data-ttu-id="fa2fa-154">**모든 액세스**</span><span class="sxs-lookup"><span data-stu-id="fa2fa-154">**Full access**</span></span>

   <span data-ttu-id="fa2fa-155">이러한 사용 권한 그룹에 포함된 개별 사용 권한에 대한 설명은 이 문서 앞부분에 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa2fa-155">The individual permissions that are included in these permission groups are described earlier in this article.</span></span>

   <span data-ttu-id="fa2fa-156">사용자 지정 권한을 지정하려면 특정 액세스 **설정(고급)을** 선택하고 다음 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="fa2fa-156">To specify custom permissions, select **Set specific access (Advanced)** and configure the following settings:</span></span>

     - <span data-ttu-id="fa2fa-157">**릴리스 작업 기본 설정 선택:** 다음 값 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fa2fa-157">**Select release action preference**: Select one of the following values:</span></span>
       - <span data-ttu-id="fa2fa-158">**릴리스 작업 없음**: 이 값이 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="fa2fa-158">**No release action**: This is the default value.</span></span>
       - <span data-ttu-id="fa2fa-159">**받는 사람이 메시지를 해제할 수 있도록 허용**</span><span class="sxs-lookup"><span data-stu-id="fa2fa-159">**Allow recipients to release a message from quarantine**</span></span>
       - <span data-ttu-id="fa2fa-160">**받는 사람이 메시지를 검지에서 릴리스하도록 요청하도록 허용**</span><span class="sxs-lookup"><span data-stu-id="fa2fa-160">**Allow recipients to request a message to be released from quarantine**</span></span>

     - <span data-ttu-id="fa2fa-161">**받는 사람이** 각기 다른 메시지에 대해 수행할 수 있는 추가 작업 선택: 다음 값을 일부 또는 모두 선택하거나 모두 선택하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fa2fa-161">**Select additional actions recipients can take on quarantined messages**: Select some, all, or none of the following values:</span></span>
       - <span data-ttu-id="fa2fa-162">**삭제**</span><span class="sxs-lookup"><span data-stu-id="fa2fa-162">**Delete**</span></span>
       - <span data-ttu-id="fa2fa-163">**미리 보기**</span><span class="sxs-lookup"><span data-stu-id="fa2fa-163">**Preview**</span></span>
       - <span data-ttu-id="fa2fa-164">**보낸 사람 허용**</span><span class="sxs-lookup"><span data-stu-id="fa2fa-164">**Allow sender**</span></span>
       - <span data-ttu-id="fa2fa-165">**보낸 사람 차단**</span><span class="sxs-lookup"><span data-stu-id="fa2fa-165">**Block sender**</span></span>

   <span data-ttu-id="fa2fa-166">이러한 사용 권한 및 이러한 사용 권한 및 최종 사용자 스팸 알림에 대한 [](#quarantine-tag-permission-details) 영향은 이 문서의 부분에 있는 태그 사용 권한 세부 정보 섹션에 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa2fa-166">These permissions and their effect on quarantined messages and in end-user spam notifications are described in the [Quarantine tag permission details](#quarantine-tag-permission-details) section later in this article.</span></span>

   <span data-ttu-id="fa2fa-167">작업을 마친 후 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="fa2fa-167">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="fa2fa-168">요약 **페이지가 나타나면** 설정을 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="fa2fa-168">On the **Summary** page that appears, review your settings.</span></span> <span data-ttu-id="fa2fa-169">각 **설정에서** 편집을 클릭하여 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa2fa-169">You can click **Edit** on each setting to modify it.</span></span>

   <span data-ttu-id="fa2fa-170">완료되면 제출을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="fa2fa-170">When you're finished, click **Submit**.</span></span>

6. <span data-ttu-id="fa2fa-171">나타나는  확인 페이지에서 완료를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="fa2fa-171">Click **Done** on the confirmation page that appears.</span></span>

<span data-ttu-id="fa2fa-172">이제 [2단계](#step-2-assign-a-quarantine-tag-to-supported-features) 섹션에 설명된 바와 같이, Quarantine 태그를 Quarantine 기능에 할당할 준비가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fa2fa-172">Now you are ready to assign the quarantine tag to a quarantine feature as described in the [Step 2](#step-2-assign-a-quarantine-tag-to-supported-features) section.</span></span>

### <a name="create-quarantine-tags-in-powershell"></a><span data-ttu-id="fa2fa-173">PowerShell에서 Quarantine 태그 만들기</span><span class="sxs-lookup"><span data-stu-id="fa2fa-173">Create quarantine tags in PowerShell</span></span>

<span data-ttu-id="fa2fa-174">PowerShell을 사용하여 검역 태그를 만드는 대신 Exchange Online PowerShell 또는 Exchange Online Protection PowerShell에 연결하고 **New-QuarantineTag** cmdlet을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="fa2fa-174">If you'd rather use PowerShell to create quarantine tags, connect to Exchange Online PowerShell or Exchange Online Protection PowerShell and use the **New-QuarantineTag** cmdlet.</span></span> <span data-ttu-id="fa2fa-175">다음 두 가지 방법으로 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa2fa-175">You have two different methods to choose from:</span></span>

- <span data-ttu-id="fa2fa-176">_EndUserQuarantinePermissionsValue_ 매개 변수를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="fa2fa-176">Use the _EndUserQuarantinePermissionsValue_ parameter.</span></span>
- <span data-ttu-id="fa2fa-177">_EndUserQuarantinePermissions 매개 변수를_ 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="fa2fa-177">Use the _EndUserQuarantinePermissions_ parameter.</span></span>

<span data-ttu-id="fa2fa-178">이러한 메서드에 대한 설명은 다음 섹션에 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa2fa-178">These methods are described in the following sections.</span></span>

#### <a name="use-the-enduserquarantinepermissionsvalue-parameter"></a><span data-ttu-id="fa2fa-179">EndUserQuarantinePermissionsValue 매개 변수 사용</span><span class="sxs-lookup"><span data-stu-id="fa2fa-179">Use the EndUserQuarantinePermissionsValue parameter</span></span>

<span data-ttu-id="fa2fa-180">_EndUserQuarantinePermissionsValue_ 매개 변수를 사용하여 Quarantine 태그를 만들 경우 다음 구문을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="fa2fa-180">To create a quarantine tag using the _EndUserQuarantinePermissionsValue_ parameter, use the following syntax:</span></span>

```powershell
New-QuarantineTag -Name "<UniqueName>" -EndUserQuarantinePermissionsValue <0 to 236>
```

<span data-ttu-id="fa2fa-181">_EndUserQuarantinePermissionsValue_ 매개 변수는 이진 값에서 변환된 10진수 값을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="fa2fa-181">The _EndUserQuarantinePermissionsValue_ parameter uses a decimal value that's converted from a binary value.</span></span> <span data-ttu-id="fa2fa-182">이진 값은 특정 순서로 사용 가능한 최종 사용자별 사용 권한에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="fa2fa-182">The binary value corresponds to the available end-user quarantine permissions in a specific order.</span></span> <span data-ttu-id="fa2fa-183">각 사용 권한에 대해 값 1은 True와 값 0은 False입니다.</span><span class="sxs-lookup"><span data-stu-id="fa2fa-183">For each permission, the value 1 equals True and the value 0 equals False.</span></span>

<span data-ttu-id="fa2fa-184">다음 표에서는 미리 설정한 사용 권한 그룹의 각 개별 권한에 대해 필요한 순서와 값을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="fa2fa-184">The required order and values for each individual permission in preset permission groups are described in the following table:</span></span>

****

|<span data-ttu-id="fa2fa-185">사용 권한</span><span class="sxs-lookup"><span data-stu-id="fa2fa-185">Permission</span></span>|<span data-ttu-id="fa2fa-186">권한 없음</span><span class="sxs-lookup"><span data-stu-id="fa2fa-186">No access</span></span>|<span data-ttu-id="fa2fa-187">제한된 액세스</span><span class="sxs-lookup"><span data-stu-id="fa2fa-187">Limited access</span></span>|<span data-ttu-id="fa2fa-188">모든 액세스</span><span class="sxs-lookup"><span data-stu-id="fa2fa-188">Full access</span></span>|
|---|:---:|:---:|:---:|
|<span data-ttu-id="fa2fa-189">PermissionToAllowSender</span><span class="sxs-lookup"><span data-stu-id="fa2fa-189">PermissionToAllowSender</span></span>|<span data-ttu-id="fa2fa-190">0</span><span class="sxs-lookup"><span data-stu-id="fa2fa-190">0</span></span>|<span data-ttu-id="fa2fa-191">0</span><span class="sxs-lookup"><span data-stu-id="fa2fa-191">0</span></span>|<span data-ttu-id="fa2fa-192">1 </span><span class="sxs-lookup"><span data-stu-id="fa2fa-192">1</span></span>|
|<span data-ttu-id="fa2fa-193">PermissionToBlockSender</span><span class="sxs-lookup"><span data-stu-id="fa2fa-193">PermissionToBlockSender</span></span>|<span data-ttu-id="fa2fa-194">0</span><span class="sxs-lookup"><span data-stu-id="fa2fa-194">0</span></span>|<span data-ttu-id="fa2fa-195">1 </span><span class="sxs-lookup"><span data-stu-id="fa2fa-195">1</span></span>|<span data-ttu-id="fa2fa-196">1 </span><span class="sxs-lookup"><span data-stu-id="fa2fa-196">1</span></span>|
|<span data-ttu-id="fa2fa-197">PermissionToDelete</span><span class="sxs-lookup"><span data-stu-id="fa2fa-197">PermissionToDelete</span></span>|<span data-ttu-id="fa2fa-198">0</span><span class="sxs-lookup"><span data-stu-id="fa2fa-198">0</span></span>|<span data-ttu-id="fa2fa-199">1 </span><span class="sxs-lookup"><span data-stu-id="fa2fa-199">1</span></span>|<span data-ttu-id="fa2fa-200">1 </span><span class="sxs-lookup"><span data-stu-id="fa2fa-200">1</span></span>|
|<span data-ttu-id="fa2fa-201">PermissionToDownload<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="fa2fa-201">PermissionToDownload<sup>\*</sup></span></span>|<span data-ttu-id="fa2fa-202">0</span><span class="sxs-lookup"><span data-stu-id="fa2fa-202">0</span></span>|<span data-ttu-id="fa2fa-203">0</span><span class="sxs-lookup"><span data-stu-id="fa2fa-203">0</span></span>|<span data-ttu-id="fa2fa-204">0</span><span class="sxs-lookup"><span data-stu-id="fa2fa-204">0</span></span>|
|<span data-ttu-id="fa2fa-205">PermissionToPreview</span><span class="sxs-lookup"><span data-stu-id="fa2fa-205">PermissionToPreview</span></span>|<span data-ttu-id="fa2fa-206">0</span><span class="sxs-lookup"><span data-stu-id="fa2fa-206">0</span></span>|<span data-ttu-id="fa2fa-207">1 </span><span class="sxs-lookup"><span data-stu-id="fa2fa-207">1</span></span>|<span data-ttu-id="fa2fa-208">1 </span><span class="sxs-lookup"><span data-stu-id="fa2fa-208">1</span></span>|
|<span data-ttu-id="fa2fa-209">PermissionToRelease<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="fa2fa-209">PermissionToRelease<sup>\*\*</sup></span></span>|<span data-ttu-id="fa2fa-210">0</span><span class="sxs-lookup"><span data-stu-id="fa2fa-210">0</span></span>|<span data-ttu-id="fa2fa-211">0</span><span class="sxs-lookup"><span data-stu-id="fa2fa-211">0</span></span>|<span data-ttu-id="fa2fa-212">1 </span><span class="sxs-lookup"><span data-stu-id="fa2fa-212">1</span></span>|
|<span data-ttu-id="fa2fa-213">PermissionToRequestRelease<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="fa2fa-213">PermissionToRequestRelease<sup>\*\*</sup></span></span>|<span data-ttu-id="fa2fa-214">0</span><span class="sxs-lookup"><span data-stu-id="fa2fa-214">0</span></span>|<span data-ttu-id="fa2fa-215">1 </span><span class="sxs-lookup"><span data-stu-id="fa2fa-215">1</span></span>|<span data-ttu-id="fa2fa-216">0</span><span class="sxs-lookup"><span data-stu-id="fa2fa-216">0</span></span>|
|<span data-ttu-id="fa2fa-217">PermissionToViewHeader<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="fa2fa-217">PermissionToViewHeader<sup>\*</sup></span></span>|<span data-ttu-id="fa2fa-218">0</span><span class="sxs-lookup"><span data-stu-id="fa2fa-218">0</span></span>|<span data-ttu-id="fa2fa-219">0</span><span class="sxs-lookup"><span data-stu-id="fa2fa-219">0</span></span>|<span data-ttu-id="fa2fa-220">0</span><span class="sxs-lookup"><span data-stu-id="fa2fa-220">0</span></span>|
|<span data-ttu-id="fa2fa-221">이진 값</span><span class="sxs-lookup"><span data-stu-id="fa2fa-221">Binary value</span></span>|<span data-ttu-id="fa2fa-222">00000000</span><span class="sxs-lookup"><span data-stu-id="fa2fa-222">00000000</span></span>|<span data-ttu-id="fa2fa-223">01101010</span><span class="sxs-lookup"><span data-stu-id="fa2fa-223">01101010</span></span>|<span data-ttu-id="fa2fa-224">11101100</span><span class="sxs-lookup"><span data-stu-id="fa2fa-224">11101100</span></span>|
|<span data-ttu-id="fa2fa-225">사용할 10진수 값</span><span class="sxs-lookup"><span data-stu-id="fa2fa-225">Decimal value to use</span></span>|<span data-ttu-id="fa2fa-226">0</span><span class="sxs-lookup"><span data-stu-id="fa2fa-226">0</span></span>|<span data-ttu-id="fa2fa-227">106</span><span class="sxs-lookup"><span data-stu-id="fa2fa-227">106</span></span>|<span data-ttu-id="fa2fa-228">236</span><span class="sxs-lookup"><span data-stu-id="fa2fa-228">236</span></span>|

<span data-ttu-id="fa2fa-229"><sup>\*</sup> 현재 이 값은 항상 0입니다.</span><span class="sxs-lookup"><span data-stu-id="fa2fa-229"><sup>\*</sup> Currently, this value is always 0.</span></span> <span data-ttu-id="fa2fa-230">PermissionToViewHeader의 경우 값 0은 해당  메시지의 세부 정보에서 메시지 헤더 보기 단추를 숨기지 않습니다(단추는 항상 사용 가능).</span><span class="sxs-lookup"><span data-stu-id="fa2fa-230">For PermissionToViewHeader, the value 0 doesn't hide the **View message header** button in the details of the quarantined message (the button is always available).</span></span>

<span data-ttu-id="fa2fa-231"><sup>\*\*</sup> 이 두 값을 모두 1로 설정하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fa2fa-231"><sup>\*\*</sup> Don't set both of these values to 1.</span></span> <span data-ttu-id="fa2fa-232">1을 1로 설정하고 다른 하나는 0으로 설정하거나 둘 다 0으로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa2fa-232">Set one to 1 and the other to 0, or set both to 0.</span></span>

<span data-ttu-id="fa2fa-233">이 예제에서는 이전 표에 설명된 액세스 권한 없음 권한을 할당하는 새 Quarantine tag name NoAccess를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="fa2fa-233">This example creates a new quarantine tag name NoAccess that assigns the No access permissions as described in the previous table.</span></span>

```powershell
New-QuarantineTag -Name NoAccess -EndUserQuarantinePermissionsValue 0
```

<span data-ttu-id="fa2fa-234">제한된 액세스 권한의 경우 값 106을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa2fa-234">For Limited access permissions, use the value 106.</span></span> <span data-ttu-id="fa2fa-235">모든 액세스 권한의 경우 값 236을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa2fa-235">For Full access permissions, use the value 236.</span></span>

<span data-ttu-id="fa2fa-236">사용자 지정 권한의 경우 앞의 표를 사용하여 원하는 사용 권한에 해당하는 이진 값을 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="fa2fa-236">For custom permissions, use the previous table to get the binary value that corresponds to the permissions you want.</span></span> <span data-ttu-id="fa2fa-237">이진 값을 10진수 값으로 변환하고 _EndUserQuarantinePermissionsValue_ 매개 변수에 10진수 값을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="fa2fa-237">Convert the binary value to a decimal value and use the decimal value for the _EndUserQuarantinePermissionsValue_ parameter.</span></span>

<span data-ttu-id="fa2fa-238">구문과 매개 변수에 대한 자세한 내용은 [New-QuarantineTag를 참조하십시오.](https://docs.microsoft.com/powershell/module/exchange/new-quarantinetag)</span><span class="sxs-lookup"><span data-stu-id="fa2fa-238">For detailed syntax and parameter information, see [New-QuarantineTag](https://docs.microsoft.com/powershell/module/exchange/new-quarantinetag).</span></span>

#### <a name="use-the-enduserquarantinepermissions-parameter"></a><span data-ttu-id="fa2fa-239">EndUserQuarantinePermissions 매개 변수 사용</span><span class="sxs-lookup"><span data-stu-id="fa2fa-239">Use the EndUserQuarantinePermissions parameter</span></span>

<span data-ttu-id="fa2fa-240">_EndUserQuarantinePermissionsValue_ 매개 변수를 사용하여 Quarantine 태그를 만들 경우 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="fa2fa-240">To create a quarantine tag using the _EndUserQuarantinePermissionsValue_ parameter, do the following steps:</span></span>

<span data-ttu-id="fa2fa-241">대답.</span><span class="sxs-lookup"><span data-stu-id="fa2fa-241">A.</span></span> <span data-ttu-id="fa2fa-242">**New-QuarantinePermissions** cmdlet을 사용하여 변수에 Quarantine permissions 개체를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="fa2fa-242">Store a quarantine permissions object in a variable using the **New-QuarantinePermissions** cmdlet.</span></span>

<p>

<span data-ttu-id="fa2fa-243">B.</span><span class="sxs-lookup"><span data-stu-id="fa2fa-243">B.</span></span> <span data-ttu-id="fa2fa-244">**변수를 New-QuarantineTag** 명령에서 _EndUserQuarantinePermissions_ 값으로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa2fa-244">Use the variable as the _EndUserQuarantinePermissions_ value in the **New-QuarantineTag** command.</span></span>

##### <a name="step-a-store-a-quarantine-permissions-object-in-a-variable"></a><span data-ttu-id="fa2fa-245">단계 A: 변수에 Quarantine permissions 개체 저장</span><span class="sxs-lookup"><span data-stu-id="fa2fa-245">Step A: Store a quarantine permissions object in a variable</span></span>

<span data-ttu-id="fa2fa-246">다음 구문을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="fa2fa-246">Use the following syntax:</span></span>

```powershell
$<VariableName> = New-QuarantinePermissions [-PermissionToAllowSender <$true | $False>] [-PermissionToBlockSender <$true | $False>] [-PermissionToDelete <$true | $False>] [-PermissionToPreview <$true | $False>] [-PermissionToRelease <$true | $False>] [-PermissionToRequestRelease <$true | $False>]
```

<span data-ttu-id="fa2fa-247">사용되지 않는 매개 변수의 기본값은 을(를) 설정하려는 매개 변수만 사용할 수 있도록 하는 `$false` `$true` 것입니다.</span><span class="sxs-lookup"><span data-stu-id="fa2fa-247">The default value for any unused parameters is `$false`, so you only need to use the parameters where you want to set value to `$true`.</span></span>

<span data-ttu-id="fa2fa-248">다음 예에서는 미리 설정한 사용 권한 그룹에 해당하는 사용 권한 개체를 만드는 방법을 보여 주며,</span><span class="sxs-lookup"><span data-stu-id="fa2fa-248">The following examples show how to create permission objects that correspond to the preset permissions groups:</span></span>

- <span data-ttu-id="fa2fa-249">**액세스 권한이 없습니다.**</span><span class="sxs-lookup"><span data-stu-id="fa2fa-249">**No access**:</span></span>

  ```powershell
  $NoAccess = New-QuarantinePermissions
  ```

- <span data-ttu-id="fa2fa-250">**제한된 액세스:**</span><span class="sxs-lookup"><span data-stu-id="fa2fa-250">**Limited access**:</span></span>

  ```powershell
  $LimitedAccess = New-QuarantinePermissions -PermissionToBlockSender $true -PermissionToDelete $true -PermissionToPreview $true -PermissionToRequestRelease $true
  ```

- <span data-ttu-id="fa2fa-251">**모든 액세스:**</span><span class="sxs-lookup"><span data-stu-id="fa2fa-251">**Full access**:</span></span>

  ```powershell
  $FullAccess = New-QuarantinePermissions -PermissionToAllowSender $true -PermissionToBlockSender $true -PermissionToDelete $true -PermissionToPreview $true -PermissionToRelease $true
  ```

<span data-ttu-id="fa2fa-252">설정한 값을 표시하기 위해 변수 이름을 명령으로 실행합니다(예: 명령을 실행). `$NoAccess`</span><span class="sxs-lookup"><span data-stu-id="fa2fa-252">To see the values that you've set, run the variable name as a command (for example, run the command `$NoAccess`).</span></span>

<span data-ttu-id="fa2fa-253">사용자 지정 권한의 경우 _PermissionToRelease_ 매개 변수와 _PermissionToRequestRelease_ 매개 변수를 모두 으로 설정하지 `$true` 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fa2fa-253">For custom permissions, don't set both the _PermissionToRelease_ and _PermissionToRequestRelease_ parameters to `$true`.</span></span> <span data-ttu-id="fa2fa-254">하나를 다른 설정으로 설정하고 그대로 두거나 둘 다 `$true` `$false` 으로 떠날 수 `$false` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa2fa-254">Set one to `$true` and leave the other as `$false`, or leave both as `$false`.</span></span>

<span data-ttu-id="fa2fa-255">또한 만든 후 **Set-QuarantinePermissions** cmdlet을 사용하여 기존 사용 권한 개체 변수를 사용하기 전에 수정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa2fa-255">You can also modify an existing permissions object variable after you create but before you use it by using the **Set-QuarantinePermissions** cmdlet.</span></span>

<span data-ttu-id="fa2fa-256">구문과 매개 변수에 대한 자세한 내용은 [New-QuarantinePermissions](https://docs.microsoft.com/powershell/module/exchange/new-quarantinepermissions) 및 [Set-QuarantinePermissions를 참조하십시오.](https://docs.microsoft.com/powershell/module/exchange/set-quarantinepermissions)</span><span class="sxs-lookup"><span data-stu-id="fa2fa-256">For detailed syntax and parameter information, see [New-QuarantinePermissions](https://docs.microsoft.com/powershell/module/exchange/new-quarantinepermissions) and [Set-QuarantinePermissions](https://docs.microsoft.com/powershell/module/exchange/set-quarantinepermissions).</span></span>

##### <a name="step-b-use-the-variable-in-the-new-quarantinetag-command"></a><span data-ttu-id="fa2fa-257">B단계: 명령줄에서 변수 New-QuarantineTag 사용</span><span class="sxs-lookup"><span data-stu-id="fa2fa-257">Step B: Use the variable in the New-QuarantineTag command</span></span>

<span data-ttu-id="fa2fa-258">사용 권한 개체를 만들어 변수에 저장한 후 다음 **New-QuarantineTag** 명령에서 _EndUserQuarantinePermission_ 매개 변수 값에 대한 변수를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="fa2fa-258">After you've created and stored the permissions object in a variable, use the variable for the _EndUserQuarantinePermission_ parameter value in the following **New-QuarantineTag** command:</span></span>

```powershell
New-QuarantineTag -Name "<UniqueName>" -EndUserQuarantinePermissions $<VariableName>
```

<span data-ttu-id="fa2fa-259">이 예제에서는 이전 단계에서 설명하고 만든 사용 권한 개체를 사용하여 LimitedAccess라는 새 Quarantine `$LimitedAccess` 태그를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="fa2fa-259">This example creates a new quarantine tag named LimitedAccess using the `$LimitedAccess` permissions object that was described and created in the previous step.</span></span>

```powershell
New-QuarantineTag -Name LimitedAccess -EndUserQuarantinePermissions $LimitedAccess
```

<span data-ttu-id="fa2fa-260">구문과 매개 변수에 대한 자세한 내용은 [New-QuarantineTag를 참조하십시오.](https://docs.microsoft.com/powershell/module/exchange/new-quarantinetag)</span><span class="sxs-lookup"><span data-stu-id="fa2fa-260">For detailed syntax and parameter information, see [New-QuarantineTag](https://docs.microsoft.com/powershell/module/exchange/new-quarantinetag).</span></span>

## <a name="step-2-assign-a-quarantine-tag-to-supported-features"></a><span data-ttu-id="fa2fa-261">2단계: 지원되는 기능에 대해 Quarantine 태그 할당</span><span class="sxs-lookup"><span data-stu-id="fa2fa-261">Step 2: Assign a quarantine tag to supported features</span></span>

<span data-ttu-id="fa2fa-262">메시지 _또는_ 파일을 자동으로 또는 구성 가능한 작업으로 차단하는 지원되는 보호 기능에서 사용 가능한 검역 작업에 검역 태그를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa2fa-262">In _supported_ protection features that quarantine messages or files (automatically or as a configurable action), you can assign a quarantine tag to the available quarantine actions.</span></span> <span data-ttu-id="fa2fa-263">다음 표에서는 메시지를 검색하고 태그를 사용할 수 있는 기능에 대한 설명을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="fa2fa-263">Features that quarantine messages and the availability of quarantine tags are described in the following table:</span></span>

****

|<span data-ttu-id="fa2fa-264">기능</span><span class="sxs-lookup"><span data-stu-id="fa2fa-264">Feature</span></span>|<span data-ttu-id="fa2fa-265">태그를 Quarantine tags supported?</span><span class="sxs-lookup"><span data-stu-id="fa2fa-265">Quarantine tags supported?</span></span>|<span data-ttu-id="fa2fa-266">사용되는 기본 Quarantine 태그</span><span class="sxs-lookup"><span data-stu-id="fa2fa-266">Default quarantine tags used</span></span>|
|---|:---:|---|
|<span data-ttu-id="fa2fa-267">[스팸 방지 정책](configure-your-spam-filter-policies.md):</span><span class="sxs-lookup"><span data-stu-id="fa2fa-267">[Anti-spam policies](configure-your-spam-filter-policies.md):</span></span> <ul><li><span data-ttu-id="fa2fa-268">**스팸(** _SpamAction)_</span><span class="sxs-lookup"><span data-stu-id="fa2fa-268">**Spam** (_SpamAction_)</span></span></li><li><span data-ttu-id="fa2fa-269">**높은 지수 스팸(** _HighConfidenceSpamAction)_</span><span class="sxs-lookup"><span data-stu-id="fa2fa-269">**High confidence spam** (_HighConfidenceSpamAction_)</span></span></li><li><span data-ttu-id="fa2fa-270">**피싱 전자** _메일(PhishSpamAction)_</span><span class="sxs-lookup"><span data-stu-id="fa2fa-270">**Phishing email** (_PhishSpamAction_)</span></span></li><li><span data-ttu-id="fa2fa-271">**높은 신뢰도 피싱 전자** _메일(HighConfidencePhishAction)_</span><span class="sxs-lookup"><span data-stu-id="fa2fa-271">**High confidence phishing email** (_HighConfidencePhishAction_)</span></span></li><li><span data-ttu-id="fa2fa-272">**대량 전자 메일(** _BulkSpamAction)_</span><span class="sxs-lookup"><span data-stu-id="fa2fa-272">**Bulk email** (_BulkSpamAction_)</span></span></li></ul>|<span data-ttu-id="fa2fa-273">예</span><span class="sxs-lookup"><span data-stu-id="fa2fa-273">Yes</span></span>|<ul><li><span data-ttu-id="fa2fa-274">DefaultSpamTag(모든 액세스)</span><span class="sxs-lookup"><span data-stu-id="fa2fa-274">DefaultSpamTag (Full access)</span></span></li><li><span data-ttu-id="fa2fa-275">DefaultHighConfSpamTag(모든 액세스)</span><span class="sxs-lookup"><span data-stu-id="fa2fa-275">DefaultHighConfSpamTag (Full access)</span></span></li><li><span data-ttu-id="fa2fa-276">DefaultPhishTag(모든 액세스)</span><span class="sxs-lookup"><span data-stu-id="fa2fa-276">DefaultPhishTag (Full access)</span></span></li><li><span data-ttu-id="fa2fa-277">DefaultHighConfPhishTag(액세스 없음)</span><span class="sxs-lookup"><span data-stu-id="fa2fa-277">DefaultHighConfPhishTag (No access)</span></span></li><li><span data-ttu-id="fa2fa-278">DefaultBulkTag(모든 액세스)</span><span class="sxs-lookup"><span data-stu-id="fa2fa-278">DefaultBulkTag (Full access)</span></span></li></ul>
|<span data-ttu-id="fa2fa-279">피싱 방지 정책:</span><span class="sxs-lookup"><span data-stu-id="fa2fa-279">Anti-phishing policies:</span></span> <ul><li><span data-ttu-id="fa2fa-280">[스푸핑 인텔리전스](set-up-anti-phishing-policies.md#spoof-settings) _보호(AuthenticationFailAction)_</span><span class="sxs-lookup"><span data-stu-id="fa2fa-280">[Spoof intelligence protection](set-up-anti-phishing-policies.md#spoof-settings) (_AuthenticationFailAction_)</span></span></li><li><span data-ttu-id="fa2fa-281">[가장 보호:](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="fa2fa-281">[Impersonation protection](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365):<sup>\*</sup></span></span> <ul><li><span data-ttu-id="fa2fa-282">**가장된** 사용자가 전자 메일을 보낸 _경우(TargetedUserProtectionAction)_</span><span class="sxs-lookup"><span data-stu-id="fa2fa-282">**If email is sent by an impersonated user** (_TargetedUserProtectionAction_)</span></span></li><li><span data-ttu-id="fa2fa-283">**가장된** 도메인에서 전자 메일을 보낸 _경우(TargetedDomainProtectionAction)_</span><span class="sxs-lookup"><span data-stu-id="fa2fa-283">**If email is sent by an impersonated domain** (_TargetedDomainProtectionAction_)</span></span></li><li><span data-ttu-id="fa2fa-284">**사서함 인텔리전스** \> **가장된** 사용자가 전자 메일을 보낸 _경우(MailboxIntelligenceProtectionAction)_</span><span class="sxs-lookup"><span data-stu-id="fa2fa-284">**Mailbox intelligence** \> **If email is sent by an impersonated user** (_MailboxIntelligenceProtectionAction_)</span></span></li></ul></li></ul></ul>|<span data-ttu-id="fa2fa-285">아니요</span><span class="sxs-lookup"><span data-stu-id="fa2fa-285">No</span></span>|<span data-ttu-id="fa2fa-286">해당 없음</span><span class="sxs-lookup"><span data-stu-id="fa2fa-286">n/a</span></span>|
|<span data-ttu-id="fa2fa-287">[맬웨어 방지 정책:](configure-anti-malware-policies.md)검색된 모든 메시지는 항상 차단됩니다.</span><span class="sxs-lookup"><span data-stu-id="fa2fa-287">[Anti-malware policies](configure-anti-malware-policies.md): All detected messages are always quarantined.</span></span>|<span data-ttu-id="fa2fa-288">아니요</span><span class="sxs-lookup"><span data-stu-id="fa2fa-288">No</span></span>|<span data-ttu-id="fa2fa-289">해당 없음</span><span class="sxs-lookup"><span data-stu-id="fa2fa-289">n/a</span></span>|
|[<span data-ttu-id="fa2fa-290">SharePoint, OneDrive 및 Microsoft Teams에 대한 ATP</span><span class="sxs-lookup"><span data-stu-id="fa2fa-290">ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>](atp-for-spo-odb-and-teams.md)|<span data-ttu-id="fa2fa-291">아니요</span><span class="sxs-lookup"><span data-stu-id="fa2fa-291">No</span></span>|<span data-ttu-id="fa2fa-292">해당 없음</span><span class="sxs-lookup"><span data-stu-id="fa2fa-292">n/a</span></span>|
|<span data-ttu-id="fa2fa-293">[다음 작업을 사용하여](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) 메일 흐름 규칙(전송 규칙라고도 합니다.)  호스트된 검단(Quarantine)으로 메시지를 _배달합니다._</span><span class="sxs-lookup"><span data-stu-id="fa2fa-293">[Mail flow rules](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (also known as transport rules) with the action: **Deliver the message to the hosted quarantine** (_Quarantine_).</span></span>|<span data-ttu-id="fa2fa-294">아니요</span><span class="sxs-lookup"><span data-stu-id="fa2fa-294">No</span></span>|<span data-ttu-id="fa2fa-295">해당 없음</span><span class="sxs-lookup"><span data-stu-id="fa2fa-295">n/a</span></span>|
|

<span data-ttu-id="fa2fa-296"><sup>\*</sup> 가장 보호 설정은 Office 365용 Microsoft Defender의 피싱 방지 정책에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa2fa-296"><sup>\*</sup> Impersonation protection settings are available only in anti-phishing policies in Microsoft Defender for Office 365.</span></span>

<span data-ttu-id="fa2fa-297">기본 Quarantine 태그에서 제공하는 최종 사용자 권한이 만족스러우면 아무 것도 할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fa2fa-297">If you're happy with the end-user permissions that are provided by the default quarantine tags, you don't need to do anything.</span></span> <span data-ttu-id="fa2fa-298">최종 사용자 스팸 알림 또는 메시지 세부 정보에서 최종 사용자 기능(사용 가능한 단추)을 사용자 지정하려는 경우 사용자 지정 차단 태그를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa2fa-298">If you want to customize the end-user capabilities (available buttons) in end-user spam notifications or in quarantined message details, you can assign a custom quarantine tag.</span></span>

### <a name="assign-quarantine-tags-in-anti-spam-policies-in-the-security--compliance-center"></a><span data-ttu-id="fa2fa-299">보안 및 준수 센터에서 스팸 방지 정책에 & 태그 할당</span><span class="sxs-lookup"><span data-stu-id="fa2fa-299">Assign quarantine tags in anti-spam policies in the Security & Compliance Center</span></span>

<span data-ttu-id="fa2fa-300">스팸 방지 정책을 만들고 수정하기 위한 전체 지침은 EOP에서 스팸 방지 정책 [구성에 설명되어 있습니다.](configure-your-spam-filter-policies.md)</span><span class="sxs-lookup"><span data-stu-id="fa2fa-300">Full instructions for creating and modifying anti-spam policies are described in [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

1. <span data-ttu-id="fa2fa-301">보안 & 준수 센터에서 **위협** 관리 정책으로 이동한 다음 스팸 \>  \> **방지를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="fa2fa-301">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> and then select **Anti-spam**.</span></span> <span data-ttu-id="fa2fa-302">또는 를 열 수 <https://protection.office.com/antispam> 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa2fa-302">Or, open <https://protection.office.com/antispam>.</span></span>

2. <span data-ttu-id="fa2fa-303">편집할 기존 스팸 방지 정책을 찾아 선택하거나 새 스팸 방지 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa2fa-303">Find and select an existing anti-spam policy to edit, or create a new anti-spam policy.</span></span>

3. <span data-ttu-id="fa2fa-304">정책 세부 정보 플라이아웃에서 스팸 및 대량 **작업 섹션을 확장합니다.**</span><span class="sxs-lookup"><span data-stu-id="fa2fa-304">In the policy details flyout, expand the **Spam and bulk actions** section.</span></span>

4. <span data-ttu-id="fa2fa-305">사용 가능한 스팸 필터링 판정의 동작에 대해 **Quarantine** 메시지를 선택한 경우 해당 판정에 대한 **Quarantine** 태그를 선택할 수 있도록 차단 정책 태그 적용 상자를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa2fa-305">If you've selected **Quarantine message** for the action of an available spam filtering verdict, the **Apply quarantine policy tag** box is available for you to select the quarantine tag for that verdict.</span></span>

   <span data-ttu-id="fa2fa-306">**참고:** 새 정책을 만들 때 스팸 필터링 결과에 대한 빈 Quarantine 태그 값은 해당 결과에 대한 기본 Quarantine 태그가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fa2fa-306">**Note**: When you create a new policy, a blank quarantine tag value for a spam filtering verdict indicates the default quarantine tag for that verdict is used.</span></span> <span data-ttu-id="fa2fa-307">나중에 정책을 편집하면 공백 값이 이전 표에 설명된 실제 기본 Quarantine 태그 이름으로 대체됩니다.</span><span class="sxs-lookup"><span data-stu-id="fa2fa-307">When you later edit the policy, the blank values are replaced by the actual default quarantine tag names as described in the previous table.</span></span>

   ![스팸 방지 정책에서 태그 선택을 차단](../../media/quarantine-tags-in-anti-spam-policies.png)

5. <span data-ttu-id="fa2fa-309">작업을 마쳤으면 **저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="fa2fa-309">When you're finished, click **Save**.</span></span>

#### <a name="assign-quarantine-tags-in-anti-spam-policies-in-powershell"></a><span data-ttu-id="fa2fa-310">PowerShell에서 스팸 방지 정책에서 스팸 방지 태그 할당</span><span class="sxs-lookup"><span data-stu-id="fa2fa-310">Assign quarantine tags in anti-spam policies in PowerShell</span></span>

<span data-ttu-id="fa2fa-311">PowerShell을 사용하여 스팸 방지 정책에서 스팸 방지 태그를 할당하는 대신 Exchange Online PowerShell 또는 Exchange Online Protection PowerShell에 연결하고 다음 구문을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="fa2fa-311">If you'd rather use PowerShell to assign quarantine tags in anti-spam policies, connect to Exchange Online PowerShell or Exchange Online Protection PowerShell and use the following syntax:</span></span>

```powershell
<New-HostedContentFilterPolicy -Name "<Unique name>" | Set-HostedContentFilterPolicy -Identity "<Policy name>">  [-SpamAction Quarantine] [-SpamQuarantineTag <QuarantineTagName>] [-HighConfidenceSpamAction Quarantine] [-HighConfidenceSpamQuarantineTag <QuarantineTagName>] [-PhishSpamAction Quarantine] [-PhishQuarantineTag <QuarantineTagName>] [-HighConfidencePhishQuarantineTag <QuarantineTagName>] [-BulkSpamAction Quarantine] [-BulkQuarantineTag <QuarantineTagName>] ...
```

<span data-ttu-id="fa2fa-312">**참고:**</span><span class="sxs-lookup"><span data-stu-id="fa2fa-312">**Notes**:</span></span>

- <span data-ttu-id="fa2fa-313">_HighConfidencePhishAction_ 매개 변수의 기본값은 Quarantine이기 때문에 새로운 스팸 방지 정책에서 높은 신뢰도의 피싱 검색에 대해 Quarantine 작업을 설정할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fa2fa-313">The default value for the _HighConfidencePhishAction_ parameter is Quarantine, so you don't need to set the Quarantine action for high confidence phishing detections in new anti-spam policies.</span></span> <span data-ttu-id="fa2fa-314">새 스팸 방지 정책 또는 기존 스팸 방지 정책의 다른 모든 스팸 필터링 판정에 대해, 작업 값이 Quarantine인 경우만 스팸 필터링 태그가 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fa2fa-314">For all other spam filtering verdicts in new or existing anti-spam policies, the quarantine tag is only effective if the action value is Quarantine.</span></span> <span data-ttu-id="fa2fa-315">기존 스팸 방지 정책의 작업 값을 표시하기 위해 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="fa2fa-315">To see the action values in existing anti-spam policies, run the following command:</span></span>

  ```powershell
  Get-HostedContentFilterPolicy | Format-Table Name,*SpamAction,HighConfidencePhishAction
  ```

  <span data-ttu-id="fa2fa-316">Standard 및 Strict의 기본 작업 값 및 권장 작업 값에 대한 자세한 내용은 EOP 스팸 방지 정책 설정을 [참조하십시오.](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings)</span><span class="sxs-lookup"><span data-stu-id="fa2fa-316">For information about the default action values and the recommended action values for Standard and Strict, see [EOP anti-spam policy settings](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings).</span></span>

- <span data-ttu-id="fa2fa-317">해당하는 Quarantine 태그 매개 변수가 없는 스팸 필터링 판정은 해당 판정에 대한 기본 [Quarantine 태그가](#step-2-assign-a-quarantine-tag-to-supported-features) 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fa2fa-317">A spam filtering verdict without a corresponding quarantine tag parameter means the [default quarantine tag](#step-2-assign-a-quarantine-tag-to-supported-features) for that verdict is used.</span></span>

  <span data-ttu-id="fa2fa-318">메일로 전송된 메시지에 대한 기본 최종 사용자 기능을 변경하려는 경우 기본 Quarantine 태그를 사용자 지정 Quarantine 태그로 바꾸기만하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fa2fa-318">You only need to replace a default quarantine tag with a custom quarantine tag if you want to change the default end-user capabilities on quarantined messages.</span></span>

- <span data-ttu-id="fa2fa-319">PowerShell의 새 스팸 방지 정책에는 **New-HostedContentFilterPolicy** cmdlet을 사용하는 스팸 필터 정책(설정)과 **New-HostedContentFilterRule** cmdlet을 사용하는 새 스팸 필터 규칙(받는 사람 필터)이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="fa2fa-319">A new anti-spam policy in PowerShell requires a spam filter policy (settings) using the **New-HostedContentFilterPolicy** cmdlet and a new spam filter rule (recipient filters) using the **New-HostedContentFilterRule** cmdlet.</span></span> <span data-ttu-id="fa2fa-320">자세한 내용은 [PowerShell을 사용하여 스팸 방지](configure-your-spam-filter-policies.md#use-powershell-to-create-anti-spam-policies)정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa2fa-320">For instructions, see [Use PowerShell to create anti-spam policies](configure-your-spam-filter-policies.md#use-powershell-to-create-anti-spam-policies).</span></span>

<span data-ttu-id="fa2fa-321">이 예에서는 다음 설정을 사용하여 Research Department라는 새 스팸 필터 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="fa2fa-321">This example creates a new spam filter policy named Research Department with the following settings:</span></span>

- <span data-ttu-id="fa2fa-322">모든 스팸 필터링 판정에 대한 작업은 Quarantine으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="fa2fa-322">The action for all spam filtering verdicts is set to Quarantine.</span></span>
- <span data-ttu-id="fa2fa-323">액세스 권한 없음을 할당하는 NoAccess라는  사용자 지정 Quarantine 태그는 기본적으로 액세스 권한 없음을 할당하지 않은 모든 기본 Quarantine 태그를 대체합니다. </span><span class="sxs-lookup"><span data-stu-id="fa2fa-323">The custom quarantine tag named NoAccess that assigns **No access** permissions replaces any default quarantine tags that don't already assign **No access** permissions by default.</span></span>

```powershell
New-HostedContentFilterPolicy -Name Research Department -SpamAction Quarantine -SpamQuarantineTag NoAccess -HighConfidenceSpamAction Quarantine -HighConfidenceSpamQuarantineTag NoAction -PhishSpamAction Quarantine -PhishQuarantineTag NoAction -BulkSpamAction Quarantine -BulkQuarantineTag NoAccess
```

<span data-ttu-id="fa2fa-324">자세한 구문 및 매개 변수 정보는 [New-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/new-hostedcontentfilterpolicy)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fa2fa-324">For detailed syntax and parameter information, see [New-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/new-hostedcontentfilterpolicy).</span></span>

<span data-ttu-id="fa2fa-325">이 예에서는 Human Resources라는 기존 스팸 필터 정책을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="fa2fa-325">This example modifies the existing spam filter policy named Human Resources.</span></span> <span data-ttu-id="fa2fa-326">스팸 차단 판정에 대한 작업은 Quarantine으로 설정되어 있으며 NoAccess라는 사용자 지정 Quarantine 태그가 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="fa2fa-326">The action for the spam quarantine verdict is set to Quarantine, and the custom quarantine tag named NoAccess is assigned.</span></span>

```powershell
Set-HostedContentFilterPolicy -Identity "Human Resources" -SpamAction Quarantine -SpamQuarantineTag NoAccess
```

<span data-ttu-id="fa2fa-327">자세한 구문 및 매개 변수 정보는 [Set-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-hostedcontentfilterpolicy)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fa2fa-327">For detailed syntax and parameter information, see [Set-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-hostedcontentfilterpolicy).</span></span>

## <a name="configure-global-quarantine-notification-settings-in-the-security--compliance-center"></a><span data-ttu-id="fa2fa-328">보안 및 준수 센터에서 전역 & 설정 구성</span><span class="sxs-lookup"><span data-stu-id="fa2fa-328">Configure global quarantine notification settings in the Security & Compliance Center</span></span>

<span data-ttu-id="fa2fa-329">각 태그에 대한 전역 설정을 사용하면 메시지를 받는 사람에게 전송되는 최종 사용자 스팸 알림을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa2fa-329">The global settings for quarantine tags allow you to customize the end-user spam notifications that are sent to recipients of messages that were quarantined.</span></span> <span data-ttu-id="fa2fa-330">이러한 알림에 대한 자세한 내용은 최종 사용자 스팸 알림을 [참조하세요.](use-spam-notifications-to-release-and-report-quarantined-messages.md)</span><span class="sxs-lookup"><span data-stu-id="fa2fa-330">For more information about these notifications, see [End-user spam notifications](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span></span>

1. <span data-ttu-id="fa2fa-331">보안 & 준수 센터에서 **위협** 관리 정책으로 이동한 다음 태그를 \>  **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="fa2fa-331">In the Security & Compliance Center, go to **Threat management** \> **Policy** and then select **Quarantine tags**.</span></span>

2. <span data-ttu-id="fa2fa-332">**Quarantine tags(태그) 페이지에서** 전역 **설정을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="fa2fa-332">On the **Quarantine tags** page, select **Global settings**.</span></span>

3. <span data-ttu-id="fa2fa-333">열 **수 있는 Quarantine notification settings** flyout, configure some or all of the following settings:</span><span class="sxs-lookup"><span data-stu-id="fa2fa-333">In the **Quarantine notification settings** flyout that opens, configure some or all of the following settings:</span></span>

   - <span data-ttu-id="fa2fa-334">**회사 로고 사용:** 최종 사용자 스팸 알림의 맨 위에 있는 기본 Microsoft 로고를 대체하려면 이 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fa2fa-334">**Use my company logo**: Select this option to replace the default Microsoft logo that's use at the top of end-user spam notifications.</span></span> <span data-ttu-id="fa2fa-335">이렇게 하기 전에 조직에서 사용자 지정 로고를 업로드할 수 있도록 [Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/setup/customize-your-organization-theme) 테마 사용자 지정의 지침을 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa2fa-335">Before you do this, you need to follow the instructions in [Customize the Microsoft 365 theme for your organization](https://docs.microsoft.com/microsoft-365/admin/setup/customize-your-organization-theme) to upload your custom logo.</span></span>

     <span data-ttu-id="fa2fa-336">다음 스크린샷은 최종 사용자 스팸 알림의 사용자 지정 로고를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="fa2fa-336">The following screenshot shows a custom logo in an end-user spam notification:</span></span>

     ![최종 사용자 스팸 알림의 사용자 지정 로고](../../media/quarantine-tags-esn-customization-logo.png)

   - <span data-ttu-id="fa2fa-338">**언어 선택:** 최종 사용자 스팸 알림이 받는 사람의 언어 설정에 따라 이미 지역화되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa2fa-338">**Choose language**: End-user spam notifications are already localized based on the recipient's language settings.</span></span> <span data-ttu-id="fa2fa-339">표시 이름 및 고지지 값에 대해 사용자 지정된 텍스트를 다른 언어로 **지정할 수** 있습니다. </span><span class="sxs-lookup"><span data-stu-id="fa2fa-339">You can specify customized text in different languages for the **Display name** and **Disclaimer** values.</span></span>

     <span data-ttu-id="fa2fa-340">첫 번째 언어 상자에서 언어를 하나 이상 선택하고 추가를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="fa2fa-340">Select at least one language from the first language box and then click **Add**.</span></span> <span data-ttu-id="fa2fa-341">각 언어 다음에 추가를 클릭하여 여러 **언어를** 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa2fa-341">You can select multiple languages by clicking **Add** after each one.</span></span> <span data-ttu-id="fa2fa-342">섹션 언어 상자에는 선택한 모든 언어가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="fa2fa-342">A section language box shows all of the languages that you've selected:</span></span>

     ![두 번째 언어 상자에 있는 선택된 언어에 대해 태그를 전 세계에 대해 전 세계에 대해 알림 설정](../../media/quarantine-tags-esn-customization-selected-languages.png)

   - <span data-ttu-id="fa2fa-344">**표시 이름:** 최종 사용자 스팸 알림에 사용되는 보낸 사람 표시 이름을 사용자 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="fa2fa-344">**Display name**: Customize the sender's display name that's used in end-user spam notifications.</span></span>

     <span data-ttu-id="fa2fa-345">추가한 각 언어에 대해 두 번째 언어 상자에서 언어를 선택하고(X를 클릭하지 않습니다) 표시 이름 상자에 원하는 텍스트 값을 **입력합니다.**</span><span class="sxs-lookup"><span data-stu-id="fa2fa-345">For each language that you've added, select the language in the second language box (don't click on the X) and enter the text value you want in the **Display name** box.</span></span>

     <span data-ttu-id="fa2fa-346">다음 스크린샷은 최종 사용자 스팸 알림의 사용자 지정된 표시 이름을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="fa2fa-346">The following screenshot shows the customized display name in an end-user spam notification:</span></span>

     ![최종 사용자 스팸 알림의 사용자 지정된 보낸 사람 표시 이름](../../media/quarantine-tags-esn-customization-display-name.png)

   - <span data-ttu-id="fa2fa-348">**고지 사항:** 최종 사용자 스팸 알림의 맨 아래에 사용자 지정 고지 사항 추가</span><span class="sxs-lookup"><span data-stu-id="fa2fa-348">**Disclaimer**: Add a custom disclaimer to the bottom of end-user spam notifications.</span></span> <span data-ttu-id="fa2fa-349">지역화된 텍스트인 조직의 고지 **사항:은** 항상 먼저 포함되는 다음에 지정한 텍스트가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="fa2fa-349">The localized text, **A disclaimer from your organization:** is always included first, followed by the text you specify.</span></span>

     <span data-ttu-id="fa2fa-350">추가한 각 언어에 대해 두 번째 언어 상자에서 언어를 선택하고(X를 클릭하지 않습니다) 고지침 상자에 원하는 텍스트 값을 **입력합니다.**</span><span class="sxs-lookup"><span data-stu-id="fa2fa-350">For each language that you've added, select the language in the second language box  (don't click the X) and enter the text value you want in the **Disclaimer** box.</span></span>

     <span data-ttu-id="fa2fa-351">다음 스크린샷은 최종 사용자 스팸 알림의 사용자 지정 고지 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="fa2fa-351">The following screenshot shows the customized disclaimer in an end-user spam notification:</span></span>

     ![최종 사용자 스팸 알림의 맨 아래에 있는 사용자 지정 고지](../../media/quarantine-tags-esn-customization-disclaimer.png)

## <a name="view-quarantine-tags-in-the-security--compliance-center"></a><span data-ttu-id="fa2fa-353">보안 및 준수 센터에서 & 태그 보기</span><span class="sxs-lookup"><span data-stu-id="fa2fa-353">View quarantine tags in the Security & Compliance Center</span></span>

1. <span data-ttu-id="fa2fa-354">보안 & 준수 센터에서 **위협** 관리 정책으로 이동한 다음 태그를 \>  **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="fa2fa-354">In the Security & Compliance Center, go to **Threat management** \> **Policy** and then select **Quarantine tags**.</span></span>

- <span data-ttu-id="fa2fa-355">기본 제공 또는 사용자 지정 Quarantine 태그의 설정을 확인하려면 목록에서 검사를 선택합니다(확인란을 선택하지는 않습니다).</span><span class="sxs-lookup"><span data-stu-id="fa2fa-355">To view the settings of built-in or custom quarantine tags, select the quarantine tag from the list (don't select the check box).</span></span>

- <span data-ttu-id="fa2fa-356">전역 설정을 보시고 전역 설정을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="fa2fa-356">To view the global settings, select **Global settings**</span></span>

### <a name="view-quarantine-tags-in-powershell"></a><span data-ttu-id="fa2fa-357">PowerShell에서 Quarantine 태그 보기</span><span class="sxs-lookup"><span data-stu-id="fa2fa-357">View quarantine tags in PowerShell</span></span>

<span data-ttu-id="fa2fa-358">PowerShell을 사용하여 태그를 보지 않고 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="fa2fa-358">If you'd rather use PowerShell to view quarantine tags, do any of the following steps:</span></span>

- <span data-ttu-id="fa2fa-359">모든 기본 제공 태그 또는 사용자 지정 태그의 요약 목록을 표시하기 위해 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="fa2fa-359">To view a summary list of all built-in or custom tags, run the following command:</span></span>

  ```powershell
  Get-QuarantineTag | Format-Table Name
  ```

- <span data-ttu-id="fa2fa-360">기본 제공 태그 또는 사용자 지정 Quarantine 태그의 설정을 보고, 해당 태그의 이름으로 바꾸고 다음 명령을 \<TagName\> 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="fa2fa-360">To view the settings of built-in or custom quarantine tags, replace \<TagName\> with the name of the quarantine tag, and run the following command:</span></span>

  ```powershell
  Get-QuarantineTag -Identity "<TagName>"
  ```

- <span data-ttu-id="fa2fa-361">전역 설정을 보시고 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="fa2fa-361">To view the global settings, run the following command:</span></span>

  ```powershell
  Get-QuarantineTag -QuarantineTagType GlobalQuarantineTag
  ```

<span data-ttu-id="fa2fa-362">자세한 구문 및 매개 변수 정보는 [Get-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/get-hostedcontentfilterpolicy)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fa2fa-362">For detailed syntax and parameter information, see [Get-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/get-hostedcontentfilterpolicy).</span></span>

## <a name="remove-quarantine-tags-in-the-security--compliance-center"></a><span data-ttu-id="fa2fa-363">보안 및 준수 센터에서 & 태그 제거</span><span class="sxs-lookup"><span data-stu-id="fa2fa-363">Remove quarantine tags in the Security & Compliance Center</span></span>

<span data-ttu-id="fa2fa-364">**참고:**</span><span class="sxs-lookup"><span data-stu-id="fa2fa-364">**Notes**:</span></span>

- <span data-ttu-id="fa2fa-365">기본 제공 분리 태그는 제거할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fa2fa-365">You can't remove built-in quarantine tags.</span></span>

- <span data-ttu-id="fa2fa-366">사용자 지정 분리 태그를 제거하기 전에 해당 태그가 사용되지 않는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa2fa-366">Before you remove a custom quarantine tag, verify that it's not being used.</span></span> <span data-ttu-id="fa2fa-367">예를 들어 PowerShell에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="fa2fa-367">For example, run the following command in PowerShell:</span></span>

  ```powershell
  Get-HostedContentFilterPolicy | Format-List Name,*QuarantineTag
  ```

  <span data-ttu-id="fa2fa-368">Quarantine 태그를 사용 중이면 해당 태그를 제거하기 전에 할당된 [분리](#step-2-assign-a-quarantine-tag-to-supported-features) 태그를 교체합니다.</span><span class="sxs-lookup"><span data-stu-id="fa2fa-368">If the quarantine tag is being used, [replace the assigned quarantine tag](#step-2-assign-a-quarantine-tag-to-supported-features) before you remove it.</span></span>

1. <span data-ttu-id="fa2fa-369">보안 & 준수 센터에서 **위협** 관리 정책으로 이동한 다음 태그를 \>  **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="fa2fa-369">In the Security & Compliance Center, go to **Threat management** \> **Policy** and then select **Quarantine tags**.</span></span>

2. <span data-ttu-id="fa2fa-370">**Quarantine tags(태그)** 페이지에서 제거할 사용자 지정 Quarantine 태그를 선택하고 삭제 태그를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="fa2fa-370">On the **Quarantine tags** page, select the custom quarantine tag that you want to remove, and the click **Delete tag**.</span></span>

3. <span data-ttu-id="fa2fa-371">나타나는 **확인 대화** 상자에서 태그 제거를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="fa2fa-371">Click **Remove tag** in the confirmation dialog that appears.</span></span>

### <a name="remove-quarantine-tags-in-powershell"></a><span data-ttu-id="fa2fa-372">PowerShell에서 분리 태그 제거</span><span class="sxs-lookup"><span data-stu-id="fa2fa-372">Remove quarantine tags in PowerShell</span></span>

<span data-ttu-id="fa2fa-373">PowerShell을 사용하여 사용자 지정 분리 태그를 제거하려면 해당 태그의 이름으로 바꾸고 다음 명령을 \<TagName\> 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="fa2fa-373">If you'd rather use PowerShell to remove a custom quarantine tag, replace \<TagName\> with the name of the quarantine tag, and run the following command:</span></span>

```powershell
Remove-QuarantineTag -Identity "<TagName>"
```

<span data-ttu-id="fa2fa-374">구문과 매개 변수에 대한 자세한 내용은 [Remove-QuarantineTag 를 참조하십시오.](https://docs.microsoft.com/powershell/module/exchange/remove-quarantinetag)</span><span class="sxs-lookup"><span data-stu-id="fa2fa-374">For detailed syntax and parameter information, see [Remove-QuarantineTag](https://docs.microsoft.com/powershell/module/exchange/remove-quarantinetag).</span></span>

## <a name="quarantine-tag-permission-details"></a><span data-ttu-id="fa2fa-375">태그 사용 권한 세부 정보 확인</span><span class="sxs-lookup"><span data-stu-id="fa2fa-375">Quarantine tag permission details</span></span>

<span data-ttu-id="fa2fa-376">다음 섹션에서는 미리 설정한 사용 권한 그룹 및 개별 사용 권한의 영향에 대해 자세히 설명하고 최종 사용자 스팸 알림에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="fa2fa-376">The following sections describe the effects of preset permission groups and individual permissions in the details of quarantined messages and in end-user spam notifications.</span></span>

### <a name="preset-permissions-groups"></a><span data-ttu-id="fa2fa-377">미리 설정한 사용 권한 그룹</span><span class="sxs-lookup"><span data-stu-id="fa2fa-377">Preset permissions groups</span></span>

<span data-ttu-id="fa2fa-378">미리 설정한 사용 권한 그룹에 포함된 개별 사용 권한은 이 문서의 시작부에 있는 표에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa2fa-378">The individual permissions that are included in preset permission groups are listed in the table at the beginning of this article.</span></span>

#### <a name="no-access"></a><span data-ttu-id="fa2fa-379">권한 없음</span><span class="sxs-lookup"><span data-stu-id="fa2fa-379">No access</span></span>

<span data-ttu-id="fa2fa-380">Quarantine 태그에 액세스 **권한** 없음(사용 권한 없음)을 할당하는 경우 사용자는 여전히 몇 가지 기준 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa2fa-380">If the quarantine tag assigns the **No access** permissions (no permissions), users still get some baseline capabilities:</span></span>

- <span data-ttu-id="fa2fa-381">**Quarantined message details:** The **View message header** button is always available.</span><span class="sxs-lookup"><span data-stu-id="fa2fa-381">**Quarantined message details**: The **View message header** button is always available.</span></span>

  ![사용자에게 액세스 권한이 없음을 제공하는 경우, 비분리된 메시지 세부 정보에서 사용 가능한 단추](../../media/quarantine-tags-quarantined-message-details-no-access.png)

- <span data-ttu-id="fa2fa-383">**최종 사용자 스팸 알림:** 사용자를 메시지로 보내기 위한 검토 단추는 항상 사용할 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="fa2fa-383">**End-user spam notifications**: The **Review** button that takes the user to the message in quarantine is always available.</span></span>

  ![차단 태그가 사용자에게 액세스 권한이 없는 경우 최종 사용자 스팸 알림의 사용 가능한 단추](../../media/quarantine-tags-esn-no-access.png)

#### <a name="limited-access"></a><span data-ttu-id="fa2fa-385">제한된 액세스</span><span class="sxs-lookup"><span data-stu-id="fa2fa-385">Limited access</span></span>

<span data-ttu-id="fa2fa-386">Quarantine 태그에 제한된  액세스 권한이 할당된 경우 사용자는 다음 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa2fa-386">If the quarantine tag assigns the **Limited access** permissions, users get the following capabilities:</span></span>

- <span data-ttu-id="fa2fa-387">**Quarantined message details:** The following buttons are available:</span><span class="sxs-lookup"><span data-stu-id="fa2fa-387">**Quarantined message details**: The following buttons are available:</span></span>
  - <span data-ttu-id="fa2fa-388">**릴리스 요청**</span><span class="sxs-lookup"><span data-stu-id="fa2fa-388">**Request release**</span></span>
  - <span data-ttu-id="fa2fa-389">**메시지 헤더 보기**</span><span class="sxs-lookup"><span data-stu-id="fa2fa-389">**View message header**</span></span>
  - <span data-ttu-id="fa2fa-390">**메시지 미리 보기**</span><span class="sxs-lookup"><span data-stu-id="fa2fa-390">**Preview message**</span></span>
  - <span data-ttu-id="fa2fa-391">**보낸 사람 차단**</span><span class="sxs-lookup"><span data-stu-id="fa2fa-391">**Block sender**</span></span>
  - <span data-ttu-id="fa2fa-392">**Quarantine에서 제거**</span><span class="sxs-lookup"><span data-stu-id="fa2fa-392">**Remove from quarantine**</span></span>

  ![사용자에게 제한된 액세스 권한을 부여하는 경우, 이 확인란의 메시지 세부 정보에서 사용 가능한 단추](../../media/quarantine-tags-quarantined-message-details-limited-access.png)

- <span data-ttu-id="fa2fa-394">**최종 사용자 스팸 알림:** 다음 단추를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa2fa-394">**End-user spam notifications**: The following buttons are available:</span></span>
  - <span data-ttu-id="fa2fa-395">**보낸 사람 차단**</span><span class="sxs-lookup"><span data-stu-id="fa2fa-395">**Block sender**</span></span>
  - <span data-ttu-id="fa2fa-396">**검토**</span><span class="sxs-lookup"><span data-stu-id="fa2fa-396">**Review**</span></span>

  ![차단 태그가 사용자에게 제한된 액세스 권한을 부여하는 경우 최종 사용자 스팸 알림의 사용 가능한 단추](../../media/quarantine-tags-esn-limited-access.png)

#### <a name="full-access"></a><span data-ttu-id="fa2fa-398">모든 액세스</span><span class="sxs-lookup"><span data-stu-id="fa2fa-398">Full access</span></span>

<span data-ttu-id="fa2fa-399">Quarantine 태그에 모든  액세스 권한(사용 가능한 모든 사용 권한)이 할당된 경우 사용자는 다음 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa2fa-399">If the quarantine tag assigns the **Full access** permissions (all available permissions), users get the following capabilities:</span></span>

- <span data-ttu-id="fa2fa-400">**Quarantined message details:** The following buttons are available:</span><span class="sxs-lookup"><span data-stu-id="fa2fa-400">**Quarantined message details**: The following buttons are available:</span></span>
  - <span data-ttu-id="fa2fa-401">**릴리스 메시지**</span><span class="sxs-lookup"><span data-stu-id="fa2fa-401">**Release message**</span></span>
  - <span data-ttu-id="fa2fa-402">**메시지 헤더 보기**</span><span class="sxs-lookup"><span data-stu-id="fa2fa-402">**View message header**</span></span>
  - <span data-ttu-id="fa2fa-403">**메시지 미리 보기**</span><span class="sxs-lookup"><span data-stu-id="fa2fa-403">**Preview message**</span></span>
  - <span data-ttu-id="fa2fa-404">**보낸 사람 차단**</span><span class="sxs-lookup"><span data-stu-id="fa2fa-404">**Block sender**</span></span>
  - <span data-ttu-id="fa2fa-405">**보낸 사람 허용**</span><span class="sxs-lookup"><span data-stu-id="fa2fa-405">**Allow sender**</span></span>
  - <span data-ttu-id="fa2fa-406">**Quarantine에서 제거**</span><span class="sxs-lookup"><span data-stu-id="fa2fa-406">**Remove from quarantine**</span></span>

  ![사용자에게 모든 액세스 권한을 부여하는 경우, 해당 태그가 사용자에게 모든 권한을 부여하는 경우, Quarantined 메시지 세부 정보에서 사용 가능한 단추](../../media/quarantine-tags-quarantined-message-details-full-access.png)

- <span data-ttu-id="fa2fa-408">**최종 사용자 스팸 알림:** 다음 단추를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa2fa-408">**End-user spam notifications**: The following buttons are available:</span></span>
  - <span data-ttu-id="fa2fa-409">**보낸 사람 차단**</span><span class="sxs-lookup"><span data-stu-id="fa2fa-409">**Block sender**</span></span>
  - <span data-ttu-id="fa2fa-410">**릴리스**</span><span class="sxs-lookup"><span data-stu-id="fa2fa-410">**Release**</span></span>
  - <span data-ttu-id="fa2fa-411">**검토**</span><span class="sxs-lookup"><span data-stu-id="fa2fa-411">**Review**</span></span>

  ![차단 태그가 사용자에게 모든 액세스 권한을 부여하는 경우 최종 사용자 스팸 알림의 사용 가능한 단추](../../media/quarantine-tags-esn-full-access.png)

### <a name="individual-permissions"></a><span data-ttu-id="fa2fa-413">개별 사용 권한</span><span class="sxs-lookup"><span data-stu-id="fa2fa-413">Individual permissions</span></span>

> [!NOTE]
> <span data-ttu-id="fa2fa-414">사용자는 항상 액세스 금지 섹션에 설명된 [단추를 얻게](#no-access) 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fa2fa-414">Remember, users always get the buttons described in the [No access](#no-access) section.</span></span> <span data-ttu-id="fa2fa-415">이러한 단추는 개별 사용 권한 설명에 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fa2fa-415">These buttons are not included in the individual permission descriptions.</span></span>

#### <a name="allow-sender-permission"></a><span data-ttu-id="fa2fa-416">보낸 사람 권한 허용</span><span class="sxs-lookup"><span data-stu-id="fa2fa-416">Allow sender permission</span></span>

<span data-ttu-id="fa2fa-417">보낸 **사람 허용** 권한(PermissionToAllowSender)은 사용자가 수신 허용 - 보낸 사람 목록에 메일로 보낸 메시지를 편리하게 추가할 수 있도록 단추에 대한 액세스를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="fa2fa-417">The **Allow sender** permission (_PermissionToAllowSender_) controls access to the button that allows users to conveniently add the quarantined message sender to their Safe Senders list.</span></span>

- <span data-ttu-id="fa2fa-418">**Quarantined message details**:</span><span class="sxs-lookup"><span data-stu-id="fa2fa-418">**Quarantined message details**:</span></span>
  - <span data-ttu-id="fa2fa-419">**보낸 사람 권한 허용** 사용: 보낸 **사람 허용** 단추를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa2fa-419">**Allow sender** permission enabled: The **Allow sender** button is available.</span></span>
  - <span data-ttu-id="fa2fa-420">**보낸 사람 권한을 허용하지** 않도록 설정: 보낸 사람 **허용** 단추를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fa2fa-420">**Allow sender** permission disabled: The **Allow sender** button is not available.</span></span>

- <span data-ttu-id="fa2fa-421">**최종 사용자 스팸 알림:** 효과가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fa2fa-421">**End-user spam notifications**: No effect.</span></span>

<span data-ttu-id="fa2fa-422">수신 - 보낸 사람 목록에 대한 [](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379666) 자세한 내용은 신뢰할 수 있는 보낸 사람이 차단되지 않도록 방지 및 [Exchange Online PowerShell을](configure-junk-email-settings-on-exo-mailboxes.md#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox)사용하여 사서함에 수신 수신 목록 모음을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="fa2fa-422">For more information about the Safe Senders list, see [Prevent trusted senders from being blocked](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379666) and [Use Exchange Online PowerShell to configure the safelist collection on a mailbox](configure-junk-email-settings-on-exo-mailboxes.md#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox).</span></span>

#### <a name="block-sender-permission"></a><span data-ttu-id="fa2fa-423">보낸 사람 권한 차단</span><span class="sxs-lookup"><span data-stu-id="fa2fa-423">Block sender permission</span></span>

<span data-ttu-id="fa2fa-424">차단 **보낸** 사람 _권한(PermissionToBlockSender)은_ 사용자가 차단된 보낸 사람 목록에 메일로 전송된 메시지를 편리하게 추가할 수 있도록 단추에 대한 액세스를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="fa2fa-424">The **Block sender** permission (_PermissionToBlockSender_) controls access to the button that allows users to conveniently add the quarantined message sender to their Blocked Senders list.</span></span>

- <span data-ttu-id="fa2fa-425">**Quarantined message details**:</span><span class="sxs-lookup"><span data-stu-id="fa2fa-425">**Quarantined message details**:</span></span>
  - <span data-ttu-id="fa2fa-426">**보낸 사람 권한 차단** 사용: 보낸 **사람 차단** 단추를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa2fa-426">**Block sender** permission enabled: The **Block sender** button is available.</span></span>
  - <span data-ttu-id="fa2fa-427">**보낸 사람 권한을** 차단하지 않도록 설정: 보낸 **사람** 차단 단추를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fa2fa-427">**Block sender** permission disabled: The **Block sender** button is not available.</span></span>

- <span data-ttu-id="fa2fa-428">**최종 사용자 스팸 알림:**</span><span class="sxs-lookup"><span data-stu-id="fa2fa-428">**End-user spam notifications**:</span></span>
  - <span data-ttu-id="fa2fa-429">**보낸 사람 권한을** 차단하지 않도록 설정: 보낸 **사람** 차단 단추를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fa2fa-429">**Block sender** permission disabled: The **Block sender** button is not available.</span></span>
  - <span data-ttu-id="fa2fa-430">**보낸 사람 권한 차단** 사용: 보낸 **사람 차단** 단추를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa2fa-430">**Block sender** permission enabled: The **Block sender** button is available.</span></span>

<span data-ttu-id="fa2fa-431">수신 차단된 보낸 사람 목록에 대한 [](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379667) 자세한 내용은 다른 사람의 메시지 차단 및 [Exchange Online PowerShell을](configure-junk-email-settings-on-exo-mailboxes.md#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox)사용하여 사서함에 수신 수신 목록 모음을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="fa2fa-431">For more information about the Blocked Senders list, see [Block messages from someone](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379667) and [Use Exchange Online PowerShell to configure the safelist collection on a mailbox](configure-junk-email-settings-on-exo-mailboxes.md#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox).</span></span>

#### <a name="delete-permission"></a><span data-ttu-id="fa2fa-432">삭제 권한</span><span class="sxs-lookup"><span data-stu-id="fa2fa-432">Delete permission</span></span>

<span data-ttu-id="fa2fa-433">삭제  _권한(PermissionToDelete)은_ 사용자가 자신의 메시지(사용자가 받는 사람인 메시지)를 Quarantine에서 삭제할 수 있는 기능을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="fa2fa-433">The **Delete** permission (_PermissionToDelete_) controls the ability to of users to delete their messages (messages where the user is a recipient) from quarantine.</span></span>

- <span data-ttu-id="fa2fa-434">**Quarantined message details**:</span><span class="sxs-lookup"><span data-stu-id="fa2fa-434">**Quarantined message details**:</span></span>
  - <span data-ttu-id="fa2fa-435">**삭제** 권한 사용: **분리에서** 제거 단추를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa2fa-435">**Delete** permission enabled: The **Remove from quarantine** button is available.</span></span>
  - <span data-ttu-id="fa2fa-436">**삭제** 권한 사용 안함: **분리에서** 제거 단추를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fa2fa-436">**Delete** permission disabled: The **Remove from quarantine** button is not available.</span></span>

- <span data-ttu-id="fa2fa-437">**최종 사용자 스팸 알림:** 효과가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fa2fa-437">**End-user spam notifications**: No effect.</span></span>

#### <a name="preview-permission"></a><span data-ttu-id="fa2fa-438">미리 보기 권한</span><span class="sxs-lookup"><span data-stu-id="fa2fa-438">Preview permission</span></span>

<span data-ttu-id="fa2fa-439">미리 **보기** _권한(PermissionToPreview)은_ 사용자가 자신의 메시지를 미리 볼 수 있는 기능을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="fa2fa-439">The **Preview** permission (_PermissionToPreview_) controls the ability to of users to preview their messages in quarantine.</span></span>

- <span data-ttu-id="fa2fa-440">**Quarantined message details**:</span><span class="sxs-lookup"><span data-stu-id="fa2fa-440">**Quarantined message details**:</span></span>
  - <span data-ttu-id="fa2fa-441">**미리** 보기 사용 권한: **미리 보기 메시지** 단추를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa2fa-441">**Preview** permission enabled: The **Preview message** button is available.</span></span>
  - <span data-ttu-id="fa2fa-442">**미리** 보기 권한이 사용되지 않도록 설정: 미리 보기 **메시지** 단추를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fa2fa-442">**Preview** permission disabled: The **Preview message** button is not available.</span></span>

- <span data-ttu-id="fa2fa-443">**최종 사용자 스팸 알림:** 효과가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fa2fa-443">**End-user spam notifications**: No effect.</span></span>

#### <a name="allow-recipients-to-release-a-message-from-quarantine-permission"></a><span data-ttu-id="fa2fa-444">받는 사람이 메시지를 검지 권한에서 해제할 수 있도록 허용</span><span class="sxs-lookup"><span data-stu-id="fa2fa-444">Allow recipients to release a message from quarantine permission</span></span>

<span data-ttu-id="fa2fa-445">받는 **사람이** 메시지를 검지 _권한(PermissionToRelease)에서_ 릴리스하도록 허용하면 사용자가 관리자의 승인 없이 직접 또는 해당 메시지를 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa2fa-445">The **Allow recipients to release a message from quarantine** permission (_PermissionToRelease_) controls the ability of users to release their quarantined messages directly and without the approval of an admin.</span></span>

- <span data-ttu-id="fa2fa-446">**Quarantined message details**:</span><span class="sxs-lookup"><span data-stu-id="fa2fa-446">**Quarantined message details**:</span></span>
  - <span data-ttu-id="fa2fa-447">사용 권한 사용: **릴리스 메시지** 단추를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa2fa-447">Permission enabled: The **Release message** button is available.</span></span>
  - <span data-ttu-id="fa2fa-448">사용 권한을 사용하지 않도록 설정: **메시지 해제** 단추를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fa2fa-448">Permission disabled: The **Release message** button is not available.</span></span>

- <span data-ttu-id="fa2fa-449">**최종 사용자 스팸 알림:**</span><span class="sxs-lookup"><span data-stu-id="fa2fa-449">**End-user spam notifications**:</span></span>
  - <span data-ttu-id="fa2fa-450">사용 권한 사용: **릴리스 단추를** 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa2fa-450">Permission enabled: The **Release** button is available.</span></span>
  - <span data-ttu-id="fa2fa-451">사용 권한을 사용하지 않도록 설정: **해제** 단추를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fa2fa-451">Permission disabled: The **Release** button is not available.</span></span>

#### <a name="allow-recipients-to-request-a-message-to-be-released-from-quarantine-permission"></a><span data-ttu-id="fa2fa-452">받는 사람이 메시지를 메시지에 대한 확인 권한에서 릴리스하도록 허용</span><span class="sxs-lookup"><span data-stu-id="fa2fa-452">Allow recipients to request a message to be released from quarantine permission</span></span>

<span data-ttu-id="fa2fa-453">받는 **사람이** 메시지의 해제를 요청하도록 허용(PermissionToRequestRelease)는 사용자가 자신의 에지된  메시지 릴리스를 요청할 수 있는 기능을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="fa2fa-453">The **Allow recipients to request a message to be released from quarantine** permission (_PermissionToRequestRelease_) controls the ability of users to _request_ the release of their quarantined messages.</span></span> <span data-ttu-id="fa2fa-454">메시지는 관리자가 요청을 승인한 후에만 릴리스됩니다.</span><span class="sxs-lookup"><span data-stu-id="fa2fa-454">The message is only released after an admin approves the request.</span></span>

- <span data-ttu-id="fa2fa-455">**Quarantined message details**:</span><span class="sxs-lookup"><span data-stu-id="fa2fa-455">**Quarantined message details**:</span></span>
  - <span data-ttu-id="fa2fa-456">사용 권한 사용: **릴리스 요청 단추를** 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa2fa-456">Permission enabled: The **Request release** button is available.</span></span>
  - <span data-ttu-id="fa2fa-457">사용 권한을 사용하지 않도록 설정: 릴리스 **요청** 단추를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fa2fa-457">Permission disabled: The **Request release** button is not available.</span></span>

- <span data-ttu-id="fa2fa-458">**최종 사용자 스팸 알림:** 릴리스 단추를 사용할 수 없습니다. </span><span class="sxs-lookup"><span data-stu-id="fa2fa-458">**End-user spam notifications**: The **Release** button is not available.</span></span>
