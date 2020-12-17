---
title: 안전한 첨부 파일 관리
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
description: 안전한 첨부 파일을 관리하는 방법을 배워야 합니다.
ms.openlocfilehash: ea1dc20b8e9e51701730a72b8e8194d2abbfac99
ms.sourcegitcommit: f231eece2927f0d01072fd092db1eab15525bbc2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/17/2020
ms.locfileid: "49702452"
---
# <a name="manage-safe-attachments"></a><span data-ttu-id="1d0a1-103">안전한 첨부 파일 관리</span><span class="sxs-lookup"><span data-stu-id="1d0a1-103">Manage safe attachments</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWtn3I?autoplay=false]

<span data-ttu-id="1d0a1-104">이전의 Microsoft 365 ATP 또는 Advanced Threat Protection이라고 하는 Office 365용 Microsoft Defender는 Outlook, OneDrive, SharePoint 및 Teams에 악성 콘텐츠가 포함된 파일로부터 비즈니스를 보호하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d0a1-104">Microsoft Defender for Office 365 , formerly called Microsoft 365 ATP, or Advanced Threat Protection, helps protect your business against files that contain malicious content in Outlook, OneDrive, SharePoint, and Teams.</span></span>

## <a name="try-it"></a><span data-ttu-id="1d0a1-105">사용해 보세요!</span><span class="sxs-lookup"><span data-stu-id="1d0a1-105">Try it!</span></span>

1. <span data-ttu-id="1d0a1-106">관리 [센터로 이동하여 설치를](https://admin.microsoft.com) **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="1d0a1-106">Go to the [admin center](https://admin.microsoft.com), and select **Setup**.</span></span>
1. <span data-ttu-id="1d0a1-107">아래로 **스크롤하여 고급 위협으로부터 보호를 강화합니다.**</span><span class="sxs-lookup"><span data-stu-id="1d0a1-107">Scroll down to **Increase protection from advanced threats**.</span></span> <span data-ttu-id="1d0a1-108">**보기,** **관리** 및 **ATP 안전한 첨부 파일을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="1d0a1-108">Select **View**, **Manage**, and then **ATP safe attachments**.</span></span>
1. <span data-ttu-id="1d0a1-109">안전한 첨부 파일 규칙을 선택한 다음 편집 **아이콘을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1d0a1-109">Select your safe attachments rule, and then choose the **Edit** icon.</span></span>
1. <span data-ttu-id="1d0a1-110">설정을 **선택한** 다음 차단이 선택되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="1d0a1-110">Select **settings**, and then verify that Block is selected.</span></span>
1. <span data-ttu-id="1d0a1-111">아래로 스크롤합니다.</span><span class="sxs-lookup"><span data-stu-id="1d0a1-111">Scroll down.</span></span> <span data-ttu-id="1d0a1-112">리디렉션 **사용을** 선택하고 차단된 첨부 파일을 검토할 사람의 전자 메일 주소 또는 주소를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="1d0a1-112">Choose **Enable redirect**, and enter your email address or the address of the person you want to review the blocked attachments.</span></span>
1. <span data-ttu-id="1d0a1-113">적용 **대상을** 선택한 다음 도메인 이름을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1d0a1-113">Select **applied to**, and then select your domain name.</span></span>
1. <span data-ttu-id="1d0a1-114">규칙을 적용할 추가 도메인(예: onmicrosoft.com 도메인)을 추가로 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d0a1-114">Choose any additional domains you own (such as your onmicrosoft.com domain) that you would like the rule applied to.</span></span> <span data-ttu-id="1d0a1-115">추가를 **선택하고** **확인을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="1d0a1-115">Select **add**, and then **OK**.</span></span>
1. <span data-ttu-id="1d0a1-116">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1d0a1-116">Select **Save**.</span></span>

<span data-ttu-id="1d0a1-117">ATP 안전한 첨부 파일 규칙이 업데이트되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1d0a1-117">Your ATP safe attachments rule has been updated.</span></span>

<span data-ttu-id="1d0a1-118">이제 보호가 시작된 후 Outlook, OneDrive, SharePoint 또는 Teams에서 악성 파일을 열 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1d0a1-118">Now that protection is in place, you won't be able to open a malicious file from Outlook, OneDrive, SharePoint, or Teams.</span></span> <span data-ttu-id="1d0a1-119">영향을 받는 파일에는 옆에 빨간색 보호가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d0a1-119">Affected files will have red shields next to them.</span></span> <span data-ttu-id="1d0a1-120">누군가가 차단된 파일을 열려고 시도하면 경고 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d0a1-120">If someone attempts to open a blocked file, they'll receive a warning message.</span></span>

<span data-ttu-id="1d0a1-121">정책이 한 동안 적용된 후 보고서 페이지를 방문하여 검사된 기능을 확인하십시오.</span><span class="sxs-lookup"><span data-stu-id="1d0a1-121">After your policy has been in place for a while, visit the Reports page to see what has been scanned.</span></span>