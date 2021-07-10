---
title: 사용자에 대한 스케줄러 Microsoft 365.
ms.author: v-aiyengar
author: AshaIyengar21
manager: serdars
audience: Admin
ms.topic: article
ms.service: scheduler
localization_priority: Normal
description: 사용자에 대한 스케줄러 Microsoft 365.
ms.openlocfilehash: 924b25e3d921f402c97632f7475ed5beea98d5c7
ms.sourcegitcommit: f7fbf45af64c5c0727fd5eaab309d20ad097a483
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/09/2021
ms.locfileid: "53362549"
---
# <a name="setting-up-scheduler-for-microsoft-365"></a><span data-ttu-id="c8be4-103">Microsoft 365용 스케줄러 설정</span><span class="sxs-lookup"><span data-stu-id="c8be4-103">Setting up Scheduler for Microsoft 365</span></span>


<span data-ttu-id="c8be4-104">다음의 선행 Microsoft 365 스케줄러를 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8be4-104">To set up the Scheduler for Microsoft 365, following are the prerequisites:</span></span>

| <span data-ttu-id="c8be4-105">필요한 것</span><span class="sxs-lookup"><span data-stu-id="c8be4-105">What do I need?</span></span> | <span data-ttu-id="c8be4-106">설명</span><span class="sxs-lookup"><span data-stu-id="c8be4-106">Description</span></span> |
|-------------------|-------------|
|<span data-ttu-id="c8be4-107">Cortana 사서함</span><span class="sxs-lookup"><span data-stu-id="c8be4-107">Cortana mailbox</span></span> |<span data-ttu-id="c8be4-108">테넌트 관리자는 "Cortana" 사서함(즉, cortana@yourdomain.com) 역할을 하게 cortana@yourdomain.com.</span><span class="sxs-lookup"><span data-stu-id="c8be4-108">Tenant admins will need to set a mailbox to serve as the “Cortana” mailbox (that is, cortana@yourdomain.com).</span></span>         |
|<span data-ttu-id="c8be4-109">Exchange Online 사서함</span><span class="sxs-lookup"><span data-stu-id="c8be4-109">Exchange Online mailbox</span></span> |<span data-ttu-id="c8be4-110">사용자에게 메일 및 Exchange Online 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8be4-110">Users must have an Exchange Online mail and calendar</span></span>         |
|<span data-ttu-id="c8be4-111">스케줄러 라이선스</span><span class="sxs-lookup"><span data-stu-id="c8be4-111">Scheduler license</span></span> |<span data-ttu-id="c8be4-112">라이선스 및 가격 정보는 에 대한 [스케줄러를 Microsoft 365.](https://www.microsoft.com/en-us/microsoft-365/meeting-scheduler-pricing)</span><span class="sxs-lookup"><span data-stu-id="c8be4-112">For licensing and pricing information, see [Scheduler for Microsoft 365](https://www.microsoft.com/en-us/microsoft-365/meeting-scheduler-pricing).</span></span>        |

## <a name="create-a-mailbox-for-cortana"></a><span data-ttu-id="c8be4-113">사용자 사서함을 Cortana</span><span class="sxs-lookup"><span data-stu-id="c8be4-113">Create a mailbox for Cortana</span></span>

<span data-ttu-id="c8be4-114">테넌트의 Exchange 사서함은 테넌트의 Cortana 사서함 역할을 하여 테넌트와 전자 메일을 보내고 받을 Cortana.</span><span class="sxs-lookup"><span data-stu-id="c8be4-114">An Exchange mailbox in your tenant acts as the Cortana mailbox for your tenant to send and receive emails to and from Cortana.</span></span> <span data-ttu-id="c8be4-115">모든 전자 메일이 Cortana 정책에 따라 테넌트의 Cortana 사서함에 보존됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8be4-115">All emails sent to Cortana are retained in your tenant’s Cortana mailbox based on your retention policy.</span></span>

- <span data-ttu-id="c8be4-116">사용자 Microsoft 365 관리 센터 사서함을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8be4-116">Use the Microsoft 365 admin center to create a user mailbox.</span></span> <span data-ttu-id="c8be4-117">30일 보존 정책이 권장됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8be4-117">A 30-day retention policy is recommended.</span></span> 
- <span data-ttu-id="c8be4-118">사서함의 Cortana SMTP 주소에 있는 이름을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="c8be4-118">Use the name Cortana in your mailbox’s primary SMTP address.</span></span> <span data-ttu-id="c8be4-119">"Cortana@yourdomain.com, 'CortanaScheduler@contoso.com' 또는 'Cortana. Scheduler@yourdomain.com 권장됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8be4-119">Names such as “Cortana@yourdomain.com,’ ‘CortanaScheduler@contoso.com,’ or ‘Cortana.Scheduler@yourdomain.com’ are recommended.</span></span>

## <a name="designate-the-mailbox-as-the-scheduler-assistant"></a><span data-ttu-id="c8be4-120">사서함을 스케줄러 도우미로 지정</span><span class="sxs-lookup"><span data-stu-id="c8be4-120">Designate the mailbox as the Scheduler Assistant</span></span>

<span data-ttu-id="c8be4-121">사용자 지정 스케줄러에 Cortana 사서함을 만든 후 공식적으로 사서함을 Microsoft 365 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8be4-121">After a unique mailbox for Cortana Scheduler has been created, you must designate the mailbox to Microsoft 365 formally.</span></span> <span data-ttu-id="c8be4-122">사용자 Cortana 사서함을 지정한 후 사용자를 대신하여 모임을 예약할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8be4-122">After you designate the Cortana Scheduler mailbox, it will be available to schedule meetings on behalf of your users.</span></span>

<span data-ttu-id="c8be4-123">예약된 Cortana 지정하려면 권한이 부여된 관리자가 한 줄 PowerShell 명령을 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8be4-123">To designate the Cortana Scheduler mailbox, an authorized admin must run a one-line PowerShell command.</span></span> 

1. <span data-ttu-id="c8be4-124">커넥트 Microsoft 365 원격 PowerShell 실행 공간을 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8be4-124">Connect to Microsoft 365 remote PowerShell run space for your organization.</span></span>

2. <span data-ttu-id="c8be4-125">다음 PowerShell 스크립트를 실행하여 스케줄러에 대한 사서함을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c8be4-125">Run the following PowerShell script to designate the mailbox for Scheduler:</span></span>

    ```powershell
    Set-mailbox cortana@contoso.com -SchedulerAssistant:$true
    ```
    
    <span data-ttu-id="c8be4-126">Cortana 스케줄러 사서함에서 이 "설정" 명령을 실행하면 사서함에 새 "PersistedCapability"가 설정되어 이 사서함이 "SchedulerAssistant"입니다.</span><span class="sxs-lookup"><span data-stu-id="c8be4-126">After running this "set" command on the Cortana Scheduler mailbox, a new "PersistedCapability" is set on the mailbox to note that this mailbox is the "SchedulerAssistant".</span></span>

> [!NOTE]
> <span data-ttu-id="c8be4-127">이전에 수행하지 않은 경우 PowerShell로 조직을 연결하기 위해 다음 커넥트 [Microsoft 365 수행합니다.](../enterprise/connect-to-microsoft-365-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="c8be4-127">Follow these steps to connect your organization to PowerShell if you’ve not done so previously: [Connect to Microsoft 365 with PowerShell](../enterprise/connect-to-microsoft-365-powershell.md).</span></span>

<span data-ttu-id="c8be4-128">조직에서 현재 일정 예약자 도우미로 설정된 사서함을 Cortana get 함수를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c8be4-128">To discover which mailbox in your organization is currently set as the Cortana Scheduler assistant, run the get function:</span></span>

```powershell
Get-mailbox | where {$_.PersistedCapabilities -Match "SchedulerAssistant"}
```

> [!IMPORTANT]
> <span data-ttu-id="c8be4-129">Scheduler 사서함이 전체 프로비전을 완료하여 SchedulerAssistant 기능을 설정하는 데 최대 2시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8be4-129">It might take up to two hours for the Scheduler mailbox to complete full provisioning to set the SchedulerAssistant capability.</span></span>

## <a name="exchange-online-mailbox"></a><span data-ttu-id="c8be4-130">Exchange Online 사서함</span><span class="sxs-lookup"><span data-stu-id="c8be4-130">Exchange Online mailbox</span></span>
<span data-ttu-id="c8be4-131">스케줄러 라이선스는 모임 이끌이가 모임 예약 Microsoft 365 일정 작업을 스케줄러 도우미에 위임할 수 있도록 하는 추가 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="c8be4-131">A Scheduler license is an add-on to Microsoft 365, that enables the meeting organizer to delegate their meeting scheduling tasks to their Scheduler assistant.</span></span> <span data-ttu-id="c8be4-132">일반적으로 예약 라이선스를 통해 스케줄러가 Microsoft 365 모임 이끌이에게는 다음 구성 요소가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="c8be4-132">For the Scheduler to work, typically through Microsoft 365 license, meeting organizers require the following components:</span></span>

- <span data-ttu-id="c8be4-133">스케줄러 도우미 사서함으로 지정된 사서함</span><span class="sxs-lookup"><span data-stu-id="c8be4-133">A mailbox designated as Scheduler assistant mailbox</span></span>
- <span data-ttu-id="c8be4-134">스케줄러 라이선스</span><span class="sxs-lookup"><span data-stu-id="c8be4-134">Scheduler license</span></span>
- <span data-ttu-id="c8be4-135">Exchange Online 사서함 및 일정</span><span class="sxs-lookup"><span data-stu-id="c8be4-135">Exchange Online mailbox and calendar</span></span>

<span data-ttu-id="c8be4-136">모임 참석자에는 Scheduler 또는 Microsoft 365 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c8be4-136">The meeting attendees do not require Scheduler or Microsoft 365 license.</span></span>

## <a name="scheduler-end-user-license-requirements"></a><span data-ttu-id="c8be4-137">스케줄러 최종 사용자 라이선스 요구 사항</span><span class="sxs-lookup"><span data-stu-id="c8be4-137">Scheduler end-user license requirements</span></span>

<span data-ttu-id="c8be4-138">스케줄러 라이선스에는 다음 라이선스 중 하나가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="c8be4-138">A Scheduler license requires one of the following licenses:</span></span>

- <span data-ttu-id="c8be4-139">Microsoft 365 E3, A3, E5, A5</span><span class="sxs-lookup"><span data-stu-id="c8be4-139">Microsoft 365 E3, A3, E5, A5</span></span>
- <span data-ttu-id="c8be4-140">Business Basic, Business, Business Standard, Business Premium</span><span class="sxs-lookup"><span data-stu-id="c8be4-140">Business Basic, Business, Business Standard, Business Premium</span></span>
- <span data-ttu-id="c8be4-141">Office 365 E1, A1, E3, A3, E5, A5</span><span class="sxs-lookup"><span data-stu-id="c8be4-141">Office 365 E1, A1, E3, A3, E5, A5</span></span>
- <span data-ttu-id="c8be4-142">Business Essentials, Business Premium</span><span class="sxs-lookup"><span data-stu-id="c8be4-142">Business Essentials, Business Premium</span></span>
- <span data-ttu-id="c8be4-143">Exchange Online 계획 1 또는 계획 2 라이선스.</span><span class="sxs-lookup"><span data-stu-id="c8be4-143">Exchange Online Plan 1 or Plan 2 license.</span></span> 

> [!Note]

> <span data-ttu-id="c8be4-144">Microsoft 365 대한 스케줄러는 영어로만 전 세계 다중 테넌트 환경에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8be4-144">Scheduler for Microsoft 365 is available in worldwide multi-tenant environments in English only.</span></span> <span data-ttu-id="c8be4-145">**다음 Microsoft 365** 사용자에 대한 스케줄러를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c8be4-145">**Scheduler for Microsoft 365** isn't available to users of:</span></span>

- <span data-ttu-id="c8be4-146">Microsoft 365 21Vianet에서 운영하는 중국</span><span class="sxs-lookup"><span data-stu-id="c8be4-146">Microsoft 365 operated by 21Vianet in China</span></span>
- <span data-ttu-id="c8be4-147">Microsoft 365 수탁자 German Telekom을 사용하는 독일 클라우드와 함께 사용</span><span class="sxs-lookup"><span data-stu-id="c8be4-147">Microsoft 365 with German cloud that uses the data trustee German Telekom</span></span>
- <span data-ttu-id="c8be4-148">정부 클라우드(GCC, 소비자, GCC High 또는 DoD 포함)</span><span class="sxs-lookup"><span data-stu-id="c8be4-148">Government cloud including GCC, Consumer, GCC High, or DoD</span></span>

<span data-ttu-id="c8be4-149">스케줄러는 데이터 위치가 독일 데이터 센터에 없는 독일의 사용자를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="c8be4-149">Scheduler does support users in Germany whose data location is not in the German datacenter.</span></span>
