---
title: 공격의 신나는 교육 사용 시작
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.custom:
- seo-marvel-apr2020
description: 관리자는 공격 시뮬레이션 교육을 사용하여 Microsoft 365 E5 계획 2 조직용 Microsoft Defender에서 시뮬레이션된 피싱 및 암호 Office 365 방법을 배울 수 있습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c5d4b77204f207c31f2014df797f6209b92c9ccb
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52822337"
---
# <a name="get-started-using-attack-simulation-training"></a><span data-ttu-id="ec32c-103">공격의 신나는 교육 사용 시작</span><span class="sxs-lookup"><span data-stu-id="ec32c-103">Get started using Attack simulation training</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="ec32c-104">조직에 위협 Microsoft 365 E5 및 대응 기능이 포함된 Office 365 계획 2용 [](office-365-ti.md)Microsoft Defender 또는 Microsoft Defender가 있는 경우 Microsoft 보안 센터의 공격 시뮬레이션 교육을 사용하여 조직에서 실제 공격 시나리오를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec32c-104">If your organization has Microsoft 365 E5 or Microsoft Defender for Office 365 Plan 2, which includes [Threat Investigation and Response capabilities](office-365-ti.md), you can use Attack simulation training in the Microsoft Security Center to run realistic attack scenarios in your organization.</span></span> <span data-ttu-id="ec32c-105">이러한 시뮬레이션된 공격은 실제 공격이 아래쪽에 영향을 미치기 전에 취약한 사용자를 식별하고 찾는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec32c-105">These simulated attacks can help you identify and find vulnerable users before a real attack impacts your bottom line.</span></span> <span data-ttu-id="ec32c-106">자세한 내용은 이 문서를 읽어 보아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec32c-106">Read this article to learn more.</span></span>

> [!NOTE]
> <span data-ttu-id="ec32c-107">공격 시뮬레이션 교육은 Microsoft Defender for Office 365 공격 시뮬레이터에 설명된 이전 공격 시뮬레이터 v1 환경을 [Office 365.](attack-simulator.md)</span><span class="sxs-lookup"><span data-stu-id="ec32c-107">Attack simulation training replaces the old Attack Simulator v1 experience that's described in [Attack Simulator in Microsoft Defender for Office 365](attack-simulator.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="ec32c-108">시작하기 전에 알아야 할 내용은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="ec32c-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="ec32c-109">Microsoft 보안 센터를 열기 위해 로 이동 <https://security.microsoft.com> 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec32c-109">To open the Microsoft Security Center, go to <https://security.microsoft.com>.</span></span> <span data-ttu-id="ec32c-110">공격 시뮬레이션 교육은 전자 **메일** 및 공동 작업 공격 시뮬레이션 \> **교육에서 사용할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="ec32c-110">Attack simulation training is available at **Email and collaboration** \> **Attack simulation training**.</span></span> <span data-ttu-id="ec32c-111">공격 시뮬레이션 교육으로 직접 이동하기 위해 를 를 를 <https://security.microsoft.com/attacksimulator> 습니다.</span><span class="sxs-lookup"><span data-stu-id="ec32c-111">To go directly to Attack simulation training, open <https://security.microsoft.com/attacksimulator>.</span></span>

