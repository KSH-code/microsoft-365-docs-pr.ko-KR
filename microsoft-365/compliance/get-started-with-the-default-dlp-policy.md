---
title: 기본 DLP 정책을 사용하여 시작
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 8/10/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: e0ada764-6422-4b44-9472-513bed04837b
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 보고서를 사용하여 조직의 기본 DLP(데이터 손실 방지) 정책을 구체화하는 방법을 학습합니다.
ms.openlocfilehash: 4530e570f0ce593a7d2cb62acc28dfa4e1658df0
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/30/2021
ms.locfileid: "52114086"
---
# <a name="get-started-with-the-default-dlp-policy"></a><span data-ttu-id="7cf53-103">기본 DLP 정책을 사용하여 시작</span><span class="sxs-lookup"><span data-stu-id="7cf53-103">Get started with the default DLP policy</span></span>

<span data-ttu-id="7cf53-104">첫 번째 DLP(데이터 손실 방지) 정책을 만들기 전에 DLP는 기본 정책으로 중요한 정보를 보호하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7cf53-104">Before you even create your first data loss prevention (DLP) policy, DLP is helping to protect your sensitive information with a default policy.</span></span> <span data-ttu-id="7cf53-105">이 기본 정책 및 권장 정책(아래 그림 참조)은 신용 카드 번호가 포함된 전자 메일 또는 문서가 조직 외부의 사용자와 공유될 때 알려 중요한 콘텐츠를 안전하게 유지하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7cf53-105">This default policy and its recommendation (shown below) help keep your sensitive content secure by notifying you when email or documents containing a credit card number were shared with someone outside your organization.</span></span> <span data-ttu-id="7cf53-106">이 권장 내용은 보안 및  준수 센터의 홈 &amp; 페이지에서 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7cf53-106">You'll see this recommendation on the **Home** page of the Security &amp; Compliance Center.</span></span> 
  
<span data-ttu-id="7cf53-107">이 위젯을 사용하여 공유된 중요한 정보의 수와 정보를 빠르게 확인한 다음 한 두 번의 클릭 또는 두 번으로 기본 DLP 정책을 구체화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7cf53-107">You can use this widget to quickly view when and how much sensitive information was shared, and then refine the default DLP policy in just a click or two.</span></span> <span data-ttu-id="7cf53-108">기본 DLP 정책은 사용자 지정이 완전히 가능하기 때문에 원하는 경우 편집할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7cf53-108">You can also edit the default DLP policy at any time because it's fully customizable.</span></span> <span data-ttu-id="7cf53-109">처음에 추천이 없는 경우 권장 섹션 아래쪽에서 **+More를** **클릭해 봐야** 합니다.</span><span class="sxs-lookup"><span data-stu-id="7cf53-109">Note that if you don't see the recommendation at first, try clicking **+More** at the bottom of the **Recommended for you** section.</span></span> 
  
![Widget named Further protect shared content](../media/2bae6dbc-cc92-4f35-b54c-c36e60226b5b.png)
  
## <a name="view-the-report-and-refine-the-default-dlp-policy"></a><span data-ttu-id="7cf53-111">보고서를 보고 기본 DLP 정책 구체화</span><span class="sxs-lookup"><span data-stu-id="7cf53-111">View the report and refine the default DLP policy</span></span>

<span data-ttu-id="7cf53-112">위젯에서 사용자가 조직 외부의 사용자와 중요한 정보를 공유했다는 것을 보여 주면 아래쪽의 **DLP** 정책 구체화 를 선택하세요.</span><span class="sxs-lookup"><span data-stu-id="7cf53-112">When the widget shows you that users have shared sensitive information with people outside your organization, choose **Refine DLP policy** at the bottom.</span></span> 
  
<span data-ttu-id="7cf53-113">자세한 보고서는 지난 30일 동안 신용 카드 번호를 포함하는 콘텐츠가 공유된 경우와 양을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="7cf53-113">The detailed report shows you when and how much content containing credit card numbers was shared in the past 30 days.</span></span> <span data-ttu-id="7cf53-114">규칙 일치는 위젯에 표시하는 데 최대 48시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7cf53-114">Note that rule matches can take up to 48 hours to show up in the widget.</span></span>
  
