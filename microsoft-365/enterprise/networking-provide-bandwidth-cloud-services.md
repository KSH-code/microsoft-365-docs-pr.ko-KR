---
title: '1단계: Microsoft 365에 맞게 네트워크 준비'
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
description: Microsoft 365 Enterprise 클라우드 서비스에 대한 인터넷 대역폭 요구를 이해합니다.
ms.openlocfilehash: ea92bcbd19c0b4cef16292d652cf5f8aa45aee07
ms.sourcegitcommit: 8bcd76e5c8749a5670fbc3356957a089454c03d1
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/02/2019
ms.locfileid: "37370295"
---
# <a name="step-1-prepare-your-network-for-microsoft-365"></a><span data-ttu-id="7ffaf-103">1단계: Microsoft 365에 맞게 네트워크 준비</span><span class="sxs-lookup"><span data-stu-id="7ffaf-103">Step 1: Prepare your network for Microsoft 365</span></span>

<span data-ttu-id="7ffaf-104">*이 단계는 필수 사항이며, Microsoft 365 Enterprise E3 및 E5 버전에 적용됩니다.*</span><span class="sxs-lookup"><span data-stu-id="7ffaf-104">*This step is required and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![1단계-네트워킹](./media/deploy-foundation-infrastructure/networking_icon-small.png)

<span data-ttu-id="7ffaf-106">1단계에서 다음을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ffaf-106">In Step 1, you must:</span></span>

- <span data-ttu-id="7ffaf-107">Microsoft 365 Enterprise 클라우드 서비스에 대한 트래픽을 수용하도록 내부 링크 및 인터넷 연결에 대한 네트워크 대역폭 평가 및 조정.</span><span class="sxs-lookup"><span data-stu-id="7ffaf-107">Evaluate and adjust network bandwidth for internal links and Internet connections to account for traffic to Microsoft 365 Enterprise cloud services.</span></span>
- <span data-ttu-id="7ffaf-108">[Office 365 참조 아키텍처](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#BKMK_P2)에 맞춰 네트워크 조정.</span><span class="sxs-lookup"><span data-stu-id="7ffaf-108">Align your network with an [Office 365 reference architecture](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#BKMK_P2).</span></span>
- <span data-ttu-id="7ffaf-109">변경을 계획하고, 파일럿 테스트를 수행한 후 해당 변경 사항이 대역폭 및 트래픽을 대기 시간 요건에 맞는지 여부 테스트.</span><span class="sxs-lookup"><span data-stu-id="7ffaf-109">Plan the changes, pilot them, and then test whether the changes fit your bandwidth and traffic latency requirements.</span></span>

<span data-ttu-id="7ffaf-110">Office 365에서 ExpressRoute를 사용하고 Microsoft 365 Enterprise의 다른 클라우드 서비스를 사용하는 방법에 대한 정보 및 권장 사항은 [Office 365 용 Azure ExpressRoute](https://docs.microsoft.com/office365/enterprise/azure-expressroute)를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="7ffaf-110">For information and recommendations about using ExpressRoute with Office 365 and the other cloud services of Microsoft 365 Enterprise, see [Azure ExpressRoute for Office 365](https://docs.microsoft.com/office365/enterprise/azure-expressroute).</span></span>

<span data-ttu-id="7ffaf-111">중간 검사점으로 이 단계에 해당하는 [종료 조건](networking-exit-criteria.md#crit-networking-step1)을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ffaf-111">As an interim checkpoint, you can see the [exit criteria](networking-exit-criteria.md#crit-networking-step1) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="7ffaf-112">다음 단계</span><span class="sxs-lookup"><span data-stu-id="7ffaf-112">Next step</span></span>

|||
|:-------|:-----|
|![2단계](./media/stepnumbers/Step2.png)|[<span data-ttu-id="7ffaf-114">각 사무실에 대해 로컬 인터넷 연결 구성</span><span class="sxs-lookup"><span data-stu-id="7ffaf-114">Configure local Internet connections for each office</span></span>](networking-dns-resolution-same-location.md)|

