---
title: 콘텐츠 형식을 허브로 푸시
description: 콘텐츠 형식을 허브로 밀어 넣는 방법에 대해 알아봅니다.
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: a852207bfd1a2a7643ce8895a533371d194954cf
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/28/2020
ms.locfileid: "48296101"
---
# <a name="push-content-types-to-a-hub"></a><span data-ttu-id="74af7-103">콘텐츠 형식을 허브로 푸시</span><span class="sxs-lookup"><span data-stu-id="74af7-103">Push content types to a hub</span></span>

<span data-ttu-id="74af7-104">중요 한 콘텐츠 형식을 SharePoint 라이브러리 및 목록에서 더 일관 되 게 사용할 수 있도록 하려면 선택한 허브에 저장 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="74af7-104">To make important content types more consistently available to SharePoint libraries and lists, you can push them to the hubs that you choose.</span></span> <span data-ttu-id="74af7-105">이렇게 하면 허브와 연결 된 사이트 및 허브에 추가 되는 모든 새 사이트에 만들어지는 모든 새 목록 및 라이브러리에 해당 사용자가 자동으로 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="74af7-105">This automatically adds them to any new lists and libraries created on the sites associated with the hub, and to any new sites added to the hub.</span></span>

<span data-ttu-id="74af7-106">이 기능이 작동 하려면 푸시되는 콘텐츠 형식이 이미 게시 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="74af7-106">For this feature to work, The content types being pushed must already be published.</span></span>

<span data-ttu-id="74af7-107">콘텐츠 형식을 허브로 푸시 하려면</span><span class="sxs-lookup"><span data-stu-id="74af7-107">To push content types to hubs</span></span>

1. <span data-ttu-id="74af7-108">SharePoint 관리 센터에서 **content services**를 확장 한 다음 **콘텐츠 형식 갤러리**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="74af7-108">In the SharePoint admin center, expand **Content services**, and then click **Content type gallery**.</span></span>

2. <span data-ttu-id="74af7-109">허브에 푸시할 콘텐츠 형식을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="74af7-109">Click the content type that you want to push to hubs.</span></span>

3. <span data-ttu-id="74af7-110">명령 모음에서 **편집** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="74af7-110">Click **Edit** in the command bar.</span></span>
 
4. <span data-ttu-id="74af7-111">**허브 사이트 선택을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="74af7-111">Click **Choose hub sites**.</span></span>
 
5. <span data-ttu-id="74af7-112">원하는 허브 사이트를 선택 하 고 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="74af7-112">Select the desired hub sites and then click **OK**.</span></span>
 
6. <span data-ttu-id="74af7-113">**저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="74af7-113">Click **Save**.</span></span>

<span data-ttu-id="74af7-114">기존 & 허브에 콘텐츠 형식을 처음으로 푸시할 경우, 허브 또는 연결 된 사이트를 방문 하는 경우 사이트에서 업데이트할 설정을 사용 하 여 최대 한 시간까지 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74af7-114">When pushing a content type to an existing hub & its existing associated sites for the first time, it can take up to an hour from when the hub or associated sites are visited, for the settings to update in the site.</span></span> <span data-ttu-id="74af7-115">허브에 대 한 모든 새 연결에는 이러한 대기가 필요 하지 않으며 설정이 몇 분 후에 반영 됩니다.</span><span class="sxs-lookup"><span data-stu-id="74af7-115">Any new associations to the hub will not require this wait and will have the settings reflected in a few minutes.</span></span> 

<span data-ttu-id="74af7-116">이 구성을 구성한 후에는 이러한 설정을 포함 하는 콘텐츠 형식을 몇 분 내에 허브와 함께 새로 연결 된 사이트에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74af7-116">Once this is configured, the content type with these settings will be available in any newly associated site with the hub in a few minutes.</span></span> <span data-ttu-id="74af7-117">만들어진 새 목록이 나 라이브러리는 만든 지 몇 분 내에 해당 콘텐츠 형식을 자동으로 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="74af7-117">Once available, any new list or library created will have the content type automatically added to it within a few minutes of creation.</span></span> <span data-ttu-id="74af7-118">푸시된 콘텐츠 형식은 문서 콘텐츠 형식에서 직접 또는 간접적으로 파생 되는 경우에만 문서 라이브러리에 추가 되 고, 콘텐츠 형식은 문서 콘텐츠 형식에서 직접 또는 간접적으로 파생 되지 않는 경우에만 목록에 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="74af7-118">A pushed content type will be added to a document library only if it derives directly or indirectly from the Document content type, and a content type will be added to a list only if it does not derive from the Document content type directly or indirectly.</span></span>

## <a name="see-also"></a><span data-ttu-id="74af7-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="74af7-119">See also</span></span>



  






