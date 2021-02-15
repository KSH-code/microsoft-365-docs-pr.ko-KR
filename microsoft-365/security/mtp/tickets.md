---
title: ServiceNow 티켓을 Microsoft 365 보안 센터 및 규정 준수 센터에 통합
description: Microsoft 365 보안 센터 및 규정 준수 센터에서 ServiceNow에서 티켓을 만들고 추적하는 방법을 학습합니다.
keywords: 보안, Microsoft 365, M365, 규정 준수, 준수 센터, 보안 센터, ServiceNow, 티켓, 작업, SNOW, 연결
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
ms.technology: m365d
ms.openlocfilehash: 4e647c2e526bb5cf99b1f40c07fc542315ebcd01
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49925485"
---
# <a name="integrate-servicenow-tickets-into-the-microsoft-365-security-center-and-compliance-center"></a><span data-ttu-id="ebfcf-104">ServiceNow 티켓을 Microsoft 365 보안 센터 및 규정 준수 센터에 통합</span><span class="sxs-lookup"><span data-stu-id="ebfcf-104">Integrate ServiceNow tickets into the Microsoft 365 security center and compliance center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

>[!CAUTION]
><span data-ttu-id="ebfcf-105">**ServiceNow 커넥터의 미리 보기 기간이 종료된 경우**</span><span class="sxs-lookup"><span data-stu-id="ebfcf-105">**The preview period for the ServiceNow connector has ended**</span></span><br>
><span data-ttu-id="ebfcf-106">이 기능은 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ebfcf-106">This capability is no longer available.</span></span> <span data-ttu-id="ebfcf-107">다음 단계를 결정하는 동안 여러분의 피드백에 감사하고 지원을 계속해주신 것을 환영합니다.</span><span class="sxs-lookup"><span data-stu-id="ebfcf-107">Thank you for your feedback and continued support while we determine next steps.</span></span>

<span data-ttu-id="ebfcf-108">ServiceNow는 기업이 엔터프라이즈 운영을 위한 디지털 워크플로를 관리하는 데 도움이 되는 인기 있는 클라우드 컴퓨팅 플랫폼입니다.</span><span class="sxs-lookup"><span data-stu-id="ebfcf-108">ServiceNow is a popular cloud computing platform that helps companies manage digital workflows for enterprise operations.</span></span> <span data-ttu-id="ebfcf-109">현재 플랫폼에는 IT 워크플로, 직원 워크플로 및 고객 워크플로가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebfcf-109">Their Now platform has IT workflows, employee workflows, and customer workflows.</span></span> [<span data-ttu-id="ebfcf-110">ServiceNow에 대해 자세히</span><span class="sxs-lookup"><span data-stu-id="ebfcf-110">Learn more about ServiceNow</span></span>](https://www.servicenow.com/)

<span data-ttu-id="ebfcf-111">Microsoft는 IT 관리자가 두 플랫폼 모두에서 티켓 및 작업을 보다 쉽게 관리할 수 있도록 ServiceNow와 협력했습니다.</span><span class="sxs-lookup"><span data-stu-id="ebfcf-111">Microsoft has partnered with ServiceNow to make it easier for IT admins to manage their tickets and tasks in both platforms.</span></span> <span data-ttu-id="ebfcf-112">ServiceNow에서 티켓을 기본적으로 만들고 추적하는 기능으로 [Microsoft 365](overview-security-center.md) 보안 센터와 [Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/microsoft-365-compliance-center) 규정 준수 센터가 향상되고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebfcf-112">[Microsoft 365 security center](overview-security-center.md) and the [Microsoft 365 compliance center](https://docs.microsoft.com/microsoft-365/compliance/microsoft-365-compliance-center) are being enhanced with the ability to natively create and track tickets in ServiceNow.</span></span>