<span data-ttu-id="7cf53-115">중요한 정보를 보호하기 위해 기본 DLP 정책은 다음을 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="7cf53-115">To help protect the sensitive information, the default DLP policy:</span></span>
  
- <span data-ttu-id="7cf53-116">하나 이상의 신용 카드 번호를 포함하는 Exchange, SharePoint 및 OneDrive 콘텐츠가 조직 외부의 사용자와 공유되는 경우를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="7cf53-116">Detects when content in Exchange, SharePoint, and OneDrive that contains at least one credit card number is shared with people outside your organization.</span></span>
    
- <span data-ttu-id="7cf53-117">사용자가 이 중요한 정보를 조직 외부의 사용자와 공유하려고 할 때 정책 팁을 표시하고 사용자에게 전자 메일 알림을 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="7cf53-117">Shows a policy tip and sends an email notification to users when they attempt to share this sensitive information with people outside your organization.</span></span> <span data-ttu-id="7cf53-118">이러한 옵션에 대한 자세한 내용은 전자 메일 알림 보내기 및 DLP 정책에 대한 정책 [팁 표시를 참조하세요.](use-notifications-and-policy-tips.md)</span><span class="sxs-lookup"><span data-stu-id="7cf53-118">For more information on these options, see [Send email notifications and show policy tips for DLP policies](use-notifications-and-policy-tips.md).</span></span>
    
- <span data-ttu-id="7cf53-119">조직 외부의 사용자와 콘텐츠를 공유한 사람 및 콘텐츠를 공유한 경우를 추적할 수 있도록 자세한 활동 보고서를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="7cf53-119">Generates detailed activity reports so that you can track things like who shared the content with people outside your organization and when they did it.</span></span> <span data-ttu-id="7cf53-120">[DLP](view-the-dlp-reports.md) 보고서 및 감사 [](search-the-audit-log-in-security-and-compliance.md) 로그 데이터(여기서 **활동**  =  **DLP)를** 사용하여 이 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7cf53-120">You can use the [DLP reports](view-the-dlp-reports.md) and [audit log data](search-the-audit-log-in-security-and-compliance.md) (where **Activity** = **DLP**) to see this information.</span></span>
    
<span data-ttu-id="7cf53-121">기본 DLP 정책을 빠르게 구체화하기 위해 다음을 하게 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7cf53-121">To quickly refine the default DLP policy, you can choose to have it:</span></span>
  
- <span data-ttu-id="7cf53-122">사용자가 이 중요한 정보를 조직 외부의 사용자와 공유할 때 문제 보고서 전자 메일을 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="7cf53-122">Send you an incident report email when users share this sensitive information with people outside your organization.</span></span>
    
- <span data-ttu-id="7cf53-123">전자 메일 문제 보고서에 다른 사용자를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="7cf53-123">Add other users to the email incident report.</span></span>
    
- <span data-ttu-id="7cf53-124">중요한 정보가 포함된 콘텐츠에 대한 액세스를 차단하지만, 사용자가 필요한 경우 사용자가 다시 설정하고 공유하거나 보낼 수 있도록 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="7cf53-124">Block access to the content containing the sensitive information, but allow the user to override and share or send if they need to.</span></span>
    
<span data-ttu-id="7cf53-125">인시던트 보고서 또는 액세스 제한에 대한 자세한 내용은 데이터 손실 방지 [참조를 참조하세요.](data-loss-prevention-policies.md)</span><span class="sxs-lookup"><span data-stu-id="7cf53-125">For more information on incident reports or restricting access, see [Data loss prevention reference](data-loss-prevention-policies.md).</span></span>
  
<span data-ttu-id="7cf53-126">나중에 이러한 옵션을 변경하려는 경우 기본 DLP 정책을 편집할 수 있습니다. 다음 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7cf53-126">If you want to change these options later, you can edit the default DLP policy at any time - see the next section.</span></span>
  
