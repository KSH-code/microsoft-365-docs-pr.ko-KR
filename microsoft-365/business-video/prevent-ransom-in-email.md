---
title: 랜섬웨어에 대한 전자 메일 규칙 만들기
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
description: 랜섬웨어를 방지하기 위한 전자 메일 규칙을 만드는 방법을 배워야 합니다.
ms.openlocfilehash: 96822916753f2f70d481c213e7e31046f7081446
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2021
ms.locfileid: "51580501"
---
# <a name="create-email-rules-to-prevent-ransomware"></a><span data-ttu-id="5938e-103">랜섬웨어를 방지하기 위한 전자 메일 규칙 만들기</span><span class="sxs-lookup"><span data-stu-id="5938e-103">Create email rules to prevent ransomware</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWrWGt?autoplay=false]

<span data-ttu-id="5938e-104">Microsoft 365 JavaScript, 배치 및 실행 파일과 같은 잠재적으로 위험한 파일이 랜섬웨어로부터 비즈니스를 열지 못하게 하여 비즈니스를 Outlook.</span><span class="sxs-lookup"><span data-stu-id="5938e-104">Microsoft 365 helps protect your business against ransomware by preventing potentially dangerous files, like JavaScript, batch, and executables, from being opened in Outlook.</span></span> <span data-ttu-id="5938e-105">추가 파일 형식을 차단하거나 경고하는 규칙을 추가하여 이 보호 수준을 높이기 위해 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="5938e-105">To increase this level of protection by adding rules that block or warn you of additional types of files, follow these steps.</span></span>

## <a name="try-it"></a><span data-ttu-id="5938e-106">사용해 보세요!</span><span class="sxs-lookup"><span data-stu-id="5938e-106">Try it!</span></span>

1. <span data-ttu-id="5938e-107">의 관리 센터에서 [https://admin.microsoft.com](https://admin.microsoft.com) 관리 **Exchange** **를 선택하세요.**</span><span class="sxs-lookup"><span data-stu-id="5938e-107">From the admin center at [https://admin.microsoft.com](https://admin.microsoft.com), choose **Exchange** under **Admin centers**.</span></span>
1. <span data-ttu-id="5938e-108">왼쪽 메뉴에서 메일 흐름 **을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="5938e-108">From the menu on the left, choose **mail flow**.</span></span>
1. <span data-ttu-id="5938e-109">규칙 탭에서 더하기 기호(+) 옆의 화살표를 선택한 다음 새 규칙 만들기 **를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="5938e-109">On the rules tab, choose the arrow next to the plus (+) symbol, and then choose **Create a new rule**.</span></span>
1. <span data-ttu-id="5938e-110">새 **규칙 페이지에서** 규칙의 이름을 입력하고 아래쪽으로 스크롤한 다음 추가 옵션을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="5938e-110">On the **new rule** page, enter a name for your rule, scroll to the bottom, and then choose **More options**.</span></span>
1. <span data-ttu-id="5938e-111">다음의 **경우 이 규칙 적용에서** **첨부 파일 을** 선택한 다음 다음 단어를 포함하는 파일 **확장명을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="5938e-111">Under **Apply this rule if**, select **Any attachment**, and then select **file extension includes these words**.</span></span>
1. <span data-ttu-id="5938e-112">단어 또는 구 지정 아래 상자에 규칙을 적용할 파일 확장명(예: 매크로를 포함할 수 있는 파일 확장명)을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="5938e-112">In the box under **specify words or phrases**, enter the file extensions that you want the rule to be applied to, such as file extensions that can contain macros.</span></span> <span data-ttu-id="5938e-113">더하기(+) 기호를 사용하여 한 번씩 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="5938e-113">Use the plus (+) symbol to add them one at a time.</span></span>

    <span data-ttu-id="5938e-114">랜섬웨어로부터 보호를 읽어 파일 형식에 대해 자세히 [알아보십시오.](../admin/security-and-compliance/secure-your-business-data.md#ransomware)</span><span class="sxs-lookup"><span data-stu-id="5938e-114">Learn more about file types by reading [Protect against ransomware](../admin/security-and-compliance/secure-your-business-data.md#ransomware).</span></span>

1. <span data-ttu-id="5938e-115">아래로 스크롤하여 목록을 검토한 다음 확인 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="5938e-115">Scroll down to review your list, and then choose **OK**.</span></span>
1. <span data-ttu-id="5938e-116">새 **규칙 페이지에서** 조건 추가 **를** 선택한 다음 다음으로 이동에서 **조건을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="5938e-116">On the **new rule** page, choose **add condition**, and then choose a condition under **Do the following**.</span></span>
1. <span data-ttu-id="5938e-117">선택할 수 있는 규칙 옵션이 많지만 이 예에서는 메시지를 받는 사람에게 **알리도록 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="5938e-117">You have many rule options to choose from, but in this example we'll choose to **Notify the recipient with a message**.</span></span>
1. <span data-ttu-id="5938e-118">알림에 대한 메시지 텍스트를 입력하고 확인 을 **선택 합니다.**</span><span class="sxs-lookup"><span data-stu-id="5938e-118">Enter message text for your notification, and then chose **OK**.</span></span>
1. <span data-ttu-id="5938e-119">선택 사항: 새 규칙  **페이지에서** 예외 추가를 선택하고 신뢰할 수 있는 보낸 사람이 보낸 메시지 등 규칙에 대한 예외에 대한 세부 정보를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="5938e-119">Optional: On the **new rule** page, choose **add exception**, and enter any details for exceptions to your rule, such as messages from trusted senders.</span></span>
1. <span data-ttu-id="5938e-120">새 규칙 페이지에서 저장 **을** 선택하고 제공된 규칙 요약 정보를 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="5938e-120">On the new rule page, choose **Save**, and review the rule summary information provided.</span></span>