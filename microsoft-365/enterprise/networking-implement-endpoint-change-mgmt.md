---
title: '4단계: URL 및 IP 주소 변경 계획'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/05/2018
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: ''
ms.openlocfilehash: dacd2ad83bdeb106ae398e8223f457c66a12b598
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2019
ms.locfileid: "34073228"
---
# <a name="step-4-plan-for-url-and-ip-address-changes"></a><span data-ttu-id="c6f8f-102">4단계: URL 및 IP 주소 변경 계획</span><span class="sxs-lookup"><span data-stu-id="c6f8f-102">Step 4: Plan for URL and IP address changes</span></span>

<span data-ttu-id="c6f8f-103">*이 단계는 선택 사항이며, Microsoft 365 Enterprise E3 및 E5 버전에 적용됩니다.*</span><span class="sxs-lookup"><span data-stu-id="c6f8f-103">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/networking_icon-small.png)

>[!Note]
><span data-ttu-id="c6f8f-p101">이 단계를 수행하려면 먼저 [3단계](networking-configure-proxies-firewalls.md)를 완료해야 합니다. 3단계를 수행하지 않은 경우 [5단계](networking-optimize-tcp-performance.md)로 건너뛸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6f8f-p101">This step requires [Step 3](networking-configure-proxies-firewalls.md). If you have not done Step 3, you can skip to [Step 5](networking-optimize-tcp-performance.md).</span></span>
>

<span data-ttu-id="c6f8f-p102">전역 Microsoft 365 네트워크에서 사용하는 URL 및 IP 주소는 시간에 따라 변경되므로 이러한 끝점에 대한 업데이트를 계획해야 합니다. 예를 들어 다음을 사용하여 보안 경계 장치를 다시 구성해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6f8f-p102">The URLs and IP addresses used by the global Microsoft 365 network change over time, so it’s important to plan for updates to these endpoints. For example, you may need to reconfigure your security perimeter devices with:</span></span>

- <span data-ttu-id="c6f8f-108">방해 없는 처리가 필요한 새로운 서비스에 대한 새 URL</span><span class="sxs-lookup"><span data-stu-id="c6f8f-108">New URLs for new services that will need unhindered processing</span></span>
- <span data-ttu-id="c6f8f-109">중단된 서비스에 대한 URL 제거</span><span class="sxs-lookup"><span data-stu-id="c6f8f-109">Removed URLs for discontinued services</span></span>
- <span data-ttu-id="c6f8f-110">인터넷상의 새로운 Microsoft 네트워크 위치 및 서버에 대한 새 IP 주소 범위</span><span class="sxs-lookup"><span data-stu-id="c6f8f-110">New IP address ranges for new Microsoft network locations and servers on the Internet</span></span> 
- <span data-ttu-id="c6f8f-111">다양한 서비스에 대한 IP 주소 범위 변경</span><span class="sxs-lookup"><span data-stu-id="c6f8f-111">Changes in IP address ranges for the different services</span></span>

<span data-ttu-id="c6f8f-112">끝점 변경 구현 계획을 수립하는 방법에 대한 자세한 내용은 [Office 365 끝점 관리 - 통합](https://support.office.com/article/Managing-Office-365-endpoints-99cab9d4-ef59-4207-9f2b-3728eb46bf9a?ui=en-US#ID0EABAAA=2._Proxies&ID0EAEAAA=3._Integration) 및 [Office 365 끝점 관리 - 프록시](https://support.office.com/article/Managing-Office-365-endpoints-99cab9d4-ef59-4207-9f2b-3728eb46bf9a#ID0EABAAA=2._Proxies&ID0EAEAAA=2._Proxies)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c6f8f-112">For more information about establishing an implementation plan for changes in endpoints, which includes being notified of changes, see [Managing Office 365 endpoints-Integration](https://support.office.com/article/Managing-Office-365-endpoints-99cab9d4-ef59-4207-9f2b-3728eb46bf9a?ui=en-US#ID0EABAAA=2._Proxies&ID0EAEAAA=3._Integration) and [Managing Office 365 endpoints-Proxies](https://support.office.com/article/Managing-Office-365-endpoints-99cab9d4-ef59-4207-9f2b-3728eb46bf9a#ID0EABAAA=2._Proxies&ID0EAEAAA=2._Proxies).</span></span>

<span data-ttu-id="c6f8f-113">중간 검사점으로 이 단계에 대한 [종료 조건](networking-exit-criteria.md#crit-networking-step4)을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6f8f-113">As an interim checkpoint, you can see the [exit criteria](networking-exit-criteria.md#crit-networking-step4) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="c6f8f-114">다음 단계</span><span class="sxs-lookup"><span data-stu-id="c6f8f-114">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step5.png)|[<span data-ttu-id="c6f8f-115">클라이언트 및 Office 365 서비스 성능 최적화</span><span class="sxs-lookup"><span data-stu-id="c6f8f-115">Optimize client and Office 365 service performance</span></span>](networking-optimize-tcp-performance.md)|
