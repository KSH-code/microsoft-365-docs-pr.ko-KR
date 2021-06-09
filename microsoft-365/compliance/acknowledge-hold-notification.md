---
title: 보류 알림 승인
f1.keywords:
- NOCSH
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
ms.custom:
- seo-marvel-apr2020
description: 전자 메일을 통해 법적 보류 Advanced eDiscovery 보내고 추가하고 의무 상태를 모니터링하는 데 사용할 수 있는 방법을 배워야 합니다.
ms.openlocfilehash: 393d8884a4d4d39056267666fdce6a2754cb582b
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034888"
---
# <a name="acknowledge-a-hold-notification"></a><span data-ttu-id="cbc99-103">보류 알림 승인</span><span class="sxs-lookup"><span data-stu-id="cbc99-103">Acknowledge a hold notification</span></span>

<span data-ttu-id="cbc99-104">규제 요청 또는 조사에 응답할 때, 귀하는 ESI(전자적으로 저장된 정보) 및 활성 또는 임박한 법적 사안과 관련이 있을 수 있는 자료를 보존할 의무를 보호자에게 알려야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cbc99-104">When responding to a regulatory request or investigation, you may be required to inform custodians of their obligation to preserve electronically stored information (ESI) and any material that may be relevant to an active or imminent legal matter.</span></span> <span data-ttu-id="cbc99-105">일단 전송된 법률 팀은 각 보호자에 대해 주어진 지침을 수신하고, 읽고, 이해하고, 동의한 것을 알고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cbc99-105">Once sent, legal teams must know that each custodian has received, read, understood, and agreed to follow the given instructions.</span></span>

<span data-ttu-id="cbc99-106">보유자에 대한 후속조치의 시간, 비용 및 노력을 줄이기 위해 Advanced eDiscovery 전자 메일을 통해 법적 보유 알림을 보내고 후속 대응할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cbc99-106">To help reduce the time, cost, and effort of following up with your custodians,  Advanced eDiscovery allows you to send and follow up on legal hold notifications through email.</span></span> <span data-ttu-id="cbc99-107">전자 메일 알림 외에도 각 수장은 개별 규정 준수 포털에 액세스할 수 있어 의무 상태 변경에 대한 정보를 보관할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cbc99-107">In addition to email notices, each custodian will have access to an individualized Compliance Portal, allowing custodians to be kept informed of changes to their obligation status.</span></span>

## <a name="email-notifications"></a><span data-ttu-id="cbc99-108">이메일 알림</span><span class="sxs-lookup"><span data-stu-id="cbc99-108">Email notifications</span></span>

<span data-ttu-id="cbc99-109">법적 보유 알림이 발급된 후 각 보유자는 정의된 법적 보유 고지 및 추가 지침을 포함하는 고유하고 개인 설정된 전자 메일을 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cbc99-109">After a Legal Hold Notification has been issued, each custodian will receive a unique and personalized email containing your defined legal hold notice and added instructions.</span></span> 

> [!TIP]
> <span data-ttu-id="cbc99-110">기본 제공 커뮤니케이션 편집기를 [](using-communications-editor.md) 사용하여 보호자가 공지를 확인하거나 전자 메일에서 직접 규정 준수 포털에 액세스할 수 있도록 하는 방법을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cbc99-110">See how you can use the built-in  [Communication Editor](using-communications-editor.md) to allow your custodians to acknowledge their notice or access their Compliance Portal directly from their email.</span></span>

<span data-ttu-id="cbc99-111">법적 보유 알림의 구성에 따라 보유자는 다음 알림을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cbc99-111">Based on the configuration of your legal hold notification, your custodians may receive the following notices:</span></span> 

- <span data-ttu-id="cbc99-112">**발행 알림:** 첫 번째 알림이 보호자에게 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="cbc99-112">**Issuance notice:** The first notice sent to your custodian.</span></span> <span data-ttu-id="cbc99-113">이 알림에는 메시지 끝에 추가된 발행 지침과 보류 알림이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cbc99-113">This notice will contain your issuance instructions and the hold notice appended to the end of your message.</span></span>

- <span data-ttu-id="cbc99-114">**미리 알림:** 사용하도록 설정하면 지정된 빈도 및 간격에 따라 미리 알림이 보호자에게 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="cbc99-114">**Reminder notice:** If enabled, a reminder notice will be sent to your custodians based on the specified frequency and interval.</span></span> <span data-ttu-id="cbc99-115">미리 알림은 Custodian가 알림을 인정하거나 미리 알림 수가 소진될 때까지 계속 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="cbc99-115">The reminders will continue to be sent either until the custodian has acknowledged their notice or until the number of reminders have been exhausted.</span></span>

- <span data-ttu-id="cbc99-116">**에스컬레이터 알림:** 사용하도록 설정하면 미리 알림이 모두 소진된 후 관리자와 관리자에게 에스컬레이터 알림이 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="cbc99-116">**Escalation notice:** If enabled, an escalation notice will be sent to your custodian and their manager after the reminder notices have been exhausted.</span></span> <span data-ttu-id="cbc99-117">시스템은 지정된 수의 에스컬레이터가 완료되거나 보유자에 보류 알림을 인정할 때까지 에스컬레이터 알림을 자동으로 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="cbc99-117">The system will automatically send escalation notices until the specified number of escalations have been completed or until the custodian acknowledges their hold notification.</span></span>

- <span data-ttu-id="cbc99-118">**다시 알림:** 조사하는 동안 보류 알림의 내용이 업데이트될 경우 업데이트된 알림이 자동으로 보유자에게 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="cbc99-118">**Reissue notice:** During the course of an investigation, if the contents of the hold notice are updated, then the updated notice will automatically be sent to the custodian.</span></span>

- <span data-ttu-id="cbc99-119">**릴리스 알림:** 이 경우, 양도인이 릴리스될 때 릴리스 알림이 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="cbc99-119">**Release notice:** When a custodian is released from the case, they'll be sent the release notice.</span></span> 

## <a name="compliance-portal"></a><span data-ttu-id="cbc99-120">준수 포털</span><span class="sxs-lookup"><span data-stu-id="cbc99-120">Compliance Portal</span></span>

<span data-ttu-id="cbc99-121">전자 메일 알림 외에도 각 관리자는 고유한 준수 포털에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cbc99-121">In addition to the email notifications, each custodian will have access to a unique Compliance Portal.</span></span> <span data-ttu-id="cbc99-122">포털을 통해 각 보유자들은 활성 보류 알림을 보고, 액세스하고, 인정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cbc99-122">Through the portal, each custodian can view, access, and acknowledge their active hold notifications.</span></span>

![규제자용 규정 준수 포털](../media/CustodianPortal.jpg)
