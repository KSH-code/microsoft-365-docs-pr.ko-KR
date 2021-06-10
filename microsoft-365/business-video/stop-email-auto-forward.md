---
title: 전자 메일 자동 전달 중지
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: 소유 정보 도용을 방지하기 위한 메일 흐름 규칙을 만들어 자동 전달 전자 메일을 중지하는 방법을 학습합니다.
ms.openlocfilehash: 82e4c80b0edc501889e0fc4dc28f1ec1ad703568
ms.sourcegitcommit: a05f61a291eb4595fa9313757a3815b7f217681d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/29/2021
ms.locfileid: "52706477"
---
# <a name="stop-email-auto-forward"></a><span data-ttu-id="5243f-103">전자 메일 자동 전달 중지</span><span class="sxs-lookup"><span data-stu-id="5243f-103">Stop email auto-forward</span></span>

## <a name="watch-stop-auto-forwarding-emails"></a><span data-ttu-id="5243f-104">감시: 전자 메일 자동 전달 중지</span><span class="sxs-lookup"><span data-stu-id="5243f-104">Watch: Stop auto-forwarding emails</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2W6kS?autoplay=false]

<span data-ttu-id="5243f-105">해커가 사용자의 사서함에 액세스할 수 있는 경우 사용자의 전자 메일을 외부 주소로 자동 전달하고 소유 정보를 도용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5243f-105">If a hacker gains access to a user's mailbox, they can auto-forward the user's email to an outside address and steal proprietary information.</span></span> <span data-ttu-id="5243f-106">메일 흐름 규칙을 만들어 이를 중지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5243f-106">You can stop this by creating a mail flow rule.</span></span>

## <a name="try-it"></a><span data-ttu-id="5243f-107">사용해 보세요!</span><span class="sxs-lookup"><span data-stu-id="5243f-107">Try it!</span></span>

1. <span data-ttu-id="5243f-108">Microsoft 365 관리 센터에서 Exchange **,** **메일** 흐름 을 선택하고  규칙 탭에서 더하기 기호를 선택하고 새 규칙 만들기 를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="5243f-108">From the Microsoft 365 admin center, select **Exchange**, **mail flow**, and on the **rules** tab, select the plus sign and choose **create a new rule**.</span></span>
1. <span data-ttu-id="5243f-109">추가 **옵션 을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="5243f-109">Select **More options**.</span></span> <span data-ttu-id="5243f-110">새 규칙의 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5243f-110">Name your new rule.</span></span>
1. <span data-ttu-id="5243f-111">그런 다음 이 규칙을 적용하기 위한 드롭다운을 **열고** 보낸 사람 **을** 선택한 다음 외부 내부 **입니다.**</span><span class="sxs-lookup"><span data-stu-id="5243f-111">Then open the drop-down for **apply this rule if**, select **the sender**, and then **is external internal**.</span></span>
1. <span data-ttu-id="5243f-112">조직 **내부 를 선택한** 다음 확인 **을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="5243f-112">Select **Inside the organization**, and then **OK**.</span></span>
1. <span data-ttu-id="5243f-113">조건 **추가를 선택하고** 드롭다운을 열고 메시지 속성 **을 선택한** 다음 메시지 유형 **을 포함합니다.**</span><span class="sxs-lookup"><span data-stu-id="5243f-113">Choose **add condition**, open the drop-down, select **The message properties**, then **include the message type**.</span></span>
1. <span data-ttu-id="5243f-114">메시지 유형 **선택 드롭다운을** 열고 자동 **전달,** 확인을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="5243f-114">Open the **select message type** drop-down, choose **Auto-forward**, then **OK**.</span></span>
1. <span data-ttu-id="5243f-115">다음 **작업을 합니다.** 드롭다운을 열고 메시지 **차단을** 선택한 다음 메시지를 **거부하고 설명을 포함합니다.**</span><span class="sxs-lookup"><span data-stu-id="5243f-115">Open the **Do the following** drop-down, select **Block the message**, then **reject the message and include an explanation**.</span></span>
1. <span data-ttu-id="5243f-116">설명에 대한 메시지 텍스트를 입력한 다음 확인 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="5243f-116">Enter the message text for your explanation, then select **OK**.</span></span>
1. <span data-ttu-id="5243f-117">아래쪽으로 스크롤하고 저장 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="5243f-117">Scroll to the bottom and select **Save**.</span></span>

    <span data-ttu-id="5243f-118">규칙이 만들어지며 해커는 더 이상 메시지를 자동 전달할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5243f-118">Your rule has been created, and hackers will no longer be able to auto-forward messages.</span></span>

## <a name="related-content"></a><span data-ttu-id="5243f-119">관련 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="5243f-119">Related content</span></span>

<span data-ttu-id="5243f-120">[사용자의 다른 전자 메일 별칭 추가](../admin/email/add-another-email-alias-for-a-user.md)(문서)</span><span class="sxs-lookup"><span data-stu-id="5243f-120">[Add another email alias for a user](../admin/email/add-another-email-alias-for-a-user.md) (article)</span></span>\
<span data-ttu-id="5243f-121">[Microsoft 365에서 전자 메일 전달 구성](../admin/email/configure-email-forwarding.md)(문서)</span><span class="sxs-lookup"><span data-stu-id="5243f-121">[Configure email forwarding in Microsoft 365](../admin/email/configure-email-forwarding.md) (article)</span></span>\
<span data-ttu-id="5243f-122">[비즈니스 관리자를 위한 전자](/exchange/troubleshoot/email-delivery/email-delivery-issues) 메일 Office 365 문제 찾기 및 해결(문서)</span><span class="sxs-lookup"><span data-stu-id="5243f-122">[Find and fix email delivery issues as an Office 365 for business admin](/exchange/troubleshoot/email-delivery/email-delivery-issues) (article)</span></span>