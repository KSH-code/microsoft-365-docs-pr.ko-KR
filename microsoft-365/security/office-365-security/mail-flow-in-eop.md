---
title: EOP의 메일 흐름
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: e109077e-cc85-4c19-ae40-d218ac7d0548
ms.custom:
- seo-marvel-apr2020
description: 이 문서에서는 EOP (Exchange Online Protection) 고객은 비즈니스 요구 사항을 준수 하는 사용자 지정 메일 라우팅을 구성 하는 방법에 대해 알아볼 수 있습니다.
ms.openlocfilehash: cdc919c628f2254ffc971678f7887c37786d2528
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034235"
---
# <a name="mail-flow-in-eop"></a><span data-ttu-id="bdb0f-103">EOP의 메일 흐름</span><span class="sxs-lookup"><span data-stu-id="bdb0f-103">Mail flow in EOP</span></span>

<span data-ttu-id="bdb0f-p101">EOP(Exchange Online Protection) 고객의 조직으로 전송되는 모든 메시지는 작업자에게 표시되기 전에 EOP를 통과합니다. 고객이 Exchange Online을 사용하여 클라우드에서 모든 사서함을 호스트하든, 기존 인프라를 계속 사용하기 위해 온-프레미스에서 사서함을 호스트하든(독립 실행형 시나리오) 관계없이 작업자의 받은 편지함으로 라우팅되기 전에 처리를 위해 EOP를 통과하는 메시지를 라우팅할 방법에 대한 옵션이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="bdb0f-p101">As an Exchange Online Protection (EOP) customer, all messages sent to your organization pass through EOP before your workers see them. Whether you host all of your mailboxes in the cloud with Exchange Online, or you host your mailboxes on premises (called a standalone scenario), perhaps to continue taking advantage of your existing infrastructure, you have options about how to route messages that will pass through EOP for processing before they are routed to your worker inboxes.</span></span>

<span data-ttu-id="bdb0f-p102">메시징이 비즈니스 요구 사항을 따르도록 사용자 지정 메일 라우팅을 구성할 수 있습니다. 예를 들어 정책 필터링 어플라이언스를 통해 모든 아웃바운드 메일을 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bdb0f-p102">You may want to configure custom mail routing to conform your messaging to a business requirement. For instance, you can pass all of your outbound mail through a policy-filtering appliance.</span></span>

## <a name="working-with-messages-and-message-access-options"></a><span data-ttu-id="bdb0f-108">메시지 및 메시지 액세스 옵션 사용</span><span class="sxs-lookup"><span data-stu-id="bdb0f-108">Working with messages and message access options</span></span>

<span data-ttu-id="bdb0f-p103">EOP는 매우 유동적인 메시지 라우팅 방식을 제공합니다. 다음 항목에서 메일 흐름 프로세스의 단계에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="bdb0f-p103">EOP offers a lot of flexibility in how your messages are routed. The following topics explain steps in the mail flow process.</span></span>

<span data-ttu-id="bdb0f-111">[디렉터리 기반 Edge 차단을 사용 하 여 잘못 된 받는 사람에 게 보낸 메시지 거부](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking) 서비스 네트워크 경계에서 잘못 된 받는 사람에 대 한 메시지를 거부할 수 있는 디렉터리 기반 Edge 차단 기능에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="bdb0f-111">[Use Directory Based Edge Blocking to reject messages sent to invalid recipients](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking) Describes the Directory Based Edge Blocking feature which lets you reject messages for invalid recipients at the service network perimeter.</span></span>

<span data-ttu-id="bdb0f-112">[View or Edit Managed Domains in EOP](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)에서는 EOP 서비스와 연결된 도메인을 관리하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="bdb0f-112">[View or Edit Managed Domains in EOP](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) describes how to manage domains that are associated with your EOP service.</span></span>

<span data-ttu-id="bdb0f-113">조직에 하위 도메인을 추가한 경우 EOP 서비스를 통해 관리할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bdb0f-113">If you add subdomains to your organization, your EOP service can help you manage these too.</span></span> <span data-ttu-id="bdb0f-114">하위 도메인에 대 한 자세한 내용은 [Exchange Online에서 하위 도메인에 대 한 메일 흐름 사용](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains)을 참고 하세요.</span><span class="sxs-lookup"><span data-stu-id="bdb0f-114">Learn more about subdomains at [Enable mail flow for subdomains in Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains).</span></span>

<span data-ttu-id="bdb0f-p105">[Configure mail flow using connectors in Office 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)에서는 커넥터에 대해 소개하고 이러한 커넥터를 통해 메일 라우팅을 사용자 지정하는 방법을 설명합니다. 또한 파트너 조직과의 통신을 보호하고 스마트 호스트를 설정하는 시나리오를 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="bdb0f-p105">[Configure mail flow using connectors in Office 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) introduces connectors and shows how you can use them to customize mail routing. Scenarios include ensuring secure communication with a partner organization and setting up a smart host.</span></span>

<span data-ttu-id="bdb0f-117">정크 메일이 각 사용자의 정크 메일 폴더로 라우팅되도록 하려면 몇 가지 구성 단계를 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bdb0f-117">To ensure that junk email is routed correctly to each user's junk-email folder, you must perform a couple configuration steps.</span></span> <span data-ttu-id="bdb0f-118">[하이브리드 환경의 정크 메일 폴더에 스팸을 배달 하도록 독립 실행형 EOP 구성](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)에 자세히 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bdb0f-118">These are detailed in [Configure standalone EOP to deliver spam to the Junk Email folder in hybrid environments](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).</span></span> <span data-ttu-id="bdb0f-119">각 사용자의 정크 메일 폴더로 메시지를 옮기지 않으려면 Exchange 관리 센터에서 콘텐츠 필터 정책을 편집하여 다른 작업을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bdb0f-119">If you do not want to move messages to each user's junk-email folder, you may choose another action by editing your content filter policies in the Exchange admin center.</span></span> <span data-ttu-id="bdb0f-120">자세한 내용은 [스팸 방지 정책 구성하기](configure-your-spam-filter-policies.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bdb0f-120">For more information, see [Configure anti-spam policies](configure-your-spam-filter-policies.md).</span></span>

## <a name="verify-mail-flow"></a><span data-ttu-id="bdb0f-121">메일 흐름 확인</span><span class="sxs-lookup"><span data-stu-id="bdb0f-121">Verify mail flow</span></span>

<span data-ttu-id="bdb0f-p107">커넥터 구성을 비롯하여 EOP 설정이 제대로 작동하는지 확인하려면 [EOP 서비스 설정](set-up-your-eop-service.md)에서 "작동 여부는 어떻게 확인합니까?" 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bdb0f-p107">To verify that your EOP setup, including your connector configuration, is working correctly, see the "How do you know this task worked?" section in [Set up your EOP service](set-up-your-eop-service.md).</span></span>

<span data-ttu-id="bdb0f-124">[메일 흐름 테스트 Microsoft 365 커넥터를 확인 하 여](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow) 메일 흐름이 올바르게 설정 되었는지 테스트 하는 지침을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="bdb0f-124">[Test mail flow by validating your Microsoft 365 connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow) provides instructions for testing that your mail flow is set up correctly.</span></span>