- <span data-ttu-id="ec32c-112">여러 Microsoft 365 구독의 공격 시뮬레이션 교육 가용성에 대한 자세한 내용은 Microsoft [Defender for Office 365 참조하세요.](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)</span><span class="sxs-lookup"><span data-stu-id="ec32c-112">For more information about the availability of Attack simulation training across different Microsoft 365 subscriptions, see [Microsoft Defender for Office 365 service description](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>

- <span data-ttu-id="ec32c-113">이 문서의 절차를 수행하려면 보안 & 준수 센터 또는 Azure Active Directory 사용 권한을 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec32c-113">You need to be assigned permissions in the Security & Compliance Center or in Azure Active Directory before you can do the procedures in this article.</span></span> <span data-ttu-id="ec32c-114">특히 조직 관리, 보안 관리자 또는 다음 역할 중 하나에 해당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec32c-114">Specifically, you need to be a member of **Organization Management**, **Security Administrator**, or one of the following roles:</span></span>
  - <span data-ttu-id="ec32c-115">**공격 시뮬레이터 관리자:** 공격 시뮬레이션 캠페인의 모든 측면을 만들고 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="ec32c-115">**Attack Simulator Administrators**: Create and managed all aspects of attack simulation campaigns.</span></span>
  - <span data-ttu-id="ec32c-116">**공격 시뮬레이터 페이로드 작성자:** 관리자가 나중에 시작할 수 있는 공격 페이로드를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="ec32c-116">**Attack Simulator Payload Authors**: Create attack payloads that an admin can initiate later.</span></span>

  <span data-ttu-id="ec32c-117">자세한 내용은 [Security & Compliance Center의](permissions-in-the-security-and-compliance-center.md) 사용 권한 또는 관리자 역할 [정보를 참조하세요.](../../admin/add-users/about-admin-roles.md)</span><span class="sxs-lookup"><span data-stu-id="ec32c-117">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md) or [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

- <span data-ttu-id="ec32c-118">공격 시뮬레이션 교육을 위한 해당 PowerShell cmdlet은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ec32c-118">There are no corresponding PowerShell cmdlets for Attack simulation training.</span></span>

- <span data-ttu-id="ec32c-119">공격 시뮬레이션 및 교육 관련 데이터는 다른 고객 데이터와 함께 Microsoft 365 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec32c-119">Attack simulation and training related data is stored with other customer data for Microsoft 365 services.</span></span> <span data-ttu-id="ec32c-120">자세한 내용은 데이터 [Microsoft 365 참조하세요.](../../enterprise/o365-data-locations.md)</span><span class="sxs-lookup"><span data-stu-id="ec32c-120">For more information see [Microsoft 365 data locations](../../enterprise/o365-data-locations.md).</span></span> <span data-ttu-id="ec32c-121">공격 시뮬레이션은 NAM, APC, EUR, IND, CAN, AUS, FRA, GBR, JPN 및 KOR 지역에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec32c-121">Attack simulation is available in the following regions: NAM, APC, EUR, IND, CAN, AUS, FRA, GBR, JPN, and KOR.</span></span>

- <span data-ttu-id="ec32c-122">2021년 6월 15일 현재, 공격 시뮬레이션 교육은 GCC.</span><span class="sxs-lookup"><span data-stu-id="ec32c-122">As of June 15 2021, Attack simulation training is available in GCC.</span></span> <span data-ttu-id="ec32c-123">조직에서 정부용 G5 Office 365 GCC 또는 Microsoft Defender for Office 365(계획 2)가 있는 경우 이 문서에 설명된 바와 같이 Microsoft 보안 센터에서 공격 시뮬레이션 교육을 사용하여 조직의 실제 공격 시나리오를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec32c-123">If your organization has Office 365 G5 GCC or Microsoft Defender for Office 365 (Plan 2) for Government, you can use Attack simulation training in the Microsoft Security Center to run realistic attack scenarios in your organization as described in this article.</span></span> <span data-ttu-id="ec32c-124">공격 시뮬레이션 교육은 High 또는 DoD 환경에서는 GCC 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ec32c-124">Attack simulation training is not yet available in GCC High or DoD environments.</span></span>

> [!NOTE]
> <span data-ttu-id="ec32c-125">공격 시뮬레이션 교육은 평가판으로 E3 고객에게 일부 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ec32c-125">Attack simulation training offers a subset of capabilities to E3 customers as a trial.</span></span> <span data-ttu-id="ec32c-126">평가판 제품에는 자격 증명 수집 페이로드를 사용하는 능력과 'ISA 피싱' 또는 '대량 시장 피싱' 교육 환경을 선택하는 능력이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec32c-126">The trial offering contains the ability to use a Credential Harvest payload and the ability to select 'ISA Phishing' or 'Mass Market Phishing' training experiences.</span></span> <span data-ttu-id="ec32c-127">다른 기능은 E3 평가판 제공에 참여하지는 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec32c-127">No other capabilities are part of the E3 trial offering.</span></span>

## <a name="simulations"></a><span data-ttu-id="ec32c-128">시뮬레이션</span><span class="sxs-lookup"><span data-stu-id="ec32c-128">Simulations</span></span>

<span data-ttu-id="ec32c-129">*피싱은* 합법적인 보낸 사람이나 신뢰할 수 있는 보낸 사람이 보낸 것으로 나타나는 메시지의 중요한 정보를 도용하려는 전자 메일 공격의 일반적인 용어입니다.</span><span class="sxs-lookup"><span data-stu-id="ec32c-129">*Phishing* is a generic term for email attacks that try to steal sensitive information in messages that appear to be from legitimate or trusted senders.</span></span> <span data-ttu-id="ec32c-130">*피싱은* 소셜 엔지니어링으로 분류하는 기술의 하위 _집합의 일부입니다._</span><span class="sxs-lookup"><span data-stu-id="ec32c-130">*Phishing* is a part of a subset of techniques we classify as _social engineering_.</span></span>

<span data-ttu-id="ec32c-131">공격 시뮬레이션 교육에서는 여러 유형의 소셜 엔지니어링 기술을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec32c-131">In Attack simulation training, multiple types of social engineering techniques are available:</span></span>

- <span data-ttu-id="ec32c-132">**자격 증명 수집:** 공격자가 URL이 포함된 메시지를 받는 사람에게 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="ec32c-132">**Credential harvest**: An attacker sends the recipient a message that contains a URL.</span></span> <span data-ttu-id="ec32c-133">받는 사람이 URL을 클릭하면 일반적으로 사용자에게 사용자 이름과 암호를 묻는 대화 상자가 표시되는 웹 사이트로 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec32c-133">When the recipient clicks on the URL, they're taken to a website that typically shows a dialog box that asks the user for their username and password.</span></span> <span data-ttu-id="ec32c-134">일반적으로 대상 페이지는 사용자에 대한 트러스트 구축을 위해 잘 알려진 웹 사이트를 나타내기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ec32c-134">Typically, the destination page is themed to represent a well-known website in order to build trust in the user.</span></span>

- <span data-ttu-id="ec32c-135">**맬웨어 첨부** 파일: 공격자가 첨부 파일이 포함된 메시지를 받는 사람에게 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="ec32c-135">**Malware attachment**: An attacker sends the recipient a message that contains an attachment.</span></span> <span data-ttu-id="ec32c-136">받는 사람이 첨부 파일을 열면 사용자의 장치에서 임의의 코드(예: 매크로)를 실행하여 공격자가 추가 코드를 설치하거나 추가 엔렌치 자체를 설치하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec32c-136">When the recipient opens the attachment, arbitrary code (for example, a macro) is run on the user's device to help the attacker install additional code or further entrench themselves.</span></span>

- <span data-ttu-id="ec32c-137">**첨부 파일 링크:** 자격 증명 수집의 하이브리드입니다.</span><span class="sxs-lookup"><span data-stu-id="ec32c-137">**Link in attachment**: This is a hybrid of a credential harvest.</span></span> <span data-ttu-id="ec32c-138">공격자는 첨부 파일 내부의 URL이 포함된 메시지를 받는 사람에게 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="ec32c-138">An attacker sends the recipient a message that contains a URL inside of an attachment.</span></span> <span data-ttu-id="ec32c-139">받는 사람이 첨부 파일을 열고 URL을 클릭하면 일반적으로 사용자에게 사용자 이름과 암호를 묻는 대화 상자가 표시되는 웹 사이트로 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec32c-139">When the recipient opens the attachment and clicks on the URL, they're taken to a website that typically shows a dialog box that asks the user for their username and password.</span></span> <span data-ttu-id="ec32c-140">일반적으로 대상 페이지는 사용자에 대한 트러스트 구축을 위해 잘 알려진 웹 사이트를 나타내기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ec32c-140">Typically, the destination page is themed to represent a well-known website in order to build trust in the user.</span></span>

- <span data-ttu-id="ec32c-141">**맬웨어에** 대한 링크: 공격자는 잘 알려진 파일 공유 사이트의 첨부 파일에 대한 링크가 포함된 메시지를 받는 사람에게 보냅니다(예: SharePoint Online 또는 Dropbox.</span><span class="sxs-lookup"><span data-stu-id="ec32c-141">**Link to malware**: An attacker sends the recipient a message that contains a link to an attachment on a well-known file sharing site (for example, SharePoint Online or Dropbox).</span></span> <span data-ttu-id="ec32c-142">받는 사람이 URL을 클릭하면 첨부 파일이 열리며 사용자의 장치에서 임의의 코드(예: 매크로)가 실행됩니다. 이를 통해 공격자가 추가 코드를 설치하거나 추가 코드를 직접 설치하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec32c-142">When the recipient clicks on the URL, the attachment opens and arbitrary code (for example, a macro) is run on the user's device to help the attacker install additional code or further entrench themselves.</span></span>

- <span data-ttu-id="ec32c-143">**드라이브-URL:** 공격자가 URL이 포함된 메시지를 받는 사람에게 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="ec32c-143">**Drive-by-url**: An attacker sends the recipient a messages that contains a URL.</span></span> <span data-ttu-id="ec32c-144">받는 사람이 URL을 클릭하면 백그라운드 코드를 실행하는 웹 사이트로 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec32c-144">When the recipient clicks on the URL, they're taken to a website that tries to run background code.</span></span> <span data-ttu-id="ec32c-145">이 백그라운드 코드는 받는 사람에 대한 정보를 수집하거나 장치에 임의 코드를 배포하려고 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="ec32c-145">This background code attempts to gather information about the recipient or deploy arbitrary code on their device.</span></span> <span data-ttu-id="ec32c-146">일반적으로 대상 웹 사이트는 손상된 잘 알려진 웹 사이트 또는 잘 알려진 웹 사이트의 복제본입니다.</span><span class="sxs-lookup"><span data-stu-id="ec32c-146">Typically, the destination website is a well-known website that has been compromised or a clone of a well-known website.</span></span> <span data-ttu-id="ec32c-147">웹 사이트에 대해 잘 알고 있는 경우 링크를 클릭하는 것이 안전한지 사용자에게 확신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec32c-147">Familiarity with the website helps convince the user that the link is safe to click.</span></span> <span data-ttu-id="ec32c-148">이 기술을 워터홀 _공격(watering hole attack)라고도 합니다._</span><span class="sxs-lookup"><span data-stu-id="ec32c-148">This technique is also known as a _watering hole attack_.</span></span>

> [!NOTE]
> <span data-ttu-id="ec32c-149">피싱 캠페인에서 URL을 사용하기 전에 지원되는 웹 브라우저에서 시뮬레이트된 피싱 URL의 가용성을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="ec32c-149">Check the availability of the simulated phishing URL in your supported web browsers before you use the URL in a phishing campaign.</span></span> <span data-ttu-id="ec32c-150">많은 URL 신뢰도 공급업체와 협력하여 항상 이러한 시뮬레이션 URL을 허용하는 반면, 항상 전체 범위가 있는 것은 아니며(예: Google Safe Browsing)</span><span class="sxs-lookup"><span data-stu-id="ec32c-150">While we work with many URL reputation vendors to always allow these simulation URLs, we don't always have full coverage (for example, Google Safe Browsing).</span></span> <span data-ttu-id="ec32c-151">대부분의 공급업체는 항상 특정 URL(예: )을 허용할 수 있는 지침을 <https://support.google.com/chrome/a/answer/7532419> 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ec32c-151">Most vendors provide guidance that allows you to always allow specific URLs (for example, <https://support.google.com/chrome/a/answer/7532419>).</span></span>

<span data-ttu-id="ec32c-152">공격 시뮬레이션 교육에 사용되는 URL은 다음 목록에 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec32c-152">The URLs that are used by Attack simulation training are described in the following list:</span></span>

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

### <a name="create-a-simulation"></a><span data-ttu-id="ec32c-153">시뮬레이션 만들기</span><span class="sxs-lookup"><span data-stu-id="ec32c-153">Create a simulation</span></span>

<span data-ttu-id="ec32c-154">새 시뮬레이션을 만들고 보내는 방법에 대한 단계별 지침은 피싱 공격 [시뮬레이트를 참조하세요.](attack-simulation-training.md)</span><span class="sxs-lookup"><span data-stu-id="ec32c-154">For step by step instructions on how to create and send a new simulation, see [Simulate a phishing attack](attack-simulation-training.md).</span></span>

### <a name="create-a-payload"></a><span data-ttu-id="ec32c-155">페이로드 만들기</span><span class="sxs-lookup"><span data-stu-id="ec32c-155">Create a payload</span></span>

<span data-ttu-id="ec32c-156">시뮬레이션 내에서 사용할 페이로드를 만드는 방법에 대한 단계별 지침은 공격 시뮬레이션 교육을 위한 사용자 지정 [페이로드 만들기를 참조하세요.](attack-simulation-training-payloads.md)</span><span class="sxs-lookup"><span data-stu-id="ec32c-156">For step by step instructions on how to create a payload for use within a simulation, see [Create a custom payload for Attack simulation training](attack-simulation-training-payloads.md).</span></span>

### <a name="gaining-insights"></a><span data-ttu-id="ec32c-157">인사이트 얻기</span><span class="sxs-lookup"><span data-stu-id="ec32c-157">Gaining insights</span></span>

<span data-ttu-id="ec32c-158">보고를 통해 인사이트를 얻는 방법에 대한 단계별 지침은 공격 시뮬레이션 교육을 통해 인사이트 [얻기를 참조하세요.](attack-simulation-training-insights.md)</span><span class="sxs-lookup"><span data-stu-id="ec32c-158">For step by step instructions on how to gain insights with reporting, see [Gain insights through Attack simulation training](attack-simulation-training-insights.md).</span></span>

> [!NOTE]
> <span data-ttu-id="ec32c-159">공격 시뮬레이터는 안전 링크 정책의 사용자 클릭 추적 안 하도록 설정이 켜져 있는 경우에도 Office 365 피싱 캠페인의 대상을 받는  사람에게 전송되는 페이로드 메시지의 URL에 대한 클릭 데이터를 안전하게 추적하기 위해 Defender의 안전한 링크를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ec32c-159">Attack Simulator uses Safe Links in Defender for Office 365 to securely track click data for the URL in the payload message that's sent to targeted recipients of a phishing campaign, even if the **Do not track user clicks** setting in Safe Links policies is turned on.</span></span>
