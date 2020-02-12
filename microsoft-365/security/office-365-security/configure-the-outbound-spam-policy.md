---
title: 아웃바운드 스팸 정책 구성
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 10/02/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a44764e9-a5d2-4c67-8888-e7fb871c17c7
ms.collection:
- M365-security-compliance
description: 아웃바운드 전자 메일 보내기 서비스를 사용하는 경우 아웃바운드 스팸 필터링이 항상 사용하도록 설정되므로 서비스와 받는 사람을 사용하여 조직을 보호할 수 있습니다.
ms.openlocfilehash: 0fa5ec23eee6144864f16b52d452d02f38b554d7
ms.sourcegitcommit: 4986032867b8664a215178b5e095cbda021f3450
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/12/2020
ms.locfileid: "41957343"
---
# <a name="configure-the-outbound-spam-policy"></a><span data-ttu-id="db97e-103">아웃바운드 스팸 정책 구성</span><span class="sxs-lookup"><span data-stu-id="db97e-103">Configure the outbound spam policy</span></span>

<span data-ttu-id="db97e-104">아웃바운드 전자 메일 보내기 서비스를 사용하는 경우 아웃바운드 스팸 필터링이 항상 사용하도록 설정되므로 서비스와 받는 사람을 사용하여 조직을 보호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db97e-104">Outbound spam filtering is always enabled if you use the service for sending outbound email, thereby protecting organizations using the service and their intended recipients.</span></span> <span data-ttu-id="db97e-105">인바운드 필터링과 마찬가지로 아웃 바운드 스팸 필터링은 연결 필터링 및 콘텐츠 필터링으로 구성 되며 특정 컨트롤에서 아웃 바운드 메시지를 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db97e-105">Similar to inbound filtering, outbound spam filtering is comprised of connection filtering and content filtering and allows some specific controls to handle outbound messages.</span></span> <span data-ttu-id="db97e-106">아웃 바운드 스팸 필터 정책 설정 유형:</span><span class="sxs-lookup"><span data-stu-id="db97e-106">Outbound spam filter policy settings types:</span></span>

- <span data-ttu-id="db97e-107">기본값: 회사 전체의 아웃 바운드 스팸 필터 설정을 구성 하는 데 기본 아웃 바운드 스팸 필터 정책이 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="db97e-107">Default: The default outbound spam filter policy is used to configure company-wide outbound spam filter settings.</span></span> <span data-ttu-id="db97e-108">이 정책은 이름을 바꿀 수 없으며 항상 켜져 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db97e-108">This policy can not be renamed and is always on.</span></span>

- <span data-ttu-id="db97e-109">사용자 지정: 사용자 지정 아웃 바운드 스팸 필터 정책은 세분화 하 여 조직의 특정 사용자, 그룹 또는 도메인에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db97e-109">Custom: Custom outbound spam filter policies can be granular and applied to specific users, groups, or domains in your organization.</span></span> <span data-ttu-id="db97e-110">사용자 지정 정책은 기본 정책보다 항상 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="db97e-110">Custom policies always take precedence over the default policy.</span></span> <span data-ttu-id="db97e-111">각 사용자 지정 정책의 우선 순위를 변경 하 여 사용자 지정 정책이 실행 되는 순서를 변경할 수 있습니다. 그러나 사용자가 여러 정책과 일치 하는 경우에는 가장 높은 우선 순위 (즉, 0에 가장 가까운 수) 정책만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="db97e-111">You can change the order in which your custom policies run by changing the priority of each custom policy; however, only the highest priority (i.e. number closest to 0) policy will apply if the user matches multiple policies.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="db97e-112">시작하기 전에 알아야 할 사항은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="db97e-112">What do you need to know before you begin?</span></span>
<span data-ttu-id="db97e-113"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="db97e-113"><a name="sectionSection0"> </a></span></span>

- <span data-ttu-id="db97e-114">예상 완료 시간: 5분</span><span class="sxs-lookup"><span data-stu-id="db97e-114">Estimated time to complete: 5 minutes</span></span>

- <span data-ttu-id="db97e-115">이러한 절차를 수행하려면 먼저 사용 권한을 할당받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="db97e-115">You need to be assigned permissions before you can perform this procedure or procedures.</span></span> <span data-ttu-id="db97e-116">필요한 권한을 확인하려면 [Exchange Online의 기능 사용 권한](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions) 항목에서 스팸 방지 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="db97e-116">To see what permissions you need, see the "Anti-spam entry in the [Feature Permissions in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions) topic.</span></span>

