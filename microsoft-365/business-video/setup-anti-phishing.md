---
title: 피싱 방지 보호 설정
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
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
description: 피싱 방지 보호를 설정하는 방법을 학습합니다.
ms.openlocfilehash: 8cef8f916a8a3e2b27dd7f76ddecd921d59ca0c4
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/04/2021
ms.locfileid: "50422006"
---
# <a name="set-up-anti-phishing"></a><span data-ttu-id="c6d19-103">피싱 방지 설정</span><span class="sxs-lookup"><span data-stu-id="c6d19-103">Set up anti-phishing</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWvt9r?autoplay=false]

<span data-ttu-id="c6d19-104">피싱은 전자 메일이 익숙한 원본에서 보낸 것으로 보이지만 개인 정보를 수집하려고 시도하는 악의적인 공격입니다.</span><span class="sxs-lookup"><span data-stu-id="c6d19-104">Phishing is a malicious attack where an email looks like it was sent from a familiar source, but it attempts to collect your personal information.</span></span> <span data-ttu-id="c6d19-105">기본적으로 Microsoft 365에는 일부 피싱 방지 보호가 포함되어 있지만 설정을 구체화하여 해당 보호를 강화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6d19-105">By default, Microsoft 365 includes some anti-phishing protection, but you can increase that protection by refining the settings.</span></span> <span data-ttu-id="c6d19-106">살펴보시겠어요.</span><span class="sxs-lookup"><span data-stu-id="c6d19-106">Let's take a look.</span></span>

## <a name="try-it"></a><span data-ttu-id="c6d19-107">사용해 보세요!</span><span class="sxs-lookup"><span data-stu-id="c6d19-107">Try it!</span></span>

1. <span data-ttu-id="c6d19-108">관리 센터 에서 [https://admin.microsoft.com](https://admin.microsoft.com) 보안, **위협** 관리, 정책, ATP 피싱 방지 **를 선택합니다.** </span><span class="sxs-lookup"><span data-stu-id="c6d19-108">In the admin center at [https://admin.microsoft.com](https://admin.microsoft.com), select **Security**, **Threat Management**, **Policy**, then **ATP Anti-phishing**.</span></span>
1. <span data-ttu-id="c6d19-109">기본 정책을 선택하여 구체화합니다. </span><span class="sxs-lookup"><span data-stu-id="c6d19-109">Select **Default Policy** to refine it.</span></span>
1. <span data-ttu-id="c6d19-110">가장 **섹션에서** 편집을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="c6d19-110">In the **Impersonation** section, select **Edit**.</span></span>
1. <span data-ttu-id="c6d19-111">보호할 **도메인 추가로** 이동하여 소유한 도메인을 자동으로 포함하려면 토글을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c6d19-111">Go to **Add domains to protect** and select the toggle to automatically include the domains you own.</span></span>
1. <span data-ttu-id="c6d19-112">작업으로 **이동하여** 드롭다운을 열고 가장된 사용자가 전자 메일을 보낸 경우 **를** 선택하고 원하는 작업을 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="c6d19-112">Go to **Actions**, open the drop-down **If email is sent by an impersonated user**, and choose the action you want.</span></span>

    <span data-ttu-id="c6d19-113">Open the drop-down **If email is sent by an impersonated domain** and choose the action you want.</span><span class="sxs-lookup"><span data-stu-id="c6d19-113">Open the drop-down **If email is sent by an impersonated domain** and choose the action you want.</span></span>
1. <span data-ttu-id="c6d19-114">가장 보안 팁 **켜기 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="c6d19-114">Select **Turn on impersonation safety tips**.</span></span> <span data-ttu-id="c6d19-115">시스템에서 가장된 사용자, 도메인 또는 비정상적인 문자를 감지할 때 사용자에게 팁을 제공해야 하는지 여부를 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="c6d19-115">Choose whether tips should be provided to users when the system detects impersonated users, domains, or unusual characters.</span></span> <span data-ttu-id="c6d19-116">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c6d19-116">Select **Save**.</span></span>
1. <span data-ttu-id="c6d19-117">사서함 **인텔리전스를** 선택하고 설정되어 있는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6d19-117">Select **Mailbox intelligence** and verify that it's turned on.</span></span> <span data-ttu-id="c6d19-118">이렇게 하면 사용 패턴을 학습하여 전자 메일의 효율성을 향상할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6d19-118">This allows your email to be more efficient by learning usage patterns.</span></span>
1. <span data-ttu-id="c6d19-119">신뢰할 **수 있는 보낸 사람 및 도메인 추가를 선택 합니다.**</span><span class="sxs-lookup"><span data-stu-id="c6d19-119">Choose **Add trusted senders and domains**.</span></span> <span data-ttu-id="c6d19-120">여기서는 가장으로 분류되지 않는 전자 메일 주소 또는 도메인을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6d19-120">Here you can add email addresses or domains that shouldn't be classified as an impersonation.</span></span>
1. <span data-ttu-id="c6d19-121">Choose **Review your settings**, make sure everything is correct, select **Save**, then **Close**.</span><span class="sxs-lookup"><span data-stu-id="c6d19-121">Choose **Review your settings**, make sure everything is correct, select **Save**, then **Close**.</span></span>

    <span data-ttu-id="c6d19-122">이제 조직에서 피싱 위협으로부터 더 나은 보호를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c6d19-122">Your organization now has better protection from phishing threats.</span></span>