---
title: 외부 전자 메일 전달, 자동 전달, 5.7.520 액세스 거부, 외부 전달을 사용 하지 않도록 설정, 관리자가 외부 전달을 사용 하지 않도록 설정, 아웃 바운드 스팸 방지 정책
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 07/01/2020
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: .
ms.openlocfilehash: c0a3849d330b508630eb60c7ee24cd8b498a32b8
ms.sourcegitcommit: 260c69fa31a898428d51cfdbd762c5f0213c403c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/10/2020
ms.locfileid: "48417235"
---
# <a name="configuring-external-email-forwarding-in-office-365"></a><span data-ttu-id="0d6c0-103">Office 365에서 외부 전자 메일 전달 구성</span><span class="sxs-lookup"><span data-stu-id="0d6c0-103">Configuring external email forwarding in Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="0d6c0-104">외부 전달은 *아웃 바운드 스팸 방지 정책* 에 의해 제어 되며 구성 된 설정에 따라 사용자에 게 범위가 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0d6c0-104">External forwarding is controlled by the *outbound anti-spam policy* and scoped to users based on the configured setting.</span></span> <span data-ttu-id="0d6c0-105">현재 3 개의 설정이 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0d6c0-105">Currently 3 settings are supported:</span></span>

- <span data-ttu-id="0d6c0-106">**자동** – 시스템이 제어 되며, 아웃 바운드 스팸 필터링을 통해 자동 외부 전자 메일 전달을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d6c0-106">**Automatic** – This is system-controlled: It allows outbound spam filtering to control automatic external email forwarding.</span></span> <span data-ttu-id="0d6c0-107">기본 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="0d6c0-107">This is the default setting.</span></span>

- <span data-ttu-id="0d6c0-108">**설정** – 자동 외부 전달은 허용 되며 제한 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0d6c0-108">**On** – Automatic external forwarding is allowed and not restricted.</span></span>

- <span data-ttu-id="0d6c0-109">**Off** -자동 외부 전달은 사용 하지 않도록 설정 되며 최종 사용자에 게 NDR (배달 못 함 보고서)이 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0d6c0-109">**Off** – Automatic external forwarding is disabled and will result in a Non-delivery report (NDR) to the end user.</span></span>

<span data-ttu-id="0d6c0-110">이러한 설정을 구성 하는 방법에 대 한 자세한 내용은 [EOP에서 아웃 바운드 스팸 필터링 구성을](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-the-outbound-spam-policy?view=o365-worldwide&preserve-view=true) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0d6c0-110">See [Configure outbound spam filtering in EOP](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-the-outbound-spam-policy?view=o365-worldwide&preserve-view=true) for more information on how to configure these settings.</span></span>

> [!NOTE]
> <span data-ttu-id="0d6c0-111">자동 전달을 사용 하지 않도록 설정 하면 메시지를 외부 주소로 리디렉션하는 받은 편지함 규칙도 사용 하지 않도록 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0d6c0-111">Disabling automatic forwarding will also disable Inbox rules that redirect messages to external addresses.</span></span>

## <a name="controlling-external-email-forwarding"></a><span data-ttu-id="0d6c0-112">외부 전자 메일 전달 제어</span><span class="sxs-lookup"><span data-stu-id="0d6c0-112">Controlling external email forwarding</span></span>

<span data-ttu-id="0d6c0-113">조직의 관리자는 받은 편지함 규칙 또는 SMTP 전달을 사용 하 여 전자 메일을 자동으로 전달할 수 있는 사용자를 제한 하거나 제어 하기 위한 회사 요구 사항이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d6c0-113">As an admin of an organization you may have company requirements to restrict or control who is able to automatically forward emails using inbox rules, or SMTP forwarding, outside of the organization.</span></span> <span data-ttu-id="0d6c0-114">전자 메일 전달은 유용한 기능 일 수 있지만 조직이 나 파트너를 공격 하는 데 활용할 수 있는 공격자에 게 정보를 제공 하는 경우에도 정보 노출을 초래할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d6c0-114">Email forwarding can be a useful feature, but can also pose a risk through the potential disclosure of information, even by providing information to attackers that can be leveraged to attack the organization or its partners.</span></span>

<span data-ttu-id="0d6c0-115">Office 365에서는 받은 편지함 규칙 또는 메일 상자 구성에서 자동 외부 전달을 허용 하지 않으므로 보안 기본 정책을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d6c0-115">Office 365 doesn't allow automatic external forwarding by either Inbox rules or mail box configuration, which provides a secure default policy.</span></span> <span data-ttu-id="0d6c0-116">그러나 관리자는 조직의 모든 사용자 또는 일부에 대해 이러한 설정을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d6c0-116">However, the admin can modify these settings for all, or some, users in the organization.</span></span> <span data-ttu-id="0d6c0-117">내부 사용자 간에 메시지를 전달 하는 것은 이러한 수정의 영향을 받지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0d6c0-117">Forwarding messages between internal users isn't affected by such a modification.</span></span>

