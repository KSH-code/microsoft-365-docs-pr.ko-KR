---
title: Microsoft 365 보안 센터에서 ServiceNow 티켓 만들기 및 추적
description: Microsoft 365 보안 센터에서 ServiceNow의 티켓을 만들고 추적 하는 방법에 대해 알아봅니다.
keywords: 보안, Microsoft 365, M365, 보안 점수, 보안 센터, ServiceNow, 티켓, 작업
ms.prod: w10
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
ms.openlocfilehash: bd5bf8533d38337c063acdf0dda073e4961e416a
ms.sourcegitcommit: 787b198765565d54ee73972f664bdbd5023d666b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/24/2020
ms.locfileid: "46867248"
---
# <a name="create-and-track-servicenow-tickets-in-the-microsoft-365-security-center"></a><span data-ttu-id="662d1-104">Microsoft 365 보안 센터에서 ServiceNow 티켓 만들기 및 추적</span><span class="sxs-lookup"><span data-stu-id="662d1-104">Create and track ServiceNow tickets in the Microsoft 365 security center</span></span>

<span data-ttu-id="662d1-105">[Microsoft 365 보안 센터](overview-security-center.md) 는 ServiceNow에서 티켓을 기본적으로 만들고 추적할 수 있도록 향상 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="662d1-105">The [Microsoft 365 security center](overview-security-center.md) has been enhanced with the ability to natively create and track tickets in ServiceNow.</span></span> [<span data-ttu-id="662d1-106">ServiceNow에 대해 자세히 알아보기</span><span class="sxs-lookup"><span data-stu-id="662d1-106">Learn more about ServiceNow</span></span>](https://www.servicenow.com/)

<span data-ttu-id="662d1-107">보안 센터에서 보안 관리자는 [Microsoft 보안 점수](microsoft-secure-score.md) 향상 작업을 ServiceNow로 직접 전송 하 고 티켓을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="662d1-107">In the security center, security administrators can send a [Microsoft Secure Score](microsoft-secure-score.md) improvement action directly to ServiceNow and create a ticket.</span></span> <span data-ttu-id="662d1-108">인시던트 관리 및 변경 관리 티켓을 모두 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="662d1-108">Both incident management and change management tickets can be created.</span></span> <span data-ttu-id="662d1-109">보안 센터 홈 페이지 및 ServiceNow의 티켓을 추적 합니다.</span><span class="sxs-lookup"><span data-stu-id="662d1-109">Track tickets in the security center home page and ServiceNow.</span></span>

- [<span data-ttu-id="662d1-110">**필수 구성 요소, 데이터 교환 및 문제 해결 방법 알아보기**</span><span class="sxs-lookup"><span data-stu-id="662d1-110">**Learn about prerequisites, data exchange, and troubleshooting**</span></span>](tickets.md)
- <span data-ttu-id="662d1-111">**준수 센터에서 ServiceNow 티켓 관리** (출시 예정)</span><span class="sxs-lookup"><span data-stu-id="662d1-111">**Manage ServiceNow tickets in the compliance center** (coming soon)</span></span>

## <a name="connect-microsoft-365-security-center-to-servicenow"></a><span data-ttu-id="662d1-112">ServiceNow에 Microsoft 365 보안 센터 연결</span><span class="sxs-lookup"><span data-stu-id="662d1-112">Connect Microsoft 365 security center to ServiceNow</span></span>

<span data-ttu-id="662d1-113">Microsoft 365 보안 센터 홈 페이지로 이동 하 여 ServiceNow 연결 카드를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="662d1-113">Navigate to the Microsoft 365 security center home page to see the ServiceNow connection card.</span></span>

![ServiceNow 사용](../../media/do-you-use-servicenow-250.png)

<span data-ttu-id="662d1-115">"ServiceNow에 연결"을 선택 하 여 ServiceNow 설정 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="662d1-115">Select "Connect to ServiceNow" to go to the ServiceNow setup page.</span></span> <span data-ttu-id="662d1-116">지침에 따라 Microsoft 365 커넥터 앱에 권한을 부여 합니다.</span><span class="sxs-lookup"><span data-stu-id="662d1-116">Follow the instructions to authorize the Microsoft 365 Connector app.</span></span>

> [!NOTE]
> <span data-ttu-id="662d1-117">Microsoft 365 보안 센터와 ServiceNow 간의 연결에 권한을 부여 하기 전에 설치 단계에서 만든 통합 사용자 로그인 및 암호를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="662d1-117">Before you authorize the connection between Microsoft 365 security center and ServiceNow, make sure you use the integration user login and password you created in the installation steps.</span></span> <span data-ttu-id="662d1-118">개인 자격 증명은 사용 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="662d1-118">Do not use your personal credentials.</span></span>

<span data-ttu-id="662d1-119">지침을 따르고 연결에 대 한 인증을 받은 후에는 Microsoft 365 보안 센터 연결 페이지 및 ServiceNow Microsoft 365 티켓 커넥터 앱 환경에서 연결 상태를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="662d1-119">After you've followed the directions and authorized the connection, view the connection status in the Microsoft 365 security center connection page and in the ServiceNow Microsoft 365 Ticketing Connector App experience.</span></span> <span data-ttu-id="662d1-120">이제 작업 만들기를 시작 하도록 설정 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="662d1-120">Now you're all set to start creating tasks!</span></span>

### <a name="troubleshooting"></a><span data-ttu-id="662d1-121">문제 해결</span><span class="sxs-lookup"><span data-stu-id="662d1-121">Troubleshooting</span></span>

<span data-ttu-id="662d1-122">연결 프로세스에서 발생할 수 있는 일반적인 오류 및 [문제 해결 섹션](tickets.md#troubleshooting)에서이를 완화 하는 방법에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="662d1-122">Learn common errors you may come across in the connection process, and how to mitigate them, in the [troubleshooting section](tickets.md#troubleshooting).</span></span>

## <a name="create-a-task-and-share-it-to-servicenow"></a><span data-ttu-id="662d1-123">작업 만들기 및 ServiceNow에 공유</span><span class="sxs-lookup"><span data-stu-id="662d1-123">Create a task and share it to ServiceNow</span></span>

<span data-ttu-id="662d1-124">통합이 설정 되 면 특정 [Microsoft 보안 점수](microsoft-secure-score.md) 향상 작업을 기반으로 ServiceNow 작업을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="662d1-124">Once the integration is set up, create ServiceNow tasks based on specific [Microsoft Secure Score](microsoft-secure-score.md) improvement actions.</span></span> <span data-ttu-id="662d1-125">Microsoft 365 보안 센터의 보안 점수 향상 작업으로 이동한 후 **공유**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="662d1-125">Go to any Secure Score improvement action in the Microsoft 365 security center, and select **Share**.</span></span> <span data-ttu-id="662d1-126">드롭다운 옵션 중 하나는 ServiceNow입니다.</span><span class="sxs-lookup"><span data-stu-id="662d1-126">One of the dropdown options is ServiceNow.</span></span>

<span data-ttu-id="662d1-127">우선 순위를 설정 하 고 이름, 설명 또는 기한을 편집할 수 있는 작업이 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="662d1-127">A task is generated where you can set the priority and edit the name, description, or due date.</span></span> <span data-ttu-id="662d1-128">필수 필드를 모두 입력 한 후에는 해당 작업을 ServiceNow로 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="662d1-128">Once all the required fields are filled in, send the task to ServiceNow.</span></span>

<span data-ttu-id="662d1-129">이 작업은 Microsoft 365 보안 및 구성 변경 요청으로 ServiceNow에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="662d1-129">The task is visible in ServiceNow as a Microsoft 365 Security and Configuration Change Request.</span></span>

## <a name="track-tickets"></a><span data-ttu-id="662d1-130">티켓 추적</span><span class="sxs-lookup"><span data-stu-id="662d1-130">Track tickets</span></span>

<span data-ttu-id="662d1-131">ServiceNow 변경 관리 및 인시던트 관리 티켓이 만들어지면 Microsoft 365 보안 센터 홈 페이지의 명함에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="662d1-131">Once ServiceNow change management and incident management tickets have been created, they're displayed on cards in the Microsoft 365 security center home page.</span></span> <span data-ttu-id="662d1-132">이러한 카드에서 티켓을 만들거나, 모든 티켓을 보거나, ServiceNow 구성을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="662d1-132">From these cards, you can create a ticket, view all tickets, or manage the ServiceNow configuration.</span></span>

![ServiceNow 변경 관리 티켓](../../media/change-management-375.png)  ![ServiceNow 인시던트 관리 티켓](../../media/incident-management-375.png)

<span data-ttu-id="662d1-135">Microsoft 365 보안 센터에서 ServiceNow 통합을 다시 구축 하거나 관리 하려면 카드 중 하나에서 **servicenow 구성 관리** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="662d1-135">To reprovision or manage your ServiceNow integration in the Microsoft 365 security center, select **Manage ServiceNow configuration** on either of the cards.</span></span> <span data-ttu-id="662d1-136">현재 ServiceNow 연결을 제거 하 고 티켓 상태 이름을 사용자 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="662d1-136">From there, remove the current ServiceNow connection and customize ticket state names.</span></span>

<span data-ttu-id="662d1-137">Microsoft 365 보안 센터에 ServiceNow 티켓이 표시 되 면 작업은 다른 보안 대시보드 항목과 함께 추적 하 고 작동할 수 있는 위치에 살고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="662d1-137">With ServiceNow tickets visible in the Microsoft 365 security center, your tasks live in a place where they can be tracked and acted upon alongside your other security dashboard items.</span></span>

## <a name="resources"></a><span data-ttu-id="662d1-138">리소스</span><span class="sxs-lookup"><span data-stu-id="662d1-138">Resources</span></span>

- [<span data-ttu-id="662d1-139">필수 구성 요소, 데이터 교환 및 문제 해결 방법 알아보기</span><span class="sxs-lookup"><span data-stu-id="662d1-139">Learn about prerequisites, data exchange, and troubleshooting</span></span>](tickets.md)
- [<span data-ttu-id="662d1-140">Microsoft 보안 점수</span><span class="sxs-lookup"><span data-stu-id="662d1-140">Microsoft Secure Score</span></span>](microsoft-secure-score.md)