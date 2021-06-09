---
title: Microsoft 365에 도메인 연결
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
- okr_smb
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: 도메인을 도메인에 연결하는 방법을 Microsoft 365.
ms.openlocfilehash: 1bec66a43026321ddf1979c73902a533bee3a07b
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49925113"
---
# <a name="connect-your-domain-to-microsoft-365-for-business"></a><span data-ttu-id="a0525-103">커넥트 도메인을 비즈니스용 Microsoft 365 수 있도록 설정</span><span class="sxs-lookup"><span data-stu-id="a0525-103">Connect your domain to Microsoft 365 for business</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LFpy?autoplay=false]

<span data-ttu-id="a0525-104">Google Workspace에서 전자 메일 Microsoft 365 설정하고 이동한 후 도메인을 도메인에 연결할 수 Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a0525-104">Once you’ve set up Microsoft 365 and moved your email data from Google Workspace, you can connect your domain to Microsoft 365.</span></span> 

<span data-ttu-id="a0525-105">먼저 Google에서 기존 DNS 레코드를 삭제해야 합니다. 그런 다음 새 DNS 레코드를 Google에서 추가할 수 Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a0525-105">First you will need to delete existing DNS records from Google, then we can add new DNS records from Microsoft 365.</span></span>

## <a name="try-it"></a><span data-ttu-id="a0525-106">사용해 보세요!</span><span class="sxs-lookup"><span data-stu-id="a0525-106">Try it!</span></span>

1. <span data-ttu-id="a0525-107">에서 Google Workspace 관리 콘솔에 [admin.google.com.](https://admin.google.com)</span><span class="sxs-lookup"><span data-stu-id="a0525-107">Sign into your Google Workspace admin console at [admin.google.com](https://admin.google.com).</span></span>
1. <span data-ttu-id="a0525-108">도메인, **도메인 관리,** **세부** 정보 **보기,** 도메인 관리, 왼쪽 nav에서 **DNS를** 선택합니다. </span><span class="sxs-lookup"><span data-stu-id="a0525-108">Select **Domains**, **Manage domains**, **View details**, **Manage domain**, then **DNS** in the left nav.</span></span>
1. <span data-ttu-id="a0525-109">아래로 스크롤하여 **가상** 레코드, **Google Workspace를** 열고 **삭제를** 선택한 다음 다시 **삭제를** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a0525-109">Scroll down to **Synthetic records**, open **Google Workspace**, select **Delete**, then **Delete** again.</span></span>
1. <span data-ttu-id="a0525-110">아래로 스크롤하여 **사용자** 지정 리소스 레코드로 이동하여 이전에 사용자 지정 리소스 레코드에 대해 이전에 만들 수 있는 DNS 레코드를 포함하여 나타나는 기존 DNS 레코드를 Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a0525-110">Scroll down to **Custom resource records** and delete any existing DNS records that appear, including any you may have created previously for Microsoft 365.</span></span>
1. <span data-ttu-id="a0525-111">Microsoft 365 [관리 센터로 이동하세요.](https://admin.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="a0525-111">Go to the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span>
1. <span data-ttu-id="a0525-112">왼쪽 nav에서 모두 표시 **,** 설정 **를 선택 합니다.** </span><span class="sxs-lookup"><span data-stu-id="a0525-112">In the left nav, choose, **Show all**, **Settings**, **Domains**.</span></span>
1. <span data-ttu-id="a0525-113">그런 다음 기본 도메인을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0525-113">Then choose your default domain.</span></span>
1. <span data-ttu-id="a0525-114">설치 **계속 을** 선택한 다음 도메인을 연결하려면 계속을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="a0525-114">Select **Continue setup**, then, to connect your domain, choose  **Continue**.</span></span>
1. <span data-ttu-id="a0525-115">아래로 스크롤하여 Google에 복사해야 하는 DNS 레코드를 시청합니다.</span><span class="sxs-lookup"><span data-stu-id="a0525-115">Scroll down to view the DNS records that need to be copied to Google.</span></span>
1. <span data-ttu-id="a0525-116">**MX 레코드를** 열고 주소 또는 값 **에서** 레코드를 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="a0525-116">Open **MX Records**, and under **Points to address or value**, copy the record.</span></span>
1. <span data-ttu-id="a0525-117">Google로 돌아가 사용자 지정 **리소스** 레코드 섹션에서 레코드 유형 드롭다운을 열고 **MX 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="a0525-117">Return to Google, and in the **Custom resource records** section, open the record type dropdown and select **MX**.</span></span>
1. <span data-ttu-id="a0525-118">데이터 **필드에** 복사한 레코드를 붙여 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="a0525-118">In the **Data** field, paste the record you copied.</span></span>
1. <span data-ttu-id="a0525-119">그런 다음 **추가** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a0525-119">Then select **Add**.</span></span>
1. <span data-ttu-id="a0525-120">CNAME 및 TXT 레코드에 대한 프로세스를 반복하고 Google DNS 관리 페이지에 값을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a0525-120">Repeat the process for CNAME and TXT records and add the values in the Google DNS management page.</span></span>
1. <span data-ttu-id="a0525-121">Microsoft 365 관리 센터로 돌아가 계속을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="a0525-121">Return to the Microsoft 365 Admin center and select **Continue**.</span></span>

    <span data-ttu-id="a0525-122">도메인 설정이 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a0525-122">Your domain setup is complete.</span></span>