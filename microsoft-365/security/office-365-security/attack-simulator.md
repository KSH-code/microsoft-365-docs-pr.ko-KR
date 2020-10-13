---
title: ATP의 공격 시뮬레이터
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
description: 관리자는 Attack 시뮬레이터를 사용 하 여 Microsoft 365 E5 또는 ATP 계획 2 조 직에서 시뮬레이트된 피싱 및 암호 공격을 실행 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: 2c837df1abc344186168c88ce0db94dd9d1d2b4a
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/13/2020
ms.locfileid: "48430790"
---
# <a name="attack-simulator-in-atp"></a><span data-ttu-id="1c9a6-103">ATP의 공격 시뮬레이터</span><span class="sxs-lookup"><span data-stu-id="1c9a6-103">Attack Simulator in ATP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="1c9a6-104">조직에 [위협 조사 및 응답 기능이](office-365-ti.md)포함 된 Office 365 Advanced Threat PROTECTION (ATP) 계획 2가 있는 경우 보안 & 준수 센터에서 공격 시뮬레이터를 사용 하 여 조직에서 현실적인 공격 시나리오를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-104">If your organization has Office 365 Advanced Threat Protection (ATP) Plan 2, which includes [Threat Investigation and Response capabilities](office-365-ti.md), you can use Attack Simulator in the Security & Compliance Center to run realistic attack scenarios in your organization.</span></span> <span data-ttu-id="1c9a6-105">이러한 시뮬레이트된 공격은 실질적인 공격이 아래 줄에 영향을 미치는 사용자를 식별 하 고 찾는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-105">These simulated attacks can help you identify and find vulnerable users before a real attack impacts your bottom line.</span></span> <span data-ttu-id="1c9a6-106">자세한 내용은이 문서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-106">Read this article to learn more.</span></span>

> [!NOTE]
> <span data-ttu-id="1c9a6-107">공격 시뮬레이션 및 교육 관련 데이터는 Microsoft 365 서비스용 다른 고객 데이터와 함께 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-107">Attack simulation and training related data is stored with other customer data for Microsoft 365 services.</span></span> <span data-ttu-id="1c9a6-108">자세한 내용은 [Microsoft 365 데이터 위치](/microsoft-365/enterprise/o365-data-locations)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-108">For more information see [Microsoft 365 data locations](/microsoft-365/enterprise/o365-data-locations).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="1c9a6-109">시작하기 전에 알아야 할 사항은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="1c9a6-109">What do you need to know before you begin?</span></span>

- <span data-ttu-id="1c9a6-110">보안 및 준수 센터를 열려면 <https://protection.office.com/>로 이동하세요.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-110">To open the Security & Compliance Center, go to <https://protection.office.com/>.</span></span> <span data-ttu-id="1c9a6-111">Attack 시뮬레이터는 **위협 관리** \> **공격 시뮬레이터**에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-111">Attack simulator is available at **Threat management** \> **Attack simulator**.</span></span> <span data-ttu-id="1c9a6-112">공격 시뮬레이터로 직접 이동 하 여 엽니다 <https://protection.office.com/attacksimulator> .</span><span class="sxs-lookup"><span data-stu-id="1c9a6-112">Go go directly to attack simulator, open <https://protection.office.com/attacksimulator>.</span></span>

