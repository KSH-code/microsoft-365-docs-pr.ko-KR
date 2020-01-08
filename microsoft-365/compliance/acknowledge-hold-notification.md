---
title: 보류 알림 승인
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 법적 조사의 일환으로 전자적으로 저장 된 정보를 보존 하도록 custodians에 게 알려야 할 수도 있습니다. Advanced eDiscovery를 사용 하면 보존 알림 프로세스를 쉽게 관리할 수 있습니다.
ms.openlocfilehash: 477396e9b249de0edbbe52c5310abe21a825a3e8
ms.sourcegitcommit: 8ac1b6586678035050fc422e6fb503fa478be397
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/07/2020
ms.locfileid: "40962374"
---
# <a name="acknowledge-a-hold-notification"></a><span data-ttu-id="cf72a-104">보류 알림 승인</span><span class="sxs-lookup"><span data-stu-id="cf72a-104">Acknowledge a hold notification</span></span>

<span data-ttu-id="cf72a-105">규정 요구 사항 또는 조사에 응답할 때 custodians에 게 알려야 하 고, ESI (전자적으로 저장 된 정보)를 보존 하 고, 활성 또는 즉시 법적 관계와 관련이 있을 수 있는 모든 자료를 유지 해야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf72a-105">When responding to a regulatory request or investigation, you may be required to inform custodians of their obligation to preserve electronically stored information (ESI) and any material that may be relevant to an active or imminent legal matter.</span></span> <span data-ttu-id="cf72a-106">합법적인 팀은 보낸 후에는 각 custodian에 게 제공 된 지침을 따르고, 읽고, 이해 하 고 동의한 것을 알아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf72a-106">Once sent, legal teams must know that each custodian has received, read, understood, and agreed to follow the given instructions.</span></span>

<span data-ttu-id="cf72a-107">Custodians의 시간, 비용 및 노력을 줄이기 위해 고급 eDiscovery를 사용 하면 전자 메일을 통해 법적 보존 알림을 주고 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf72a-107">To help reduce the time, cost, and effort of following up with your custodians,  Advanced eDiscovery allows you to send and follow up on legal hold notifications through email.</span></span> <span data-ttu-id="cf72a-108">전자 메일 알림 외에도 각 custodian는 개별화 준수 포털에 액세스할 수 있으며,이를 통해 custodians가 의무 상태 변경 사항에 대 한 알림을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf72a-108">In addition to email notices, each custodian will have access to an individualized Compliance Portal, allowing custodians to be kept informed of changes to their obligation status.</span></span>

## <a name="email-notifications"></a><span data-ttu-id="cf72a-109">이메일 알림</span><span class="sxs-lookup"><span data-stu-id="cf72a-109">Email notifications</span></span>

<span data-ttu-id="cf72a-110">법적 보존 알림이 발급 된 후에는 각 custodian에 정의 된 법적 보존 공지와 지침이 추가 된 고유한 개인 설정 전자 메일이 수신 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf72a-110">After a Legal Hold Notification has been issued, each custodian will receive a unique and personalized email containing your defined legal hold notice and added instructions.</span></span> 

> [!TIP]
> <span data-ttu-id="cf72a-111">기본 제공 [통신 편집기](using-communications-editor.md) 를 사용 하 여 custodians에서 해당 알림을 승인 하거나 전자 메일에서 직접 준수 포털에 액세스 하도록 하는 방법을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="cf72a-111">See how you can use the built-in  [Communication Editor](using-communications-editor.md) to allow your custodians to acknowledge their notice or access their Compliance Portal directly from their email.</span></span>

<span data-ttu-id="cf72a-112">법적 보존 알림 구성에 따라 custodians에 다음과 같은 알림이 표시 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf72a-112">Based on the configuration of your legal hold notification, your custodians may receive the following notices:</span></span> 

- <span data-ttu-id="cf72a-113">**발급 알림:** Custodian로 전송 되는 첫 번째 알림입니다.</span><span class="sxs-lookup"><span data-stu-id="cf72a-113">**Issuance notice:** The first notice sent to your custodian.</span></span> <span data-ttu-id="cf72a-114">이 경고에는 사용자의 발급 지침 및 메시지 끝에 추가 알림 메시지가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf72a-114">This notice will contain your issuance instructions and the hold notice appended to the end of your message.</span></span>

- <span data-ttu-id="cf72a-115">**미리 알림 알림:** 이 옵션을 설정 하면 지정 된 빈도 및 간격에 따라 미리 알림 알림이 custodians로 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf72a-115">**Reminder notice:** If enabled, a reminder notice will be sent to your custodians based on the specified frequency and interval.</span></span> <span data-ttu-id="cf72a-116">미리 알림은 custodian가 알림을 승인할 때까지 또는 미리 알림 수가 모두 소모 될 때까지 계속 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf72a-116">The reminders will continue to be sent either until the custodian has acknowledged their notice or until the number of reminders have been exhausted.</span></span>

- <span data-ttu-id="cf72a-117">**에스컬레이션 알림:** 이 옵션을 설정 하면 미리 알림 알림이 모두 사용 된 후에는 custodian 및 관리자에 게 에스컬레이션 알림이 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf72a-117">**Escalation notice:** If enabled, an escalation notice will be sent to your custodian and their manager after the reminder notices have been exhausted.</span></span> <span data-ttu-id="cf72a-118">시스템은 지정 된 에스컬레이션 수가 완료 되거나 custodian가 해당 보존 알림을 승인 하기 전까지 에스컬레이션 알림을 자동으로 전송 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf72a-118">The system will automatically send escalation notices until the specified number of escalations have been completed or until the custodian acknowledges their hold notification.</span></span>

- <span data-ttu-id="cf72a-119">**재발급 알림:** 조사를 진행 하는 동안 보존 공지의 내용이 업데이트 되 면 업데이트 된 공지가 자동으로 custodian로 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf72a-119">**Reissue notice:** During the course of an investigation, if the contents of the hold notice are updated, then the updated notice will automatically be sent to the custodian.</span></span>

- <span data-ttu-id="cf72a-120">**릴리스 알림:** Custodian이 사례에서 해제 되 면 릴리스 알림을 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf72a-120">**Release notice:** When a custodian is released from the case, they'll be sent the release notice.</span></span> 

## <a name="compliance-portal"></a><span data-ttu-id="cf72a-121">준수 포털</span><span class="sxs-lookup"><span data-stu-id="cf72a-121">Compliance Portal</span></span>

<span data-ttu-id="cf72a-122">전자 메일 알림 외에도 각 custodian는 고유한 준수 포털에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf72a-122">In addition to the email notifications, each custodian will have access to a unique Compliance Portal.</span></span> <span data-ttu-id="cf72a-123">포털을 통해 각 custodian은 활성 보류 알림을 보고, 액세스 하 고, 승인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf72a-123">Through the portal, each custodian can view, access, and acknowledge their active hold notifications.</span></span>

![Custodian에 대 한 준수 포털](media/CustodianPortal.jpg)
