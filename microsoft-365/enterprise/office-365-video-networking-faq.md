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
# <a name="office-365-video-networking-frequently-asked-questions"></a>Office 365 비디오 네트워킹 질문과 대답

Office 365 비디오 리포지토리 및 스트리밍 서비스를 통해 조직 내에서 비디오를 간단하게 저장하고 스트리밍할 수 있습니다. [Office 365](https://support.office.com/article/Find-help-about-Office-365-Video-b435f99a-f47e-4ebd-a946-f5c965844f50)비디오에 대한 많은 정보가 있습니다. 이 네트워킹 FAQ는 대역폭 계획, 암호화 및 서비스가 CDNS(콘텐츠 배달 [](content-delivery-networks.md) 네트워크)를 활용하는 방법에 대한 가장 일반적인 질문에 답변하도록 디자인되어 있습니다.
  
비디오가 업로드되거나 재생될 때 발생하는 일에 대한 철저한 이해가 없는 경우 Office [365](https://www.youtube.com/watch?v=HXSZ0jYBKlM)비디오에 업로드할 때 비디오 파일에 어떤 일이 발생하는지 이 비디오를 살펴보아야 합니다.
  
## <a name="what-are-the-office-365-video-bandwidth-requirements"></a>Office 365 비디오 대역폭 요구 사항은 무엇입니까?

Office 365에 [업로드할](https://support.office.com/article/dd1af01c-fd8e-4640-b17b-93ee02b9b817) 수 있는 다양한 지원되는 비디오 형식이 있습니다. 그런 다음 각 비디오 파일은 재생을 위해 여러 다른 비디오 자질을 사용하여 표준 형식으로 인코딩됩니다. Office 365 비디오는 적응형 비트레이트 스트리밍을 사용하여 사용 가능한 네트워크 대역폭 및 비디오 플레이어의 크기에 따라 최상의 비디오 재생 품질을 선택합니다. 이를 위해 플레이어가 처음에 가장 낮은 재생 품질을 요청합니다. 그러면 서비스에서 비디오 플레이어에게 2초 비디오 세그먼트를 보내기 시작합니다. 그러면 플레이어는 각 세그먼트가 얼마나 빨리 전달되는가에 따라 더 높거나 낮은 재생 품질을 요청할 수 있습니다.
  
적응 비트레이트 스트리밍은 비디오가 중단 또는 버퍼링을 최소화하면서 재생되는 동안 백그라운드에서 이 모든 기능을 합니다. 비디오 재생 중에 비디오 플레이어를 사용하면 뷰어가 자동 재생 품질을 수동으로 다시 정의하여 특정 비디오 재생 품질을 선택할 수 있습니다.
  
다음은 각 비디오 재생 자질에 대한 네트워크 요구 사항을 간략하게 설명한 표입니다. 비디오를 재생하는 데 필요한 개인당 최소 대역폭은 802Kbps입니다.
  
| 재생 품질 | 네트워크 속도 |
|:-----|:-----|
|288p  <br/> |802Kbps  <br/> |
|360p  <br/> |1.2Mbps  <br/> |
|576p  <br/> |2.5Mbps  <br/> |
|720p  <br/> |3.8Mbps  <br/> |

([Back to top](office-365-video-networking-faq.md))
  
## <a name="how-do-content-delivery-networks-cdns-help-video-playback"></a>CDNS(콘텐츠 배달 네트워크)는 비디오 재생을 어떻게 지원하나요?

같은 지리적 위치 내의 같은 조직의 여러 사용자가 동일한 비디오를 스트리밍하는 경우 CDNS는 이러한 비디오의 복사본을 해당 지리적 지역에 더 가까운 위치에 저장합니다. 비디오가 저장되거나 가장 가까운 위치에 캐시된 경우 각 사람은 더 가까운 위치가 아닌 가장 가까운 위치에서 비디오를 스트리밍합니다. Office 365 비디오는 Azure Media Services를 사용하여 Azure CDNS에 캐시된 것을 관리하고 기간을 관리합니다. Azure Media Services는 [Azure CDN](/azure/cdn/cdn-pop-locations) 위치를 사용하여 며칠 동안 비디오 조각 및 매니페스트를 캐시할 수 있습니다. 조직의 사용자가 캐시된 비디오를 계속 보는 경우 캐시에 유지됩니다. 며칠 동안 아무도 비디오에 액세스하지 않았다면 결국 비디오가 캐시에서 삭제됩니다. 다음에 누군가가 비디오를 시청하려고 할 때 가장 가까운 CDN 위치에 다시 캐시됩니다.
  
콘텐츠가 가까운 CDN에 캐시되는 동안 비디오를 시청하려는 모든 사람은 비디오가 가깝게 제공되고 대부분의 경우 홉 수가 적게 멀어지는 이점이 있습니다. 그러면 비디오 재생 속도가 향상됩니다. 그러나 비디오를 재생하기 위한 네트워크 요구 사항은 변경되지 않습니다.
  
> [!NOTE]
> 용량 제한에 도달하는 등 3일이 경과하기 전에 비디오를 제거할 수 있는 상황이 있습니다.
  
([Back to top](office-365-video-networking-faq.md))
  
## <a name="can-i-cache-the-videos-locally-for-faster-playback"></a>더 빠른 재생을 위해 비디오를 로컬로 캐시할 수 있나요?

예. Office 365는 더 빠른 액세스를 위해 로컬 CDN 또는 캐싱 프록시를 사용하여 비디오 또는 기타 Office 365 콘텐츠를 로컬 네트워크로 가져오는 것을 방지하지 않습니다. 네트워크에서 로컬 캐싱 솔루션을 구현하는 방법에는 여러 가지가 있습니다. 가장 일반적인 방법은 콘텐츠를 로컬로 캐시하는 프록시 솔루션을 사용하는 것입니다. 프록시 또는 개인 CDN이 비디오 조각 및 매니페스트를 캐시한 후 프록시 또는 개인 CDN을 통해 라우팅되는 파일에 대한 향후 요청은 로컬 캐시에서 끌어오고 인터넷 위치에서 끌어오지 않습니다. 다음과 같은 솔루션을 계획하는 동안 네트워크 대역폭, 용량 및 비디오 재생 동시성에 대해 고려해야 합니다.
  
([Back to top](office-365-video-networking-faq.md))
  
## <a name="how-videos-are-encrypted-and-secured"></a>비디오를 암호화하고 보호하는 방법

Office 365 비디오는 데이터를 안전하고 비공개로 유지하는 것이 얼마나 중요한지 알고 있습니다. [Microsoft 보안 센터는](https://products.office.com/business/office-365-trust-center-welcome) 콘텐츠의 개인 정보 보호 및 보안에 대한 Microsoft의 노력에 대해 설명하고 있습니다. 비디오 재생을 사용할 경우 좋은 환경을 위해 속도가 중요합니다. 그러나 속도를 위해 보안 또는 개인 정보 보호를 손상하지 않습니다. 다음은 속도, 보안 및 개인 정보를 수용하는 방법입니다.
  
사용자 또는 조직의 누군가가 새 비디오를 업로드하면 해당 비디오가 코드 변환되고 AES-128 암호화로 암호화되며 Azure Media Services에 저장됩니다. 즉, 비디오가 전송 중 및 미사일 시 모두 암호화됩니다.
  
조직의 누군가가 새 비디오를 시청하려고 시도하면 다음 단계를 따릅니다.
  
1. SharePoint Online에 비디오를 볼 수 있는 권한이 있는지 물어 묻습니다.

2. SharePoint Online에서는 파일 사용 권한을 사용하여 사용자가 비디오를 볼 수 있는지 여부를 판단합니다.

3. 허용되는 경우 SharePoint Online은 Azure에서 비디오 플레이어에게 주는 토큰을 검색합니다.

4. 그런 다음 비디오 플레이어는 토큰을 사용하여 Azure에서 암호 해독 키를 요청합니다.

5. 암호 해독 키를 사용하여 비디오 플레이어는 비디오를 스트리밍할 수 있습니다.

![O365 비디오 재생](../media/9d3c6e76-151d-48a3-a30e-ba8dd07db0b7.png)
  
([Back to top](office-365-video-networking-faq.md))
  
## <a name="what-are-the-requirements-to-playback-office-365-video"></a>Office 365 비디오를 재생하기 위해 필요한 사항은 무엇입니까?

Office 365 비디오 지원 운영 체제 및 웹 브라우저는 Office 365 시스템 요구 사항의 SharePoint Online 요구 [사항과 동일합니다.](https://support.office.com/article/Office-365-system-requirements-719254c0-2671-4648-9c84-c6a3d4f3be45) 어떤 운영 체제 및 웹 브라우저 구성에 따라 비디오 플레이어의 특정 요구 사항을 결정할 수 있습니다. 비디오 재생 요구 사항에 대한 [자세한 내용은 다음과 있습니다.](https://support.office.com/article/ca1cc1a9-a615-46e1-b6a3-40dbd99939a6)
  
([Back to top](office-365-video-networking-faq.md))
  
## <a name="i-cant-get-office-365-video-to-work-where-should-i-start"></a>Office 365 비디오를 작동할 수 없는 경우 어디에서 시작해야 하나요?

Office 365 비디오에 대한 연결 문제 해결에는 네트워크, ISP 및 Office 365의 구성 문제 해결이 수반됩니다. 먼저 서비스 상태 대시보드를 시작할 수 있습니다. Office 365 비디오에 문제가 있는지 알 수 있습니다. 모든 것이 멋지다면 도움이 되는 몇 가지 추가 리소스가 있습니다.
  
- [Office 365](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2)비디오에 필요한 네트워크 끝점에 연결할 수 있는지 확인합니다.

- [Office 365](https://support.office.com/article/Office-365-performance-tuning-and-troubleshooting-Admin-and-IT-Pro-1492cb94-bd62-43e6-b8d0-2a61ed88ebae)네트워크 문제 해결 가이드를 사용하여 네트워크 연결을 확인합니다.

- 느린 [네트워크에서 Office 365를](https://support.office.com/article/Best-practices-for-using-Office-365-on-a-slow-network-fd16c8d2-4799-4c39-8fd7-045f06640166)사용하는 모범 사례를 참조합니다.

- [Office 365 비디오 구성에 대한 도움말을 찾아야 합니다.](https://support.office.com/article/Find-help-about-Office-365-Video-b435f99a-f47e-4ebd-a946-f5c965844f50)

([Back to top](office-365-video-networking-faq.md))
  
## <a name="office-365-video-resources"></a>Office 365 비디오 리소스

Office 365 비디오를 성공적으로 배포하고 사용하는 데 도움이 되는 몇 가지 다른 리소스는 다음과 같습니다.
  
[Office 365 비디오 구성에 대한 도움말 찾기](https://support.office.com/article/Find-help-about-Office-365-Video-b435f99a-f47e-4ebd-a946-f5c965844f50)
  
[Office 365 비디오 만나기](https://support.office.com/article/Meet-Office-365-Video-ca1cc1a9-a615-46e1-b6a3-40dbd99939a6)
  
[Office 365 비디오에서 채널 만들기 및 관리](https://support.office.com/article/Create-and-manage-a-channel-in-Office-365-Video-1fede4cc-13c0-435a-b585-e7fbf1c83bb2)
  
[Office 365 비디오 포털 관리](https://support.office.com/article/Manage-your-Office-365-Video-portal-c059465b-eba9-44e1-b8c7-8ff7793ff5da)
  
[Office 365 비디오에서 작동 하는 비디오 형식](https://support.office.com/article/Video-formats-that-work-in-Office-365-Video-dd1af01c-fd8e-4640-b17b-93ee02b9b817)
  
([Back to top](office-365-video-networking-faq.md))
  
다음의 간단한 링크를 사용할 수 있습니다. [https://aka.ms/video365networkfaq]()