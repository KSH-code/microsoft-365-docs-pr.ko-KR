---
title: Google Workspace 도메인 추가
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
- okr_smb
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Google Workspace에서 비즈니스용 Microsoft 365로 도메인을 이동하는 방법을 배워야 합니다.
ms.openlocfilehash: 23ca451cfdcb67898a10935101efedcdf360ef91
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49925005"
---
# <a name="add-your-google-workspace-domain-to-microsoft-365"></a><span data-ttu-id="673bf-103">Microsoft 365에 Google Workspace 도메인 추가</span><span class="sxs-lookup"><span data-stu-id="673bf-103">Add your Google Workspace domain to Microsoft 365</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LWKT?autoplay=false]

<span data-ttu-id="673bf-104">비즈니스 전자 메일 주소를 계속 사용할 수 있도록 비즈니스용 Microsoft 365에 Google Workspace 도메인을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="673bf-104">Add your Google Workspace domain to Microsoft 365 for business so you can keep using your business email address.</span></span>

## <a name="try-it"></a><span data-ttu-id="673bf-105">사용해 보세요!</span><span class="sxs-lookup"><span data-stu-id="673bf-105">Try it!</span></span>

1. <span data-ttu-id="673bf-106">[Microsoft 365 관리 센터로 이동하세요.](https://admin.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="673bf-106">Go to the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span>
1. <span data-ttu-id="673bf-107">Microsoft 365 관리 센터의 왼쪽 nav에서 모두  **표시,** 설정 및 **도메인을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="673bf-107">In the Microsoft 365 Admin Center, in the left nav, select **Show all**, **Settings** and then **Domains**.</span></span>
1. <span data-ttu-id="673bf-108">Choose **Add domain**, enter your domain name then select Use this **domain**.</span><span class="sxs-lookup"><span data-stu-id="673bf-108">Choose **Add domain**, enter your domain name then select **Use this domain**.</span></span> 
1. <span data-ttu-id="673bf-109">Choose, **Add a TXT record to the domains DNS records,** select **Continue,** and copy the TXT value.</span><span class="sxs-lookup"><span data-stu-id="673bf-109">Choose, **Add a TXT record to the domains DNS records**, select **Continue**, and copy the TXT value.</span></span> 
1. <span data-ttu-id="673bf-110">Go back to the [Google Admin Console,](https://admin.google.com)choose **Domains,** **Manage domains,** **View Details, Manage** **domain**, **DNS,** and then scroll down to **Custom resource records.**</span><span class="sxs-lookup"><span data-stu-id="673bf-110">Go back to the [Google Admin Console](https://admin.google.com), choose **Domains**, **Manage domains**, **View Details**, **Manage domain**, **DNS**, and  then scroll down to **Custom resource records**.</span></span> 
1. <span data-ttu-id="673bf-111">레코드 종류 드롭다운을 열고 **TXT를** 선택한 다음 복사한 TXT 값을 붙여 넣은 다음 추가를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="673bf-111">Open the record type drop-down, choose **TXT**, paste the TXT value you copied then select **Add**.</span></span> 

    <span data-ttu-id="673bf-112">업데이트는 일반적으로 몇 분 이내에 팩트에 걸리지만 최대 48시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="673bf-112">The update usually takes a fact within a few minutes but may take up to 48 hours.</span></span> 
1. <span data-ttu-id="673bf-113">Microsoft 365 관리 센터로 돌아가서 확인을 선택한 다음 **닫습니다.**</span><span class="sxs-lookup"><span data-stu-id="673bf-113">Return to the Microsoft 365 Admin Center, select **Verify**,and then **Close**.</span></span> 
1. <span data-ttu-id="673bf-114">도메인을 사용자의 기본 전자 메일로 설정하려면 왼쪽 nav에서 사용자 활성 **사용자를**  >  **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="673bf-114">To set your domain as the primary email for your users, in the left nav, select **Users** > **Active users**.</span></span> 
1. <span data-ttu-id="673bf-115">사용자를 선택하고 사용자 이름 **및** 전자 메일 관리, **편집,** 드롭다운에서 도메인 선택, 완료 **및** 변경 내용 **저장을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="673bf-115">Choose a user, select **Manage username and email**, **Edit**, select your domain from the dropdown, then select **Done** and **Save changes**.</span></span> 
1. <span data-ttu-id="673bf-116">각 사용자에 대해 이 프로세스를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="673bf-116">Repeat this process for each user.</span></span> 

    <span data-ttu-id="673bf-117">완료되면 Office 앱을 설치하고 전자 메일 및 일정 항목을 Microsoft 365로 마이그레이션할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="673bf-117">When you're finished, you'll be ready to install Office apps and migrate your email and calendar items to Microsoft 365.</span></span> 