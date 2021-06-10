---
title: Google Workspace 도메인 추가
f1.keywords:
- NOCSH
ms.author: twerner
author: twernermsft
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
description: Google Workspace에서 비즈니스용 도메인으로 도메인을 Microsoft 365 방법을 배워야 합니다.
ms.openlocfilehash: 814e714527467bb6e7008ea141989f3117ddcdd8
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2021
ms.locfileid: "51578774"
---
# <a name="add-your-google-workspace-domain-to-microsoft-365"></a><span data-ttu-id="ae985-103">Google Workspace 도메인을 추가하여 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ae985-103">Add your Google Workspace domain to Microsoft 365</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LWKT?autoplay=false]

<span data-ttu-id="ae985-104">비즈니스용 전자 메일 주소를 계속 Microsoft 365 수 있도록 비즈니스용 전자 메일에 Google Workspace 도메인을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="ae985-104">Add your Google Workspace domain to Microsoft 365 for business so you can keep using your business email address.</span></span>

## <a name="try-it"></a><span data-ttu-id="ae985-105">사용해 보세요!</span><span class="sxs-lookup"><span data-stu-id="ae985-105">Try it!</span></span>

1. <span data-ttu-id="ae985-106">Microsoft 365 [관리 센터로 이동하세요.](https://admin.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="ae985-106">Go to the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span>
1. <span data-ttu-id="ae985-107">in the Microsoft 365 Admin Center, in the left nav, select **Show all**, **설정** and then **Domains**.</span><span class="sxs-lookup"><span data-stu-id="ae985-107">In the Microsoft 365 Admin Center, in the left nav, select **Show all**, **Settings** and then **Domains**.</span></span>
1. <span data-ttu-id="ae985-108">도메인 **추가를** 선택하고 도메인 이름을 입력한 다음 이 **도메인 사용을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="ae985-108">Choose **Add domain**, enter your domain name then select **Use this domain**.</span></span> 
1. <span data-ttu-id="ae985-109">**TXT** 레코드를 도메인 DNS 레코드에 추가를 선택하고 계속을 선택하고 TXT 값을 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="ae985-109">Choose, **Add a TXT record to the domains DNS records**, select **Continue**, and copy the TXT value.</span></span> 
1. <span data-ttu-id="ae985-110">Go back to the [Google Admin Console](https://admin.google.com), choose **Domains**, **Manage domains**, View **Details**, **Manage domain**, **DNS**, and then scroll down to Custom **resource records**.</span><span class="sxs-lookup"><span data-stu-id="ae985-110">Go back to the [Google Admin Console](https://admin.google.com), choose **Domains**, **Manage domains**, **View Details**, **Manage domain**, **DNS**, and  then scroll down to **Custom resource records**.</span></span> 
1. <span data-ttu-id="ae985-111">레코드 종류 드롭다운을 열고 **TXT를** 선택하고 복사한 TXT 값을 붙여 넣은 다음 추가 를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="ae985-111">Open the record type drop-down, choose **TXT**, paste the TXT value you copied then select **Add**.</span></span> 

    <span data-ttu-id="ae985-112">일반적으로 업데이트는 몇 분 이내에 팩트가 사용되지만 최대 48시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae985-112">The update usually takes a fact within a few minutes but may take up to 48 hours.</span></span> 
1. <span data-ttu-id="ae985-113">Microsoft 365 관리 센터로 돌아가서 **확인을** 선택한 다음 **닫습니다.**</span><span class="sxs-lookup"><span data-stu-id="ae985-113">Return to the Microsoft 365 Admin Center, select **Verify**,and then **Close**.</span></span> 
1. <span data-ttu-id="ae985-114">도메인을 사용자의 기본 전자 메일로 설정하려면 왼쪽 nav에서 사용자 활성 **사용자를**  >  **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="ae985-114">To set your domain as the primary email for your users, in the left nav, select **Users** > **Active users**.</span></span> 
1. <span data-ttu-id="ae985-115">사용자를 선택하고 사용자 이름 및 전자 **메일 관리,** **편집을** 선택하고 드롭다운에서 도메인을 선택한 다음 완료 **및** 변경 내용 **저장을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="ae985-115">Choose a user, select **Manage username and email**, **Edit**, select your domain from the dropdown, then select **Done** and **Save changes**.</span></span> 
1. <span data-ttu-id="ae985-116">각 사용자에 대해 이 프로세스를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="ae985-116">Repeat this process for each user.</span></span> 

    <span data-ttu-id="ae985-117">완료되면 앱 앱을 설치하고 전자 메일 및 일정 Office 마이그레이션할 준비가 Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ae985-117">When you're finished, you'll be ready to install Office apps and migrate your email and calendar items to Microsoft 365.</span></span> 