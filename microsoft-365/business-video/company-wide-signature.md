---
title: 회사 전체 서명 만들기
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
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: 회사 전체의 전자 메일 서명을 만드는 방법을 배워야 합니다.
ms.openlocfilehash: 64c269abd25cab74ec5b0836975902e46a611c8c
ms.sourcegitcommit: f231eece2927f0d01072fd092db1eab15525bbc2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/17/2020
ms.locfileid: "49703031"
---
# <a name="create-a-company-wide-email-signature"></a><span data-ttu-id="8f066-103">회사 전체 전자 메일 서명 만들기</span><span class="sxs-lookup"><span data-stu-id="8f066-103">Create a company-wide email signature</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1IEWf?autoplay=false]

<span data-ttu-id="8f066-104">조직 내 사람들이 보낸 모든 전자 메일에 회사 전체 전자 메일 서명이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="8f066-104">A company-wide email signature appears on every email sent by people in your organization.</span></span> <span data-ttu-id="8f066-105">회사 연락처 정보 또는 법적 고지 사항과 같은 중요한 세부 정보를 표시하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f066-105">You can use it to display important details, like your company contact information or a legal disclaimer.</span></span> 

## <a name="try-it"></a><span data-ttu-id="8f066-106">사용해 보세요!</span><span class="sxs-lookup"><span data-stu-id="8f066-106">Try it!</span></span>

1. <span data-ttu-id="8f066-107">Microsoft 365 관리 센터에서 **Exchange를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="8f066-107">In the Microsoft 365 admin center, select **Exchange**.</span></span>
1. <span data-ttu-id="8f066-108">메일 **흐름을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="8f066-108">Select **Mail flow**.</span></span>
1. <span data-ttu-id="8f066-109">추가 **+ 를** 선택한 다음 고지 조항 **적용을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="8f066-109">Select **Add +**, and then select **Apply disclaimers**.</span></span>
1. <span data-ttu-id="8f066-110">새 규칙 **페이지에서 다음을** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8f066-110">On the **New rule** page:</span></span>
    1. <span data-ttu-id="8f066-111">규칙의 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="8f066-111">Enter a name for the rule.</span></span>
    1. <span data-ttu-id="8f066-112">드롭다운 **목록의** 이 규칙 적용 목록에서 모든 메시지에 **적용을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="8f066-112">From the **Apply this rule if** drop-down list, select **Apply to all messages**.</span></span>
    1. <span data-ttu-id="8f066-113">다음 드롭다운 목록 **실행 목록에서** 고지 조항 추가가 **표시되는지** 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f066-113">In the **Do the following** drop-down list, verify that **Append the disclaimer** is displayed.</span></span>
    1. <span data-ttu-id="8f066-114">페이지 오른쪽에서 텍스트 입력을 선택한 다음 전자 메일 서명에 대한 텍스트를 고지문 지정 텍스트 상자에 **입력합니다.**</span><span class="sxs-lookup"><span data-stu-id="8f066-114">On the right side of the page, select **Enter text**, and then enter the text for your email signature in the **Specify disclaimer** text box.</span></span> <span data-ttu-id="8f066-115">HTML로 텍스트 서식을 지정하여 서명의 모양을 향상시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f066-115">You can improve the look of your signature by formatting the text with HTML.</span></span>
    1. <span data-ttu-id="8f066-116">서명에 이미지를 표시하려면 해당 이미지에 대해 공개적으로 사용 가능한 URL을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f066-116">If you want an image to appear in your signature, you'll need to use a publicly available URL for that image.</span></span> <span data-ttu-id="8f066-117">웹에서 이미지를 찾아 마우스 오른쪽 단추로 클릭한 다음 이미지 주소 **복사를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="8f066-117">Browse to the image on the web, right-click it, and select **Copy image address**.</span></span> <span data-ttu-id="8f066-118">주소를 고지 조항 지정 텍스트 **상자에 붙여** 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="8f066-118">Paste the address into the **Specify disclaimer** text box.</span></span> <span data-ttu-id="8f066-119">확인을 **선택한** 다음 아래로 스크롤합니다.</span><span class="sxs-lookup"><span data-stu-id="8f066-119">Select **OK**, then scroll down.</span></span>
    1. <span data-ttu-id="8f066-120">서명이 암호화된 전자 메일에서 작동하는지 확인하기 위해 변경 옵션을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="8f066-120">To make sure the signature works with encrypted emails, add a fallback option.</span></span> <span data-ttu-id="8f066-121">On the right of the page, choose **one,** choose **Wrap,** and then select **OK.**</span><span class="sxs-lookup"><span data-stu-id="8f066-121">On the right of the page, choose **Select one**, choose **Wrap**, and then select **OK**.</span></span>
    1. <span data-ttu-id="8f066-122">아래로 스크롤하여 모드를 적용으로 설정한 다음 **저장을** **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="8f066-122">Scroll down and leave the mode set to **Enforce**, and then select **Save**.</span></span>
1. <span data-ttu-id="8f066-123">경고 메시지가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="8f066-123">A warning message will appear.</span></span> <span data-ttu-id="8f066-124">**다음의** 모든 메시지에 규칙을 적용하려면 '예'를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8f066-124">Select **Yes** to apply the rule to all future messages.</span></span>

    <span data-ttu-id="8f066-125">서명이 만들어졌습니다.</span><span class="sxs-lookup"><span data-stu-id="8f066-125">Your signature has been created.</span></span> <span data-ttu-id="8f066-126">다음 전자 메일을 보내면 방금 만든 서명이 볼 수 없지만 전자 메일 받는 사람에게 전자 메일이 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="8f066-126">When you send your next email, you won't see the signature you just created, but the email recipients will see it.</span></span>