---
title: EOP의 메일 흐름
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
localization_priority: Normal
ms.assetid: e109077e-cc85-4c19-ae40-d218ac7d0548
ms.custom:
- seo-marvel-apr2020
description: 관리자는 EOP(Exchange Online Protection)에서 메일 흐름 및 라우팅을 구성하는 옵션에 대해 학습할 수 있습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: cd07c4448d9b30c90c97c7bc89c787b2fdc08cdd
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/09/2021
ms.locfileid: "50167242"
---
# <a name="mail-flow-in-eop"></a><span data-ttu-id="29a98-103">EOP의 메일 흐름</span><span class="sxs-lookup"><span data-stu-id="29a98-103">Mail flow in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="29a98-104">**적용 대상**</span><span class="sxs-lookup"><span data-stu-id="29a98-104">**Applies to**</span></span>
- [<span data-ttu-id="29a98-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="29a98-105">Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)
- [<span data-ttu-id="29a98-106">Microsoft Defender for Office 365 요금제 1 및 계획 2</span><span class="sxs-lookup"><span data-stu-id="29a98-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="29a98-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="29a98-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="29a98-108">Exchange Online 사서함이 있는 Microsoft 365 조직 또는 Exchange Online 사서함이 없는 독립 실행형 EOP(Exchange Online Protection) 조직에서는 조직으로 전송된 모든 메시지가 작업자에게 표시되기 전에 EOP를 통과합니다.</span><span class="sxs-lookup"><span data-stu-id="29a98-108">In Microsoft 365 organizations with Exchange Online mailboxes, or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, all messages sent to your organization pass through EOP before your workers see them.</span></span> <span data-ttu-id="29a98-109">처리를 위해 EOP를 통과하는 메시지를 작업 받은 편지함으로 라우팅하기 전에 라우팅하는 방법에 대한 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29a98-109">You have options about how to route messages that pass through EOP for processing before they are routed to your worker inboxes.</span></span>

## <a name="working-with-messages-and-message-access-options"></a><span data-ttu-id="29a98-110">메시지 및 메시지 액세스 옵션 사용</span><span class="sxs-lookup"><span data-stu-id="29a98-110">Working with messages and message access options</span></span>

<span data-ttu-id="29a98-111">EOP는 메시지 라우팅 방식에 유연성을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="29a98-111">EOP offers flexibility in how your messages are routed.</span></span> <span data-ttu-id="29a98-112">다음 항목에서 메일 흐름 프로세스의 단계에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="29a98-112">The following topics explain steps in the mail flow process.</span></span>

<span data-ttu-id="29a98-113">[디렉터리 기반 Edge 차단을 사용하여](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking) 잘못된 받는 사람에게 보낸 메시지 거부 서비스 네트워크 경계에서 잘못된 받는 사람에 대한 메시지를 거부할 수 있는 디렉터리 기반 Edge 차단 기능에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="29a98-113">[Use Directory Based Edge Blocking to reject messages sent to invalid recipients](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking) Describes the Directory Based Edge Blocking feature which lets you reject messages for invalid recipients at the service network perimeter.</span></span>

<span data-ttu-id="29a98-114">[View or Edit Managed Domains in EOP](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)에서는 EOP 서비스와 연결된 도메인을 관리하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="29a98-114">[View or Edit Managed Domains in EOP](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) describes how to manage domains that are associated with your EOP service.</span></span>

<span data-ttu-id="29a98-115">조직에 하위 도메인을 추가한 경우 EOP 서비스를 통해 관리할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29a98-115">If you add subdomains to your organization, your EOP service can help you manage these too.</span></span> <span data-ttu-id="29a98-116">하위 종에 대한 자세한 내용은 [Exchange Online에서](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains)하위 서버의 메일 흐름을 사용하도록 설정하세요.</span><span class="sxs-lookup"><span data-stu-id="29a98-116">Learn more about subdomains at [Enable mail flow for subdomains in Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains).</span></span>

<span data-ttu-id="29a98-117">[커넥터를 사용하여](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) 메일 흐름을 구성하고 커넥터를 사용하여 메일 라우팅을 사용자 지정하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="29a98-117">[Configure mail flow using connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) introduces connectors and shows how you can use them to customize mail routing.</span></span> <span data-ttu-id="29a98-118">또한 파트너 조직과의 통신을 보호하고 스마트 호스트를 설정하는 시나리오를 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="29a98-118">Scenarios include ensuring secure communication with a partner organization and setting up a smart host.</span></span>

<span data-ttu-id="29a98-119">[커넥터에 대한](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) 향상된 필터링에서는 메일이 EOP 전에 서비스 또는 장치로 라우팅되는 경우 커넥터를 구성하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="29a98-119">[Enhanced Filtering for Connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) describes how to configure connectors if your mail is routed to a service or device before EOP.</span></span>

<span data-ttu-id="29a98-120">독립 실행형 EOP 조직에서는 몇 가지 구성 단계를 수행하여 정크 메일이 각 사용자의 정크 메일 폴더로 올바르게 라우팅되도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="29a98-120">In standalone EOP organizations, you need to perform a couple configuration steps to ensure that junk email is routed correctly to each user's junk-email folder.</span></span> <span data-ttu-id="29a98-121">이러한 내용은 하이브리드 환경의 정크 메일 폴더로 스팸을 배달하도록 독립 실행형 EOP 구성에 [자세히 설명됩니다.](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)</span><span class="sxs-lookup"><span data-stu-id="29a98-121">These are detailed in [Configure standalone EOP to deliver spam to the Junk Email folder in hybrid environments](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).</span></span> <span data-ttu-id="29a98-122">각 사용자의 정크 메일 폴더로 메시지를 이동하지 않을 경우 스팸 방지 정책(콘텐츠 필터 정책)을 편집하여 다른 작업을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29a98-122">If you do not want to move messages to each user's junk-email folder, you may choose another action by editing your anti-spam policies (also known as content filter policies).</span></span> <span data-ttu-id="29a98-123">자세한 내용은 [스팸 방지 정책 구성하기](configure-your-spam-filter-policies.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="29a98-123">For more information, see [Configure anti-spam policies](configure-your-spam-filter-policies.md).</span></span>

## <a name="verify-mail-flow"></a><span data-ttu-id="29a98-124">메일 흐름 확인</span><span class="sxs-lookup"><span data-stu-id="29a98-124">Verify mail flow</span></span>

<span data-ttu-id="29a98-p106">커넥터 구성을 비롯하여 EOP 설정이 제대로 작동하는지 확인하려면 [EOP 서비스 설정](set-up-your-eop-service.md)에서 "작동 여부는 어떻게 확인합니까?" 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="29a98-p106">To verify that your EOP setup, including your connector configuration, is working correctly, see the "How do you know this task worked?" section in [Set up your EOP service](set-up-your-eop-service.md).</span></span>

<span data-ttu-id="29a98-127">[Microsoft 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow) 커넥터의 유효성을 검사하여 메일 흐름을 테스트하면 메일 흐름이 올바르게 설정되어 있는지 테스트하기 위한 지침이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29a98-127">[Test mail flow by validating your Microsoft 365 connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow) provides instructions for testing that your mail flow is set up correctly.</span></span>