![설정 보호라는 위젯에 대한 정보 표시](../media/dad30a84-2715-4c0a-a5c5-44d85492363e.png)
  
## <a name="edit-the-default-dlp-policy"></a><span data-ttu-id="7cf53-128">기본 DLP 정책 편집</span><span class="sxs-lookup"><span data-stu-id="7cf53-128">Edit the default DLP policy</span></span>

<span data-ttu-id="7cf53-129">이 정책의 이름은 **기본 DLP 정책으로,** 보안  및 준수 센터의 정책 페이지에서 데이터 손실 방지 아래에  &amp; 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="7cf53-129">This policy is named **Default DLP policy** and appears under **Data loss prevention** on the **Policy** page of the Security &amp; Compliance Center.</span></span> 
  
<span data-ttu-id="7cf53-130">이 정책은 처음부터 직접 만든 DLP 정책과 동일하게 완전히 사용자 지정 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="7cf53-130">This policy is fully customizable, the same as any DLP policy that you create yourself from scratch.</span></span> <span data-ttu-id="7cf53-131">사용자가 더 이상 정책 팁 또는 전자 메일 알림을 받지 못하게 정책을 끄거나 삭제할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7cf53-131">You can also turn off or delete the policy, so that your users no longer receive policy tips or email notifications.</span></span>
  
![기본 DLP 정책이라는 DLP 정책](../media/260731e8-4d57-4c98-abec-07b052ec48d5.png)
  
## <a name="when-the-widget-does-and-does-not-appear"></a><span data-ttu-id="7cf53-133">위젯이 나타나고 나타나지 않는 경우</span><span class="sxs-lookup"><span data-stu-id="7cf53-133">When the widget does and does not appear</span></span>

<span data-ttu-id="7cf53-134">보안 및 준수 **센터** 홈 페이지의  권장 섹션에  공유 콘텐츠 추가 보호라는 &amp; 위젯이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="7cf53-134">The widget named **Further protect shared content** appears in the **Recommended for you** section of the **Home** page of the Security &amp; Compliance Center.</span></span> 
  
<span data-ttu-id="7cf53-135">이 위젯은</span><span class="sxs-lookup"><span data-stu-id="7cf53-135">This widget appears only when:</span></span>
  
- <span data-ttu-id="7cf53-136">보안 및 준수 센터 또는 관리 센터에는 데이터 &amp; 손실 Exchange 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7cf53-136">There are no data loss prevention policies in the Security &amp; Compliance Center or Exchange admin center.</span></span> <span data-ttu-id="7cf53-137">이 위젯은 DLP를 시작하는 데 도움을 주기 위해 고안된 것으로, 이미 DLP 정책이 있는 경우 나타나지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7cf53-137">This widget is intended to help you get started with DLP, so it doesn't appear if you already have DLP policies.</span></span>
    
- <span data-ttu-id="7cf53-138">지난 30일 동안 하나 이상의 신용 카드를 포함하는 콘텐츠가 조직 외부의 사용자와 공유된 경우</span><span class="sxs-lookup"><span data-stu-id="7cf53-138">Content containing least one credit card has been shared with someone outside your organization in the past 30 days.</span></span>
    
<span data-ttu-id="7cf53-139">위젯에서 규칙 일치를 사용할 수 있는 데 최대 48시간이 걸릴 수 있으므로 외부에서 공유되는 중요한 정보가 감지된 후 권장 사항 표시에 최대 2일이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7cf53-139">Note that rule matches can take up to 48 hours to be available to the widget, so after sensitive information shared externally is detected, it may take up to two days for the recommendation to appear.</span></span>
  
<span data-ttu-id="7cf53-140">마지막으로 위젯을 사용하여 기본 DLP 정책을 구체화하면 홈 페이지에서  위젯이 사라집니다.</span><span class="sxs-lookup"><span data-stu-id="7cf53-140">Finally, after you use the widget to refine the default DLP policy, the widget disappears from the **Home** page.</span></span> 
  