- <span data-ttu-id="1c9a6-113">서로 다른 Microsoft 365 구독에서 공격 시뮬레이터를 사용할 경우의 가용성에 대 한 자세한 내용은 [Office 365 Advanced Threat Protection 서비스 설명을](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-113">For more information about the availability of Attack Simulator across different Microsoft 365 subscriptions, see [Office 365 Advanced Threat Protection service description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>

- <span data-ttu-id="1c9a6-114">**조직 관리** 또는 **보안 관리자** 역할 그룹의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-114">You need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="1c9a6-115">보안 및 규정 준수 센터의 역할 그룹에 대한 자세한 내용은 [보안 및 규정 준수 센터의 사용 권한](permissions-in-the-security-and-compliance-center.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-115">For more information about role groups in the Security & Compliance Center, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="1c9a6-116">MFA (multi-factor authentication)를 사용 하 여 공격 시뮬레이터에서 캠페인을 만들고 관리 하도록 계정을 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-116">Your account needs to be configured for multi-factor authentication (MFA) to create and manage campaigns in Attack Simulator.</span></span> <span data-ttu-id="1c9a6-117">자세한 내용은 [다단계 인증 설정을](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/set-up-multi-factor-authentication)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-117">For instructions, see [Set up multi-factor authentication](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/set-up-multi-factor-authentication).</span></span>

- <span data-ttu-id="1c9a6-118">피싱 캠페인은 30 일 동안 이벤트를 수집 하 고 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-118">Phishing campaigns will collect and process events for 30 days.</span></span> <span data-ttu-id="1c9a6-119">캠페인을 시작한 후 최대 90 일 동안 역사적 캠페인 데이터를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-119">Historical campaign data will be available for up to 90 days after you launch the campaign.</span></span>

- <span data-ttu-id="1c9a6-120">Attack 시뮬레이터에 해당 하는 PowerShell cmdlet이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-120">There are no corresponding PowerShell cmdlets for Attack Simulator.</span></span>

## <a name="spear-phishing-campaigns"></a><span data-ttu-id="1c9a6-121">스피어 피싱 캠페인</span><span class="sxs-lookup"><span data-stu-id="1c9a6-121">Spear phishing campaigns</span></span>

<span data-ttu-id="1c9a6-122">*피싱은* 적법 하거나 신뢰할 수 있는 보낸 사람 으로부터 온 것 처럼 보이는 메시지의 중요 한 정보를 도용 하는 전자 메일 공격에 대 한 일반 용어입니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-122">*Phishing* is a generic term for email attacks that try to steal sensitive information in messages that appear to be from legitimate or trusted senders.</span></span> <span data-ttu-id="1c9a6-123">*스피어 피싱은* 대상 지정 된 받는 사람에 따라 특별히 조정 된 중요 한 콘텐츠 (일반적으로 공격자가 받는 사람을 검사 한 후)를 사용 하는 대상 피싱 공격입니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-123">*Spear phishing* is a targeted phishing attack that uses focused and customized content that's specifically tailored to the targeted recipients (typically, after reconnaissance on the recipients by the attacker).</span></span>

<span data-ttu-id="1c9a6-124">Attack 시뮬레이터에서는 다음과 같은 두 가지 유형의 스피어 피싱 캠페인을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-124">In Attack Simulator, two different types of spear phishing campaigns are available:</span></span>

- <span data-ttu-id="1c9a6-125">**스피어 피싱 (자격 증명 수집)**:이 공격은 수신자에 게 메시지의 URL을 클릭 하도록 유도 하려고 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-125">**Spear phishing (credentials harvest)**: The attack tries to convince the recipients to click a URL in the message.</span></span> <span data-ttu-id="1c9a6-126">링크를 클릭 하면 해당 사용자에 게 자격 증명을 입력 하 라는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-126">If they click the link, they're asked to enter their credentials.</span></span> <span data-ttu-id="1c9a6-127">이러한 경우에는 다음 위치 중 하나로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-127">If they do, they're taken to one of the following locations:</span></span>

  - <span data-ttu-id="1c9a6-128">이것이 테스트 일 뿐 이며 피싱 메시지를 인식 하기 위한 팁을 제공 하는 기본 페이지입니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-128">A default page that explains that this was a just a test, and gives tips for recognizing phishing messages.</span></span>

    ![피싱 링크를 클릭 하 고 해당 자격 증명을 입력 하면 사용자에 게 표시 되는 항목](../../media/attack-simulator-phishing-result.png)

  - <span data-ttu-id="1c9a6-130">지정 하는 사용자 지정 페이지 (URL)입니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-130">A custom page (URL) that you specify.</span></span>

- <span data-ttu-id="1c9a6-131">**스피어 피싱 (첨부 파일)**:이 공격은 받는 사람이 메시지에 있는 .docx 또는 .pdf 첨부 파일을 열도록 유도 하려고 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-131">**Spear phishing (attachment)**: The attack tries to convince the recipients to open a .docx or .pdf attachment in the message.</span></span> <span data-ttu-id="1c9a6-132">첨부 파일에는 기본 피싱 링크와 동일한 콘텐츠가 포함 되어 있지만 첫 문장이 "라는 \<Display Name\> 최근 전자 메일 메시지로 표시 됩니다."로 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-132">The attachment contains the same content from the default phishing link, but the first sentence starts with "\<Display Name\>, you are seeing this message as a recent email message you opened...".</span></span>

> [!NOTE]
> <span data-ttu-id="1c9a6-133">현재 공격 시뮬레이터의 스피어 피싱 캠페인은 만료 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-133">Currently, spear phishing campaigns in Attack Simulator don't expire.</span></span>

### <a name="create-a-spear-phishing-campaign"></a><span data-ttu-id="1c9a6-134">스피어 피싱 캠페인 만들기</span><span class="sxs-lookup"><span data-stu-id="1c9a6-134">Create a spear phishing campaign</span></span>

<span data-ttu-id="1c9a6-135">모든 스피어 피싱 캠페인의 중요 한 부분은 대상으로 지정 된 받는 사람에 게 전송 되는 전자 메일 메시지의 모양과 느낌입니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-135">An important part of any spear phishing campaign is the look and feel of the email message that's sent to the targeted recipients.</span></span> <span data-ttu-id="1c9a6-136">전자 메일 메시지를 만들고 구성 하려면 다음 옵션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-136">To create and configure the email message, you have these options:</span></span>

- <span data-ttu-id="1c9a6-137">**기본 제공 전자 메일 서식 파일 사용**: **Giveaway** 및 **급여 업데이트**라는 두 가지 기본 제공 서식 파일을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-137">**Use a built-in email template**: Two built-in templates are available: **Prize Giveaway** and **Payroll Update**.</span></span> <span data-ttu-id="1c9a6-138">캠페인을 만들고 시작할 때 서식 파일에서 전자 메일 속성의 일부, 전체 또는 일부를 추가로 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-138">You can further customize some, all, or none of the email properties from the template when you create and launch the campaign.</span></span>

- <span data-ttu-id="1c9a6-139">**재사용 가능한 전자 메일 서식 파일 만들기**: 전자 메일 템플릿을 만들고 저장 한 후 나중에 스피어 피싱 캠페인에서 다시 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-139">**Create a reusable email template**: After you create and save the email template, you can use it again in future spear phishing campaigns.</span></span> <span data-ttu-id="1c9a6-140">캠페인을 만들고 시작할 때 서식 파일에서 전자 메일 속성의 일부, 전체 또는 일부를 추가로 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-140">You can further customize some, all, or none of the email properties from the template when you create and launch the campaign.</span></span>

- <span data-ttu-id="1c9a6-141">**마법사에서 전자 메일 메시지 만들기**: 스피어 피싱 캠페인을 만들고 시작할 때 마법사에서 직접 전자 메일 메시지를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-141">**Create the email message in the wizard**: You can create the email message directly in the wizard as you create and launch the spear phishing campaign.</span></span>

#### <a name="step-1-optional-create-a-custom-email-template"></a><span data-ttu-id="1c9a6-142">1 단계 (선택 사항): 사용자 지정 전자 메일 서식 파일 만들기</span><span class="sxs-lookup"><span data-stu-id="1c9a6-142">Step 1 (Optional): Create a custom email template</span></span>

<span data-ttu-id="1c9a6-143">기본 제공 서식 파일 중 하나를 사용 하거나 마법사에서 직접 전자 메일 메시지를 만들려는 경우이 단계를 건너뛸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-143">If you're going to use one of the built-in templates or create the email message directly in the wizard, you can skip this step.</span></span>

1. <span data-ttu-id="1c9a6-144">보안 & 준수 센터에서 **위협 관리** \> **공격 시뮬레이터**로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-144">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="1c9a6-145">**공격 시뮬레이션** 페이지의 **스피어 피싱 (자격 증명 수집)** 또는 **스피어 피싱 (첨부 파일)** 섹션에서 **공격 세부 정보**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-145">On the **Simulate attacks** page, in either the **Spear Phishing (Credentials Harvest)** or **Spear Phishing (Attachment)** sections, click **Attack Details**.</span></span>

   <span data-ttu-id="1c9a6-146">서식 파일을 만드는 위치는 중요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-146">It doesn't matter where you create the template.</span></span> <span data-ttu-id="1c9a6-147">서식 파일에서 사용할 수 있는 옵션은 두 가지 유형의 피싱 공격 모두에서 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-147">The available options in the template are the same for both types of phishing attacks.</span></span>

3. <span data-ttu-id="1c9a6-148">**공격 세부 정보** 페이지가 열리면 **피싱 템플릿** 섹션의 **서식 파일 만들기** 영역에서 **새 서식 파일**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-148">In the **Attack details** page that opens, in the **Phishing Templates** section, in the **Create Templates** area, click **New Template**.</span></span>

4. <span data-ttu-id="1c9a6-149">**피싱 서식 파일 구성** 마법사가 새 플라이 아웃에서 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-149">The **Configure Phishing Template** wizard starts in a new flyout.</span></span> <span data-ttu-id="1c9a6-150">**시작** 단계에 서식 파일의 고유한 표시 이름을 입력 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-150">In the **Start** step, enter a unique display name for the template, and then click **Next**.</span></span>

5. <span data-ttu-id="1c9a6-151">**전자 메일 세부 정보 구성** 단계에서 다음 설정을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-151">In the **Configure email details** step, configure the following settings:</span></span>

   - <span data-ttu-id="1c9a6-152">**From (이름)**: 메시지 보낸 사람에 게 사용 되는 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-152">**From (Name)**: The display name that's used for the message sender.</span></span>

   - <span data-ttu-id="1c9a6-153">보낸 사람 **(전자 메일)**: 보낸 사람의 전자 메일 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-153">**From (Email)**: The sender's email address.</span></span>

   - <span data-ttu-id="1c9a6-154">**피싱 로그인 서버 URL**: 드롭다운을 클릭 하 고 목록에서 사용 가능한 url 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-154">**Phishing Login Server URL**: Click the drop down and select one of the available URLs from the list.</span></span> <span data-ttu-id="1c9a6-155">사용자가 클릭 하려고 하는 URL입니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-155">This is the URL that users will be tempted to click.</span></span> <span data-ttu-id="1c9a6-156">선택은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-156">The choices are:</span></span>

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
     > - <span data-ttu-id="1c9a6-157">모든 Url은 https가 아닌 고의로 http입니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-157">All of the URLs are intentionally http, not https.</span></span>
     >
     > - <span data-ttu-id="1c9a6-158">URL 신뢰도 서비스가 이러한 Url 중 하나 이상을 안전 하지 않은 것으로 식별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-158">A URL reputation service might identify one or more of these URLs as unsafe.</span></span> <span data-ttu-id="1c9a6-159">피싱 캠페인에서 URL을 사용 하기 전에 지원 되는 웹 브라우저에서 URL의 가용성을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-159">Check the availability of the URL in your supported web browsers before you use the URL in a phishing campaign.</span></span>

   - <span data-ttu-id="1c9a6-160">**사용자 지정 랜딩 페이지 URL**: 사용자가 피싱 링크를 클릭 하 고 해당 자격 증명을 입력할 수 있는 선택적 랜딩 페이지를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-160">**Custom Landing Page URL**: Enter an optional landing page where users are taken if they click the phishing link and enter their credentials.</span></span> <span data-ttu-id="1c9a6-161">이 링크는 기본 랜딩 페이지를 대체 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-161">This link replaces the default landing page.</span></span> <span data-ttu-id="1c9a6-162">예를 들어 내부 인식 교육이 있는 경우 여기에서 해당 URL을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-162">For example, if you have internal awareness training, you can specify that URL here.</span></span>

   - <span data-ttu-id="1c9a6-163">**범주**: 현재이 설정은 사용 되지 않습니다 (입력 한 내용은 무시 됨).</span><span class="sxs-lookup"><span data-stu-id="1c9a6-163">**Category**: Currently, this setting isn't used (anything you enter is ignored).</span></span>

   - <span data-ttu-id="1c9a6-164">**제목**: 전자 메일 메시지의 **제목** 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-164">**Subject**: The **Subject** field of the email message.</span></span>

   <span data-ttu-id="1c9a6-165">작업을 마친 후 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-165">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="1c9a6-166">**전자 메일 작성** 단계에서 전자 메일 메시지의 메시지 본문을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-166">In the **Compose email** step, create the message body of the email message.</span></span> <span data-ttu-id="1c9a6-167">**전자 메일** 탭 (리치 html 편집기) 또는 **원본** 탭 (원시 HTML 코드)을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-167">You can use the **Email** tab (a rich HTML editor) or the **Source** tab (raw HTML code).</span></span>

   <span data-ttu-id="1c9a6-168">HTML 서식 지정은 필요한 경우에는 단순 하거나 복잡할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-168">The HTML formatting can be as simple or complex as you need it to be.</span></span> <span data-ttu-id="1c9a6-169">이미지와 텍스트를 삽입 하 여 받는 사람의 전자 메일 클라이언트에서 메시지의 believability을 향상 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-169">You can insert images and text to enhance the believability of the message in the recipient's email client.</span></span>

   - <span data-ttu-id="1c9a6-170">`${username}` 받는 사람의 이름을 삽입 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-170">`${username}` inserts the recipient's name.</span></span>

   - <span data-ttu-id="1c9a6-171">`${loginserverurl}` 이전 단계의 **피싱 로그인 서버 URL** 값을 삽입 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-171">`${loginserverurl}` inserts the **Phishing Login Server URL** value from the previous step.</span></span>

   <span data-ttu-id="1c9a6-172">작업을 마친 후 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-172">When you're finished, click **Next**.</span></span>

7. <span data-ttu-id="1c9a6-173">**확인** 단계에서 **마침을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-173">In the **Confirm** step, click **Finish**.</span></span>

#### <a name="step-2-create-and-launch-the-spear-phishing-campaign"></a><span data-ttu-id="1c9a6-174">2 단계: 스피어 피싱 캠페인 만들기 및 시작</span><span class="sxs-lookup"><span data-stu-id="1c9a6-174">Step 2: Create and launch the spear phishing campaign</span></span>

1. <span data-ttu-id="1c9a6-175">보안 & 준수 센터에서 **위협 관리** \> **공격 시뮬레이터**로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-175">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="1c9a6-176">**공격 시뮬레이션** 페이지에서 만들려는 캠페인 유형에 따라 다음 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-176">On the **Simulate attacks** page, make one of the following selections based on the type of campaign you want to create:</span></span>

   - <span data-ttu-id="1c9a6-177">**스피어 피싱 (자격 증명 수집)** 섹션에서 **공격 시작** 을 클릭 하거나 **공격 정보** \> **시작 공격**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-177">In the **Spear Phishing (Credentials Harvest)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

   - <span data-ttu-id="1c9a6-178">**스피어 피싱 (첨부 파일)** 섹션에서 **공격 시작** 을 클릭 하거나 **공격 정보** \> **시작 공격**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-178">In the **Spear Phishing (Attachment)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

3. <span data-ttu-id="1c9a6-179">**피싱 공격 구성** 마법사가 새 플라이 아웃으로 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-179">The **Configure Phishing Attack** wizard starts in a new flyout.</span></span> <span data-ttu-id="1c9a6-180">**시작** 단계에서 다음 단계 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-180">In the **Start** step, do one of the following steps:</span></span>

   - <span data-ttu-id="1c9a6-181">**이름** 상자에 캠페인의 고유한 표시 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-181">In the **Name** box, enter a unique display name for the campaign.</span></span> <span data-ttu-id="1c9a6-182">마법사에서 나중에 전자 메일 메시지를 만들기 때문에 **서식 파일 사용**을 클릭 하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-182">Don't click **Use Template**, because you'll create the email message later in the wizard.</span></span>

   - <span data-ttu-id="1c9a6-183">**서식 파일 사용** 을 클릭 하 고 기본 제공 또는 사용자 지정 전자 메일 서식 파일을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-183">Click **Use Template** and select a built-in or custom email template.</span></span> <span data-ttu-id="1c9a6-184">서식 파일을 선택한 후에는 **이름** 상자에 서식 파일이 자동으로 입력 되지만 이름을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-184">After you select the template, the **Name** box is automatically filled based on the template, but you can change the name.</span></span>

   ![피싱 시작 페이지](../../media/5e93b3cc-5981-462f-8b45-bdf85d97f1b8.jpg)

   <span data-ttu-id="1c9a6-186">작업을 마친 후 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-186">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="1c9a6-187">**대상 받는 사람** 단계에서 다음 단계 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-187">In the **Target recipients** step, do one of the following steps:</span></span>

   - <span data-ttu-id="1c9a6-188">**주소록** 을 클릭 하 여 캠페인에 대 한 받는 사람 (사용자 또는 그룹)을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-188">Click **Address Book** to select the recipients (users or groups) for the campaign.</span></span> <span data-ttu-id="1c9a6-189">각각의 대상 지정 받는 사람에 게 Exchange Online 사서함이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-189">Each targeted recipient must have an Exchange Online mailbox.</span></span> <span data-ttu-id="1c9a6-190">검색 조건을 입력 하지 않고 **필터** 및 **적용** 을 클릭 하면 모든 받는 사람이 반환 되 고 캠페인에 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-190">If you click **Filter** and **Apply** without entering a search criteria, all recipients are returned and added to the campaign.</span></span>

   - <span data-ttu-id="1c9a6-191">**파일** 가져오기를 클릭 하 여 CSV (쉼표로 구분 된 값) 또는 전자 메일 주소에 대 한 행 구분 파일 **을 가져옵니다.**</span><span class="sxs-lookup"><span data-stu-id="1c9a6-191">Click **Import** then **File Import** to import a comma-separated value (CSV) or line-separated file of email addresses.</span></span> <span data-ttu-id="1c9a6-192">각 줄에는 받는 사람의 전자 메일 주소가 포함 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-192">Each line must contain the recipient's email address.</span></span>

   <span data-ttu-id="1c9a6-193">작업을 마친 후 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-193">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="1c9a6-194">**전자 메일 세부 정보 구성** 단계에서 다음 설정을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-194">In the **Configure email details** step, configure the following settings:</span></span>

   <span data-ttu-id="1c9a6-195">**시작** 단계에서 템플릿을 선택한 경우 이러한 값의 대부분은 이미 구성 되어 있지만 변경할 수는 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-195">If you selected a template in the **Start** step, most of these values are already configured, but you can change them.</span></span>

   - <span data-ttu-id="1c9a6-196">**From (이름)**: 메시지 보낸 사람에 게 사용 되는 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-196">**From (Name)**: The display name that's used for the message sender.</span></span>

   - <span data-ttu-id="1c9a6-197">보낸 사람 **(전자 메일)**: 보낸 사람의 전자 메일 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-197">**From (Email)**: The sender's email address.</span></span> <span data-ttu-id="1c9a6-198">조직의 전자 메일 도메인에서 실제 또는 가짜 전자 메일 주소를 입력 하거나, 실제 또는 가짜 외부 전자 메일 주소를 입력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-198">You can enter a real or fake email address from your organization's email domain, or you can enter a real or fake external email address.</span></span> <span data-ttu-id="1c9a6-199">조직의 유효한 보낸 사람 전자 메일 주소가 실제로 받는 사람의 전자 메일 클라이언트에서 확인 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-199">A valid sender email address from your organization will actually resolve in the recipient's email client.</span></span>

   - <span data-ttu-id="1c9a6-200">**피싱 로그인 서버 URL**: 드롭다운을 클릭 하 고 목록에서 사용 가능한 url 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-200">**Phishing Login Server URL**: Click the drop down and select one of the available URLs from the list.</span></span> <span data-ttu-id="1c9a6-201">사용자가 클릭 하려고 하는 URL입니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-201">This is the URL that users will be tempted to click.</span></span> <span data-ttu-id="1c9a6-202">선택은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-202">The choices are:</span></span>

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
     > - <span data-ttu-id="1c9a6-203">모든 Url은 https가 아닌 고의로 http입니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-203">All of the URLs are intentionally http, not https.</span></span>
     >
     > - <span data-ttu-id="1c9a6-204">URL 신뢰도 서비스가 이러한 Url 중 하나 이상을 안전 하지 않은 것으로 식별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-204">A URL reputation service might identify one or more of these URLs as unsafe.</span></span> <span data-ttu-id="1c9a6-205">피싱 캠페인에서 URL을 사용 하기 전에 지원 되는 웹 브라우저에서 URL의 가용성을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-205">Check the availability of the URL in your supported web browsers before you use the URL in a phishing campaign.</span></span>
     >
     > - <span data-ttu-id="1c9a6-206">URL을 선택 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-206">You are required to select a URL.</span></span> <span data-ttu-id="1c9a6-207">**스피어 피싱 (첨부 파일)** 캠페인의 경우 다음 단계에서 메시지 본문의 링크를 제거할 수 있습니다 (그렇지 않으면 메시지에 링크 **와** 첨부 파일이 모두 포함 됨).</span><span class="sxs-lookup"><span data-stu-id="1c9a6-207">For **Spear Phishing (Attachment)** campaigns, you can remove the link from the body of the message in the next step (otherwise, the message will contain both a link **and** an attachment).</span></span>

   - <span data-ttu-id="1c9a6-208">**첨부 파일 형식**:이 설정은 **스피어 피싱 (첨부 파일)** 캠페인 에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-208">**Attachment Type**: This setting is only available in **Spear Phishing (Attachment)** campaigns.</span></span> <span data-ttu-id="1c9a6-209">드롭다운을 클릭 하 고를 선택 **합니다. .DOCX** 또는 \*\*. \*\* 목록에서 PDF를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-209">Click the drop down and select **.DOCX** or **.PDF** from the list.</span></span>

   - <span data-ttu-id="1c9a6-210">**첨부 파일 이름**:이 설정은 **스피어 피싱 (첨부 파일)** 캠페인 에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-210">**Attachment Name**: This setting is only available in **Spear Phishing (Attachment)** campaigns.</span></span> <span data-ttu-id="1c9a6-211">.Docx 또는 .pdf 첨부 파일의 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-211">Enter a filename for the .docx or .pdf attachment.</span></span>

   - <span data-ttu-id="1c9a6-212">**사용자 지정 랜딩 페이지 URL**: 사용자가 피싱 링크를 클릭 하 고 해당 자격 증명을 입력할 수 있는 선택적 랜딩 페이지를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-212">**Custom Landing Page URL**: Enter an optional landing page where users are taken if they click the phishing link and enter their credentials.</span></span> <span data-ttu-id="1c9a6-213">이 링크는 기본 랜딩 페이지를 대체 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-213">This link replaces the default landing page.</span></span> <span data-ttu-id="1c9a6-214">예를 들어 내부 인식 교육이 있는 경우 여기에서 해당 URL을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-214">For example, if you have internal awareness training, you can specify that URL here.</span></span>

   - <span data-ttu-id="1c9a6-215">**제목**: 전자 메일 메시지의 **제목** 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-215">**Subject**: The **Subject** field of the email message.</span></span>

   <span data-ttu-id="1c9a6-216">작업을 마친 후 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-216">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="1c9a6-217">**전자 메일 작성** 단계에서 전자 메일 메시지의 메시지 본문을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-217">In the **Compose email** step, create the message body of the email message.</span></span> <span data-ttu-id="1c9a6-218">**시작** 단계에서 템플릿을 선택한 경우 메시지 본문이 이미 구성 되어 있지만 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-218">If you selected a template in the **Start** step, the message body is already configured, but you can customize it.</span></span> <span data-ttu-id="1c9a6-219">**전자 메일** 탭 (리치 html 편집기) 또는 **원본** 탭 (원시 HTML 코드)을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-219">You can use the **Email** tab (a rich HTML editor) or the **Source** tab (raw HTML code).</span></span>

   <span data-ttu-id="1c9a6-220">HTML 서식 지정은 필요한 경우에는 단순 하거나 복잡할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-220">The HTML formatting can be as simple or complex as you need it to be.</span></span> <span data-ttu-id="1c9a6-221">이미지와 텍스트를 삽입 하 여 받는 사람의 전자 메일 클라이언트에서 메시지의 believability을 향상 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-221">You can insert images and text to enhance the believability of the message in the recipient's email client.</span></span>

   - <span data-ttu-id="1c9a6-222">`${username}` 받는 사람의 이름을 삽입 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-222">`${username}` inserts the recipient's name.</span></span>

   - <span data-ttu-id="1c9a6-223">`${loginserverurl}`**피싱 로그인 서버 URL** 값을 삽입 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-223">`${loginserverurl}` inserts the **Phishing Login Server URL** value.</span></span>

   <span data-ttu-id="1c9a6-224">**스피어 피싱 (첨부 파일)** 캠페인의 경우 메시지 본문에서 링크를 제거 해야 합니다 (그렇지 않으면 메시지에 링크 **와** 첨부 파일이 모두 포함 되며 첨부 파일 캠페인에서는 링크 클릭이 추적 되지 않음).</span><span class="sxs-lookup"><span data-stu-id="1c9a6-224">For **Spear Phishing (Attachment)** campaigns, you should remove the link from the body of the message (otherwise, the message will contain both a link **and** an attachment, and link clicks aren't tracked in an attachment campaign).</span></span>

   ![전자 메일 본문 작성](../../media/9bd65af4-1f9d-45c1-8c06-796d7ccfd425.jpg)

   <span data-ttu-id="1c9a6-226">작업을 마친 후 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-226">When you're finished, click **Next**.</span></span>

7. <span data-ttu-id="1c9a6-227">**확인** 단계에서 **마침을** 클릭 하 여 캠페인을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-227">In the **Confirm** step, click **Finish** to launch the campaign.</span></span> <span data-ttu-id="1c9a6-228">피싱 메시지는 대상이 지정 된 받는 사람에 게 배달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-228">The phishing message is delivered to the targeted recipients.</span></span>

## <a name="password-attack-campaigns"></a><span data-ttu-id="1c9a6-229">암호 공격 캠페인</span><span class="sxs-lookup"><span data-stu-id="1c9a6-229">Password attack campaigns</span></span>

<span data-ttu-id="1c9a6-230">*암호 공격은* 대개 공격자가 하나 이상의 유효한 사용자 계정을 식별 한 후 조직의 사용자 계정에 대 한 암호를 추측 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-230">A *password attack* tries to guess passwords for user accounts in an organization, typically after the attacker has identified one or more valid user accounts.</span></span>

<span data-ttu-id="1c9a6-231">Attack 시뮬레이터에서는 사용자 암호의 복잡도를 테스트 하기 위해 다음과 같은 두 가지 유형의 암호 공격 캠페인을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-231">In Attack Simulator, two different types of password attack campaigns are available for you to test the complexity of your users' passwords:</span></span>

- <span data-ttu-id="1c9a6-232">**무작위 암호 (사전 공격)**: 무작위 또는 *사전* 공격에서는 사용자 계정 중 하나에 대 한 암호 (대부분의 암호는 여러 개)를 사용할 수 있는 *강력한* 사전 파일을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-232">**Brute force password (dictionary attack)**: A *brute force* or *dictionary* attack uses a large dictionary file of passwords on a user account with the hope that one of them will work (many passwords against one account).</span></span> <span data-ttu-id="1c9a6-233">잘못 된 암호 잠금 해제로 인해 무작위 암호 공격을 방지 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-233">Incorrect password lock-outs help deter brute force password attacks.</span></span>

  <span data-ttu-id="1c9a6-234">사전 공격의 경우에는 하나 이상의 암호를 지정 하 여 (수동으로 입력 하거나 업로드 한 파일에) 시도할 수 있으며, 하나 또는 여러 명의 사용자를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-234">For the dictionary attack, you can specify one or many passwords to try (manually entered or in an uploaded file), and you can specify one or many users.</span></span>

- <span data-ttu-id="1c9a6-235">**암호 분무 공격**: *암호 분무* 공격에서는 사용자 계정 목록 (여러 계정에 대해 암호 하나씩)에 대해 신중 하 게 동일한 암호를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-235">**Password spray attack**: A *password spray* attack uses the same carefully considered password against a list of user accounts (one password against many accounts).</span></span> <span data-ttu-id="1c9a6-236">암호 분무 공격은 무작위 암호 공격 보다 검색 하기가 더 어렵게 됩니다 (공격자가 사용자의 잘못 된 암호 잠금을 통과 하는 위험 없이 수십 또는 수백 개의 계정에서 암호를 한 번에 입력 해야 하는 경우에는 성공 확률이 증가 함).</span><span class="sxs-lookup"><span data-stu-id="1c9a6-236">Password spray attacks are harder to detect than brute force password attacks (the probability of success increases when an attacker tries one password across dozens or hundreds of accounts without the risk of tripping the user's incorrect password lock-out).</span></span>

  <span data-ttu-id="1c9a6-237">암호 분무 공격의 경우 시도할 암호를 하나만 지정할 수 있으며, 한 명 또는 여러 명의 사용자를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-237">For the password spray attack, you can only specify one password to try, and you can specify one or many users.</span></span>

> [!NOTE]
> <span data-ttu-id="1c9a6-238">Attack 시뮬레이터의 암호 공격은 사용자 이름 및 암호 기본 인증 요청을 끝점에 전달 하므로 다른 인증 방법 (AD FS, 암호 해시 동기화, 통과, 공동 페더레이션 등) 에서도 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-238">The password attacks in Attack Simulator pass username and password Basic auth requests to an endpoint, so they also work with other authentication methods (AD FS, password hash sync, pass-through, PingFederate, etc.).</span></span> <span data-ttu-id="1c9a6-239">MFA를 사용 하도록 설정 된 사용자의 경우 암호 공격이 실제 암호를 시도 하더라도 항상 실패로 등록 됩니다 (즉, MFA 사용자는 해당 캠페인의 **성공한 시도** 횟수에 표시 되지 않음).</span><span class="sxs-lookup"><span data-stu-id="1c9a6-239">For users that have MFA enabled, even if the password attack tries their actual password, the attempt will always register as a failure (in other words, MFA users will never appear in the **Successful attempts** count of the campaign).</span></span> <span data-ttu-id="1c9a6-240">이는 예상 되는 결과입니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-240">This is the expected result.</span></span> <span data-ttu-id="1c9a6-241">MFA는 암호 공격 으로부터 보호 하는 기본 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-241">MFA is a primary method to help protect against password attacks.</span></span>

### <a name="create-and-launch-a-password-attack-campaign"></a><span data-ttu-id="1c9a6-242">암호 공격 캠페인 만들기 및 시작</span><span class="sxs-lookup"><span data-stu-id="1c9a6-242">Create and launch a password attack campaign</span></span>

1. <span data-ttu-id="1c9a6-243">보안 & 준수 센터에서 **위협 관리** \> **공격 시뮬레이터**로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-243">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="1c9a6-244">**공격 시뮬레이션** 페이지에서 만들려는 캠페인 유형에 따라 다음 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-244">On the **Simulate attacks** page, make one of the following selections based on the type of campaign you want to create:</span></span>

   - <span data-ttu-id="1c9a6-245">**무작위 암호 (사전 공격)** 섹션에서 **공격 시작** 을 클릭 하거나 **공격 정보** \> **시작 공격**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-245">In the **Brute Force Password (Dictionary Attack)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

   - <span data-ttu-id="1c9a6-246">**암호 분무 공격** 섹션에서 **공격 시작** 을 클릭 하거나 **공격 정보** \> **시작 공격**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-246">in the **Password spray attack** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

3. <span data-ttu-id="1c9a6-247">**암호 공격 구성** 마법사가 새 플라이 아웃으로 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-247">The **Configure Password Attack** wizard starts in a new flyout.</span></span> <span data-ttu-id="1c9a6-248">**시작** 단계에서 캠페인의 고유한 표시 이름을 입력 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-248">In the **Start** step, enter a unique display name for the campaign, and then click **Next**.</span></span>

4. <span data-ttu-id="1c9a6-249">**대상 사용자** 단계에서 다음 단계 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-249">In the **Target users** step, do one of the following steps:</span></span>

   - <span data-ttu-id="1c9a6-250">**주소록** 을 클릭 하 여 캠페인에 대 한 받는 사람 (사용자 또는 그룹)을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-250">Click **Address Book** to select the recipients (users or groups) for the campaign.</span></span> <span data-ttu-id="1c9a6-251">각각의 대상 지정 받는 사람에 게 Exchange Online 사서함이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-251">Each targeted recipient must have an Exchange Online mailbox.</span></span> <span data-ttu-id="1c9a6-252">검색 조건을 입력 하지 않고 **필터** 및 **적용** 을 클릭 하면 모든 받는 사람이 반환 되 고 캠페인에 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-252">If you click **Filter** and **Apply** without entering a search criteria, all recipients are returned and added to the campaign.</span></span>

   - <span data-ttu-id="1c9a6-253">**파일** 가져오기를 클릭 하 여 CSV (쉼표로 구분 된 값) 또는 전자 메일 주소에 대 한 행 구분 파일 **을 가져옵니다.**</span><span class="sxs-lookup"><span data-stu-id="1c9a6-253">Click **Import** then **File Import** to import a comma-separated value (CSV) or line-separated file of email addresses.</span></span> <span data-ttu-id="1c9a6-254">각 줄에는 받는 사람의 전자 메일 주소가 포함 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-254">Each line must contain the recipient's email address.</span></span>

   <span data-ttu-id="1c9a6-255">작업을 마친 후 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-255">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="1c9a6-256">**공격 설정 선택** 단계에서 캠페인 유형에 따라 수행할 작업을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-256">In the **Choose attack settings** step, choose what to do based on the campaign type:</span></span>

   - <span data-ttu-id="1c9a6-257">**무작위 암호 (사전 공격)**: 다음 단계 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-257">**Brute Force Password (Dictionary Attack)**: Do either of the following steps:</span></span>

     - <span data-ttu-id="1c9a6-258">**암호를 수동으로 입력**합니다. **암호를 추가 하려면 Enter 키를 누릅니다** 상자에 암호를 입력 한 다음 enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-258">**Enter passwords manually**: In the **Press enter to add a password** box, type a password and then press ENTER.</span></span> <span data-ttu-id="1c9a6-259">필요한 만큼 이 단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-259">Repeat this step as many times as necessary.</span></span>

     - <span data-ttu-id="1c9a6-260">**사전 파일에서 암호 업로드**: **업로드** 를 클릭 하 여 각 줄에 하나의 암호를 포함 하는 기존 텍스트 파일을 가져오고 마지막 줄에는 빈 행을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-260">**Upload passwords from a dictionary file**: Click **Upload** to import an existing text file that contains one password on each line and a blank last line.</span></span> <span data-ttu-id="1c9a6-261">텍스트 파일의 크기는 10mb이 하 여야 하며, 3만 개 이하의 암호를 포함할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-261">The text file must be 10 MB or less in size, and can't contain more than 30000 passwords.</span></span>

   - <span data-ttu-id="1c9a6-262">**암호 분무 공격**: **공격 상자에 사용할 암호** 에 암호를 하나 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-262">**Password spray attack**: In **The password(s) to use in the attack** box, enter one password.</span></span>

   <span data-ttu-id="1c9a6-263">작업을 마친 후 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-263">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="1c9a6-264">**확인** 단계에서 **마침을** 클릭 하 여 캠페인을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-264">In the **Confirm** step, click **Finish** to launch the campaign.</span></span> <span data-ttu-id="1c9a6-265">지정한 암호가 지정한 사용자에 게 시도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-265">The passwords you specified are tried on users you specified.</span></span>

## <a name="view-campaign-results"></a><span data-ttu-id="1c9a6-266">캠페인 결과 보기</span><span class="sxs-lookup"><span data-stu-id="1c9a6-266">View campaign results</span></span>

<span data-ttu-id="1c9a6-267">캠페인을 시작한 후에는 기본 **시뮬레이트 공격** 페이지에서 진행률 및 결과를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-267">After you launch a campaign, you can check the progress and results on the main **Simulate attacks** page.</span></span>

<span data-ttu-id="1c9a6-268">활성 캠페인은 상태 표시줄, 완료 된 백분율 값 및 "(전체 사용자)" 수 "개수를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-268">Active campaigns will show a status bar, a completed percentage value and "(completed users) of (total users)" count.</span></span> <span data-ttu-id="1c9a6-269">**새로 고침** 단추를 클릭 하면 활성 캠페인의 진행률이 업데이트 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-269">Clicking the **Refresh** button will update the progress of any active campaigns.</span></span> <span data-ttu-id="1c9a6-270">또한 **종료** 를 클릭 하 여 활성 캠페인을 중지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-270">You can also click **Terminate** to stop an active campaign.</span></span>

<span data-ttu-id="1c9a6-271">캠페인이 완료 되 면 상태가 " **공격 완료 됨**"으로 변경 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-271">When the campaign is finished, the status changes to **Attack completed**.</span></span> <span data-ttu-id="1c9a6-272">다음 작업 중 하나를 수행 하 여 캠페인의 결과를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-272">You can view the results of the campaign by doing either of the following actions:</span></span>

- <span data-ttu-id="1c9a6-273">주 **시뮬레이트 공격** 페이지에서 캠페인 이름 아래에 있는 **보고서 보기** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-273">On the main **Simulate attacks** page, click **View Report** under the name of the campaign.</span></span>

- <span data-ttu-id="1c9a6-274">주 **시뮬레이트 공격** 페이지에서 공격 유형에 대 한 섹션에서 **공격 세부 정보** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-274">On the main **Simulate attacks** page, click **Attack Details** in the section for the type of attack.</span></span> <span data-ttu-id="1c9a6-275">**공격 정보** 페이지가 열리면 **공격 기록** 섹션에서 캠페인을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-275">On the **Attack details** page that opens, select the campaign in the **Attack History** section.</span></span>

<span data-ttu-id="1c9a6-276">이전 작업 중 하나를 수행 하면 **Attack details**라는 페이지가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-276">Either of the previous actions will take you to a page named **Attack details**.</span></span> <span data-ttu-id="1c9a6-277">각 캠페인 유형에 대해이 페이지에서 제공 되는 정보는 다음 섹션에 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-277">The information that's available on this page for each type of campaign is described in the following sections.</span></span>

### <a name="spear-phishing-credentials-harvest-campaign-results"></a><span data-ttu-id="1c9a6-278">스피어 피싱 (자격 증명 수집) 캠페인 결과</span><span class="sxs-lookup"><span data-stu-id="1c9a6-278">Spear Phishing (Credentials Harvest) campaign results</span></span>

<span data-ttu-id="1c9a6-279">각 캠페인의 **공격 세부 정보** 페이지에서는 다음 정보를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-279">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="1c9a6-280">캠페인의 기간 (시작 날짜/시간 및 종료 날짜/시간)입니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-280">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="1c9a6-281">**총 대상 사용자**</span><span class="sxs-lookup"><span data-stu-id="1c9a6-281">**Total users targeted**</span></span>

- <span data-ttu-id="1c9a6-282">**성공**: 링크를 클릭 **하 고** 자격 증명 (*사용자 이름 및* 암호 값)을 입력 한 사용자 수입니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-282">**Successful attempts**: The number of users who clicked the link **and** entered their credentials (*any* username and password value).</span></span>

- <span data-ttu-id="1c9a6-283">**전체 성공률**: 총 사용자 수에 대해 **성공한 시도**를 통해 계산 되는 백분율  /  **Total users targeted**입니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-283">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="1c9a6-284">**고속 클릭**: 처음 사용자가 캠페인을 시작한 후 링크를 클릭 하는 데 소요 되는 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-284">**Fastest Click**: How long it took the first user to click the link after you launched the campaign.</span></span>

- <span data-ttu-id="1c9a6-285">**Average 클릭**: 모든 사용자가 링크를 클릭 하는 데 걸린 시간 합계를 링크를 클릭 한 사용자 수로 나눕니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-285">**Average Click**: The sum of how long it took everyone to click the link divided by the number of users who clicked the link.</span></span>

- <span data-ttu-id="1c9a6-286">**성공률**: (링크를 클릭 한 사용자 수)/ **총 대상 사용자**에 게 계산 되는 백분율을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-286">**Click Success Rate**: A percentage that's calculated by (number of users who clicked the link) / **Total users targeted**.</span></span>

- <span data-ttu-id="1c9a6-287">**가장 빠른 자격 증명**: 캠페인을 시작한 후 첫 번째 사용자가 자격 증명을 입력 하는 데 소요 되는 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-287">**Fastest Credentials**: How long it took the first user to enter their credentials after you launched the campaign.</span></span>

- <span data-ttu-id="1c9a6-288">**평균 자격 증명**: 모든 사용자가 자격 증명을 입력 하는 데 걸린 시간 합계입니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-288">**Average Credentials**: The sum of how long it took everyone to enter their credentials divided by the number of users who entered their credentials.</span></span>

- <span data-ttu-id="1c9a6-289">**자격 증명 성공률**: (자격 증명을 입력 한 사용자 수)/ **총 대상 사용자**를 기준으로 계산 되는 백분율입니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-289">**Credential Success Rate**: A percentage that's calculated by (number of users who entered their credentials) / **Total users targeted**.</span></span>

- <span data-ttu-id="1c9a6-290">**클릭 한 링크** 와 하루 당 제공 되는 **자격 증명** 수를 보여 주는 막대 그래프입니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-290">A bar graph that shows the **Link clicked** and **Credential supplied** numbers per day.</span></span>

- <span data-ttu-id="1c9a6-291">**클릭 한 링크**, **제공 된 자격 증명**및 캠페인에 대 한 **백분율을** 보여주는 원 그래프입니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-291">A circle graph that shows the **Link clicked**, **Credential supplied**, and **None** percentages for the campaign.</span></span>

- <span data-ttu-id="1c9a6-292">**손상 된 사용자** 섹션에는 링크를 클릭 한 사용자에 대 한 자세한 정보가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-292">The **Compromised Users** section lists the details of the users who clicked the link:</span></span>

  - <span data-ttu-id="1c9a6-293">사용자의 전자 메일 주소</span><span class="sxs-lookup"><span data-stu-id="1c9a6-293">The user's email address</span></span>

  - <span data-ttu-id="1c9a6-294">링크를 클릭 한 날짜/시간입니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-294">The date/time when they clicked the link.</span></span>

  - <span data-ttu-id="1c9a6-295">클라이언트 IP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-295">The client IP address.</span></span>

  - <span data-ttu-id="1c9a6-296">사용자 버전의 Windows 및 웹 브라우저에 대 한 세부 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-296">Details about the user's version of Windows and web browser.</span></span>

  <span data-ttu-id="1c9a6-297">**내보내기를** 클릭 하 여 결과를 CSV 파일로 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-297">You can click **Export** to export the results to a CSV file.</span></span>

### <a name="spear-phishing-attachment-campaign-results"></a><span data-ttu-id="1c9a6-298">스피어 피싱 (첨부 파일) 캠페인 결과</span><span class="sxs-lookup"><span data-stu-id="1c9a6-298">Spear Phishing (Attachment) campaign results</span></span>

<span data-ttu-id="1c9a6-299">각 캠페인의 **공격 세부 정보** 페이지에서는 다음 정보를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-299">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="1c9a6-300">캠페인의 기간 (시작 날짜/시간 및 종료 날짜/시간)입니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-300">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="1c9a6-301">**총 대상 사용자**</span><span class="sxs-lookup"><span data-stu-id="1c9a6-301">**Total users targeted**</span></span>

- <span data-ttu-id="1c9a6-302">**성공한 시도**: 첨부 파일을 열거나 다운로드 한 후 연 사용자 수 (미리 보기에서 계산 되지 않음)입니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-302">**Successful attempts**: The number of users who opened or downloaded and opened the attachment (preview doesn't count).</span></span>

- <span data-ttu-id="1c9a6-303">**전체 성공률**: 총 사용자 수에 대해 **성공한 시도**를 통해 계산 되는 백분율  /  **Total users targeted**입니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-303">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="1c9a6-304">**가장 빠른 첨부 파일 열기 시간**: 캠페인을 시작한 후 첫 번째 사용자가 첨부 파일을 여는 데 소요 되는 기간입니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-304">**Fastest attachment open time**: How long it took the first user to open the attachment after you launched the campaign.</span></span>

- <span data-ttu-id="1c9a6-305">**평균 첨부 파일 열기 시간**: 모든 사용자가 첨부 파일을 여는 데 걸린 시간 합계입니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-305">**Average attachment open time**: The sum of how long it took everyone to open the attachment divided by the number of users who opened the attachment.</span></span>

- <span data-ttu-id="1c9a6-306">**첨부 파일 열기 성공률**: (첨부 파일을 연 사용자 수)/ **총 대상 사용자**를 기준으로 계산 되는 백분율입니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-306">**Attachment open success rate**: A percentage that's calculated by (number of users who opened the attachment) / **Total users targeted**.</span></span>

### <a name="brute-force-password-dictionary-attack-campaign-results"></a><span data-ttu-id="1c9a6-307">무작위 암호 (사전 공격) 캠페인 결과</span><span class="sxs-lookup"><span data-stu-id="1c9a6-307">Brute Force Password (Dictionary Attack) campaign results</span></span>

<span data-ttu-id="1c9a6-308">각 캠페인의 **공격 세부 정보** 페이지에서는 다음 정보를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-308">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="1c9a6-309">캠페인의 기간 (시작 날짜/시간 및 종료 날짜/시간)입니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-309">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="1c9a6-310">**총 대상 사용자**</span><span class="sxs-lookup"><span data-stu-id="1c9a6-310">**Total users targeted**</span></span>

- <span data-ttu-id="1c9a6-311">**성공한 시도**: 지정 된 암호 중 하나를 사용 하는 것으로 확인 된 사용자 수입니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-311">**Successful attempts**: The number of users who were found to be using one of the specified passwords.</span></span>

- <span data-ttu-id="1c9a6-312">**전체 성공률**: 총 사용자 수에 대해 **성공한 시도**를 통해 계산 되는 백분율  /  **Total users targeted**입니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-312">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="1c9a6-313">**손상 된 사용자** 섹션에는 영향을 받는 사용자의 전자 메일 주소가 나열 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-313">The **Compromised Users** section lists the email addresses of the affected users.</span></span> <span data-ttu-id="1c9a6-314">**내보내기를** 클릭 하 여 결과를 CSV 파일로 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-314">You can click **Export** to export the results to a CSV file.</span></span>

### <a name="password-spray-attack-campaign-results"></a><span data-ttu-id="1c9a6-315">암호 분무 공격 캠페인 결과</span><span class="sxs-lookup"><span data-stu-id="1c9a6-315">Password spray attack campaign results</span></span>

<span data-ttu-id="1c9a6-316">각 캠페인의 **공격 세부 정보** 페이지에서는 다음 정보를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-316">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="1c9a6-317">캠페인의 기간 (시작 날짜/시간 및 종료 날짜/시간)입니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-317">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="1c9a6-318">**총 대상 사용자**</span><span class="sxs-lookup"><span data-stu-id="1c9a6-318">**Total users targeted**</span></span>

- <span data-ttu-id="1c9a6-319">**성공**: 지정 된 암호를 사용 하 여 검색 된 사용자 수입니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-319">**Successful attempts**: The number of users who were found to be using the specified password.</span></span>

- <span data-ttu-id="1c9a6-320">**전체 성공률**: 총 사용자 수에 대해 **성공한 시도**를 통해 계산 되는 백분율  /  **Total users targeted**입니다.</span><span class="sxs-lookup"><span data-stu-id="1c9a6-320">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>
