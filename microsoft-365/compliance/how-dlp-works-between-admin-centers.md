---
title: DLP가 보안 및 준수 센터 및 & 작동하는 & Exchange 방법
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 04/19/2019
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: a7e4342a-a0a1-4b43-b166-3d7eecf5d2fd
description: 보안 및 준수 센터의 DLP가 & 관리 센터의 DLP 및 메일 흐름 규칙(전송 규칙)에서 작동하는 Exchange 알아보습니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c5249279e1dd04447235aae813128cf458adde03
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/30/2021
ms.locfileid: "52114076"
---
# <a name="how-dlp-works-between-the-security--compliance-center-and-exchange-admin-center"></a><span data-ttu-id="a1e87-103">보안 및 준수 센터와 Exchange 관리 센터 사이에서 DLP가 작동 하는 방식</span><span class="sxs-lookup"><span data-stu-id="a1e87-103">How DLP works between the Security & Compliance Center and Exchange admin center</span></span>

<span data-ttu-id="a1e87-104">이 Office 365 두 개의 서로 다른 관리 센터에서 DLP(데이터 손실 방지) 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1e87-104">In Office 365, you can create a data loss prevention (DLP) policy in two different admin centers:</span></span>
  
- <span data-ttu-id="a1e87-105">보안 **&** 준수 센터에서 단일 DLP 정책을 만들어 SharePoint, OneDrive, Exchange 및 현재 Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="a1e87-105">In the **Security & Compliance Center**, you can create a single DLP policy to help protect content in SharePoint, OneDrive, Exchange, and now Microsoft Teams.</span></span> <span data-ttu-id="a1e87-106">가능한 경우 여기에서 DLP 정책을 만드는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a1e87-106">When possible, we recommend that you create a DLP policy here.</span></span> <span data-ttu-id="a1e87-107">자세한 내용은 데이터 손실 방지 [참조 를 참조하세요.](data-loss-prevention-policies.md)</span><span class="sxs-lookup"><span data-stu-id="a1e87-107">For more information, see [Data Loss Prevention reference](data-loss-prevention-policies.md).</span></span>
    
- <span data-ttu-id="a1e87-108">Exchange **관리** 센터에서 콘텐츠만 보호하는 데 도움이 되는 DLP 정책을 만들 수 Exchange.</span><span class="sxs-lookup"><span data-stu-id="a1e87-108">In the **Exchange admin center**, you can create a DLP policy to help protect content only in Exchange.</span></span> <span data-ttu-id="a1e87-109">이 정책은 Exchange 흐름 규칙(전송 규칙)을 사용할 수 있으므로 전자 메일 처리와 관련한 더 많은 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1e87-109">This policy can use Exchange mail flow rules (also known as transport rules), so it has more options specific to handling email.</span></span> <span data-ttu-id="a1e87-110">자세한 내용은 Exchange [관리 센터의 DLP를 참조하세요.](/exchange/security-and-compliance/data-loss-prevention/data-loss-prevention)</span><span class="sxs-lookup"><span data-stu-id="a1e87-110">For more information, see [DLP in the Exchange admin center](/exchange/security-and-compliance/data-loss-prevention/data-loss-prevention).</span></span>
    
<span data-ttu-id="a1e87-111">이러한 관리 센터에서 만든 DLP 경찰은 나란히 작동됩니다. 이 항목에서는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a1e87-111">DLP polices created in these admin centers work side by side - this topic explains how.</span></span>
  
![보안 및 준수 센터 및 Exchange 관리 센터의 DLP 페이지](../media/d3eaa7e7-3b16-457b-bd9c-26707f7b584f.png)
  
## <a name="how-dlp-in-the-security--compliance-center-works-with-dlp-and-mail-flow-rules-in-the-exchange-admin-center"></a><span data-ttu-id="a1e87-113">보안 및 준수 센터의 DLP가 & 관리 센터의 DLP 및 메일 흐름 규칙과 Exchange 방법</span><span class="sxs-lookup"><span data-stu-id="a1e87-113">How DLP in the Security & Compliance Center works with DLP and mail flow rules in the Exchange admin center</span></span>

<span data-ttu-id="a1e87-114">보안 및 준수 센터에서 DLP 정책을 & 정책은 정책에 포함된 모든 위치에 배포됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1e87-114">After you create a DLP policy in the Security & Compliance Center, the policy is deployed to all of the locations included in the policy.</span></span> <span data-ttu-id="a1e87-115">정책에 Exchange Online 정책이 동기화되어 정책 관리 센터에서 만든 DLP 정책과 Exchange 동일하게 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1e87-115">If the policy includes Exchange Online, the policy's synced there and enforced in exactly the same way as a DLP policy created in the Exchange admin center.</span></span> 
  
