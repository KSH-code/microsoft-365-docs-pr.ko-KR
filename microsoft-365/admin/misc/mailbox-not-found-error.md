---
title: 웹에서 Outlook에서 사서함을 찾을 수 없는 오류 발생
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
ROBOTS: NOINDEX, NOFOLLOW
search.appverid:
- MET150
ms.assetid: 7e453a40-66df-44ab-92a1-96786cb7fb34
description: '**사서함을 찾을 수 없음** 오류는 웹에서 Outlook에 연결하는 데 사용한 계정에 Exchange Online 라이선스가 없음을 의미합니다.'
ms.openlocfilehash: 5ae850da3b9a4022c01f8bf4469f5e86f44b10bd
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52537442"
---
# <a name="getting-a-mailbox-not-found-error-in-outlook-on-the-web"></a><span data-ttu-id="7dff8-103">웹용 Outlook에서 사서함을 찾을 수 없음 오류가 발생하나요?</span><span class="sxs-lookup"><span data-stu-id="7dff8-103">Getting a mailbox not found error in Outlook on the web?</span></span>

<span data-ttu-id="7dff8-104">웹용 Outlook을 사용 중이고 **사서함을 찾을 수 없음** 오류가 표시되는 경우 웹용 Outlook에 연결하는 데 사용한 계정에 Exchange Online 라이선스가 없으므로 , 계정과 연결된 사서함이 없는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="7dff8-104">If you're using Outlook on the web and you get a  **Mailbox couldn't be found for**  error, the account that you used to connect to Outlook on the web doesn't have an Exchange Online license and therefore, no mailbox is associated with the account.</span></span> 

## <a name="assign-a-license-to-your-account"></a><span data-ttu-id="7dff8-105">계정에 라이선스 할당</span><span class="sxs-lookup"><span data-stu-id="7dff8-105">Assign a license to your account</span></span>

<span data-ttu-id="7dff8-106">관리자는 다음 단계에 따라 계정에 라이선스를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7dff8-106">Your admin can assign a license to your account by following these steps:</span></span>

1. <span data-ttu-id="7dff8-107">[Microsoft 365 관리 센터](https://portal.office.com/adminportal/home#/homepage)를 열고 **사용자** 섹션 아래의 **활성 사용자** 로 이동하여 오류가 표시되는 사용자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7dff8-107">Open the  [Microsoft 365 admin center](https://portal.office.com/adminportal/home#/homepage)  and go to  **Active users**  under the  **Users**  section, and select the user who is seeing the error.</span></span>
1. <span data-ttu-id="7dff8-108">열리는 사용자 페이지에서 **라이선스 및 앱** 섹션으로 이동하여 적절한 **위치** 값을 선택하고 Exchange Online이 포함된 라이선스를 할당합니다(세부 정보를 보려면 라이선스를 확장).</span><span class="sxs-lookup"><span data-stu-id="7dff8-108">In the user page that opens, go to the  **Licenses and Apps**  section, select the appropriate  **Location**  value, and assign a license that contains Exchange Online (expand the license to see its details).</span></span> 
1. <span data-ttu-id="7dff8-109">작업을 마쳤으면 **변경 내용 저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7dff8-109">When you're finished, click  **Save changes**.</span></span>

## <a name="related-content"></a><span data-ttu-id="7dff8-110">관련 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="7dff8-110">Related content</span></span>

<span data-ttu-id="7dff8-111">[사용자의 다른 전자 메일 별칭 추가](../email/add-another-email-alias-for-a-user.md) (문서)</span><span class="sxs-lookup"><span data-stu-id="7dff8-111">[Add another email alias for a user](../email/add-another-email-alias-for-a-user.md) (article)</span></span>

<span data-ttu-id="7dff8-112">[Microsoft 365에서 전자 메일 전달 구성](../email/configure-email-forwarding.md)(문서)</span><span class="sxs-lookup"><span data-stu-id="7dff8-112">[Configure email forwarding in Microsoft 365](../email/configure-email-forwarding.md) (article)</span></span>

<span data-ttu-id="7dff8-113">[공유 사서함 만들기](../email/create-a-shared-mailbox.md)(문서)</span><span class="sxs-lookup"><span data-stu-id="7dff8-113">[Create a shared mailbox](../email/create-a-shared-mailbox.md) (article)</span></span>