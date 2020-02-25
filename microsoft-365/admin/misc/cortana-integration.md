---
title: Office 365와 Cortana 통합
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 7257cb50-0d5c-4f7a-ac2e-9fe5d13bb5cb
description: 'Office 365와 통합 된 경우 Cortana를 사용 하는 방법에 대해 알아봅니다. 관리 센터에서 Cortana를 해제 하 여 조직의 데이터에 대 한 액세스를 제한할 수 있습니다. '
ms.openlocfilehash: 21de80d127498dd40db932923a8d650b87b8a24c
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/24/2020
ms.locfileid: "42257423"
---
# <a name="cortana-in-office-365"></a><span data-ttu-id="a57b3-104">Office 365의 Cortana</span><span class="sxs-lookup"><span data-stu-id="a57b3-104">Cortana in Office 365</span></span>

<span data-ttu-id="a57b3-105">Cortana는 장치 및 Microsoft 서비스에서 작동 하는 클라우드 기반 디지털 도우미와 Microsoft 365 및 Office 365 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="a57b3-105">Cortana is a cloud-based digital assistant and Microsoft 365 and Office 365 service that works across your devices and Microsoft services.</span></span> <span data-ttu-id="a57b3-106">Cortana는 Microsoft 365 및 Office 365에 저장 된 정보를 사용 하 여 조직의 사용자가 최신 상태로 유지 하 고 의견, 제안 된 작업, 그리고 모임, 문서 및 연락처에 대 한 도움말을 얻을 수 있도록 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="a57b3-106">Cortana can use information stored in Microsoft 365 and Office 365 to help people in your organization stay up to date and get insights, suggested tasks, and help with their meetings, documents, and contacts.</span></span>
  
## <a name="info-for-admins"></a><span data-ttu-id="a57b3-107">관리자를 위한 정보</span><span class="sxs-lookup"><span data-stu-id="a57b3-107">Info for admins</span></span>

<span data-ttu-id="a57b3-108">준수는 Microsoft에서 기업 고객에 게 주는 약정입니다.</span><span class="sxs-lookup"><span data-stu-id="a57b3-108">Compliance is a commitment that Microsoft makes to enterprise customers.</span></span> [<span data-ttu-id="a57b3-109">Microsoft 준수 프레임 워크에 대해 자세히 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="a57b3-109">Learn more about the Microsoft compliance framework.</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=2109173)

