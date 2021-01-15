---
title: 공격 시뮬레이션 교육 사용 시작
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: da5845db-c578-4a41-b2cb-5a09689a551b
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.custom:
- seo-marvel-apr2020
description: 관리자는 Microsoft 365 E5 또는 Microsoft Defender for Office 365 Plan 2 조직에서 공격 시뮬레이션 교육을 사용하여 시뮬레이션된 피싱 및 암호 공격을 실행하는 방법을 배울 수 있습니다.
ms.openlocfilehash: 9d97816edf7d59c002658fc8bb3f39e72dbc2430
ms.sourcegitcommit: df58fd8ebe14ca98fc1be84dbfb9c29ef7ab1d62
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/15/2021
ms.locfileid: "49871251"
---
# <a name="get-started-using-attack-simulation-training"></a><span data-ttu-id="627f7-103">공격 시뮬레이션 교육 사용 시작</span><span class="sxs-lookup"><span data-stu-id="627f7-103">Get started using Attack simulation training</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="627f7-104">조직에 위협 조사 및 대응 기능이 포함된 Microsoft 365 E5 또는 [](office-365-ti.md)Microsoft Defender for Office 365 계획 2가 있는 경우 Microsoft 보안 센터의 공격 시뮬레이션 교육을 사용하여 조직에서 실제 공격 시나리오를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="627f7-104">If your organization has Microsoft 365 E5 or Microsoft Defender for Office 365 Plan 2, which includes [Threat Investigation and Response capabilities](office-365-ti.md), you can use Attack simulation training in the Microsoft Security Center to run realistic attack scenarios in your organization.</span></span> <span data-ttu-id="627f7-105">이러한 시뮬레이션된 공격은 실제 공격이 아래쪽에 영향을 미치기 전에 취약한 사용자를 식별하고 찾는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="627f7-105">These simulated attacks can help you identify and find vulnerable users before a real attack impacts your bottom line.</span></span> <span data-ttu-id="627f7-106">자세한 내용은 이 문서를 읽어보아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="627f7-106">Read this article to learn more.</span></span>

> [!NOTE]
> <span data-ttu-id="627f7-107">공격 시뮬레이션 교육은 [Office 365용 Microsoft Defender의](attack-simulator.md)공격 시뮬레이터에 설명된 이전 공격 시뮬레이터 v1 환경을 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="627f7-107">Attack simulation training replaces the old Attack Simulator v1 experience that's described in [Attack Simulator in Microsoft Defender for Office 365](attack-simulator.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="627f7-108">시작하기 전에 알아야 할 내용</span><span class="sxs-lookup"><span data-stu-id="627f7-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="627f7-109">Microsoft 보안 센터를 열기 위해 다음으로 이동 <https://security.microsoft.com/> 합니다.</span><span class="sxs-lookup"><span data-stu-id="627f7-109">To open the Microsoft Security Center, go to <https://security.microsoft.com/>.</span></span> <span data-ttu-id="627f7-110">공격 시뮬레이션 교육은 전자 메일 및 공동 작업 공격 **시뮬레이션** \> **교육에서 사용할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="627f7-110">Attack simulation training is available at **Email and collaboration** \> **Attack simulation training**.</span></span> <span data-ttu-id="627f7-111">공격 시뮬레이션 교육으로 직접 이동하기 위해 를 열고 <https://security.microsoft.com/attacksimulator> .</span><span class="sxs-lookup"><span data-stu-id="627f7-111">To go directly to Attack simulation training, open <https://security.microsoft.com/attacksimulator>.</span></span>