> [!NOTE]
> <span data-ttu-id="0d6c0-118">Office 365에서 외부 주소로 자동 전달을 사용 하지 않도록 설정 하는 작업은 [메시지가 센터](https://admin.microsoft.com/Adminportal/Home?source=applauncher&ref=/MessageCenter) 게시물을 통해 전달 되는 세부 정보와 함께 단계별로 진행 되 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d6c0-118">Disabling automatic forwarding to external addresses in Office 365 is being rolled out in phases with details communicated via [Message Center](https://admin.microsoft.com/Adminportal/Home?source=applauncher&ref=/MessageCenter) posts.</span></span> <span data-ttu-id="0d6c0-119">관리자가 이러한 변경 내용을 준비할 수 있도록 하기 위해 사용자에 게 중단이 발생 하지 않도록 사전에 정책을 수정 하 게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0d6c0-119">To help administrators prepare for these changes have them modify policies ahead of time to ensure there is no disruption to their users.</span></span>

<span data-ttu-id="0d6c0-120">조직에서 자동 전달 (받은 편지함 규칙 또는 SMTP 전달)을 사용 하는 사용자에 대 한 자세한 내용은 [자동 전달 메시지 보고서](https://docs.microsoft.com/microsoft-365/security/office-365-security/mfi-auto-forwarded-messages-report?view=o365-worldwide&preserve-view=true)에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d6c0-120">More information about users that are using automatic forwarding (inbox rules or SMTP forwarding) in your organization can be found in the [auto-forwarded messages report](https://docs.microsoft.com/microsoft-365/security/office-365-security/mfi-auto-forwarded-messages-report?view=o365-worldwide&preserve-view=true).</span></span>

## <a name="how-does-this-policy-work-with-other-automatic-forwarding-controls"></a><span data-ttu-id="0d6c0-121">이 정책이 다른 자동 전달 컨트롤에서 작동 하는 방식</span><span class="sxs-lookup"><span data-stu-id="0d6c0-121">How does this policy work with other automatic forwarding controls</span></span>

<span data-ttu-id="0d6c0-122">관리자는 [원격 도메인](https://docs.microsoft.com/exchange/mail-flow-best-practices/remote-domains/remote-domains) 의 자동 전달을 차단 하 고 Etr (Exchange 전송 규칙) 사용과 같은 다른 유형의 컨트롤을 이미 배치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d6c0-122">As an admin, you may already have other types of controls in place, such blocking automatic forwarding in [remote domains](https://docs.microsoft.com/exchange/mail-flow-best-practices/remote-domains/remote-domains) and the use of an Exchange Transport Rule (ETR).</span></span> <span data-ttu-id="0d6c0-123">원격 도메인에 대해 자동 전달을 허용 하지만 아웃 바운드 스팸 정책을 통한 자동 전달을 차단 하는 경우에는 이러한 두 컨트롤이이 특정 기능에 독립적입니다.</span><span class="sxs-lookup"><span data-stu-id="0d6c0-123">Both of these controls are independent of this particular feature, for example if you allow automatic forwarding for a remote domain, but block automatic forwarding via the outbound spam policy the result will be that the automatically forwarded message is blocked.</span></span> <span data-ttu-id="0d6c0-124">마찬가지로, 아웃 바운드 스팸 정책에서 자동 전달을 허용 하지만 ETR 또는 원격 도메인에서 메시지를 차단 하는 경우에는 이러한 컨트롤 중 하나에 의해 메시지가 차단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0d6c0-124">Similarly if you allow automatic forwarding in the outbound spam policy but block it in an ETR or remote domain then the message will be blocked by either of these controls.</span></span> <span data-ttu-id="0d6c0-125">예를 들어 아웃 바운드 스팸 정책에서 자동 전달을 허용 하 고 원격 도메인을 이용 하 여 사용자가 메시지를 자동으로 전달할 수 있는 도메인을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d6c0-125">This allows you to, for example, allow automatic forwarding in the outbound spam policy and utilize remote domains to control the domains that users can automatic forward messages to.</span></span>


## <a name="the-blocked-email-forwarding-message"></a><span data-ttu-id="0d6c0-126">차단 된 전자 메일 전달 메시지</span><span class="sxs-lookup"><span data-stu-id="0d6c0-126">The blocked email forwarding message</span></span>

<span data-ttu-id="0d6c0-127">메시지가 자동으로 전달 되는 것으로 감지 되 고 조직 정책에서 해당 활동을 *차단* 하는 **배달 못 함 보고서 (NDR)** 가 최종 사용자에 게 다시 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0d6c0-127">When a message is detected as automatically forwarded and the organizational policy *blocks* that activity a **Non-delivery report (NDR)** will be generated back to the end user.</span></span> <span data-ttu-id="0d6c0-128">보고서에서 메시지가 배달 되지 않았음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0d6c0-128">The report will indicate the message was not delivered.</span></span> <span data-ttu-id="0d6c0-129">NDR의 형식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0d6c0-129">The NDR will have the following format:</span></span> 

`5.7.520 Access Denied – Your administrator has disabled external forwarding – AS(XXXX)`
