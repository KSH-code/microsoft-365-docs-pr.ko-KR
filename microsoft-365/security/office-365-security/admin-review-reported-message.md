---
title: 보고된 메시지에 대한 관리자 검토
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
audience: Admin
ms.topic: how-to
localization_priority: Normal
ms.collection:
- M365-security-compliance
description: 보고된 메시지를 검토하고 사용자에게 피드백을 주는 방법을 배워야 합니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 7386f5b283e2bfabb76eee91d33dfda0e42ec7b1
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2021
ms.locfileid: "52769128"
---
# <a name="admin-review-for-reported-messages"></a><span data-ttu-id="61c74-103">보고된 메시지에 대한 관리자 검토</span><span class="sxs-lookup"><span data-stu-id="61c74-103">Admin review for reported messages</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!NOTE]
> <span data-ttu-id="61c74-104">이 문서의 정보는 상업적으로 출시되기 전에 상당수 수정될 수 있는 미리 보기 제품과 관련이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61c74-104">The information in this article relates to a preview product that may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="61c74-105">이 문서는 평가 및 탐색 목적으로만 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="61c74-105">This document is provided for evaluation and exploration purposes only.</span></span>

<span data-ttu-id="61c74-106">**적용 대상**</span><span class="sxs-lookup"><span data-stu-id="61c74-106">**Applies to**</span></span>
- [<span data-ttu-id="61c74-107">Office 365용 Microsoft Defender 플랜 1 및 플랜 2</span><span class="sxs-lookup"><span data-stu-id="61c74-107">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="61c74-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="61c74-108">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="61c74-109">Microsoft 365 사서함이 Exchange Online 및 Microsoft Defender for Office 365 조직에서 관리자는 이제 보고된 메시지를 검토한 후 템플릿 기반 메시지를 최종 사용자에게 다시 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61c74-109">In Microsoft 365 organizations with Exchange Online mailboxes and Microsoft Defender for Office 365, admins can now send templated messages back to end users after they review reported messages.</span></span> <span data-ttu-id="61c74-110">이는 조직에 맞게 사용자 지정하고 관리자의 판결에 따라 사용자 지정될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61c74-110">This can be customized for your organization and based on your admin’s verdict as well.</span></span>

<span data-ttu-id="61c74-111">이 기능은 사용자에게 피드백을 제공하도록 설계되지만 시스템의 메시지에 대한 판정은 변경되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="61c74-111">This feature is designed to give feedback to your users but does not change the verdicts of messages in the system.</span></span> <span data-ttu-id="61c74-112">Microsoft에서 필터를 업데이트하고 개선할 수 있도록 관리자 제출을 사용하여 분석을 위해 메시지를 [제출해야 합니다.](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="61c74-112">To help Microsoft update and improve its filters, you will need to submit messages for analysis using [Admin submission](admin-submission.md).</span></span>

<span data-ttu-id="61c74-113">메시지가 가음성 또는 가음성으로 보고된 경우 검토 결과를 표시하고 사용자에게 [알릴 수만 있습니다.](report-false-positives-and-false-negatives.md)</span><span class="sxs-lookup"><span data-stu-id="61c74-113">You will only be able to mark and notify users of review results if the message was reported as a [false positives or false negatives](report-false-positives-and-false-negatives.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="61c74-114">시작하기 전에 알아야 할 내용은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="61c74-114">What do you need to know before you begin?</span></span>

- <span data-ttu-id="61c74-115">사용자 제출에 대한 구성을 수정하려면 다음 역할 그룹 중 하나의 구성원이 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="61c74-115">To modify the configuration for User submissions, you need to be a member of one of the following role groups:</span></span>
  - <span data-ttu-id="61c74-116">Microsoft 365 보안 센터의 [조직 관리 또는 보안 관리자](permissions-microsoft-365-security-center.md)</span><span class="sxs-lookup"><span data-stu-id="61c74-116">Organization Management or Security Administrator in the [Microsoft 365 security center](permissions-microsoft-365-security-center.md).</span></span>
  - <span data-ttu-id="61c74-117">에서 조직 [Exchange Online.](/Exchange/permissions-exo/permissions-exo)</span><span class="sxs-lookup"><span data-stu-id="61c74-117">Organization Management in [Exchange Online](/Exchange/permissions-exo/permissions-exo).</span></span>

- <span data-ttu-id="61c74-118">PowerShell을 사용하려면 Exchange Online 액세스해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="61c74-118">You'll also need access to the Exchange Online PowerShell.</span></span> <span data-ttu-id="61c74-119">사용하려는 계정이 Exchange Online PowerShell에 액세스할 수 없는 경우 도메인에 전자 메일 주소 지정 을 입력하는 오류가 *표시됩니다.*</span><span class="sxs-lookup"><span data-stu-id="61c74-119">If the account that you're trying to use doesn't have access to Exchange Online PowerShell, you'll receive an error that says *Specify an email address in your domain*.</span></span> <span data-ttu-id="61c74-120">PowerShell에 대한 액세스를 활성화하거나 Exchange Online 자세한 내용은 다음 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="61c74-120">For more information about enabling or disabling access to Exchange Online PowerShell, see the following topics:</span></span>
  - [<span data-ttu-id="61c74-121">PowerShell에 대한 액세스 Exchange Online 사용 또는 사용 안 하도록 설정</span><span class="sxs-lookup"><span data-stu-id="61c74-121">Enable or disable access to Exchange Online PowerShell</span></span>](/powershell/exchange/disable-access-to-exchange-online-powershell)
  - [<span data-ttu-id="61c74-122">클라이언트 액세스 규칙의 Exchange Online</span><span class="sxs-lookup"><span data-stu-id="61c74-122">Client Access Rules in Exchange Online</span></span>](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules)

## <a name="configure-the-messages-used-to-notify-users"></a><span data-ttu-id="61c74-123">사용자에게 알리는 데 사용되는 메시지 구성</span><span class="sxs-lookup"><span data-stu-id="61c74-123">Configure the messages used to notify users</span></span>

1. <span data-ttu-id="61c74-124">보안 [Microsoft 365 에서](../defender/overview-security-center.md)정책 정책 & 정책 위협 정책 사용자가 메시지 **설정을** \>  \> **보고했습니다.**</span><span class="sxs-lookup"><span data-stu-id="61c74-124">In the [Microsoft 365 security center](../defender/overview-security-center.md), go to **Policies & rules** \> **Threat policies** \> **User reported message settings**.</span></span>

2. <span data-ttu-id="61c74-125">보낸 사람 표시 이름을 지정하려면 관리자 검토 결과에 대한 **전자 메일 알림 섹션에서** 보낸  사람으로 사용할 Office 365 전자 메일 주소 지정 확인란을 확인하고 사용할 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="61c74-125">If you want to specify the sender display name, check the box for **Specify Office 365 email address to use as sender** under the **Email notifications for admin review results** section, and enter in the name you wish to use.</span></span> <span data-ttu-id="61c74-126">이 전자 메일 주소는 메시지에 표시될 Outlook 위치로 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="61c74-126">This is the email address that will be visible in Outlook and where replies will go to.</span></span>

3. <span data-ttu-id="61c74-127">서식 파일을 사용자 지정하려면 전자 메일 알림 **사용자 지정 을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="61c74-127">If you want to customize any of the templates, click **Customize email notification**.</span></span> <span data-ttu-id="61c74-128">이 플라이아웃에서는 다음만 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61c74-128">In this flyout, you will be able to customize only the following:</span></span>
    - <span data-ttu-id="61c74-129">피싱</span><span class="sxs-lookup"><span data-stu-id="61c74-129">Phishing</span></span>
    - <span data-ttu-id="61c74-130">정크</span><span class="sxs-lookup"><span data-stu-id="61c74-130">Junk</span></span>
    - <span data-ttu-id="61c74-131">위협을 찾을 수 없음</span><span class="sxs-lookup"><span data-stu-id="61c74-131">No threats found</span></span>
    - <span data-ttu-id="61c74-132">인식 교육</span><span class="sxs-lookup"><span data-stu-id="61c74-132">Awareness training</span></span>
    - <span data-ttu-id="61c74-133">바닥글</span><span class="sxs-lookup"><span data-stu-id="61c74-133">Footer</span></span>

4. <span data-ttu-id="61c74-134">작업을 마쳤으면 **저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="61c74-134">When you're finished, click **Save**.</span></span> <span data-ttu-id="61c74-135">이러한 값을 지우려면 사용자 **제출** 페이지에서 삭제를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="61c74-135">To clear these values, click **Discard** on the User submissions page.</span></span>
