---
title: 전자 메일 자동 전달 중지
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
- okr_smb
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: 전자 메일 자동 전달을 중지하는 방법을 배워야 합니다.
ms.openlocfilehash: ebbe37ab5c4a60c6ac4b6ebf8877247199460fa1
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49925889"
---
# <a name="stop-email-auto-forward"></a><span data-ttu-id="eca09-103">전자 메일 자동 전달 중지</span><span class="sxs-lookup"><span data-stu-id="eca09-103">Stop email auto-forward</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2W6kS?autoplay=false]

<span data-ttu-id="eca09-104">해커가 사용자의 사서함에 액세스할 수 있는 경우 사용자의 전자 메일을 외부 주소로 자동 전달하고 소유 정보를 도용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eca09-104">If a hacker gains access to a user's mailbox, they can auto-forward the user's email to an outside address and steal proprietary information.</span></span> <span data-ttu-id="eca09-105">메일 흐름 규칙을 만들어 이를 중지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eca09-105">You can stop this by creating a mail flow rule.</span></span>

## <a name="try-it"></a><span data-ttu-id="eca09-106">사용해 보세요!</span><span class="sxs-lookup"><span data-stu-id="eca09-106">Try it!</span></span>

1. <span data-ttu-id="eca09-107">Microsoft 365 관리 센터에서 **Exchange,** 메일 흐름을  선택하고 규칙 탭에서 더하기 기호를 선택하고 새 규칙  **만들기를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="eca09-107">From the Microsoft 365 admin center, select **Exchange**, **mail flow**, and on the **rules** tab, select the plus sign and choose **create a new rule**.</span></span>
1. <span data-ttu-id="eca09-108">다른 **옵션을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="eca09-108">Select **More options**.</span></span> <span data-ttu-id="eca09-109">새 규칙의 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="eca09-109">Name your new rule.</span></span>
1. <span data-ttu-id="eca09-110">그런 다음 이 규칙을 적용하기 위해 드롭다운을 열고 보낸 사람이 선택된 다음 외부 **내부입니다.**</span><span class="sxs-lookup"><span data-stu-id="eca09-110">Then open the drop-down for **apply this rule if**, select **the sender**, and then **is external internal**.</span></span>
1. <span data-ttu-id="eca09-111">조직 **내부를 선택한** 다음 **확인을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="eca09-111">Select **Inside the organization**, and then **OK**.</span></span>
1. <span data-ttu-id="eca09-112">조건 **추가를** 선택하고 드롭다운을 열고 메시지 속성을 **선택한** 다음 메시지 **유형을 포함합니다.**</span><span class="sxs-lookup"><span data-stu-id="eca09-112">Choose **add condition**, open the drop-down, select **The message properties**, then **include the message type**.</span></span>
1. <span data-ttu-id="eca09-113">메시지 유형 **선택** 드롭다운을 열고 자동 전달을 선택한 **다음** **확인을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="eca09-113">Open the **select message type** drop-down, choose **Auto-forward**, then **OK**.</span></span>
1. <span data-ttu-id="eca09-114">다음 **Do 드롭다운을** 열고 메시지 차단을 선택한 다음 메시지를 **거부하고 설명을 포함합니다.**</span><span class="sxs-lookup"><span data-stu-id="eca09-114">Open the **Do the following** drop-down, select **Block the message**, then **reject the message and include an explanation**.</span></span>
1. <span data-ttu-id="eca09-115">설명에 대한 메시지 텍스트를 입력한 다음 확인을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="eca09-115">Enter the message text for your explanation, then select **OK**.</span></span>
1. <span data-ttu-id="eca09-116">아래로 스크롤하여 저장을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="eca09-116">Scroll to the bottom and select **Save**.</span></span>

    <span data-ttu-id="eca09-117">규칙이 만들어지며 해커는 더 이상 메시지를 자동 전달할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="eca09-117">Your rule has been created, and hackers will no longer be able to auto-forward messages.</span></span>