<span data-ttu-id="a57b3-110">다른 Microsoft 365 및 Office 365 서비스와 마찬가지로 호환 되는 Cortana 기능은 보호 되며, 우발적 손실, 변경 으로부터 사용자 데이터를 보호 하는 것과 관련 된 약속을 포함 하는 온라인 서비스 약관에 따라 보안이 유지 됩니다. 권한 없는 공개 또는 액세스 또는 불법적 소멸</span><span class="sxs-lookup"><span data-stu-id="a57b3-110">Consistent with other Microsoft 365 and Office 365 services, compliant Cortana features are protected and secured subject to the Online Service Terms that includes a set of promises involving protection of user data against accidental loss, alteration, unauthorized disclosure or access, or unlawful destruction.</span></span> <span data-ttu-id="a57b3-111">다른 모든 Cortana 기능 (즉, Cortana 선택적 연결 서비스)은 [Microsoft 서비스 계약](https://go.microsoft.com/fwlink/p/?LinkId=2109174) 및 [Microsoft 개인정보 취급 방침](https://go.microsoft.com/fwlink/p/?LinkId=2109175) 을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="a57b3-111">All other Cortana features (i.e., Cortana optional connected services) are subject to the [Microsoft Services Agreement](https://go.microsoft.com/fwlink/p/?LinkId=2109174) and  [Microsoft Privacy Statement.](https://go.microsoft.com/fwlink/p/?LinkId=2109175)</span></span>

<span data-ttu-id="a57b3-112">Cortana 서비스는 사용자가 제어할 수 있는 **규격** 및 **선택적 연결 서비스로**두 가지 데이터 범주로 나뉩니다.</span><span class="sxs-lookup"><span data-stu-id="a57b3-112">Cortana services are broken into two data categories, **compliant** and **optional connected services**, which you can control.</span></span>

## <a name="turn-off-cortana-optional-connected-services"></a><span data-ttu-id="a57b3-113">Cortana 선택적 연결 된 서비스 해제</span><span class="sxs-lookup"><span data-stu-id="a57b3-113">Turn off Cortana optional connected services</span></span>

<span data-ttu-id="a57b3-114">Cortana 선택적인 연결 된 서비스는 조직의 직원 들에 대해 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a57b3-114">Cortana optional connected services can be turned off for employees at your organization.</span></span> <span data-ttu-id="a57b3-115">이렇게 하면 Windows 및 Cortana 모바일 앱에서 Cortana의 선택적 연결 서비스를 사용 하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a57b3-115">This will disable Cortana optional connected services in Cortana on Windows and the Cortana mobile app.</span></span> <span data-ttu-id="a57b3-116">여기에는 Cortana 미리 알림, 목록, 작업 및 기타 기능이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a57b3-116">This includes Cortana reminders, lists, tasks, and other features.</span></span> <span data-ttu-id="a57b3-117">호환 범주 (예: Cortana OST 환경)의 서비스와 Cortana의 브리핑 전자 메일을 비롯 한 전자 메일을 재생 하는 기능은 활성 상태로 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a57b3-117">Services in the compliant category (i.e., Cortana OST experiences), such as Cortana’s Briefing email, and Play My Emails in Outlook mobile, will remain active.</span></span>

1. <span data-ttu-id="a57b3-118">Microsoft 365 관리 센터에서 **설정** > **설정을** 선택 하 고 **Cortana**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a57b3-118">In the Microsoft 365 admin center, select **Settings** > **Settings** and select **Cortana**.</span></span>

4. <span data-ttu-id="a57b3-119">Cortana에서 연결 **된 Microsoft 호스팅된 데이터를 사용** 하 여 cortana 연결 환경을 사용 하거나 사용 하지 않도록 설정할 수 있는 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a57b3-119">Select the checkbox for **Allow Cortana optional connected experiences to use your organizations's Microsoft hosted data** to enable or disable Cortana connected experiences.</span></span>

5. <span data-ttu-id="a57b3-120">**변경 내용 저장**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a57b3-120">Select **Save changes**.</span></span>

## <a name="turn-off-cortana-ost-experiences"></a><span data-ttu-id="a57b3-121">Cortana OST 환경 끄기</span><span class="sxs-lookup"><span data-stu-id="a57b3-121">Turn off Cortana OST experiences</span></span>

<span data-ttu-id="a57b3-122">조직의 직원은 아래 단계에 따라 개별적으로 Cortana OST 환경을 거부할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a57b3-122">Your organization's employees can opt out of Cortana OST experiences individually by following the steps below.</span></span>

1. <span data-ttu-id="a57b3-123">Outlook mobile을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="a57b3-123">Open Outlook mobile.</span></span>

2. <span data-ttu-id="a57b3-124">**설정**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="a57b3-124">Go to **Settings**.</span></span>
  
3. <span data-ttu-id="a57b3-125">**전자 메일 재생**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a57b3-125">Select **Play My Emails**.</span></span>

4. <span data-ttu-id="a57b3-126">사용 하지 않도록 설정 하려는 계정에 대해 토글을 off로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="a57b3-126">Move the toggle to off on the accounts you want to disable.</span></span>

### <a name="briefing-email"></a><span data-ttu-id="a57b3-127">브리핑 전자 메일</span><span class="sxs-lookup"><span data-stu-id="a57b3-127">Briefing email</span></span>

<span data-ttu-id="a57b3-128">작업 표시줄에서 Cortana를 사용 하지 않도록 설정 해도 Cortana의 브리핑 전자 메일이 사용 하도록 설정 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a57b3-128">Disabling Cortana on the taskbar won't disable Cortana’s Briefing email.</span></span> <span data-ttu-id="a57b3-129">직원은 개별적으로 구독을 취소 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a57b3-129">Employees must unsubscribe individually.</span></span> <span data-ttu-id="a57b3-130">조직의 개별 사용자는 메시지 바닥글에서 **구독 취소** 를 선택 하 여 Cortana의 브리핑 전자 메일을 제외할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a57b3-130">Individuals from your organization can opt out of Cortana’s Briefing email by selecting **Unsubscribe** in the footer of the message.</span></span>