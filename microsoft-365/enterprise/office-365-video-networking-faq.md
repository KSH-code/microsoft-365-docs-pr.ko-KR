---
title: Office 365 비디오 네트워킹 질문과 대답
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 3/14/2019
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: 2bed67a1-4052-49ff-a4ce-b7e6530eb98e
ms.custom:
- Adm_O365
- seo-marvel-apr2020
description: 서비스에서 CDNS(콘텐츠 배달 네트워크)를 활용하는 방법에 대한 대역폭 계획, 암호화, & 질문과 대답을 찾아보겠습니다.
ms.openlocfilehash: 8bc0a69ff744967d24aa7d21ed6daee1a839f159
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921573"
---
# <a name="office-365-video-networking-frequently-asked-questions"></a><span data-ttu-id="0f358-103">Office 365 비디오 네트워킹 질문과 대답</span><span class="sxs-lookup"><span data-stu-id="0f358-103">Office 365 Video networking Frequently Asked Questions</span></span>

<span data-ttu-id="0f358-104">Office 365 비디오 리포지토리 및 스트리밍 서비스를 통해 조직 내에서 비디오를 간단하게 저장하고 스트리밍할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f358-104">The Office 365 Video repository and streaming services make storing and streaming videos within your organization simple.</span></span> <span data-ttu-id="0f358-105">[Office 365](https://support.office.com/article/Find-help-about-Office-365-Video-b435f99a-f47e-4ebd-a946-f5c965844f50)비디오에 대한 많은 정보가 있습니다. 이 네트워킹 FAQ는 대역폭 계획, 암호화 및 서비스가 CDNS(콘텐츠 배달 [](content-delivery-networks.md) 네트워크)를 활용하는 방법에 대한 가장 일반적인 질문에 답변하도록 디자인되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f358-105">There's a lot of great [information about Office 365 Video](https://support.office.com/article/Find-help-about-Office-365-Video-b435f99a-f47e-4ebd-a946-f5c965844f50); this networking FAQ is designed to answer the most common questions around bandwidth planning, encryption, and how the service leverages [Content Delivery Networks](content-delivery-networks.md) (CDNs).</span></span>
  