- <span data-ttu-id="db97e-117">원격 PowerShell에서이 항목의 절차를 수행할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db97e-117">You can also do the procedures in this topic in remote PowerShell.</span></span> <span data-ttu-id="db97e-118">[Get-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-hostedoutboundspamfilterpolicy) cmdlet을 사용하여 설정을 검토하고 [Set-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedoutboundspamfilterpolicy) cmdlet을 사용하여 아웃바운드 스팸 정책 설정을 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db97e-118">Use the [Get-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-hostedoutboundspamfilterpolicy) cmdlet to review your settings, and the [Set-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedoutboundspamfilterpolicy) to edit your outbound spam policy settings.</span></span>

  <span data-ttu-id="db97e-119">Exchange Online PowerShell에 연결하려면 [Exchange Online PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="db97e-119">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="db97e-120">Exchange Online Protection PowerShell에 연결 하려면 [Exchange Online Protection powershell에 연결](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="db97e-120">To connect to Exchange Online Protection PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

## <a name="use-the-security--compliance-center-scc-to-edit-the-default-outbound-spam-policy"></a><span data-ttu-id="db97e-121">SCC (보안 & 준수 센터)를 사용 하 여 기본 아웃 바운드 스팸 정책 편집</span><span class="sxs-lookup"><span data-stu-id="db97e-121">Use the Security & Compliance Center (SCC) to edit the default outbound spam policy</span></span>

<span data-ttu-id="db97e-122">다음 절차에 따라 기본 아웃바운드 스팸 정책을 편집합니다.</span><span class="sxs-lookup"><span data-stu-id="db97e-122">Use the following procedure to edit the default outbound spam policy:</span></span>

### <a name="to-configure-the-default-outbound-spam-policy"></a><span data-ttu-id="db97e-123">기본 아웃바운드 스팸 정책을 구성하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="db97e-123">To configure the default outbound spam policy</span></span>

1. <span data-ttu-id="db97e-124">SCC에서 **위협 관리** \> **정책** \> **스팸 방지** 로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="db97e-124">In the SCC, navigate to **Threat Management** \> **Policy** \> **Anti-spam**</span></span>

2. <span data-ttu-id="db97e-125">**아웃 바운드 스팸 필터 정책 (ALWAYS ON)** 섹션을 확장 하 고 **정책 편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="db97e-125">Expand the **Outbound spam filter policy (always ON)** section and click **Edit policy**.</span></span>

3. <span data-ttu-id="db97e-126">**알림** 섹션을 확장 하 고 아웃 바운드 메시지에 대 한 다음 확인란을 선택한 다음 **사용자 추가** 를 선택 하 여 해당 대화 상자에 연결 된 전자 메일 주소나 주소를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="db97e-126">Expand the **Notifications** section and select the following check boxes pertaining to outbound messages, then select **Add people** to add an associated email address or addresses in the accompanying dialog box.</span></span> <span data-ttu-id="db97e-127">(이는 올바른 SMTP 대상으로 확인 되는 경우 메일 목록 일 수 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="db97e-127">(these can be distribution lists if they resolve as valid SMTP destinations):</span></span>

   - <span data-ttu-id="db97e-128">**의심 스러운 모든 아웃 바운드 전자 메일 메시지의 복사본을 다음 전자 메일 주소 또는 주소로 보내기**: SCL 등급에 관계 없이 필터에 의해 스팸으로 표시 된 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="db97e-128">**Send a copy of all suspicious outbound email messages to the following email address or addresses**: These are messages that are marked as spam by the filter (regardless of the SCL rating).</span></span> <span data-ttu-id="db97e-129">필터에 의해 거부 되지는 않지만 높은 위험 배달 풀을 통해 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="db97e-129">They are not rejected by the filter but are routed through the higher risk delivery pool.</span></span> <span data-ttu-id="db97e-130">주소가 여러 개인 경우 세미콜론으로 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="db97e-130">Separate multiple addresses with a semicolon.</span></span> <span data-ttu-id="db97e-131">지정 된 받는 사람은 메시지를 Bcc (숨은 참조) 주소로 받습니다 (보낸 사람 및 받는 사람 필드는 원본에 대 한 송신자 및 수신자).</span><span class="sxs-lookup"><span data-stu-id="db97e-131">Note that the recipients specified will receive the messages as a Blind carbon copy (Bcc) address (the From and To fields are the original sender and recipient).</span></span>

   - <span data-ttu-id="db97e-132">**보낸 사람이 아웃 바운드 스팸을 보낼 수 없도록 차단 된 경우 다음 전자 메일 주소로 알림 보내기**: 세미콜론을 사용 하 여 여러 주소를 구분 합니다.</span><span class="sxs-lookup"><span data-stu-id="db97e-132">**Send a notification to the following email address when a sender is blocked sending outbound spam**: Separate multiple addresses with a semicolon.</span></span>

   <span data-ttu-id="db97e-133">특정 사용자가 상당량의 스팸 또는 기타 보내기 예외를 감지 하면 사용자가 전자 메일 메시지를 보낼 수 없으며 지정 된 전자 메일 주소로 알림이 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="db97e-133">When a significant amount of spam or other sending anomalies are detected from a particular user, the user is restricted from sending email messages and a notification is sent to the email addresses specified.</span></span>

   <span data-ttu-id="db97e-134">이 설정을 사용하여 지정되는 도메인의 관리자에게는 해당 사용자의 아웃바운드 메시지가 차단되었다는 알림이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="db97e-134">The administrator for the domain, who is specified using this setting, will be informed that outbound messages are blocked for this user.</span></span>  <span data-ttu-id="db97e-135">이 알림의 모양을 보려면 [보낸 사람이 보내는 아웃 바운드 스팸 차단 되 면 샘플 알림](sample-notification-when-a-sender-is-blocked-sending-outbound-spam.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="db97e-135">To see what this notification looks like, see [Sample notification when a sender is blocked sending outbound spam](sample-notification-when-a-sender-is-blocked-sending-outbound-spam.md).</span></span>

   > [!NOTE]
   > <span data-ttu-id="db97e-136">사용자가 제한 되었음을 나타내는 시스템 경고도 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="db97e-136">A system alert is also generated indicating the user has been restricted.</span></span> <span data-ttu-id="db97e-137">경고에 대 한 자세한 내용을 보고 사용자를 복구 하는 방법에 대 한 자세한 내용은 [스팸 메일을 보낸 후 제한 된 사용자 포털에서 사용자 제거](removing-user-from-restricted-users-portal-after-spam.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="db97e-137">To learn more about the alert and how to recover the user, see [Removing a user from the Restricted Users portal after sending spam email](removing-user-from-restricted-users-portal-after-spam.md).</span></span>

4. <span data-ttu-id="db97e-138">**받는 사람 제한** 섹션을 확장 하 여 사용자가 내부 및 외부 받는 사람에 대해 하루 당 최대 수와 함께 보낼 수 있는 최대 받는 사람 수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="db97e-138">Expand the **Recipient limits** section to specify the maximum number of recipients that a user can send to, per hour for internal and external recipients together with the maximum number per day.</span></span>

   > [!NOTE]
   > <span data-ttu-id="db97e-139">모든 입력의 최대 수는 1만입니다.</span><span class="sxs-lookup"><span data-stu-id="db97e-139">The maximum number for any input is 10000.</span></span> <span data-ttu-id="db97e-140">자세한 내용은 [Exchange online 내에서의 수신 및 전송 제한](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#receiving-and-sending-limits) 참조</span><span class="sxs-lookup"><span data-stu-id="db97e-140">For more information see [receiving and sending limits within Exchange online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#receiving-and-sending-limits)</span></span>

7. <span data-ttu-id="db97e-141">사용자가 지정 된 제한을 초과 했을 때 수행할 **작업** 을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="db97e-141">Specify the **action** to take when a user exceeds the specified limits.</span></span>  <span data-ttu-id="db97e-142">가능한 작업은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="db97e-142">The actions that are possible are as follows:</span></span>

   - <span data-ttu-id="db97e-143">**다음 날까지 사용자가 메일을 보낼 수 없도록**합니다.</span><span class="sxs-lookup"><span data-stu-id="db97e-143">**Restrict the user from sending mail till the following day**.</span></span>  <span data-ttu-id="db97e-144">전송 제한이 초과 되 면 (내부, 외부 또는 매일) 관리자에 대 한 경고가 생성 되며 사용자는 UTC 시간을 기준으로 다음 날까지 더 이상 전자 메일을 보낼 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="db97e-144">Once any sending limit has been exceeded (internal, external or daily) an alert will be generated for the admin and the user will be unable to send any further email until the following day, based on UTC time.</span></span> <span data-ttu-id="db97e-145">관리자가이 블록을 무시할 수 있는 방법은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="db97e-145">There is no way for the administrator to override this block.</span></span>

   - <span data-ttu-id="db97e-146">**사용자가 메일을 보낼 수 없도록 제한**합니다.</span><span class="sxs-lookup"><span data-stu-id="db97e-146">**Restrict the user from sending mail**.</span></span>  <span data-ttu-id="db97e-147">전송 제한이 초과 되는 경우 (내부, 외부 또는 매일) 관리자에 대 한 알림이 생성 되 고 사용자가 제한을 제거할 때까지 더 이상 전자 메일을 보낼 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="db97e-147">Once any sending limit has been exceeded (internal, external or daily) an alert will be generated for the admin and the user will be unable to send any further email until the administrator removes the restriction.</span></span>  <span data-ttu-id="db97e-148">이러한 경우 사용자는 [제한 된 사용자 페이지](removing-user-from-restricted-users-portal-after-spam.md)에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="db97e-148">In these cases the user will be listed on the [Restricted Users page](removing-user-from-restricted-users-portal-after-spam.md).</span></span>  <span data-ttu-id="db97e-149">목록에서 제거 된 사용자는 해당 날짜에 대해 다시 제한 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="db97e-149">Once removed from the list the user will not be restricted again for that day.</span></span>

   - <span data-ttu-id="db97e-150">**작업/알림을 받지 않습니다**.</span><span class="sxs-lookup"><span data-stu-id="db97e-150">**No Action/Alert only**.</span></span> <span data-ttu-id="db97e-151">전송 제한이 초과 되 면 (내부, 외부 또는 매일) 관리자에 대 한 경고가 생성 되지만 사용자를 제한 하기 위한 조치는 수행 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="db97e-151">Once any sending limit has been exceeded (internal, external or daily) an alert will be generated for the admin but no action will be taken to restrict the user.</span></span>

6. <span data-ttu-id="db97e-152">**적용 대상** 섹션을 확장 하 고이 정책을 적용할 사용자, 그룹 및 도메인을 지정 하는 조건 기반 규칙을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="db97e-152">Expand the **Applies to** section and then create a condition-based rule to specify the users, groups, and domains to which to apply this policy.</span></span> <span data-ttu-id="db97e-153">고유한 조건을 여러 개 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db97e-153">You can create multiple conditions, if they are unique.</span></span>  <span data-ttu-id="db97e-154">참고: 사용자는 여러 조건을 지정할 때 모든 조건을 충족 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="db97e-154">Note: that users must meet all the conditions when multiple conditions are specified.</span></span>  

   - <span data-ttu-id="db97e-155">사용자를 선택 하려면 **보낸 사람**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="db97e-155">To select users, select **The sender is**.</span></span> <span data-ttu-id="db97e-156">그러면 표시되는 대화 상자의 사용자 선택 목록에서 회사의 보낸 사람을 한 명 이상 선택하고 추가를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="db97e-156">In the subsequent dialog box, select one or more senders from your company from the user picker list, and then click add.</span></span> <span data-ttu-id="db97e-157">목록에 없는 보낸 사람을 추가하려면 해당 전자 메일 주소를 입력한 다음 이름 확인을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="db97e-157">To add senders who aren't on the list, type their email addresses, and then click Check names.</span></span> <span data-ttu-id="db97e-158">원하는 항목을 모두 선택한 후 확인을 클릭하여 주 화면으로 돌아갑니다.</span><span class="sxs-lookup"><span data-stu-id="db97e-158">When you are done making your selections, click ok to return to the main screen.</span></span>

   - <span data-ttu-id="db97e-159">그룹을 선택 하려면 **보낸 사람이 구성원 인**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="db97e-159">To select groups, select **The sender is a member of**.</span></span> <span data-ttu-id="db97e-160">그런 다음 후속 대화 상자에서 그룹을 선택하거나 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="db97e-160">Then, in the subsequent dialog box, select or specify the groups.</span></span> <span data-ttu-id="db97e-161">그런 후에 확인을 클릭하여 주 화면으로 돌아갑니다.</span><span class="sxs-lookup"><span data-stu-id="db97e-161">Click ok to return to the main screen.</span></span>

   - <span data-ttu-id="db97e-162">도메인을 선택 하려면 **보낸 사람 도메인**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="db97e-162">To select domains, select **The sender domain is**.</span></span> <span data-ttu-id="db97e-163">그런 다음 후속 대화 상자에서 도메인을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="db97e-163">Then, in the subsequent dialog box, add the domains.</span></span> <span data-ttu-id="db97e-164">그런 후에 확인을 클릭하여 주 화면으로 돌아갑니다.</span><span class="sxs-lookup"><span data-stu-id="db97e-164">Click ok to return to the main screen.</span></span>

   <span data-ttu-id="db97e-165">규칙 내에서 예외를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db97e-165">You can create exceptions within the rule.</span></span> <span data-ttu-id="db97e-166">예를 들어 특정 도메인을 제외한 모든 도메인에서 보내는 메시지를 필터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db97e-166">For example, you can filter messages from all domains except for a certain domain.</span></span> <span data-ttu-id="db97e-167">이렇게 하려면 예외 추가를 클릭하고 다른 조건을 만들 때와 비슷한 방식으로 예외 조건을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="db97e-167">Click add exception, and then create your exception conditions similar to the way that you created the other conditions.</span></span>

   <span data-ttu-id="db97e-168">그룹에 아웃 바운드 스팸 정책을 적용 하는 것은 메일 사용이 가능한 보안 그룹에 대해서만 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="db97e-168">Applying an outbound spam policy to a group is supported only for Mail Enabled Security Groups.</span></span>

7. <span data-ttu-id="db97e-169">**저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="db97e-169">Click **save**.</span></span>

## <a name="to-create-a-custom-policy-for-a-specific-set-of-users"></a><span data-ttu-id="db97e-170">특정 사용자 집합에 대 한 사용자 지정 정책을 만들려면</span><span class="sxs-lookup"><span data-stu-id="db97e-170">To create a custom policy for a specific set of users</span></span>

1. <span data-ttu-id="db97e-171">SCC에서 **위협 관리** \> **정책** \> **스팸 방지** 로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="db97e-171">In the SCC, navigate to **Threat Management** \> **Policy** \> **Anti-spam**</span></span>

2. <span data-ttu-id="db97e-172">**아웃 바운드 정책 만들기** 단추를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="db97e-172">Click on the **Create an outbound policy** button.</span></span>

3. <span data-ttu-id="db97e-173">**알림** 섹션을 확장 하 고 아웃 바운드 메시지에 대 한 다음 확인란을 선택한 다음 **사용자 추가** 를 선택 하 여 해당 대화 상자에 연결 된 전자 메일 주소나 주소를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="db97e-173">Expand the **Notifications** section and select the following check boxes pertaining to outbound messages, then select **Add people** to add an associated email address or addresses in the accompanying dialog box.</span></span>

4. <span data-ttu-id="db97e-174">받는 사람 **제한** 섹션을 확장 하 여 내부 및 외부 받는 사람 및 하루 최대 수에 대해 사용자가 보낼 수 있는 최대 받는 사람 수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="db97e-174">Expand the **Recipient limits** section to specify the maximum number of recipients that a user can send to, per hour for internal and external recipients and maximum number per day.</span></span>

7. <span data-ttu-id="db97e-175">사용자가 지정 된 제한을 초과 했을 때 수행할 **작업** 을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="db97e-175">Specify the **action** to take when a user exceeds the specified limits.</span></span>

6. <span data-ttu-id="db97e-176">**적용 대상** 섹션을 확장 하 고이 정책을 적용할 사용자, 그룹 및 도메인을 지정 하는 조건 기반 규칙을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="db97e-176">Expand the **Applies to** section and create a condition-based rule to specify the users, groups, and domains to which to apply this policy.</span></span> <span data-ttu-id="db97e-177">고유한 조건을 여러 개 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db97e-177">You can create multiple conditions, if they are unique.</span></span>  

8. <span data-ttu-id="db97e-178">**저장** 을 클릭</span><span class="sxs-lookup"><span data-stu-id="db97e-178">Click **save**</span></span>

## <a name="for-more-information"></a><span data-ttu-id="db97e-179">자세한 내용</span><span class="sxs-lookup"><span data-stu-id="db97e-179">For more information</span></span>

[<span data-ttu-id="db97e-180">스팸 메일을 보낸 후 제한된 사용자 포털에서 사용자 제거</span><span class="sxs-lookup"><span data-stu-id="db97e-180">Removing a user from the Restricted Users portal after sending spam email</span></span>](https://docs.microsoft.com/office365/SecurityCompliance/removing-user-from-restricted-users-portal-after-spam)

[<span data-ttu-id="db97e-181">아웃바운드 메시지용 높은 위험 배달 풀</span><span class="sxs-lookup"><span data-stu-id="db97e-181">High-risk delivery pool for outbound messages</span></span>](high-risk-delivery-pool-for-outbound-messages.md)

[<span data-ttu-id="db97e-182">스팸 방지 및 보호 FAQ</span><span class="sxs-lookup"><span data-stu-id="db97e-182">Anti-spam protection FAQ</span></span>](anti-spam-protection-faq.md)