<span data-ttu-id="a1e87-116">Exchange 관리 센터에서 DLP 정책을 만든 경우 해당 정책은 보안 및 준수 센터에서 만든 전자 메일에 대한 모든 정책과 & 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1e87-116">If you've created DLP policies in the Exchange admin center, those policies will continue to work side by side with any policies for email that you create in the Security & Compliance Center.</span></span> <span data-ttu-id="a1e87-117">그러나 Exchange 관리 센터에서 만든 규칙이 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="a1e87-117">But note that rules created in the Exchange admin center take precedence.</span></span> <span data-ttu-id="a1e87-118">모든 Exchange 메일 흐름 규칙이 먼저 처리된 다음 보안 및 준수 센터의 DLP & 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1e87-118">All Exchange mail flow rules are processed first, and then the DLP rules from the Security & Compliance Center are processed.</span></span>
  
<span data-ttu-id="a1e87-119">즉,</span><span class="sxs-lookup"><span data-stu-id="a1e87-119">This means that:</span></span>
  
- <span data-ttu-id="a1e87-120">메일 흐름 규칙에 의해 Exchange 보안 및 준수 센터에서 만든 DLP 규칙에 의해 & 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a1e87-120">Messages that are blocked by Exchange mail flow rules won't get scanned by DLP rules created in the Security & Compliance Center.</span></span>
    
- <span data-ttu-id="a1e87-121">Exchange 메일 흐름 규칙이 외부 사용자 추가와 같은 보안 및 준수 센터의 D & LP 정책과 일치하도록 하는 방식으로 메시지를 수정하는 경우 DLP 규칙은 이를 검색하고 필요한 경우 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="a1e87-121">If an Exchange mail flow rule modifies a message in a way that causes it to match a DLP policy in the Security & Compliance Center - such as adding external users - then the DLP rules will detect this and enforce the policy as needed.</span></span>
    
<span data-ttu-id="a1e87-122">또한 Exchange "처리 중지" 작업을 사용하는 메일 흐름 규칙은 보안 & 준수 센터의 DLP 규칙 처리에 영향을 주지 않습니다. 이러한 규칙은 계속 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1e87-122">Also note that Exchange mail flow rules that use the "stop processing" action don't affect the processing of DLP rules in the Security & Compliance Center - they'll still be processed.</span></span>
  
## <a name="policy-tips-in-the-security--compliance-center-vs-the-exchange-admin-center"></a><span data-ttu-id="a1e87-123">보안 및 준수 센터의 & 및 Exchange 팁</span><span class="sxs-lookup"><span data-stu-id="a1e87-123">Policy tips in the Security & Compliance Center vs. the Exchange admin center</span></span>

<span data-ttu-id="a1e87-124">정책 팁은 Exchange 관리 센터에서 만든 DLP 정책 및 메일 흐름 규칙 또는 보안 및 준수 센터에서 만든 DLP & 사용할 수 있지만 둘 다 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a1e87-124">Policy tips can work either with DLP policies and mail flow rules created in the Exchange admin center, or with DLP policies created in the Security & Compliance Center, but not both.</span></span> <span data-ttu-id="a1e87-125">이러한 정책은 서로 다른 위치에 저장되지만 정책 팁은 단일 위치에서만 그릴 수 있기 때문에입니다.</span><span class="sxs-lookup"><span data-stu-id="a1e87-125">This is because these policies are stored in different locations, but policy tips can draw only from a single location.</span></span>
  
<span data-ttu-id="a1e87-126">Exchange 관리 센터에서 정책 팁을 구성한 경우 & 준수 센터에서 구성한 정책 팁은 Outlook 관리 센터에서 팁을 해제할 때까지 웹용 Outlook 및 Outlook 201 Exchange 3 이상에 있는 사용자에게 나타나지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a1e87-126">If you've configured policy tips in the Exchange admin center, any policy tips that you configure in the Security & Compliance Center won't appear to users in Outlook on the web and Outlook 2013 and later until you turn off the tips in the Exchange admin center.</span></span> <span data-ttu-id="a1e87-127">이렇게 하면 현재 Exchange 메일 흐름 규칙이 보안 및 준수 센터로 전환할 때까지 계속 & 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1e87-127">This ensures that your current Exchange mail flow rules will continue to work until you choose to switch over to the Security & Compliance Center.</span></span>
  
<span data-ttu-id="a1e87-128">정책 팁은 단일 위치에서만 그릴 수 있는 반면, 보안 및 준수 센터와 & 관리 센터 둘 다에서 DLP 정책을 사용하는 경우에도 전자 메일 Exchange 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1e87-128">Note that while policy tips can draw only from a single location, email notifications are always sent, even if you're using DLP policies in both the Security & Compliance Center and the Exchange admin center.</span></span>