<span data-ttu-id="0f358-106">비디오가 업로드되거나 재생될 때 발생하는 일에 대한 철저한 이해가 없는 경우 Office [365](https://www.youtube.com/watch?v=HXSZ0jYBKlM)비디오에 업로드할 때 비디오 파일에 어떤 일이 발생하는지 이 비디오를 살펴보아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f358-106">If you don't already have a thorough understanding of what happens when a video is uploaded or played back, have a look at this video we put together, [What happens to a video file when uploaded to Office 365 Video](https://www.youtube.com/watch?v=HXSZ0jYBKlM).</span></span>
  
## <a name="what-are-the-office-365-video-bandwidth-requirements"></a><span data-ttu-id="0f358-107">Office 365 비디오 대역폭 요구 사항은 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="0f358-107">What are the Office 365 Video bandwidth requirements?</span></span>

<span data-ttu-id="0f358-108">Office 365에 [업로드할](https://support.office.com/article/dd1af01c-fd8e-4640-b17b-93ee02b9b817) 수 있는 다양한 지원되는 비디오 형식이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f358-108">There are a numerous [supported video formats](https://support.office.com/article/dd1af01c-fd8e-4640-b17b-93ee02b9b817) that can be uploaded to Office 365.</span></span> <span data-ttu-id="0f358-109">그런 다음 각 비디오 파일은 재생을 위해 여러 다른 비디오 자질을 사용하여 표준 형식으로 인코딩됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f358-109">Each video file is then encoded to a standard format with several different video qualities for playback.</span></span> <span data-ttu-id="0f358-110">Office 365 비디오는 적응형 비트레이트 스트리밍을 사용하여 사용 가능한 네트워크 대역폭 및 비디오 플레이어의 크기에 따라 최상의 비디오 재생 품질을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0f358-110">Office 365 Video uses adaptive bitrate streaming to select the best video playback quality based on the available network bandwidth and size of the video player.</span></span> <span data-ttu-id="0f358-111">이를 위해 플레이어가 처음에 가장 낮은 재생 품질을 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="0f358-111">To do this, the player initially requests the lowest playback quality.</span></span> <span data-ttu-id="0f358-112">그러면 서비스에서 비디오 플레이어에게 2초 비디오 세그먼트를 보내기 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="0f358-112">The service then begins sending 2-second video segments to the video player.</span></span> <span data-ttu-id="0f358-113">그러면 플레이어는 각 세그먼트가 얼마나 빨리 전달되는가에 따라 더 높거나 낮은 재생 품질을 요청할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f358-113">The player can then request higher or lower playback quality based on how quickly each segment is delivered.</span></span>
  
<span data-ttu-id="0f358-114">적응 비트레이트 스트리밍은 비디오가 중단 또는 버퍼링을 최소화하면서 재생되는 동안 백그라운드에서 이 모든 기능을 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f358-114">The adaptive bitrate streaming does all this in the background while the video plays with the least amount of disruption or buffering.</span></span> <span data-ttu-id="0f358-115">비디오 재생 중에 비디오 플레이어를 사용하면 뷰어가 자동 재생 품질을 수동으로 다시 정의하여 특정 비디오 재생 품질을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f358-115">During video playback, the video player allows the viewer to manually override the automatic playback quality, to select a specific video playback quality.</span></span>
  
<span data-ttu-id="0f358-116">다음은 각 비디오 재생 자질에 대한 네트워크 요구 사항을 간략하게 설명한 표입니다.</span><span class="sxs-lookup"><span data-stu-id="0f358-116">Here's a quick table that outlines the network requirements for each of the video playback qualities.</span></span> <span data-ttu-id="0f358-117">비디오를 재생하는 데 필요한 개인당 최소 대역폭은 802Kbps입니다.</span><span class="sxs-lookup"><span data-stu-id="0f358-117">The minimum bandwidth per person needed to play a video is 802Kbps.</span></span>
  
| <span data-ttu-id="0f358-118">재생 품질</span><span class="sxs-lookup"><span data-stu-id="0f358-118">Playback Quality</span></span> | <span data-ttu-id="0f358-119">네트워크 속도</span><span class="sxs-lookup"><span data-stu-id="0f358-119">Network Speed</span></span> |
|:-----|:-----|
|<span data-ttu-id="0f358-120">288p</span><span class="sxs-lookup"><span data-stu-id="0f358-120">288p</span></span>  <br/> |<span data-ttu-id="0f358-121">802Kbps</span><span class="sxs-lookup"><span data-stu-id="0f358-121">802Kbps</span></span>  <br/> |
|<span data-ttu-id="0f358-122">360p</span><span class="sxs-lookup"><span data-stu-id="0f358-122">360p</span></span>  <br/> |<span data-ttu-id="0f358-123">1.2Mbps</span><span class="sxs-lookup"><span data-stu-id="0f358-123">1.2 Mbps</span></span>  <br/> |
|<span data-ttu-id="0f358-124">576p</span><span class="sxs-lookup"><span data-stu-id="0f358-124">576p</span></span>  <br/> |<span data-ttu-id="0f358-125">2.5Mbps</span><span class="sxs-lookup"><span data-stu-id="0f358-125">2.5 Mbps</span></span>  <br/> |
|<span data-ttu-id="0f358-126">720p</span><span class="sxs-lookup"><span data-stu-id="0f358-126">720p</span></span>  <br/> |<span data-ttu-id="0f358-127">3.8Mbps</span><span class="sxs-lookup"><span data-stu-id="0f358-127">3.8 Mbps</span></span>  <br/> |

<span data-ttu-id="0f358-128">([Back to top](office-365-video-networking-faq.md))</span><span class="sxs-lookup"><span data-stu-id="0f358-128">([Back to top](office-365-video-networking-faq.md))</span></span>
  
## <a name="how-do-content-delivery-networks-cdns-help-video-playback"></a><span data-ttu-id="0f358-129">CDNS(콘텐츠 배달 네트워크)는 비디오 재생을 어떻게 지원하나요?</span><span class="sxs-lookup"><span data-stu-id="0f358-129">How do Content Delivery Networks (CDNs) help video playback?</span></span>

<span data-ttu-id="0f358-130">같은 지리적 위치 내의 같은 조직의 여러 사용자가 동일한 비디오를 스트리밍하는 경우 CDNS는 이러한 비디오의 복사본을 해당 지리적 지역에 더 가까운 위치에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="0f358-130">If several people from the same organization within the same geographic location are streaming the same video(s), CDNs will store a copy of these videos in a location closer to that geographic region.</span></span> <span data-ttu-id="0f358-131">비디오가 저장되거나 가장 가까운 위치에 캐시된 경우 각 사람은 더 가까운 위치가 아닌 가장 가까운 위치에서 비디오를 스트리밍합니다.</span><span class="sxs-lookup"><span data-stu-id="0f358-131">With the video stored, or cached at the closest location, each person streams the video from the location closest to them instead of a location further away.</span></span> <span data-ttu-id="0f358-132">Office 365 비디오는 Azure Media Services를 사용하여 Azure CDNS에 캐시된 것을 관리하고 기간을 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="0f358-132">Office 365 Video uses Azure Media Services to manage what is cached in the Azure CDNs, and for how long.</span></span> <span data-ttu-id="0f358-133">Azure Media Services는 [Azure CDN](/azure/cdn/cdn-pop-locations) 위치를 사용하여 며칠 동안 비디오 조각 및 매니페스트를 캐시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f358-133">Azure Media Services can use any of the [Azure CDN locations](/azure/cdn/cdn-pop-locations) to cache video fragments and manifests for a few days.</span></span> <span data-ttu-id="0f358-134">조직의 사용자가 캐시된 비디오를 계속 보는 경우 캐시에 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f358-134">If people in your organization continue to watch the cached videos they'll stay in the cache.</span></span> <span data-ttu-id="0f358-135">며칠 동안 아무도 비디오에 액세스하지 않았다면 결국 비디오가 캐시에서 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f358-135">If no one accesses the video for several days, the video will eventually drop be dropped from the cache.</span></span> <span data-ttu-id="0f358-136">다음에 누군가가 비디오를 시청하려고 할 때 가장 가까운 CDN 위치에 다시 캐시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f358-136">The next time someone attempts to watch the video it's once again cached at the nearest CDN location.</span></span>
  
<span data-ttu-id="0f358-137">콘텐츠가 가까운 CDN에 캐시되는 동안 비디오를 시청하려는 모든 사람은 비디오가 가깝게 제공되고 대부분의 경우 홉 수가 적게 멀어지는 이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f358-137">Everyone who attempts to watch the video while the content is cached at a nearby CDN benefits from the video being closer, and in most cases less hops, away.</span></span> <span data-ttu-id="0f358-138">그러면 비디오 재생 속도가 향상됩니다. 그러나 비디오를 재생하기 위한 네트워크 요구 사항은 변경되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0f358-138">This improves video playback speed; however, it doesn't change the network requirement to play the video.</span></span>
  
> [!NOTE]
> <span data-ttu-id="0f358-139">용량 제한에 도달하는 등 3일이 경과하기 전에 비디오를 제거할 수 있는 상황이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f358-139">There are some circumstances, such as our capacity limit being reached, where the video may be removed before the three days has been reached.</span></span>
  
<span data-ttu-id="0f358-140">([Back to top](office-365-video-networking-faq.md))</span><span class="sxs-lookup"><span data-stu-id="0f358-140">([Back to top](office-365-video-networking-faq.md))</span></span>
  
## <a name="can-i-cache-the-videos-locally-for-faster-playback"></a><span data-ttu-id="0f358-141">더 빠른 재생을 위해 비디오를 로컬로 캐시할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="0f358-141">Can I cache the videos locally for faster playback?</span></span>

<span data-ttu-id="0f358-142">예.</span><span class="sxs-lookup"><span data-stu-id="0f358-142">Yes.</span></span> <span data-ttu-id="0f358-143">Office 365는 더 빠른 액세스를 위해 로컬 CDN 또는 캐싱 프록시를 사용하여 비디오 또는 기타 Office 365 콘텐츠를 로컬 네트워크로 가져오는 것을 방지하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0f358-143">Office 365 won't prevent you from using a local CDN or a caching proxy to bring video or other Office 365 content into your local network for faster access.</span></span> <span data-ttu-id="0f358-144">네트워크에서 로컬 캐싱 솔루션을 구현하는 방법에는 여러 가지가 있습니다. 가장 일반적인 방법은 콘텐츠를 로컬로 캐시하는 프록시 솔루션을 사용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="0f358-144">There are several ways to implement a local caching solution on your network, the most common method is to use a proxy solution that caches content locally.</span></span> <span data-ttu-id="0f358-145">프록시 또는 개인 CDN이 비디오 조각 및 매니페스트를 캐시한 후 프록시 또는 개인 CDN을 통해 라우팅되는 파일에 대한 향후 요청은 로컬 캐시에서 끌어오고 인터넷 위치에서 끌어오지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0f358-145">Once a proxy or private CDN has cached the video fragments and manifests, future requests for those files that route through the proxy or private CDN are pulled from the local cache and not pulled from an internet location.</span></span> <span data-ttu-id="0f358-146">다음과 같은 솔루션을 계획하는 동안 네트워크 대역폭, 용량 및 비디오 재생 동시성에 대해 고려해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f358-146">Consider network bandwidth, capacity, and video playback concurrency during the planning of a solution like this.</span></span>
  
<span data-ttu-id="0f358-147">([Back to top](office-365-video-networking-faq.md))</span><span class="sxs-lookup"><span data-stu-id="0f358-147">([Back to top](office-365-video-networking-faq.md))</span></span>
  
## <a name="how-videos-are-encrypted-and-secured"></a><span data-ttu-id="0f358-148">비디오를 암호화하고 보호하는 방법</span><span class="sxs-lookup"><span data-stu-id="0f358-148">How videos are encrypted and secured?</span></span>

<span data-ttu-id="0f358-149">Office 365 비디오는 데이터를 안전하고 비공개로 유지하는 것이 얼마나 중요한지 알고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f358-149">Office 365 Video knows how important it is to keep your data secure and private.</span></span> <span data-ttu-id="0f358-150">[Microsoft 보안 센터는](https://products.office.com/business/office-365-trust-center-welcome) 콘텐츠의 개인 정보 보호 및 보안에 대한 Microsoft의 노력에 대해 설명하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f358-150">[Microsoft Trust Center](https://products.office.com/business/office-365-trust-center-welcome) describes our commitment to the privacy and security of your content.</span></span> <span data-ttu-id="0f358-151">비디오 재생을 사용할 경우 좋은 환경을 위해 속도가 중요합니다. 그러나 속도를 위해 보안 또는 개인 정보 보호를 손상하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0f358-151">With video playback, speed is important for a good experience; however, we don't compromise your security or privacy in exchange for speed.</span></span> <span data-ttu-id="0f358-152">다음은 속도, 보안 및 개인 정보를 수용하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="0f358-152">Here's how we accommodate speed, security and privacy.</span></span>
  
<span data-ttu-id="0f358-153">사용자 또는 조직의 누군가가 새 비디오를 업로드하면 해당 비디오가 코드 변환되고 AES-128 암호화로 암호화되며 Azure Media Services에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f358-153">When you or someone in your organization uploads a new video, that video is transcoded, encrypted with AES-128 encryption, and stored in Azure Media Services.</span></span> <span data-ttu-id="0f358-154">즉, 비디오가 전송 중 및 미사일 시 모두 암호화됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f358-154">This means the videos are encrypted both in transit and at rest.</span></span>
  
<span data-ttu-id="0f358-155">조직의 누군가가 새 비디오를 시청하려고 시도하면 다음 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="0f358-155">When someone in your organization attempts to watch a new video, they follow these steps:</span></span>
  
1. <span data-ttu-id="0f358-156">SharePoint Online에 비디오를 볼 수 있는 권한이 있는지 물어 묻습니다.</span><span class="sxs-lookup"><span data-stu-id="0f358-156">Ask SharePoint Online if they have permission to view the video.</span></span>

2. <span data-ttu-id="0f358-157">SharePoint Online에서는 파일 사용 권한을 사용하여 사용자가 비디오를 볼 수 있는지 여부를 판단합니다.</span><span class="sxs-lookup"><span data-stu-id="0f358-157">SharePoint Online uses the file permissions to determine if the person can watch the video.</span></span>

3. <span data-ttu-id="0f358-158">허용되는 경우 SharePoint Online은 Azure에서 비디오 플레이어에게 주는 토큰을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="0f358-158">If they're allowed, SharePoint Online retrieves a token from Azure to give to the video player.</span></span>

4. <span data-ttu-id="0f358-159">그런 다음 비디오 플레이어는 토큰을 사용하여 Azure에서 암호 해독 키를 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="0f358-159">The video player then uses the token to request the decryption key from Azure.</span></span>

5. <span data-ttu-id="0f358-160">암호 해독 키를 사용하여 비디오 플레이어는 비디오를 스트리밍할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f358-160">With the decryption key in hand, the video player is able to stream the video.</span></span>

![O365 비디오 재생](../media/9d3c6e76-151d-48a3-a30e-ba8dd07db0b7.png)
  
<span data-ttu-id="0f358-162">([Back to top](office-365-video-networking-faq.md))</span><span class="sxs-lookup"><span data-stu-id="0f358-162">([Back to top](office-365-video-networking-faq.md))</span></span>
  
## <a name="what-are-the-requirements-to-playback-office-365-video"></a><span data-ttu-id="0f358-163">Office 365 비디오를 재생하기 위해 필요한 사항은 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="0f358-163">What are the requirements to playback Office 365 Video?</span></span>

<span data-ttu-id="0f358-164">Office 365 비디오 지원 운영 체제 및 웹 브라우저는 Office 365 시스템 요구 사항의 SharePoint Online 요구 [사항과 동일합니다.](https://support.office.com/article/Office-365-system-requirements-719254c0-2671-4648-9c84-c6a3d4f3be45)</span><span class="sxs-lookup"><span data-stu-id="0f358-164">Office 365 Video supported operating systems and web browsers are the same as the SharePoint Online requirements in [Office 365 system requirements](https://support.office.com/article/Office-365-system-requirements-719254c0-2671-4648-9c84-c6a3d4f3be45).</span></span> <span data-ttu-id="0f358-165">어떤 운영 체제 및 웹 브라우저 구성에 따라 비디오 플레이어의 특정 요구 사항을 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f358-165">Depending on which operating system and web browser configuration you have will determine the specific needs of the video player.</span></span> <span data-ttu-id="0f358-166">비디오 재생 요구 사항에 대한 [자세한 내용은 다음과 있습니다.](https://support.office.com/article/ca1cc1a9-a615-46e1-b6a3-40dbd99939a6)</span><span class="sxs-lookup"><span data-stu-id="0f358-166">Here's more information on [video playback requirements](https://support.office.com/article/ca1cc1a9-a615-46e1-b6a3-40dbd99939a6).</span></span>
  
<span data-ttu-id="0f358-167">([Back to top](office-365-video-networking-faq.md))</span><span class="sxs-lookup"><span data-stu-id="0f358-167">([Back to top](office-365-video-networking-faq.md))</span></span>
  
## <a name="i-cant-get-office-365-video-to-work-where-should-i-start"></a><span data-ttu-id="0f358-168">Office 365 비디오를 작동할 수 없는 경우 어디에서 시작해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="0f358-168">I can't get Office 365 video to work, where should I start?</span></span>

<span data-ttu-id="0f358-169">Office 365 비디오에 대한 연결 문제 해결에는 네트워크, ISP 및 Office 365의 구성 문제 해결이 수반됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f358-169">Troubleshooting connectivity to Office 365 Video involves troubleshooting your network, your ISP(s), and your configuration of Office 365.</span></span> <span data-ttu-id="0f358-170">먼저 서비스 상태 대시보드를 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f358-170">The first place to start is the service health dashboard.</span></span> <span data-ttu-id="0f358-171">Office 365 비디오에 문제가 있는지 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f358-171">This will tell you of Office 365 Video is having a problem or not.</span></span> <span data-ttu-id="0f358-172">모든 것이 멋지다면 도움이 되는 몇 가지 추가 리소스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f358-172">If everything looks great there, here's some additional resources to help you.</span></span>
  
- <span data-ttu-id="0f358-173">[Office 365](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2)비디오에 필요한 네트워크 끝점에 연결할 수 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="0f358-173">Make sure you can connect to the [network endpoints required for Office 365 Video](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2).</span></span>

- <span data-ttu-id="0f358-174">[Office 365](https://support.office.com/article/Office-365-performance-tuning-and-troubleshooting-Admin-and-IT-Pro-1492cb94-bd62-43e6-b8d0-2a61ed88ebae)네트워크 문제 해결 가이드를 사용하여 네트워크 연결을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="0f358-174">Check your network connectivity using our [Office 365 network troubleshooting guide](https://support.office.com/article/Office-365-performance-tuning-and-troubleshooting-Admin-and-IT-Pro-1492cb94-bd62-43e6-b8d0-2a61ed88ebae).</span></span>

- <span data-ttu-id="0f358-175">느린 [네트워크에서 Office 365를](https://support.office.com/article/Best-practices-for-using-Office-365-on-a-slow-network-fd16c8d2-4799-4c39-8fd7-045f06640166)사용하는 모범 사례를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="0f358-175">See our [best practices for using Office 365 on a slow network](https://support.office.com/article/Best-practices-for-using-Office-365-on-a-slow-network-fd16c8d2-4799-4c39-8fd7-045f06640166).</span></span>

- <span data-ttu-id="0f358-176">[Office 365 비디오 구성에 대한 도움말을 찾아야 합니다.](https://support.office.com/article/Find-help-about-Office-365-Video-b435f99a-f47e-4ebd-a946-f5c965844f50)</span><span class="sxs-lookup"><span data-stu-id="0f358-176">[Find help about Office 365 Video configuration](https://support.office.com/article/Find-help-about-Office-365-Video-b435f99a-f47e-4ebd-a946-f5c965844f50).</span></span>

<span data-ttu-id="0f358-177">([Back to top](office-365-video-networking-faq.md))</span><span class="sxs-lookup"><span data-stu-id="0f358-177">([Back to top](office-365-video-networking-faq.md))</span></span>
  
## <a name="office-365-video-resources"></a><span data-ttu-id="0f358-178">Office 365 비디오 리소스</span><span class="sxs-lookup"><span data-stu-id="0f358-178">Office 365 Video resources</span></span>

<span data-ttu-id="0f358-179">Office 365 비디오를 성공적으로 배포하고 사용하는 데 도움이 되는 몇 가지 다른 리소스는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0f358-179">Here's a few other resources to help you successfully deploy and use Office 365 Video:</span></span>
  
[<span data-ttu-id="0f358-180">Office 365 비디오 구성에 대한 도움말 찾기</span><span class="sxs-lookup"><span data-stu-id="0f358-180">Find help about Office 365 Video configuration</span></span>](https://support.office.com/article/Find-help-about-Office-365-Video-b435f99a-f47e-4ebd-a946-f5c965844f50)
  
[<span data-ttu-id="0f358-181">Office 365 비디오 만나기</span><span class="sxs-lookup"><span data-stu-id="0f358-181">Meet Office 365 Video</span></span>](https://support.office.com/article/Meet-Office-365-Video-ca1cc1a9-a615-46e1-b6a3-40dbd99939a6)
  
[<span data-ttu-id="0f358-182">Office 365 비디오에서 채널 만들기 및 관리</span><span class="sxs-lookup"><span data-stu-id="0f358-182">Create and manage a channel in Office 365 Video</span></span>](https://support.office.com/article/Create-and-manage-a-channel-in-Office-365-Video-1fede4cc-13c0-435a-b585-e7fbf1c83bb2)
  
[<span data-ttu-id="0f358-183">Office 365 비디오 포털 관리</span><span class="sxs-lookup"><span data-stu-id="0f358-183">Manage your Office 365 Video portal</span></span>](https://support.office.com/article/Manage-your-Office-365-Video-portal-c059465b-eba9-44e1-b8c7-8ff7793ff5da)
  
[<span data-ttu-id="0f358-184">Office 365 비디오에서 작동 하는 비디오 형식</span><span class="sxs-lookup"><span data-stu-id="0f358-184">Video formats that work in Office 365 Video</span></span>](https://support.office.com/article/Video-formats-that-work-in-Office-365-Video-dd1af01c-fd8e-4640-b17b-93ee02b9b817)
  
<span data-ttu-id="0f358-185">([Back to top](office-365-video-networking-faq.md))</span><span class="sxs-lookup"><span data-stu-id="0f358-185">([Back to top](office-365-video-networking-faq.md))</span></span>
  
<span data-ttu-id="0f358-186">다음의 간단한 링크를 사용할 수 있습니다. [https://aka.ms/video365networkfaq]()</span><span class="sxs-lookup"><span data-stu-id="0f358-186">Here's a short link you can use to come back: [https://aka.ms/video365networkfaq]()</span></span>