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
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: e109077e-cc85-4c19-ae40-d218ac7d0548
ms.custom:
- seo-marvel-apr2020
description: 관리자는 EOP(Exchange Online Protection)에서 메일 흐름 및 라우팅을 구성하기 위한 옵션을 자세히 학습할 수 있습니다.
ms.openlocfilehash: c58981afaadf2c4083b6a6db99c74cf9544715c3
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827728"
---
# <a name="mail-flow-in-eop"></a><span data-ttu-id="aff0f-103">EOP의 메일 흐름</span><span class="sxs-lookup"><span data-stu-id="aff0f-103">Mail flow in EOP</span></span>

<span data-ttu-id="aff0f-104">Exchange Online 사서함이 있는 Microsoft 365 조직 또는 Exchange Online 사서함이 없는 독립 실행형 EOP(Exchange Online Protection) 조직에서 조직으로 전송되는 모든 메시지는 작업자에게 표시되기 전에 EOP를 통과합니다.</span><span class="sxs-lookup"><span data-stu-id="aff0f-104">In Microsoft 365 organizations with Exchange Online mailboxes, or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, all messages sent to your organization pass through EOP before your workers see them.</span></span> <span data-ttu-id="aff0f-105">작업자의 받은 편지함으로 라우팅되기 전에 처리를 위해 EOP를 통과하는 메시지를 라우팅하는 방법에 대한 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aff0f-105">You have options about how to route messages that pass through EOP for processing before they are routed to your worker inboxes.</span></span>

## <a name="working-with-messages-and-message-access-options"></a><span data-ttu-id="aff0f-106">메시지 및 메시지 액세스 옵션 사용</span><span class="sxs-lookup"><span data-stu-id="aff0f-106">Working with messages and message access options</span></span>

<span data-ttu-id="aff0f-107">EOP를 사용하면 메시지 라우팅 방식에 유연성을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="aff0f-107">EOP offers flexibility in how your messages are routed.</span></span> <span data-ttu-id="aff0f-108">다음 항목에서 메일 흐름 프로세스의 단계에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="aff0f-108">The following topics explain steps in the mail flow process.</span></span>

<span data-ttu-id="aff0f-109">[디렉터리 기반 Edge 차단을 사용하여 잘못된 받는 사람에게 전송된 메시지 거부](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking) 서비스 네트워크 경계에서 잘못된 받는 사람의 메시지를 거부할 수 있는 디렉터리 기반 Edge 차단 기능에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="aff0f-109">[Use Directory Based Edge Blocking to reject messages sent to invalid recipients](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking) Describes the Directory Based Edge Blocking feature which lets you reject messages for invalid recipients at the service network perimeter.</span></span>

<span data-ttu-id="aff0f-110">[View or Edit Managed Domains in EOP](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)에서는 EOP 서비스와 연결된 도메인을 관리하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="aff0f-110">[View or Edit Managed Domains in EOP](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) describes how to manage domains that are associated with your EOP service.</span></span>

<span data-ttu-id="aff0f-111">조직에 하위 도메인을 추가한 경우 EOP 서비스를 통해 관리할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aff0f-111">If you add subdomains to your organization, your EOP service can help you manage these too.</span></span> <span data-ttu-id="aff0f-112">Exchange Online에서 하위 도메인에 대한 [메일 흐름을 사용하도록 설정에서 하위 도메인에 대해 자세히 알아보세요.](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains)</span><span class="sxs-lookup"><span data-stu-id="aff0f-112">Learn more about subdomains at [Enable mail flow for subdomains in Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains).</span></span>

<span data-ttu-id="aff0f-113">[커넥터를 사용하여 메일 흐름을 구성하면](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) 커넥터가 소트되며 이러한 커넥터를 통해 메일 라우팅을 사용자 지정하는 방법이 설명됩니다.</span><span class="sxs-lookup"><span data-stu-id="aff0f-113">[Configure mail flow using connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) introduces connectors and shows how you can use them to customize mail routing.</span></span> <span data-ttu-id="aff0f-114">또한 파트너 조직과의 통신을 보호하고 스마트 호스트를 설정하는 시나리오를 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="aff0f-114">Scenarios include ensuring secure communication with a partner organization and setting up a smart host.</span></span>

<span data-ttu-id="aff0f-115">[커넥터에 대한 향상된 필터링은](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) EOP 이전에 메일이 서비스 또는 장치로 라우팅되는지 여부에 대한 커넥터 구성 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="aff0f-115">[Enhanced Filtering for Connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) describes how to configure connectors if your mail is routed to a service or device before EOP.</span></span>

<span data-ttu-id="aff0f-116">독립 실행형 EOP 조직에서는 여러 가지 구성 단계를 수행하여 정크 메일이 각 사용자의 정크 메일 폴더로 라우팅되도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aff0f-116">In standalone EOP organizations, you need to perform a couple configuration steps to ensure that junk email is routed correctly to each user's junk-email folder.</span></span> <span data-ttu-id="aff0f-117">이러한 단계는 하이브리드 [환경의 정크 메일 폴더로 스팸을 배달하도록 독립 실행형 EOP 구성에 자세히 설명되어 있습니다.](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)</span><span class="sxs-lookup"><span data-stu-id="aff0f-117">These are detailed in [Configure standalone EOP to deliver spam to the Junk Email folder in hybrid environments](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).</span></span> <span data-ttu-id="aff0f-118">각 사용자의 정크 메일 폴더로 메시지를 이동하지 않도록 하려면 스팸 방지 정책(콘텐츠 필터 정책이라고도 함)을 편집하여 다른 작업을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aff0f-118">If you do not want to move messages to each user's junk-email folder, you may choose another action by editing your anti-spam policies (also known as content filter policies).</span></span> <span data-ttu-id="aff0f-119">자세한 내용은 [스팸 방지 정책 구성하기](configure-your-spam-filter-policies.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="aff0f-119">For more information, see [Configure anti-spam policies](configure-your-spam-filter-policies.md).</span></span>

## <a name="verify-mail-flow"></a><span data-ttu-id="aff0f-120">메일 흐름 확인</span><span class="sxs-lookup"><span data-stu-id="aff0f-120">Verify mail flow</span></span>

<span data-ttu-id="aff0f-p106">커넥터 구성을 비롯하여 EOP 설정이 제대로 작동하는지 확인하려면 [EOP 서비스 설정](set-up-your-eop-service.md)에서 "작동 여부는 어떻게 확인합니까?" 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="aff0f-p106">To verify that your EOP setup, including your connector configuration, is working correctly, see the "How do you know this task worked?" section in [Set up your EOP service](set-up-your-eop-service.md).</span></span>

<span data-ttu-id="aff0f-123">[Microsoft 365 커넥터를 확인하여 메일 흐름을](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow) 테스트하는 지침을 통해 메일 흐름이 올바르게 설정되었는지 테스트하는 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="aff0f-123">[Test mail flow by validating your Microsoft 365 connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow) provides instructions for testing that your mail flow is set up correctly.</span></span>