- <span data-ttu-id="627f7-112">여러 Microsoft 365 구독에서 공격 시뮬레이션 교육의 가용성에 대한 자세한 내용은 [Microsoft Defender for Office 365 서비스 설명을 참조하세요.](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)</span><span class="sxs-lookup"><span data-stu-id="627f7-112">For more information about the availability of Attack simulation training across different Microsoft 365 subscriptions, see [Microsoft Defender for Office 365 service description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>

- <span data-ttu-id="627f7-113">이 문서의 절차를 수행하려면 먼저 보안 & 준수 센터 또는 Azure Active Directory에서 사용 권한을 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="627f7-113">You need to be assigned permissions in the Security & Compliance Center or in Azure Active Directory before you can do the procedures in this article.</span></span> <span data-ttu-id="627f7-114">특히 조직 관리의 구성원 또는 보안 관리자 또는 다음 역할 중 하나에 해당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="627f7-114">Specifically, you need to be a member of **Organization Management**, **Security Administrator**, or one of the following roles:</span></span>
  - <span data-ttu-id="627f7-115">**공격 시뮬레이터 관리자:** 공격 시뮬레이션 캠페인의 모든 측면을 만들고 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="627f7-115">**Attack Simulator Administrators**: Create and managed all aspects of attack simulation campaigns.</span></span>
  - <span data-ttu-id="627f7-116">**공격 시뮬레이터 페이로드 작성자:** 관리자가 나중에 시작할 수 있는 공격 페이로드를 만드세요.</span><span class="sxs-lookup"><span data-stu-id="627f7-116">**Attack Simulator Payload Authors**: Create attack payloads that an admin can initiate later.</span></span>

  <span data-ttu-id="627f7-117">자세한 내용은 보안 및 준수 센터 또는 & [정보의](permissions-in-the-security-and-compliance-center.md) 사용 [권한을 참조하세요.](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)</span><span class="sxs-lookup"><span data-stu-id="627f7-117">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md) or [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>

- <span data-ttu-id="627f7-118">공격 시뮬레이션 교육을 위한 해당 PowerShell cmdlet은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="627f7-118">There are no corresponding PowerShell cmdlets for Attack simulation training.</span></span>

- <span data-ttu-id="627f7-119">공격 시뮬레이션 및 교육 관련 데이터는 Microsoft 365 서비스의 다른 고객 데이터와 함께 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="627f7-119">Attack simulation and training related data is stored with other customer data for Microsoft 365 services.</span></span> <span data-ttu-id="627f7-120">자세한 내용은 [Microsoft 365](/microsoft-365/enterprise/o365-data-locations)데이터 위치를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="627f7-120">For more information see [Microsoft 365 data locations](/microsoft-365/enterprise/o365-data-locations).</span></span> <span data-ttu-id="627f7-121">공격 시뮬레이션은 현재 SGP, NOR, UAE, ZAF, GER, BRA 및 CHE 지역에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="627f7-121">Attack simulation is currently not available in the following regions: SGP, NOR, UAE, ZAF, GER, BRA, and CHE.</span></span>

## <a name="simulations"></a><span data-ttu-id="627f7-122">시뮬레이션</span><span class="sxs-lookup"><span data-stu-id="627f7-122">Simulations</span></span>

<span data-ttu-id="627f7-123">*피싱은* 합법적 또는 신뢰할 수 있는 보낸 사람으로부터 보낸 것으로 나타나는 메시지의 중요한 정보를 도용하려는 전자 메일 공격에 대한 일반적인 용어입니다.</span><span class="sxs-lookup"><span data-stu-id="627f7-123">*Phishing* is a generic term for email attacks that try to steal sensitive information in messages that appear to be from legitimate or trusted senders.</span></span> <span data-ttu-id="627f7-124">*피싱은* 소셜 엔지니어링으로 분류하는 기술의 하위 _집합의 일부입니다._</span><span class="sxs-lookup"><span data-stu-id="627f7-124">*Phishing* is a part of a subset of techniques we classify as _social engineering_.</span></span>

<span data-ttu-id="627f7-125">공격 시뮬레이션 교육에서는 여러 유형의 소셜 엔지니어링 기술을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="627f7-125">In Attack simulation training, multiple types of social engineering techniques are available:</span></span>

- <span data-ttu-id="627f7-126">**자격 증명 수집**: 공격자가 URL이 포함된 메시지를 받는 사람에게 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="627f7-126">**Credential harvest**: An attacker sends the recipient a message that contains a URL.</span></span> <span data-ttu-id="627f7-127">받는 사람이 URL을 클릭하면 일반적으로 사용자에게 사용자 이름과 암호를 묻는 대화 상자가 표시되는 웹 사이트로 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="627f7-127">When the recipient clicks on the URL, they're taken to a website that typically shows a dialog box that asks the user for their username and password.</span></span> <span data-ttu-id="627f7-128">일반적으로 대상 페이지는 사용자 신뢰를 구축하기 위해 잘 알려진 웹 사이트를 나타내기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="627f7-128">Typically, the destination page is themed to represent a well-known website in order to build trust in the user.</span></span>

- <span data-ttu-id="627f7-129">**맬웨어 첨부** 파일 : 공격자가 첨부 파일이 포함된 메시지를 받는 사람에게 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="627f7-129">**Malware attachment**: An attacker sends the recipient a message that contains an attachment.</span></span> <span data-ttu-id="627f7-130">받는 사람이 첨부 파일을 열면 사용자의 장치에서 임의의 코드(예: 매크로)가 실행하여 공격자가 추가 코드를 설치하거나 추가 코드를 직접 설치하는 데 도움을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="627f7-130">When the recipient opens the attachment, arbitrary code (for example, a macro) is run on the user's device to help the attacker install additional code or further entrench themselves.</span></span>

- <span data-ttu-id="627f7-131">**첨부 파일 링크**: 자격 증명 수집의 하이브리드입니다.</span><span class="sxs-lookup"><span data-stu-id="627f7-131">**Link in attachment**: This is a hybrid of a credential harvest.</span></span> <span data-ttu-id="627f7-132">공격자는 첨부 파일 내부의 URL이 포함된 메시지를 받는 사람에게 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="627f7-132">An attacker sends the recipient a message that contains a URL inside of an attachment.</span></span> <span data-ttu-id="627f7-133">받는 사람이 첨부 파일을 열고 URL을 클릭하면 일반적으로 사용자에게 사용자 이름과 암호를 묻는 대화 상자가 표시되는 웹 사이트로 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="627f7-133">When the recipient opens the attachment and clicks on the URL, they're taken to a website that typically shows a dialog box that asks the user for their username and password.</span></span> <span data-ttu-id="627f7-134">일반적으로 대상 페이지는 사용자 신뢰를 구축하기 위해 잘 알려진 웹 사이트를 나타내기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="627f7-134">Typically, the destination page is themed to represent a well-known website in order to build trust in the user.</span></span>

- <span data-ttu-id="627f7-135">**맬웨어에** 대한 링크: 공격자는 잘 알려진 파일 공유 사이트의 첨부 파일에 대한 링크가 포함된 메시지를 받는 사람에게 보냅니다(예: SharePoint Online 또는 Dropbox).</span><span class="sxs-lookup"><span data-stu-id="627f7-135">**Link to malware**: An attacker sends the recipient a message that contains a link to an attachment on a well-known file sharing site (for example, SharePoint Online or Dropbox).</span></span> <span data-ttu-id="627f7-136">받는 사람이 URL을 클릭하면 첨부 파일이 열리며 사용자의 장치에서 임의의 코드(예: 매크로)가 실행됩니다. 공격자가 추가 코드를 설치하거나 추가 코드를 직접 설치하는 데 도움을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="627f7-136">When the recipient clicks on the URL, the attachment opens and arbitrary code (for example, a macro) is run on the user's device to help the attacker install additional code or further entrench themselves.</span></span>

- <span data-ttu-id="627f7-137">**드라이브-url:** 공격자는 URL이 포함된 메시지를 받는 사람에게 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="627f7-137">**Drive-by-url**: An attacker sends the recipient a messages that contains a URL.</span></span> <span data-ttu-id="627f7-138">받는 사람이 URL을 클릭하면 백그라운드 코드를 실행하는 웹 사이트로 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="627f7-138">When the recipient clicks on the URL, they're taken to a website that tries to run background code.</span></span> <span data-ttu-id="627f7-139">이 백그라운드 코드는 받는 사람에 대한 정보를 수집하거나 장치에 임의 코드를 배포하려고 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="627f7-139">This background code attempts to gather information about the recipient or deploy arbitrary code on their device.</span></span> <span data-ttu-id="627f7-140">일반적으로 대상 웹 사이트는 손상된 잘 알려진 웹 사이트 또는 잘 알려진 웹 사이트의 복제본입니다.</span><span class="sxs-lookup"><span data-stu-id="627f7-140">Typically, the destination website is a well-known website that has been compromised or a clone of a well-known website.</span></span> <span data-ttu-id="627f7-141">웹 사이트에 대해 잘 알고 있는 경우 링크를 클릭하기에 안전한지 사용자에게 확신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="627f7-141">Familiarity with the website helps convince the user that the link is safe to click.</span></span> <span data-ttu-id="627f7-142">이 기술을 워터홀 _공격(watering hole attack)라고도 합니다._</span><span class="sxs-lookup"><span data-stu-id="627f7-142">This technique is also known as a _watering hole attack_.</span></span>

> [!NOTE]
> <span data-ttu-id="627f7-143">피싱 캠페인에서 URL을 사용하기 전에 지원되는 웹 브라우저에서 시뮬레이트된 피싱 URL의 가용성을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="627f7-143">Check the availability of the simulated phishing URL in your supported web browsers before you use the URL in a phishing campaign.</span></span> <span data-ttu-id="627f7-144">항상 이러한 시뮬레이션 URL을 허용하기 위해 많은 URL 신뢰도 공급업체와 협력하고 있는 반면, Google Safe Browsing과 같은 전체 범위가 항상 있는 것은 아니며,</span><span class="sxs-lookup"><span data-stu-id="627f7-144">While we work with many URL reputation vendors to always allow these simulation URLs, we don't always have full coverage (for example, Google Safe Browsing).</span></span> <span data-ttu-id="627f7-145">대부분의 공급업체는 항상 특정 URL(예: )을 허용할 수 있는 지침을 <https://support.google.com/chrome/a/answer/7532419> 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="627f7-145">Most vendors provide guidance that allows you to always allow specific URLs (for example, <https://support.google.com/chrome/a/answer/7532419>).</span></span>

<span data-ttu-id="627f7-146">공격 시뮬레이션 교육에 사용되는 URL은 다음 목록에 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="627f7-146">The URLs that are used by Attack simulation training are described in the following list:</span></span>

- <https://www.mcsharepoint.com>
- <https://www.attemplate.com>
- <https://www.doctricant.com>
- <https://www.mesharepoint.com>
- <https://www.officence.com>
- <https://www.officenced.com>
- <https://www.officences.com>
- <https://www.officentry.com>
- <https://www.officested.com>
- <https://www.prizegives.com>
- <https://www.prizemons.com>
- <https://www.prizewel.com>
- <https://www.prizewings.com>
- <https://www.shareholds.com>
- <https://www.sharepointen.com>
- <https://www.sharepointin.com>
- <https://www.sharepointle.com>
- <https://www.sharesbyte.com>
- <https://www.sharession.com>
- <https://www.sharestion.com>
- <https://www.templateau.com>
- <https://www.templatent.com>
- <https://www.templatern.com>
- <https://www.windocyte.com>

### <a name="create-a-simulation"></a><span data-ttu-id="627f7-147">시뮬레이션 만들기</span><span class="sxs-lookup"><span data-stu-id="627f7-147">Create a simulation</span></span>

<span data-ttu-id="627f7-148">새 시뮬레이션을 만들고 보내는 방법에 대한 단계별 지침은 피싱 공격 [시뮬레이트를 참조하세요.](attack-simulation-training.md)</span><span class="sxs-lookup"><span data-stu-id="627f7-148">For step by step instructions on how to create and send a new simulation, see [Simulate a phishing attack](attack-simulation-training.md).</span></span>

### <a name="create-a-payload"></a><span data-ttu-id="627f7-149">페이로드 만들기</span><span class="sxs-lookup"><span data-stu-id="627f7-149">Create a payload</span></span>

<span data-ttu-id="627f7-150">시뮬레이션 내에서 사용할 페이로드를 만드는 방법에 대한 단계별 지침은 공격 시뮬레이션 교육을 위한 사용자 지정 [페이로드 만들기를 참조하세요.](attack-simulation-training-payloads.md)</span><span class="sxs-lookup"><span data-stu-id="627f7-150">For step by step instructions on how to create a payload for use within a simulation, see [Create a custom payload for Attack simulation training](attack-simulation-training-payloads.md).</span></span>

### <a name="gaining-insights"></a><span data-ttu-id="627f7-151">인사이트 얻기</span><span class="sxs-lookup"><span data-stu-id="627f7-151">Gaining insights</span></span>

<span data-ttu-id="627f7-152">보고를 통해 인사이트를 얻는 방법에 대한 단계별 지침은 공격 시뮬레이션 교육을 통해 인사이트 [얻기를 참조하세요.](attack-simulation-training-insights.md)</span><span class="sxs-lookup"><span data-stu-id="627f7-152">For step by step instructions on how to gain insights with reporting, see [Gain insights through Attack simulation training](attack-simulation-training-insights.md).</span></span>
