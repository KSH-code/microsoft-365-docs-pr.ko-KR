---
title: 허브로 콘텐츠 유형 푸시
description: 허브로 콘텐츠 유형 푸시하는 방법 알아보기
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
ms.openlocfilehash: 89c03a70da364bd4b945debc64de02255dec15e1
ms.sourcegitcommit: 162c01dfaa2fdb3225ce4c24964c1065ce22ed5d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2021
ms.locfileid: "49975718"
---
# <a name="push-content-types-to-a-hub"></a><span data-ttu-id="729ac-103">허브로 콘텐츠 유형 푸시</span><span class="sxs-lookup"><span data-stu-id="729ac-103">Push content types to a hub</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4GyeV]  

</br>


<span data-ttu-id="729ac-104">SharePoint 라이브러리 및 목록에서 중요한 콘텐츠 형식을 더 일관성 있게 사용하도록 하려면 선택한 허브에 이를 밀어 넣을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="729ac-104">To make important content types more consistently available to SharePoint libraries and lists, you can push them to the hubs that you choose.</span></span> <span data-ttu-id="729ac-105">콘텐츠 유형을 푸시하면 허브와 연결된 사이트에서 생성된 새 목록 및 라이브러리와 허브에 추가된 새 사이트에 자동으로 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="729ac-105">Pushing the content types automatically adds them to any new lists and libraries created on the sites associated with the hub, and to any new sites added to the hub.</span></span>

<span data-ttu-id="729ac-106">이 기능이 작동되려면 푸시되는 콘텐츠 유형이 이미 게시되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="729ac-106">For this feature to work, the content types being pushed must already be published.</span></span>

<span data-ttu-id="729ac-107">허브로 콘텐츠 유형을 푸시하려면</span><span class="sxs-lookup"><span data-stu-id="729ac-107">To push content types to hubs</span></span>

1. <span data-ttu-id="729ac-108">SharePoint 관리 센터에서 **콘텐츠 서비스** 를 확장하고 **콘텐츠 유형 갤러리** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="729ac-108">In the SharePoint admin center, expand **Content services**, and then select **Content type gallery**.</span></span>
2. <span data-ttu-id="729ac-109">허브로 푸시하고자 하는 콘텐츠 유형을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="729ac-109">Select the content type that you want to push to hubs.</span></span>
3. <span data-ttu-id="729ac-110">명령 모음에서 **편집** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="729ac-110">Select **Edit** in the command bar.</span></span>
4. <span data-ttu-id="729ac-111">**허브 사이트 선택** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="729ac-111">Select **Choose hub sites**.</span></span>
5. <span data-ttu-id="729ac-112">원하는 허브 사이트를 선택한 다음 **확인** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="729ac-112">Select the hub sites you want and then choose **OK**.</span></span>
6. <span data-ttu-id="729ac-113">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="729ac-113">Choose **Save**.</span></span>

<span data-ttu-id="729ac-114">기존 허브 및 관련된 사이트로 콘텐츠 유형을 푸시하는 것이 처음이라면 허브 혹은 관련된 사이트를 방문할 때 사이트에서 설정이 업데이트되는 데 최대 1시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="729ac-114">When you push a content type to an existing hub & its existing associated sites for the first time, it can take up to an hour from when the hub or associated sites are visited, for the settings to update in the site.</span></span> <span data-ttu-id="729ac-115">허브에 대한 모든 새로운 연결에는 이러한 대기가 필요하지 않으며 몇 분 이내에 설정이 반영됩니다.</span><span class="sxs-lookup"><span data-stu-id="729ac-115">Any new associations to the hub won't require this wait and will have the settings reflected in a few minutes.</span></span>

<span data-ttu-id="729ac-116">설정이 업데이트되면 이 설정의 콘텐츠 유형은 몇 분 이내에 허브의 새 연결된 사이트에서 사용 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="729ac-116">After the settings are updated, the content type with these settings will be available in any newly associated site with the hub in a few minutes.</span></span> <span data-ttu-id="729ac-117">그러면, 생성된 새 목록 또는 라이브러리에는 생성된 지 몇 분 이내에 자동으로 콘텐츠 유형이 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="729ac-117">Then, any new list or library created will have the content type automatically added to it within a few minutes of creation.</span></span> <span data-ttu-id="729ac-118">푸시된 콘텐츠 형식은 문서 콘텐츠 유형에서 직접 혹은 간접적으로 파생 되는 경우에만 문서 라이브러리에 추가되고 콘텐츠 유형은 문서 콘텐츠 유형에서 직접 혹은 간접적으로 파생 되지 않은 경우에만 목록에 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="729ac-118">A pushed content type will be added to a document library only if it derives directly or indirectly from the Document content type, and a content type will be added to a list only if it does not derive from the Document content type directly or indirectly.</span></span>

## <a name="see-also"></a><span data-ttu-id="729ac-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="729ac-119">See also</span></span>
