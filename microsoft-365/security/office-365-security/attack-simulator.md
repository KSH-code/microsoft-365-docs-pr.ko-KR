---
title: Microsoft Defender에서 공격 시뮬레이터를 Office 365
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
ms.assetid: da5845db-c578-4a41-b2cb-5a09689a551b
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: 관리자는 공격 시뮬레이터를 사용하여 계획 2 조직용 Microsoft Defender 또는 Microsoft 365 E5 Microsoft Defender에서 시뮬레이션된 피싱 Office 365 방법을 배울 수 있습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 73ad3501ed9818261c9fbec6ba12b4dc884da84f
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/24/2021
ms.locfileid: "52624828"
---
# <a name="attack-simulator-in-microsoft-defender-for-office-365"></a><span data-ttu-id="41b7c-103">Microsoft Defender에서 공격 시뮬레이터를 Office 365</span><span class="sxs-lookup"><span data-stu-id="41b7c-103">Attack Simulator in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="41b7c-104">**Microsoft** [Defender for Office 365 요금제 2에 적용](defender-for-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="41b7c-104">**Applies to** [Microsoft Defender for Office 365 plan 2](defender-for-office-365.md)</span></span>

<span data-ttu-id="41b7c-105">조직에 위협 조사 및 대응 기능이 포함된 Office 365 [](office-365-ti.md)계획 & 2용 Microsoft Defender가 있는 경우 보안 및 준수 센터의 공격 시뮬레이터를 사용하여 조직에서 실제적인 공격 시나리오를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-105">If your organization has Microsoft Defender for Office 365 Plan 2, which includes [Threat Investigation and Response capabilities](office-365-ti.md), you can use Attack Simulator in the Security & Compliance Center to run realistic attack scenarios in your organization.</span></span> <span data-ttu-id="41b7c-106">이러한 시뮬레이션된 공격은 실제 공격이 아래쪽에 영향을 미치기 전에 취약한 사용자를 식별하고 찾는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-106">These simulated attacks can help you identify and find vulnerable users before a real attack impacts your bottom line.</span></span> <span data-ttu-id="41b7c-107">자세한 내용은 이 문서를 읽어 보아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-107">Read this article to learn more.</span></span>

