---
title: '5단계: 클라이언트 Office 365 서비스 성능 최적화'
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/23/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: 성능 향상을 위해 TCP 설정 및 Office 365 서비스를 구성합니다.
ms.openlocfilehash: e3aefb417330ab791a3dd217e2e34591eba3e1d1
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42066544"
---
# <a name="step-5-optimize-client-and-office-365-service-performance"></a><span data-ttu-id="ee8d1-103">5단계: 클라이언트 Office 365 서비스 성능 최적화</span><span class="sxs-lookup"><span data-stu-id="ee8d1-103">Step 5: Optimize client and Office 365 service performance</span></span>

<span data-ttu-id="ee8d1-104">*이 단계는 선택 사항이며, Microsoft 365 Enterprise E3 및 E5 버전에 적용됩니다.*</span><span class="sxs-lookup"><span data-stu-id="ee8d1-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![1단계-네트워킹](../media/deploy-foundation-infrastructure/networking_icon-small.png)

<span data-ttu-id="ee8d1-106">클라이언트 장치와 Office 365 서비스 간에 TCP(전송 제어 프로토콜)가 작동하는 방식을 세밀하게 조정하여 성능을 개선 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee8d1-106">You can increase performance by fine tuning the way that the Transmission Control Protocol (TCP) works between client devices and Office 365 services.</span></span>

<span data-ttu-id="ee8d1-107">클라이언트 장치의 경우 클라이언트 장치에서 다음 TCP 설정을 변경하여 TCP 성능을 최적화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee8d1-107">For client devices, you can change the following TCP settings on client devices to optimize TCP performance:</span></span>

- <span data-ttu-id="ee8d1-108">[TCP 창 배율](https://blogs.technet.microsoft.com/onthewire/2014/03/28/ensuring-your-office-365-network-connection-isnt-throttled-by-your-proxy/) - 클라이언트 장치에서 승인을 받지 않아도 추가 데이터를 보낼 수 있도록 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="ee8d1-108">[TCP window scaling](https://blogs.technet.microsoft.com/onthewire/2014/03/28/ensuring-your-office-365-network-connection-isnt-throttled-by-your-proxy/), so your client device can send more data before requiring an acknowledgement</span></span>
- <span data-ttu-id="ee8d1-109">[TCP 유휴 시간](https://blogs.technet.microsoft.com/onthewire/2014/03/04/network-perimeters-tcp-idle-session-settings-for-outlook-on-office-365/) - 클라이언트 장치에서 열려 있는 연결을 보다 효율적으로 처리할 수 있도록 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="ee8d1-109">[TCP idle time](https://blogs.technet.microsoft.com/onthewire/2014/03/04/network-perimeters-tcp-idle-session-settings-for-outlook-on-office-365/), so your client device can handle open connections more efficiently</span></span>
- <span data-ttu-id="ee8d1-110">[TCP 최대 세그먼트 크기](https://blogs.technet.microsoft.com/onthewire/2014/06/27/checking-your-tcp-packets-are-pulling-their-weight-tcp-max-segment-size-or-mss/) - 클라이언트 장치에서 패킷 데이터의 최대 블록을 보낼 수 있도록 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="ee8d1-110">[TCP maximum segment size](https://blogs.technet.microsoft.com/onthewire/2014/06/27/checking-your-tcp-packets-are-pulling-their-weight-tcp-max-segment-size-or-mss/), so your client device can send the largest blocks of data in a packet</span></span>
- <span data-ttu-id="ee8d1-111">[TCP 선택적 승인](https://blogs.technet.microsoft.com/onthewire/2014/06/27/ensuring-your-tcp-stack-isnt-throwing-data-away/) - 클라이언트 장치에서 받은 데이터를 보다 효율적으로 승인할 수 있도록 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="ee8d1-111">[TCP selective acknowledgements](https://blogs.technet.microsoft.com/onthewire/2014/06/27/ensuring-your-tcp-stack-isnt-throwing-data-away/), so your client device can acknowledge received data more efficiently</span></span>

<span data-ttu-id="ee8d1-112">Office 365 서비스의 경우 다음 추가 리소스를 참조하여 성능을 최적화하세요.</span><span class="sxs-lookup"><span data-stu-id="ee8d1-112">For Office 365 services, see these additional resources to optimize performance:</span></span>

- [<span data-ttu-id="ee8d1-113">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="ee8d1-113">Exchange Online</span></span>](https://docs.microsoft.com/office365/enterprise/tune-exchange-online-performance)
- [<span data-ttu-id="ee8d1-114">비즈니스용 Skype Online</span><span class="sxs-lookup"><span data-stu-id="ee8d1-114">Skype for Business Online</span></span>](https://docs.microsoft.com/office365/enterprise/tune-skype-for-business-online-performance)
- [<span data-ttu-id="ee8d1-115">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="ee8d1-115">SharePoint Online</span></span>](https://docs.microsoft.com/office365/enterprise/tune-sharepoint-online-performance)
- [<span data-ttu-id="ee8d1-116">Project Online의 Project Web App</span><span class="sxs-lookup"><span data-stu-id="ee8d1-116">Project Web App in Project Online</span></span>](https://docs.microsoft.com/ProjectOnline/tune-project-online-performance)

<span data-ttu-id="ee8d1-117">중간 검사점으로 이 단계에 대한 [종료 조건](networking-exit-criteria.md#crit-networking-step5)을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee8d1-117">As an interim checkpoint, you can see the [exit criteria](networking-exit-criteria.md#crit-networking-step5) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="ee8d1-118">다음 단계</span><span class="sxs-lookup"><span data-stu-id="ee8d1-118">Next step</span></span>

[<span data-ttu-id="ee8d1-119">네트워킹 인프라 종료 조건</span><span class="sxs-lookup"><span data-stu-id="ee8d1-119">Networking infrastructure exit criteria</span></span>](networking-exit-criteria.md)
