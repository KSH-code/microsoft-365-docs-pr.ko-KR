---
title: Exchange Online에서의 안전한 발신자 및 차단된 발신자 목록
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 111ab6b0-2dd2-4a87-a928-4931df6b3c4d
ms.collection:
- M365-security-compliance
description: Exchange Online 또는 EOP (Exchange Online Protection) 관리자는 서비스를 통과 하는 전자 메일 메시지가 스팸으로 표시 되지 않도록 할 수 있습니다. 이 작업을 수행 하는 한 가지 방법은 조직의 사용자에 대해 수신 허용-보낸 사람 및 수신 거부 목록을 만드는 것입니다.
ms.openlocfilehash: 9c281460aeff64226343af5e5608ccf42fc83799
ms.sourcegitcommit: a122fd1fce523171529c7f610bb7faf09d30a8bb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/18/2020
ms.locfileid: "41238395"
---
# <a name="safe-sender-and-blocked-sender-lists-in-exchange-online"></a><span data-ttu-id="d2608-104">Exchange Online에서의 안전한 발신자 및 차단된 발신자 목록</span><span class="sxs-lookup"><span data-stu-id="d2608-104">Safe sender and blocked sender lists in Exchange Online</span></span>

<span data-ttu-id="d2608-105">Exchange Online 또는 EOP (Exchange Online Protection) 관리자는 서비스를 통과 하는 전자 메일 메시지가 스팸으로 표시 되지 않도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2608-105">As an Exchange Online or Exchange Online Protection (EOP) administrator, you can help ensure that an email message traveling through the service isn't marked as spam.</span></span> <span data-ttu-id="d2608-106">이 작업을 수행 하는 한 가지 방법은 조직의 사용자에 대해 수신 허용-보낸 사람 및 수신 거부 목록을 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d2608-106">One way to do this is to create safe sender and blocked sender lists for the people in your organization.</span></span>

<span data-ttu-id="d2608-107">[Office 365에서 전자 메일이 스팸으로 표시 되지 않도록](prevent-email-from-being-marked-as-spam.md)하는 방법에서 이러한 목록을 관리자로 사용 하는 *방법에 대 한 업데이트 된 버전의 팁 및 절차를 참조 하세요* .</span><span class="sxs-lookup"><span data-stu-id="d2608-107">*See the updated version of the tips and procedures for how to work with these lists as an admin in* [How to prevent good email from being marked as spam in Office 365](prevent-email-from-being-marked-as-spam.md).</span></span>

<span data-ttu-id="d2608-108">관리자가 아닌 경우 Outlook에서 수신 허용-보낸 사람 목록을 사용 하 여 자신의 정크 메일을 관리 하려면[정크 메일 필터 개요](https://support.office.com/article/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089)의 단계를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2608-108">If you're not an admin, and you just want to manage your own junk email in Outlook by using a safe sender list, check out the steps in the[Overview of the Junk Email Filter](https://support.office.com/article/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089).</span></span>

## <a name="what-is-the-safe-and-blocked-sender-limits-in-exchange-online"></a><span data-ttu-id="d2608-109">Exchange Online에서 수신 허용 및 차단 된 보낸 사람 제한은 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="d2608-109">What is the safe and blocked sender limits in Exchange Online?</span></span>

<span data-ttu-id="d2608-110">Exchange Online의 수신 및 차단 된 보낸 사람 제한은 Active Directory 및 Outlook 제한과 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="d2608-110">The safe and blocked sender limits in Exchange Online differ from the Active Directory and Outlook limits.</span></span> <span data-ttu-id="d2608-111">해당 지식 영역은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d2608-111">They are:</span></span>

- <span data-ttu-id="d2608-112">수신 허용-보낸 사람 제한: 1024</span><span class="sxs-lookup"><span data-stu-id="d2608-112">Safe sender limit: 1,024</span></span>

- <span data-ttu-id="d2608-113">차단 된 보낸 사람 제한: 500</span><span class="sxs-lookup"><span data-stu-id="d2608-113">Blocked sender limit: 500</span></span>

<span data-ttu-id="d2608-114">참고:</span><span class="sxs-lookup"><span data-stu-id="d2608-114">Note:</span></span>

<span data-ttu-id="d2608-115">[KB2590466](https://support.microsoft.com/help/2590466/you-receive-the-error-junk-e-mail-validation-error-in-outlook-web-app)에 설명 되어 있는 오류가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2608-115">You may experience the error that is described in [KB2590466](https://support.microsoft.com/help/2590466/you-receive-the-error-junk-e-mail-validation-error-in-outlook-web-app).</span></span> <span data-ttu-id="d2608-116">이 문제를 해결 하려면 "내 연락처에서 전자 메일 신뢰" 확인란의 선택을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2608-116">To resolve this issue, clear the "Trust emails from my contacts" check box.</span></span> <span data-ttu-id="d2608-117">또는 "MaxSafeSenders" 특성에 대해 설정 된 Exchange Online에서 허용 되는 최대 제한인 1024에 표시 되도록 기본 연락처 폴더에 있는 전자 메일 주소 크기를 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2608-117">Alternatively, decrease the amount of email addresses that are in your default Contacts folder to bring it within the maximum allowed limit of 1024 in Exchange Online that is set for "MaxSafeSenders" attribute.</span></span> <span data-ttu-id="d2608-118">이 특성 및 사서함 cmdlet에 대 한 자세한 내용은 다음 항목을 slmgr.vbs.</span><span class="sxs-lookup"><span data-stu-id="d2608-118">For more information about this attribute and the Set-Mailbox cmdlet, seethe following topic:</span></span>

[<span data-ttu-id="d2608-119">Set-Mailbox</span><span class="sxs-lookup"><span data-stu-id="d2608-119">Set-Mailbox</span></span>](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Set-Mailbox)

## <a name="see-also"></a><span data-ttu-id="d2608-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d2608-120">See also</span></span>

[<span data-ttu-id="d2608-121">Exchange Server의 보낸 사람 필터링</span><span class="sxs-lookup"><span data-stu-id="d2608-121">Sender filtering in Exchange Server</span></span>](https://docs.microsoft.com/exchange/antispam-and-antimalware/antispam-protection/sender-filtering)