> [!NOTE]
>
> <span data-ttu-id="41b7c-108">이 문서에 설명된 공격 시뮬레이터는 이제 읽기 전용으로, 보안  센터의 전자 메일 & 공동 작업 노드에서 공격 시뮬레이션 [Microsoft 365 대체했습니다.](https://security.microsoft.com) </span><span class="sxs-lookup"><span data-stu-id="41b7c-108">Attack Simulator as described in this article is now read-only and has been replaced by **Attack simulation training** in the **Email & collaboration** node in the [Microsoft 365 security center](https://security.microsoft.com).</span></span> <span data-ttu-id="41b7c-109">자세한 내용은 공격 시뮬레이션 교육 사용 [시작을 참조하세요.](attack-simulation-training-get-started.md)</span><span class="sxs-lookup"><span data-stu-id="41b7c-109">For more information, see [Get started using Attack simulation training](attack-simulation-training-get-started.md).</span></span>
>
> <span data-ttu-id="41b7c-110">이 버전의 공격 시뮬레이터에서 새 시뮬레이션을 시작 하는 기능을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-110">The ability to launch new simulations from this version of Attack Simulator has been disabled.</span></span> <span data-ttu-id="41b7c-111">그러나 2021년 1월 24일 이후 최대 90일 동안 보고서에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-111">However, you can still access reports for up to 90 days from January 24, 2021.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="41b7c-112">시작하기 전에 알아야 할 사항은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="41b7c-112">What do you need to know before you begin?</span></span>

- <span data-ttu-id="41b7c-113">보안 및 준수 센터를 열려면 <https://protection.office.com/>로 이동하세요.</span><span class="sxs-lookup"><span data-stu-id="41b7c-113">To open the Security & Compliance Center, go to <https://protection.office.com/>.</span></span> <span data-ttu-id="41b7c-114">공격 시뮬레이터는 **위협** 관리 공격 \> **시뮬레이터에서 사용할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="41b7c-114">Attack simulator is available at **Threat management** \> **Attack simulator**.</span></span> <span data-ttu-id="41b7c-115">공격 시뮬레이터로 직접 이동하기 위해 를 를 <https://protection.office.com/attacksimulator> 습니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-115">To go directly to attack simulator, open <https://protection.office.com/attacksimulator>.</span></span>

- <span data-ttu-id="41b7c-116">여러 Microsoft 365 구독의 공격 시뮬레이터 가용성에 대한 자세한 내용은 Microsoft [Defender for Office 365 참조하세요.](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)</span><span class="sxs-lookup"><span data-stu-id="41b7c-116">For more information about the availability of Attack Simulator across different Microsoft 365 subscriptions, see [Microsoft Defender for Office 365 service description](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>

- <span data-ttu-id="41b7c-117">조직 관리 또는 보안 관리자 역할 **그룹의** **구성원이면** 됩니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-117">You need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="41b7c-118">보안 및 규정 준수 센터의 역할 그룹에 대한 자세한 내용은 [보안 및 규정 준수 센터의 사용 권한](permissions-in-the-security-and-compliance-center.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="41b7c-118">For more information about role groups in the Security & Compliance Center, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="41b7c-119">공격 시뮬레이터에서 캠페인을 만들고 관리하려면 MFA(다단계 인증)를 위해 계정을 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-119">Your account needs to be configured for multi-factor authentication (MFA) to create and manage campaigns in Attack Simulator.</span></span> <span data-ttu-id="41b7c-120">자세한 내용은 [다단계 인증 설정 을 참조하세요.](../../admin/security-and-compliance/set-up-multi-factor-authentication.md)</span><span class="sxs-lookup"><span data-stu-id="41b7c-120">For instructions, see [Set up multi-factor authentication](../../admin/security-and-compliance/set-up-multi-factor-authentication.md).</span></span>

- <span data-ttu-id="41b7c-121">공격 시뮬레이터는 클라우드 기반 사서함에서만 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-121">Attack Simulator only works on cloud-based mailboxes.</span></span>

- <span data-ttu-id="41b7c-122">피싱 캠페인은 30일 동안 이벤트를 수집하고 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-122">Phishing campaigns will collect and process events for 30 days.</span></span> <span data-ttu-id="41b7c-123">이전 캠페인 데이터는 캠페인을 시작한 후 최대 90일 동안 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-123">Historical campaign data will be available for up to 90 days after you launch the campaign.</span></span>

- <span data-ttu-id="41b7c-124">공격 시뮬레이션 및 교육 관련 데이터는 다른 고객 데이터와 함께 Microsoft 365 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-124">Attack simulation and training related data is stored with other customer data for Microsoft 365 services.</span></span> <span data-ttu-id="41b7c-125">자세한 내용은 데이터 [Microsoft 365 참조하세요.](../../enterprise/o365-data-locations.md)</span><span class="sxs-lookup"><span data-stu-id="41b7c-125">For more information see [Microsoft 365 data locations](../../enterprise/o365-data-locations.md).</span></span>

- <span data-ttu-id="41b7c-126">공격 시뮬레이터에 해당하는 PowerShell cmdlet은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-126">There are no corresponding PowerShell cmdlets for Attack Simulator.</span></span>

## <a name="spear-phishing-campaigns"></a><span data-ttu-id="41b7c-127">스피어 피싱 캠페인</span><span class="sxs-lookup"><span data-stu-id="41b7c-127">Spear phishing campaigns</span></span>

<span data-ttu-id="41b7c-128">*피싱은* 합법적인 보낸 사람이나 신뢰할 수 있는 보낸 사람이 보낸 것으로 나타나는 메시지의 중요한 정보를 도용하려는 전자 메일 공격의 일반적인 용어입니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-128">*Phishing* is a generic term for email attacks that try to steal sensitive information in messages that appear to be from legitimate or trusted senders.</span></span> <span data-ttu-id="41b7c-129">*스피어* 피싱은 대상 받는 사람(일반적으로 공격자가 받는 사람을 정정한 후)에 맞게 특별히 조정된 포커스가 있는 사용자 지정된 콘텐츠를 사용하는 대상 피싱 공격입니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-129">*Spear phishing* is a targeted phishing attack that uses focused and customized content that's specifically tailored to the targeted recipients (typically, after reconnaissance on the recipients by the attacker).</span></span>

<span data-ttu-id="41b7c-130">공격 시뮬레이터에서는 두 가지 유형의 스피어 피싱 캠페인을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-130">In Attack Simulator, two different types of spear phishing campaigns are available:</span></span>

- <span data-ttu-id="41b7c-131">**스피어 피싱(자격** 증명 수집) : 공격은 받는 사람이 메시지의 URL을 클릭할 수 있도록 설득합니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-131">**Spear phishing (credentials harvest)**: The attack tries to convince the recipients to click a URL in the message.</span></span> <span data-ttu-id="41b7c-132">링크를 클릭하면 자격 증명을 입력할지 묻는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-132">If they click the link, they're asked to enter their credentials.</span></span> <span data-ttu-id="41b7c-133">이 경우 다음 위치 중 하나로 이관됩니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-133">If they do, they're taken to one of the following locations:</span></span>

  - <span data-ttu-id="41b7c-134">이 테스트가 단지 테스트에 불과하다는 설명과 피싱 메시지를 인식하기 위한 팁을 제공하는 기본 페이지입니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-134">A default page that explains that this was a just a test, and gives tips for recognizing phishing messages.</span></span>

    ![피싱 링크를 클릭하고 자격 증명을 입력하면 사용자에게 표시](../../media/attack-simulator-phishing-result.png)

  - <span data-ttu-id="41b7c-136">지정한 사용자 지정 페이지(URL)입니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-136">A custom page (URL) that you specify.</span></span>

- <span data-ttu-id="41b7c-137">**스피어 피싱(첨부 파일)**: 공격은 받는 사람이 메시지에 첨부 파일을 .docx .pdf 설득합니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-137">**Spear phishing (attachment)**: The attack tries to convince the recipients to open a .docx or .pdf attachment in the message.</span></span> <span data-ttu-id="41b7c-138">첨부 파일에는 기본 피싱 링크의 동일한 콘텐츠가 포함되어 있지만 첫 번째 문장은 " 로 시작합니다. 이 메시지가 최근에 연 전자 메일 메시지로 \<Display Name\> 표시됩니다...".</span><span class="sxs-lookup"><span data-stu-id="41b7c-138">The attachment contains the same content from the default phishing link, but the first sentence starts with "\<Display Name\>, you are seeing this message as a recent email message you opened...".</span></span>

> [!NOTE]
> <span data-ttu-id="41b7c-139">현재 공격 시뮬레이터의 스피어 피싱 캠페인은 만료되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-139">Currently, spear phishing campaigns in Attack Simulator don't expire.</span></span>

### <a name="create-a-spear-phishing-campaign"></a><span data-ttu-id="41b7c-140">스피어 피싱 캠페인 만들기</span><span class="sxs-lookup"><span data-stu-id="41b7c-140">Create a spear phishing campaign</span></span>

<span data-ttu-id="41b7c-141">스피어 피싱 캠페인의 중요한 부분은 대상 받는 사람에게 전송된 전자 메일 메시지의 모양과 느낌입니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-141">An important part of any spear phishing campaign is the look and feel of the email message that's sent to the targeted recipients.</span></span> <span data-ttu-id="41b7c-142">전자 메일 메시지를 만들고 구성하기 위해 다음 옵션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-142">To create and configure the email message, you have these options:</span></span>

- <span data-ttu-id="41b7c-143">**기본 제공** 전자 메일 서식 파일 사용: 두 가지 기본 제공 템플릿인 **공제** 및 급여 업데이트가 **제공됩니다.**</span><span class="sxs-lookup"><span data-stu-id="41b7c-143">**Use a built-in email template**: Two built-in templates are available: **Prize Giveaway** and **Payroll Update**.</span></span> <span data-ttu-id="41b7c-144">캠페인을 만들고 시작하면 템플릿의 전자 메일 속성 중 일부, 전체 또는 전혀 사용자 지정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-144">You can further customize some, all, or none of the email properties from the template when you create and launch the campaign.</span></span>

- <span data-ttu-id="41b7c-145">**다시 사용할 수** 있는 전자 메일 템플릿 만들기: 전자 메일 서식 파일을 만들고 저장한 후 이후 스피어 피싱 캠페인에서 다시 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-145">**Create a reusable email template**: After you create and save the email template, you can use it again in future spear phishing campaigns.</span></span> <span data-ttu-id="41b7c-146">캠페인을 만들고 시작하면 템플릿의 전자 메일 속성 중 일부, 전체 또는 전혀 사용자 지정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-146">You can further customize some, all, or none of the email properties from the template when you create and launch the campaign.</span></span>

- <span data-ttu-id="41b7c-147">**마법사에서** 전자 메일 메시지 만들기: 스피어 피싱 캠페인을 만들고 시작하면 마법사에서 직접 전자 메일 메시지를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-147">**Create the email message in the wizard**: You can create the email message directly in the wizard as you create and launch the spear phishing campaign.</span></span>

#### <a name="step-1-optional-create-a-custom-email-template"></a><span data-ttu-id="41b7c-148">1단계(선택 사항): 사용자 지정 전자 메일 서식 파일 만들기</span><span class="sxs-lookup"><span data-stu-id="41b7c-148">Step 1 (Optional): Create a custom email template</span></span>

<span data-ttu-id="41b7c-149">기본 제공 템플릿 중 하나를 사용하거나 마법사에서 직접 전자 메일 메시지를 만들 경우 이 단계를 건너뛸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-149">If you're going to use one of the built-in templates or create the email message directly in the wizard, you can skip this step.</span></span>

1. <span data-ttu-id="41b7c-150">보안 및 & 센터에서 **위협** 관리 공격 \> **시뮬레이터로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="41b7c-150">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="41b7c-151">공격 **시뮬레이트** 페이지의 스피어 피싱(자격 증명 **수집)** 또는 스피어 **피싱(첨부 파일)** 섹션에서 공격 세부 정보를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="41b7c-151">On the **Simulate attacks** page, in either the **Spear Phishing (Credentials Harvest)** or **Spear Phishing (Attachment)** sections, click **Attack Details**.</span></span>

   <span data-ttu-id="41b7c-152">템플릿을 만드는 위치는 중요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-152">It doesn't matter where you create the template.</span></span> <span data-ttu-id="41b7c-153">템플릿에서 사용할 수 있는 옵션은 두 유형의 피싱 공격에 대해 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-153">The available options in the template are the same for both types of phishing attacks.</span></span>

3. <span data-ttu-id="41b7c-154">공격 **세부 정보** 페이지가 열리면  피싱 서식 파일 섹션의 서식 파일 만들기 영역에서 새 템플릿  **을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="41b7c-154">In the **Attack details** page that opens, in the **Phishing Templates** section, in the **Create Templates** area, click **New Template**.</span></span>

4. <span data-ttu-id="41b7c-155">피싱 **서식 파일 구성 마법사가** 새 플라이아웃에서 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-155">The **Configure Phishing Template** wizard starts in a new flyout.</span></span> <span data-ttu-id="41b7c-156">시작 **단계에서** 템플릿의 고유한 표시 이름을 입력하고 다음 을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="41b7c-156">In the **Start** step, enter a unique display name for the template, and then click **Next**.</span></span>

5. <span data-ttu-id="41b7c-157">전자 메일 **세부 정보 구성 단계에서** 다음 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-157">In the **Configure email details** step, configure the following settings:</span></span>

   - <span data-ttu-id="41b7c-158">**보낸 사람(이름)**: 메시지 보낸 사람에 사용되는 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-158">**From (Name)**: The display name that's used for the message sender.</span></span>

   - <span data-ttu-id="41b7c-159">**보낸 사람(전자 메일)**: 보낸 사람 전자 메일 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-159">**From (Email)**: The sender's email address.</span></span>

   - <span data-ttu-id="41b7c-160">**피싱 로그인** 서버 URL: 드롭다운을 클릭하고 목록에서 사용 가능한 URL 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-160">**Phishing Login Server URL**: Click the drop down and select one of the available URLs from the list.</span></span> <span data-ttu-id="41b7c-161">사용자가 클릭할 수 있는 URL입니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-161">This is the URL that users will be tempted to click.</span></span> <span data-ttu-id="41b7c-162">선택은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-162">The choices are:</span></span>

     - <http://portal.docdeliveryapp.com>
     - <http://portal.docdeliveryapp.net>
     - <http://portal.docstoreinternal.com>
     - <http://portal.docstoreinternal.net>
     - <http://portal.hardwarecheck.net>
     - <http://portal.hrsupportint.com>
     - <http://portal.payrolltooling.com>
     - <http://portal.payrolltooling.net>
     - <http://portal.prizegiveaway.net>
     - <http://portal.prizesforall.com>
     - <http://portal.salarytoolint.com>
     - <http://portal.salarytoolint.net>

     > [!NOTE]
     >
     > <span data-ttu-id="41b7c-163">URL 신뢰도 서비스는 이러한 URL 중 하나 이상을 안전하지 않은 것으로 식별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-163">A URL reputation service might identify one or more of these URLs as unsafe.</span></span> <span data-ttu-id="41b7c-164">피싱 캠페인에서 URL을 사용하기 전에 지원되는 웹 브라우저에서 URL의 가용성을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-164">Check the availability of the URL in your supported web browsers before you use the URL in a phishing campaign.</span></span>

   - <span data-ttu-id="41b7c-165">사용자 지정 방문 페이지 **URL:** 피싱 링크를 클릭하고 자격 증명을 입력할 경우 사용자가 이동되는 선택적 방문 페이지를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-165">**Custom Landing Page URL**: Enter an optional landing page where users are taken if they click the phishing link and enter their credentials.</span></span> <span data-ttu-id="41b7c-166">이 링크는 기본 방문 페이지를 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-166">This link replaces the default landing page.</span></span> <span data-ttu-id="41b7c-167">예를 들어 내부 인식 교육이 있는 경우 여기에서 해당 URL을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-167">For example, if you have internal awareness training, you can specify that URL here.</span></span>

   - <span data-ttu-id="41b7c-168">**범주:** 현재 이 설정은 사용되지 않습니다(입력한 항목은 무시).</span><span class="sxs-lookup"><span data-stu-id="41b7c-168">**Category**: Currently, this setting isn't used (anything you enter is ignored).</span></span>

   - <span data-ttu-id="41b7c-169">**제목:** 전자 메일 메시지의 **제목** 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-169">**Subject**: The **Subject** field of the email message.</span></span>

   <span data-ttu-id="41b7c-170">작업을 마친 후 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-170">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="41b7c-171">전자 **메일 작성 단계에서** 전자 메일 메시지의 메시지 본문을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-171">In the **Compose email** step, create the message body of the email message.</span></span> <span data-ttu-id="41b7c-172">전자 메일  탭(다양한 HTML 편집기) 또는 원본  탭(원시 HTML 코드)을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-172">You can use the **Email** tab (a rich HTML editor) or the **Source** tab (raw HTML code).</span></span>

   <span data-ttu-id="41b7c-173">HTML 서식은 필요한만큼 간단하거나 복잡할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-173">The HTML formatting can be as simple or complex as you need it to be.</span></span> <span data-ttu-id="41b7c-174">이미지와 텍스트를 삽입하여 받는 사람의 전자 메일 클라이언트에서 메시지의 신원을 향상시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-174">You can insert images and text to enhance the believability of the message in the recipient's email client.</span></span>

   - <span data-ttu-id="41b7c-175">`${username}` 받는 사람의 이름을 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-175">`${username}` inserts the recipient's name.</span></span>

   - <span data-ttu-id="41b7c-176">`${loginserverurl}` 이전 단계의 **피싱 로그인** 서버 URL 값을 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-176">`${loginserverurl}` inserts the **Phishing Login Server URL** value from the previous step.</span></span>

   <span data-ttu-id="41b7c-177">작업을 마친 후 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-177">When you're finished, click **Next**.</span></span>

7. <span data-ttu-id="41b7c-178">확인 **단계에서** 마친 을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="41b7c-178">In the **Confirm** step, click **Finish**.</span></span>

#### <a name="step-2-create-and-launch-the-spear-phishing-campaign"></a><span data-ttu-id="41b7c-179">2단계: 스피어 피싱 캠페인 만들기 및 실행</span><span class="sxs-lookup"><span data-stu-id="41b7c-179">Step 2: Create and launch the spear phishing campaign</span></span>

1. <span data-ttu-id="41b7c-180">보안 및 & 센터에서 **위협** 관리 공격 \> **시뮬레이터로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="41b7c-180">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="41b7c-181">공격 **시뮬레이트 페이지에서** 만들 캠페인 유형에 따라 다음 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-181">On the **Simulate attacks** page, make one of the following selections based on the type of campaign you want to create:</span></span>

   - <span data-ttu-id="41b7c-182">스피어 **피싱(자격 증명 수집)** 섹션에서  공격 시작을 클릭하거나 공격 세부 정보 시작  \> **공격 을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="41b7c-182">In the **Spear Phishing (Credentials Harvest)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

   - <span data-ttu-id="41b7c-183">**스피어 피싱(첨부 파일)** 섹션에서  공격 시작을 클릭하거나 공격 **세부 정보 시작** 공격 \> **을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="41b7c-183">In the **Spear Phishing (Attachment)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

3. <span data-ttu-id="41b7c-184">피싱 **공격 구성 마법사가** 새 플라이아웃에서 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-184">The **Configure Phishing Attack** wizard starts in a new flyout.</span></span> <span data-ttu-id="41b7c-185">시작 **단계에서** 다음 단계 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-185">In the **Start** step, do one of the following steps:</span></span>

   - <span data-ttu-id="41b7c-186">이름 **상자에** 캠페인의 고유한 표시 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-186">In the **Name** box, enter a unique display name for the campaign.</span></span> <span data-ttu-id="41b7c-187">템플릿 사용을 **클릭하지** 않습니다. 나중에 마법사에서 전자 메일 메시지를 만들 수 있기 때문에 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-187">Don't click **Use Template**, because you'll create the email message later in the wizard.</span></span>

   - <span data-ttu-id="41b7c-188">서식 **파일 사용을** 클릭하고 기본 제공 또는 사용자 지정 전자 메일 서식 파일을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-188">Click **Use Template** and select a built-in or custom email template.</span></span> <span data-ttu-id="41b7c-189">템플릿을 선택하면 서식  파일을 기준으로 이름 상자가 자동으로 채워지지만 이름을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-189">After you select the template, the **Name** box is automatically filled based on the template, but you can change the name.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="41b7c-190">![피싱 시작 페이지](../../media/5e93b3cc-5981-462f-8b45-bdf85d97f1b8.jpg)</span><span class="sxs-lookup"><span data-stu-id="41b7c-190">![Phishing Start Page](../../media/5e93b3cc-5981-462f-8b45-bdf85d97f1b8.jpg)</span></span>

   <span data-ttu-id="41b7c-191">작업을 마친 후 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-191">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="41b7c-192">받는 **사람 대상 단계에서** 다음 단계 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-192">In the **Target recipients** step, do one of the following steps:</span></span>

   - <span data-ttu-id="41b7c-193">주소 **책을 클릭하여** 캠페인의 받는 사람(사용자 또는 그룹)을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-193">Click **Address Book** to select the recipients (users or groups) for the campaign.</span></span> <span data-ttu-id="41b7c-194">각 대상 받는 사람에게는 사서함이 Exchange Online 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-194">Each targeted recipient must have an Exchange Online mailbox.</span></span> <span data-ttu-id="41b7c-195">검색 조건을 **입력하지** 않고 필터 및 적용을 클릭하면 모든 받는 사람이 반환되어 캠페인에 추가됩니다. </span><span class="sxs-lookup"><span data-stu-id="41b7c-195">If you click **Filter** and **Apply** without entering a search criteria, all recipients are returned and added to the campaign.</span></span>

   - <span data-ttu-id="41b7c-196">**가져오기,** **파일 가져오기** 를 클릭하여 CSV(콤보로 구분된 값) 또는 줄로 구분된 전자 메일 주소 파일을 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-196">Click **Import** then **File Import** to import a comma-separated value (CSV) or line-separated file of email addresses.</span></span> <span data-ttu-id="41b7c-197">각 줄에는 받는 사람의 전자 메일 주소가 포함되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-197">Each line must contain the recipient's email address.</span></span>

   <span data-ttu-id="41b7c-198">작업을 마친 후 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-198">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="41b7c-199">전자 메일 **세부 정보 구성 단계에서** 다음 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-199">In the **Configure email details** step, configure the following settings:</span></span>

   <span data-ttu-id="41b7c-200">시작 단계에서 템플릿을  선택한 경우 이러한 값은 대부분 이미 구성되어 있지만 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-200">If you selected a template in the **Start** step, most of these values are already configured, but you can change them.</span></span>

   - <span data-ttu-id="41b7c-201">**보낸 사람(이름)**: 메시지 보낸 사람에 사용되는 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-201">**From (Name)**: The display name that's used for the message sender.</span></span>

   - <span data-ttu-id="41b7c-202">**보낸 사람(전자 메일)**: 보낸 사람 전자 메일 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-202">**From (Email)**: The sender's email address.</span></span> <span data-ttu-id="41b7c-203">조직의 전자 메일 도메인에서 실제 또는 가짜 전자 메일 주소를 입력하거나 실제 또는 가짜 외부 전자 메일 주소를 입력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-203">You can enter a real or fake email address from your organization's email domain, or you can enter a real or fake external email address.</span></span> <span data-ttu-id="41b7c-204">조직의 유효한 보낸 사람 전자 메일 주소는 받는 사람의 전자 메일 클라이언트에서 실제로 확인됩니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-204">A valid sender email address from your organization will actually resolve in the recipient's email client.</span></span>

   - <span data-ttu-id="41b7c-205">**피싱 로그인** 서버 URL: 드롭다운을 클릭하고 목록에서 사용 가능한 URL 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-205">**Phishing Login Server URL**: Click the drop down and select one of the available URLs from the list.</span></span> <span data-ttu-id="41b7c-206">사용자가 클릭할 수 있는 URL입니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-206">This is the URL that users will be tempted to click.</span></span> <span data-ttu-id="41b7c-207">선택은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-207">The choices are:</span></span>

     - <http://portal.docdeliveryapp.com>
     - <http://portal.docdeliveryapp.net>
     - <http://portal.docstoreinternal.com>
     - <http://portal.docstoreinternal.net>
     - <http://portal.hardwarecheck.net>
     - <http://portal.hrsupportint.com>
     - <http://portal.payrolltooling.com>
     - <http://portal.payrolltooling.net>
     - <http://portal.prizegiveaway.net>
     - <http://portal.prizesforall.com>
     - <http://portal.salarytoolint.com>
     - <http://portal.salarytoolint.net>

     > [!NOTE]
     >
     > - <span data-ttu-id="41b7c-208">모든 URL은 https가 아니라 의도적으로 http입니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-208">All of the URLs are intentionally http, not https.</span></span>
     >
     > - <span data-ttu-id="41b7c-209">URL 신뢰도 서비스는 이러한 URL 중 하나 이상을 안전하지 않은 것으로 식별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-209">A URL reputation service might identify one or more of these URLs as unsafe.</span></span> <span data-ttu-id="41b7c-210">피싱 캠페인에서 URL을 사용하기 전에 지원되는 웹 브라우저에서 URL의 가용성을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-210">Check the availability of the URL in your supported web browsers before you use the URL in a phishing campaign.</span></span>
     >
     > - <span data-ttu-id="41b7c-211">URL을 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-211">You are required to select a URL.</span></span> <span data-ttu-id="41b7c-212">**스피어 피싱(첨부 파일)** 캠페인의 경우 다음 단계에서 메시지 본문에서 링크를 제거할 수 있습니다. 그렇지 않으면  메시지에 링크와 첨부 파일이 모두 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-212">For **Spear Phishing (Attachment)** campaigns, you can remove the link from the body of the message in the next step (otherwise, the message will contain both a link **and** an attachment).</span></span>

   - <span data-ttu-id="41b7c-213">**첨부 파일 형식:** 이 설정은 **스피어 피싱(첨부 파일)** 캠페인에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-213">**Attachment Type**: This setting is only available in **Spear Phishing (Attachment)** campaigns.</span></span> <span data-ttu-id="41b7c-214">드롭다운을 클릭하고 **목록에서**.DOCX **.PDF** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-214">Click the drop down and select **.DOCX** or **.PDF** from the list.</span></span>

   - <span data-ttu-id="41b7c-215">**첨부 파일 이름:** 이 설정은 스피어 피싱(첨부 **파일)** 캠페인에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-215">**Attachment Name**: This setting is only available in **Spear Phishing (Attachment)** campaigns.</span></span> <span data-ttu-id="41b7c-216">첨부 파일 또는 첨부 파일의 파일 .docx .pdf 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-216">Enter a filename for the .docx or .pdf attachment.</span></span>

   - <span data-ttu-id="41b7c-217">사용자 지정 방문 페이지 **URL:** 피싱 링크를 클릭하고 자격 증명을 입력할 경우 사용자가 이동되는 선택적 방문 페이지를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-217">**Custom Landing Page URL**: Enter an optional landing page where users are taken if they click the phishing link and enter their credentials.</span></span> <span data-ttu-id="41b7c-218">이 링크는 기본 방문 페이지를 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-218">This link replaces the default landing page.</span></span> <span data-ttu-id="41b7c-219">예를 들어 내부 인식 교육이 있는 경우 여기에서 해당 URL을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-219">For example, if you have internal awareness training, you can specify that URL here.</span></span>

   - <span data-ttu-id="41b7c-220">**제목:** 전자 메일 메시지의 **제목** 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-220">**Subject**: The **Subject** field of the email message.</span></span>

   <span data-ttu-id="41b7c-221">작업을 마친 후 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-221">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="41b7c-222">전자 **메일 작성 단계에서** 전자 메일 메시지의 메시지 본문을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-222">In the **Compose email** step, create the message body of the email message.</span></span> <span data-ttu-id="41b7c-223">시작 단계에서 템플릿을  선택한 경우 메시지 본문이 이미 구성되어 있지만 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-223">If you selected a template in the **Start** step, the message body is already configured, but you can customize it.</span></span> <span data-ttu-id="41b7c-224">전자 메일  탭(다양한 HTML 편집기) 또는 원본  탭(원시 HTML 코드)을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-224">You can use the **Email** tab (a rich HTML editor) or the **Source** tab (raw HTML code).</span></span>

   <span data-ttu-id="41b7c-225">HTML 서식은 필요한만큼 간단하거나 복잡할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-225">The HTML formatting can be as simple or complex as you need it to be.</span></span> <span data-ttu-id="41b7c-226">이미지와 텍스트를 삽입하여 받는 사람의 전자 메일 클라이언트에서 메시지의 신원을 향상시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-226">You can insert images and text to enhance the believability of the message in the recipient's email client.</span></span>

   - <span data-ttu-id="41b7c-227">`${username}` 받는 사람의 이름을 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-227">`${username}` inserts the recipient's name.</span></span>

   - <span data-ttu-id="41b7c-228">`${loginserverurl}` 피싱 **로그인** 서버 URL 값을 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-228">`${loginserverurl}` inserts the **Phishing Login Server URL** value.</span></span>

   <span data-ttu-id="41b7c-229">**스피어 피싱(첨부 파일)** 캠페인의 경우 메시지 본문에서 링크를 제거해야 합니다. 그렇지 않으면  메시지에 링크와 첨부 파일이 모두 포함되어 있으며 첨부 파일 캠페인에서 링크 클릭이 추적되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-229">For **Spear Phishing (Attachment)** campaigns, you should remove the link from the body of the message (otherwise, the message will contain both a link **and** an attachment, and link clicks aren't tracked in an attachment campaign).</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="41b7c-230">![전자 메일 본문 작성](../../media/9bd65af4-1f9d-45c1-8c06-796d7ccfd425.jpg)</span><span class="sxs-lookup"><span data-stu-id="41b7c-230">![Compose Email Body](../../media/9bd65af4-1f9d-45c1-8c06-796d7ccfd425.jpg)</span></span>

   <span data-ttu-id="41b7c-231">작업을 마친 후 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-231">When you're finished, click **Next**.</span></span>

7. <span data-ttu-id="41b7c-232">확인 **단계에서** **마친을 클릭하여** 캠페인을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-232">In the **Confirm** step, click **Finish** to launch the campaign.</span></span> <span data-ttu-id="41b7c-233">피싱 메시지는 대상 받는 사람에게 배달됩니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-233">The phishing message is delivered to the targeted recipients.</span></span>

## <a name="password-attack-campaigns"></a><span data-ttu-id="41b7c-234">암호 공격 캠페인</span><span class="sxs-lookup"><span data-stu-id="41b7c-234">Password attack campaigns</span></span>

<span data-ttu-id="41b7c-235">암호 *공격은* 일반적으로 공격자가 하나 이상의 유효한 사용자 계정을 식별한 후 조직의 사용자 계정에 대한 암호를 추측합니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-235">A *password attack* tries to guess passwords for user accounts in an organization, typically after the attacker has identified one or more valid user accounts.</span></span>

<span data-ttu-id="41b7c-236">공격 시뮬레이터에서는 두 가지 유형의 암호 공격 캠페인을 사용하여 사용자의 암호의 복잡성을 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-236">In Attack Simulator, two different types of password attack campaigns are available for you to test the complexity of your users' passwords:</span></span>

- <span data-ttu-id="41b7c-237">**무차별** 암호 대시(사전 공격) :  무차별 암호 대시(사전 공격) : 무차별 암호 대시(brute *force)* 또는 사전 공격은 사용자 계정에서 암호의 큰 사전 파일을 사용하길 원합니다(한 계정에 대해 많은 암호).</span><span class="sxs-lookup"><span data-stu-id="41b7c-237">**Brute force password (dictionary attack)**: A *brute force* or *dictionary* attack uses a large dictionary file of passwords on a user account with the hope that one of them will work (many passwords against one account).</span></span> <span data-ttu-id="41b7c-238">잘못된 암호 잠금은 암호 무차별 암호 무차별 암호 공격을 억지하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-238">Incorrect password lock-outs help deter brute force password attacks.</span></span>

  <span data-ttu-id="41b7c-239">사전 공격의 경우 시도할 하나 또는 여러 암호를 지정할 수 있으며(수동으로 입력하거나 업로드된 파일에) 한 개 또는 여러 사용자를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-239">For the dictionary attack, you can specify one or many passwords to try (manually entered or in an uploaded file), and you can specify one or many users.</span></span>

- <span data-ttu-id="41b7c-240">**암호 분사 공격:** *암호* 분무 공격은 사용자 계정 목록(여러 계정에 대해 하나의 암호)에 대해 동일한 신중하게 고려된 암호를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-240">**Password spray attack**: A *password spray* attack uses the same carefully considered password against a list of user accounts (one password against many accounts).</span></span> <span data-ttu-id="41b7c-241">암호 분사 공격은 무차별 암호 대폭 공격보다 감지하기 더 어려워집니다(공격자가 사용자의 잘못된 암호 잠금을 겹치지 않고 수십 또는 수백 개의 계정에서 암호 하나를 사용하면 성공 확률이 증가함).</span><span class="sxs-lookup"><span data-stu-id="41b7c-241">Password spray attacks are harder to detect than brute force password attacks (the probability of success increases when an attacker tries one password across dozens or hundreds of accounts without the risk of tripping the user's incorrect password lock-out).</span></span>

  <span data-ttu-id="41b7c-242">암호 분사 공격의 경우 시도할 암호를 하나만 지정할 수 있으며 한 개 또는 여러 사용자를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-242">For the password spray attack, you can only specify one password to try, and you can specify one or many users.</span></span>

> [!NOTE]
> <span data-ttu-id="41b7c-243">공격 시뮬레이터의 암호 공격은 사용자 이름 및 암호 기본 인증 요청을 끝점에 전달하기 때문에 다른 인증 방법(AD FS, 암호 해시 동기화, 통과, PingFederate 등)도 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-243">The password attacks in Attack Simulator pass username and password Basic auth requests to an endpoint, so they also work with other authentication methods (AD FS, password hash sync, pass-through, PingFederate, etc.).</span></span> <span data-ttu-id="41b7c-244">MFA를 사용하도록 설정한 사용자의 경우 암호 공격이 실제 암호를 시도하는 경우에도 시도는 항상 실패로 등록됩니다(즉,  MFA 사용자는 캠페인의 성공 시도 횟수에 나타나지 않습니다).</span><span class="sxs-lookup"><span data-stu-id="41b7c-244">For users that have MFA enabled, even if the password attack tries their actual password, the attempt will always register as a failure (in other words, MFA users will never appear in the **Successful attempts** count of the campaign).</span></span> <span data-ttu-id="41b7c-245">이는 예상된 결과입니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-245">This is the expected result.</span></span> <span data-ttu-id="41b7c-246">MFA는 암호 공격으로부터 보호하는 주요 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-246">MFA is a primary method to help protect against password attacks.</span></span>

### <a name="create-and-launch-a-password-attack-campaign"></a><span data-ttu-id="41b7c-247">암호 공격 캠페인 만들기 및 시작</span><span class="sxs-lookup"><span data-stu-id="41b7c-247">Create and launch a password attack campaign</span></span>

1. <span data-ttu-id="41b7c-248">보안 및 & 센터에서 **위협** 관리 공격 \> **시뮬레이터로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="41b7c-248">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="41b7c-249">공격 **시뮬레이트 페이지에서** 만들 캠페인 유형에 따라 다음 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-249">On the **Simulate attacks** page, make one of the following selections based on the type of campaign you want to create:</span></span>

   - <span data-ttu-id="41b7c-250">Brute **Force Password (Dictionary Attack)**  섹션에서 공격  시작을 클릭하거나 공격 세부 정보 시작 \> **공격 을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="41b7c-250">In the **Brute Force Password (Dictionary Attack)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

   - <span data-ttu-id="41b7c-251">암호 **분무 공격 섹션에서** 공격 시작을 **클릭하거나** 공격 **세부 정보** 시작 \> **공격 을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="41b7c-251">in the **Password spray attack** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

3. <span data-ttu-id="41b7c-252">암호 **공격 구성** 마법사가 새 플라이아웃에서 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-252">The **Configure Password Attack** wizard starts in a new flyout.</span></span> <span data-ttu-id="41b7c-253">시작 **단계에서** 캠페인의 고유한 표시 이름을 입력하고 다음 을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="41b7c-253">In the **Start** step, enter a unique display name for the campaign, and then click **Next**.</span></span>

4. <span data-ttu-id="41b7c-254">대상 사용자 **단계에서** 다음 단계 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-254">In the **Target users** step, do one of the following steps:</span></span>

   - <span data-ttu-id="41b7c-255">주소 **책을 클릭하여** 캠페인의 받는 사람(사용자 또는 그룹)을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-255">Click **Address Book** to select the recipients (users or groups) for the campaign.</span></span> <span data-ttu-id="41b7c-256">각 대상 받는 사람에게는 사서함이 Exchange Online 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-256">Each targeted recipient must have an Exchange Online mailbox.</span></span> <span data-ttu-id="41b7c-257">검색 조건을 **입력하지** 않고 필터 및 적용을 클릭하면 모든 받는 사람이 반환되어 캠페인에 추가됩니다. </span><span class="sxs-lookup"><span data-stu-id="41b7c-257">If you click **Filter** and **Apply** without entering a search criteria, all recipients are returned and added to the campaign.</span></span>

   - <span data-ttu-id="41b7c-258">**가져오기,** **파일 가져오기** 를 클릭하여 CSV(콤보로 구분된 값) 또는 줄로 구분된 전자 메일 주소 파일을 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-258">Click **Import** then **File Import** to import a comma-separated value (CSV) or line-separated file of email addresses.</span></span> <span data-ttu-id="41b7c-259">각 줄에는 받는 사람의 전자 메일 주소가 포함되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-259">Each line must contain the recipient's email address.</span></span>

   <span data-ttu-id="41b7c-260">작업을 마친 후 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-260">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="41b7c-261">공격 **설정 선택 단계에서** 캠페인 유형에 따라 할 작업을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-261">In the **Choose attack settings** step, choose what to do based on the campaign type:</span></span>

   - <span data-ttu-id="41b7c-262">**Brute Force Password (Dictionary Attack)**: 다음 단계 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-262">**Brute Force Password (Dictionary Attack)**: Do either of the following steps:</span></span>

     - <span data-ttu-id="41b7c-263">**암호를 수동으로 입력:** Enter enter to add a password(암호를 추가하려면 **Enter를 누르기)** 상자에 암호를 입력한 다음 Enter(Enter)를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-263">**Enter passwords manually**: In the **Press enter to add a password** box, type a password and then press ENTER.</span></span> <span data-ttu-id="41b7c-264">필요한 만큼 이 단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-264">Repeat this step as many times as necessary.</span></span>

     - <span data-ttu-id="41b7c-265">**업로드** 파일에서 암호 저장: 업로드  줄마다 암호가 하나씩 포함된 기존 텍스트 파일을 가져오고 마지막 줄에는 빈 텍스트 파일을 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-265">**Upload passwords from a dictionary file**: Click **Upload** to import an existing text file that contains one password on each line and a blank last line.</span></span> <span data-ttu-id="41b7c-266">텍스트 파일은 10MB 이하의 크기와 30000개 이상의 암호를 포함할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-266">The text file must be 10 MB or less in size, and can't contain more than 30000 passwords.</span></span>

   - <span data-ttu-id="41b7c-267">**암호 분사 공격:** **공격** 상자에 사용할 암호 상자에 암호 하나를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-267">**Password spray attack**: In **The password(s) to use in the attack** box, enter one password.</span></span>

   <span data-ttu-id="41b7c-268">작업을 마친 후 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-268">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="41b7c-269">확인 **단계에서** **마친을 클릭하여** 캠페인을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-269">In the **Confirm** step, click **Finish** to launch the campaign.</span></span> <span data-ttu-id="41b7c-270">지정한 암호는 지정한 사용자에 대해 시도됩니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-270">The passwords you specified are tried on users you specified.</span></span>

## <a name="view-campaign-results"></a><span data-ttu-id="41b7c-271">캠페인 결과 보기</span><span class="sxs-lookup"><span data-stu-id="41b7c-271">View campaign results</span></span>

<span data-ttu-id="41b7c-272">캠페인을 시작한 후 주 공격 시뮬레이트 페이지에서 진행률 및 결과를 **확인할 수** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-272">After you launch a campaign, you can check the progress and results on the main **Simulate attacks** page.</span></span>

<span data-ttu-id="41b7c-273">활성 캠페인에는 상태 표시줄, 완료된 백분율 값 및 "(총 사용자)" 수가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-273">Active campaigns will show a status bar, a completed percentage value and "(completed users) of (total users)" count.</span></span> <span data-ttu-id="41b7c-274">새로 **고침 단추를** 클릭하면 활성 캠페인의 진행률이 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-274">Clicking the **Refresh** button will update the progress of any active campaigns.</span></span> <span data-ttu-id="41b7c-275">종료를 **클릭하여** 활성 캠페인을 중지할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-275">You can also click **Terminate** to stop an active campaign.</span></span>

<span data-ttu-id="41b7c-276">캠페인이 완료되면 상태가 공격 **완료로 변경됩니다.**</span><span class="sxs-lookup"><span data-stu-id="41b7c-276">When the campaign is finished, the status changes to **Attack completed**.</span></span> <span data-ttu-id="41b7c-277">다음 작업 중 하나를 수행하여 캠페인 결과를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-277">You can view the results of the campaign by doing either of the following actions:</span></span>

- <span data-ttu-id="41b7c-278">주 공격 **시뮬레이트** 페이지에서  캠페인 이름 아래의 보고서 보기를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-278">On the main **Simulate attacks** page, click **View Report** under the name of the campaign.</span></span>

- <span data-ttu-id="41b7c-279">기본 공격 **시뮬레이트** 페이지에서  공격 유형에 대한 섹션의 공격 세부 정보를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-279">On the main **Simulate attacks** page, click **Attack Details** in the section for the type of attack.</span></span> <span data-ttu-id="41b7c-280">공격 **세부 정보** 페이지가 열리면 공격 기록 섹션에서 **캠페인을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-280">On the **Attack details** page that opens, select the campaign in the **Attack History** section.</span></span>

<span data-ttu-id="41b7c-281">이전 작업 중 하나를 수행하면 공격 세부 정보 페이지로 **이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="41b7c-281">Either of the previous actions will take you to a page named **Attack details**.</span></span> <span data-ttu-id="41b7c-282">각 캠페인 유형에 대해 이 페이지에서 사용할 수 있는 정보는 다음 섹션에 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-282">The information that's available on this page for each type of campaign is described in the following sections.</span></span>

### <a name="spear-phishing-credentials-harvest-campaign-results"></a><span data-ttu-id="41b7c-283">스피어 피싱(자격 증명 수집) 캠페인 결과</span><span class="sxs-lookup"><span data-stu-id="41b7c-283">Spear Phishing (Credentials Harvest) campaign results</span></span>

<span data-ttu-id="41b7c-284">다음 정보는 각 캠페인의 **공격** 세부 정보 페이지에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-284">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="41b7c-285">캠페인의 기간(시작 날짜/시간 및 종료 날짜/시간)입니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-285">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="41b7c-286">**대상이 지정된 총 사용자 수**</span><span class="sxs-lookup"><span data-stu-id="41b7c-286">**Total users targeted**</span></span>

- <span data-ttu-id="41b7c-287">**시도** 성공 횟수: 링크를 클릭하고 자격  증명(사용자 이름 및 암호 값)을 입력한 사용자 수입니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-287">**Successful attempts**: The number of users who clicked the link **and** entered their credentials (*any* username and password value).</span></span>

- <span data-ttu-id="41b7c-288">**전체 성공률:** 성공한 시도에 의해 계산된 총 사용자  /  수입니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-288">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="41b7c-289">**가장 빠른 클릭:** 캠페인을 시작한 후 첫 번째 사용자가 링크를 클릭하는 데 걸렸다는 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-289">**Fastest Click**: How long it took the first user to click the link after you launched the campaign.</span></span>

- <span data-ttu-id="41b7c-290">**Average Click:** 모든 사용자가 링크를 클릭하는 데 걸려 있는 시간의 합계를 링크를 클릭한 사용자 수로 나눈 것입니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-290">**Average Click**: The sum of how long it took everyone to click the link divided by the number of users who clicked the link.</span></span>

- <span data-ttu-id="41b7c-291">**성공률**: (링크를 클릭한 사용자 수) / 대상이 인 총 사용자 수로 계산된 **백분율입니다.**</span><span class="sxs-lookup"><span data-stu-id="41b7c-291">**Click Success Rate**: A percentage that's calculated by (number of users who clicked the link) / **Total users targeted**.</span></span>

- <span data-ttu-id="41b7c-292">**가장 빠른 자격** 증명: 캠페인을 시작한 후 첫 번째 사용자가 자격 증명을 입력하는 데 걸려오는 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-292">**Fastest Credentials**: How long it took the first user to enter their credentials after you launched the campaign.</span></span>

- <span data-ttu-id="41b7c-293">**평균 자격 증명:** 모든 사용자가 자격 증명을 입력하는 데 걸려오는 시간의 합계를 자격 증명을 입력한 사용자 수로 나눈 것입니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-293">**Average Credentials**: The sum of how long it took everyone to enter their credentials divided by the number of users who entered their credentials.</span></span>

- <span data-ttu-id="41b7c-294">**자격 증명 성공률:**(자격 증명을 입력한 사용자 수) / 대상을 지정한 총 사용자 수로 계산되는 **백분율입니다.**</span><span class="sxs-lookup"><span data-stu-id="41b7c-294">**Credential Success Rate**: A percentage that's calculated by (number of users who entered their credentials) / **Total users targeted**.</span></span>

- <span data-ttu-id="41b7c-295">하루당 링크 클릭  및 자격 증명 제공 번호를 **표시하는 막대** 그래프입니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-295">A bar graph that shows the **Link clicked** and **Credential supplied** numbers per day.</span></span>

- <span data-ttu-id="41b7c-296">링크 클릭, 자격 증명 제공 및 캠페인에 대한 없음 백분율을 표시하는 원 그래프입니다. </span><span class="sxs-lookup"><span data-stu-id="41b7c-296">A circle graph that shows the **Link clicked**, **Credential supplied**, and **None** percentages for the campaign.</span></span>

- <span data-ttu-id="41b7c-297">손상된 **사용자 섹션에는** 링크를 클릭한 사용자의 세부 정보가 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-297">The **Compromised Users** section lists the details of the users who clicked the link:</span></span>

  - <span data-ttu-id="41b7c-298">사용자의 전자 메일 주소</span><span class="sxs-lookup"><span data-stu-id="41b7c-298">The user's email address</span></span>

  - <span data-ttu-id="41b7c-299">링크를 클릭한 날짜/시간입니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-299">The date/time when they clicked the link.</span></span>

  - <span data-ttu-id="41b7c-300">클라이언트 IP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-300">The client IP address.</span></span>

  - <span data-ttu-id="41b7c-301">사용자 버전 및 웹 브라우저에 Windows 세부 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-301">Details about the user's version of Windows and web browser.</span></span>

  <span data-ttu-id="41b7c-302">내보내기 **를 클릭하여** 결과를 CSV 파일로 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-302">You can click **Export** to export the results to a CSV file.</span></span>

### <a name="spear-phishing-attachment-campaign-results"></a><span data-ttu-id="41b7c-303">스피어 피싱(첨부 파일) 캠페인 결과</span><span class="sxs-lookup"><span data-stu-id="41b7c-303">Spear Phishing (Attachment) campaign results</span></span>

<span data-ttu-id="41b7c-304">다음 정보는 각 캠페인의 **공격** 세부 정보 페이지에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-304">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="41b7c-305">캠페인의 기간(시작 날짜/시간 및 종료 날짜/시간)입니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-305">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="41b7c-306">**대상이 지정된 총 사용자 수**</span><span class="sxs-lookup"><span data-stu-id="41b7c-306">**Total users targeted**</span></span>

- <span data-ttu-id="41b7c-307">**성공 횟수:** 첨부 파일을 열거나 다운로드하고 연 사용자 수(미리 보기는 계산되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-307">**Successful attempts**: The number of users who opened or downloaded and opened the attachment (preview doesn't count).</span></span>

- <span data-ttu-id="41b7c-308">**전체 성공률:** 성공한 시도에 의해 계산된 총 사용자  /  수입니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-308">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="41b7c-309">가장 빠른 첨부 **파일 열기 시간:** 캠페인을 시작한 후 첫 번째 사용자가 첨부 파일을 여는 데 걸려오는 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-309">**Fastest attachment open time**: How long it took the first user to open the attachment after you launched the campaign.</span></span>

- <span data-ttu-id="41b7c-310">**평균 첨부 파일 열기** 시간: 모든 사용자가 첨부 파일을 여는 데 걸려오는 시간을 첨부 파일을 연 사용자 수로 나눈 합계입니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-310">**Average attachment open time**: The sum of how long it took everyone to open the attachment divided by the number of users who opened the attachment.</span></span>

- <span data-ttu-id="41b7c-311">**첨부 파일 열기** 성공률 : (첨부 파일을 연 사용자 수) / 대상이 인 총 사용자 수로 계산되는 **백분율입니다.**</span><span class="sxs-lookup"><span data-stu-id="41b7c-311">**Attachment open success rate**: A percentage that's calculated by (number of users who opened the attachment) / **Total users targeted**.</span></span>

### <a name="brute-force-password-dictionary-attack-campaign-results"></a><span data-ttu-id="41b7c-312">무차별 암호 강제(사전 공격) 캠페인 결과</span><span class="sxs-lookup"><span data-stu-id="41b7c-312">Brute Force Password (Dictionary Attack) campaign results</span></span>

<span data-ttu-id="41b7c-313">다음 정보는 각 캠페인의 **공격** 세부 정보 페이지에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-313">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="41b7c-314">캠페인의 기간(시작 날짜/시간 및 종료 날짜/시간)입니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-314">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="41b7c-315">**대상이 지정된 총 사용자 수**</span><span class="sxs-lookup"><span data-stu-id="41b7c-315">**Total users targeted**</span></span>

- <span data-ttu-id="41b7c-316">**성공 횟수:** 지정된 암호 중 하나를 사용하는 것으로 확인된 사용자 수입니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-316">**Successful attempts**: The number of users who were found to be using one of the specified passwords.</span></span>

- <span data-ttu-id="41b7c-317">**전체 성공률:** 성공한 시도에 의해 계산된 총 사용자  /  수입니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-317">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="41b7c-318">손상된 **사용자 섹션에는** 영향을 받는 사용자의 전자 메일 주소가 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-318">The **Compromised Users** section lists the email addresses of the affected users.</span></span> <span data-ttu-id="41b7c-319">내보내기 **를 클릭하여** 결과를 CSV 파일로 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-319">You can click **Export** to export the results to a CSV file.</span></span>

### <a name="password-spray-attack-campaign-results"></a><span data-ttu-id="41b7c-320">암호 분무 공격 캠페인 결과</span><span class="sxs-lookup"><span data-stu-id="41b7c-320">Password spray attack campaign results</span></span>

<span data-ttu-id="41b7c-321">다음 정보는 각 캠페인의 **공격** 세부 정보 페이지에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-321">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="41b7c-322">캠페인의 기간(시작 날짜/시간 및 종료 날짜/시간)입니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-322">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="41b7c-323">**대상이 지정된 총 사용자 수**</span><span class="sxs-lookup"><span data-stu-id="41b7c-323">**Total users targeted**</span></span>

- <span data-ttu-id="41b7c-324">**시도 성공:** 지정된 암호를 사용하는 것으로 확인된 사용자 수입니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-324">**Successful attempts**: The number of users who were found to be using the specified password.</span></span>

- <span data-ttu-id="41b7c-325">**전체 성공률:** 성공한 시도에 의해 계산된 총 사용자  /  수입니다.</span><span class="sxs-lookup"><span data-stu-id="41b7c-325">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>
